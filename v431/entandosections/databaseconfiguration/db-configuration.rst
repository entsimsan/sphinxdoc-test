******************************
Database Configuration
******************************

By default Entando is configured to use Apache Derby database.
To use another database the following changes need to be applied:

In the folder src/main/filters edit the appropriate file for your environment and deployment, for example in a developement environment on Unix sistems you need to edit the filter-development-unix.properties file.

Open the file with a text editor, locate the part in the file marked as **Database Configuration: DERBY** and comment out all the section lines, this part should look like the following:

.. code:: bash

	# --------------------- Database Configuration: DERBY ---------------------
	#profile.database.hostname=localhost
	#profile.database.port=1527
	#profile.database.username=agile
	#profile.database.password=agile

	#usually no need to change the following group of 3 properties:
	#profile.database.driverClassName=org.apache.derby.jdbc.EmbeddedDriver
	#profile.database.url.portdb=jdbc:derby:${project.build.directory}/derby/production/${profile.application.name}#Port;create=true
	#profile.database.url.servdb=jdbc:derby:${project.build.directory}/derby/production/${profile.application.name}#Serv;create=true



find the part which refers to you database es. MySQL and uncomment the lines as shown below and set the parameters according to your db configuration

.. code:: bash

	# --------------------- Database Configuration: MySQL ---------------------
	profile.database.hostname=localhost
	profile.database.port=3306
	profile.database.username=agile
	profile.database.password=agile
	
	#usually no need to change the following group of 3 properties:
	profile.database.driverClassName=com.mysql.jdbc.Driver
	profile.database.url.portdb=jdbc:mysql://${profile.database.hostname}:${profile.database.port}/${profile.application.name}Port
	profile.database.url.servdb=jdbc:mysql://${profile.database.hostname}:${profile.database.port}/${profile.application.name}Serv



* Save the file

Open the pom.xml file with a text editor and comment the lines which refer to Derby properties and uncomment the part which refers to MySQL, the file should look like the following:

.. code:: bash


        <test.database.driver>com.mysql.jdbc.Driver</test.database.driver>
        <test.database.hostname>localhost</test.database.hostname>
        <test.database.port>3306</test.database.port>
        <test.database.username>root</test.database.username>
        <test.database.password>agile</test.database.password>
        <test.database.port.url>jdbc:mysql://${test.database.hostname}:${test.database.port}/${project.artifactId}testPort</test.database.port.url>
        <test.database.serv.url>jdbc:mysql://${test.database.hostname}:${test.database.port}/${project.artifactId}testServ</test.database.serv.url>
       
        <!--
        <test.database.driver>org.apache.derby.jdbc.EmbeddedDriver</test.database.driver>
        <test.database.hostname>localhost</test.database.hostname>
        <test.database.port>1527</test.database.port>
        <test.database.username>agile</test.database.username>
        <test.database.password>agile</test.database.password>
        <test.database.port.url>jdbc:derby:${project.build.directory}/test/db/${project.artifactId}testPort;create=true</   test.database.port.url>
        <test.database.serv.url>jdbc:derby:${project.build.directory}/test/db/${project.artifactId}testServ;create=true</test.database.serv.url>
        -->



Then uncomment the dependency part of the file

.. code:: bash

      <dependency>
                   <groupId>mysql</groupId>
                   <artifactId>mysql-connector-java</artifactId>
                    <version>5.1.18</version>
      </dependency>



* Save the file


Create two databases in you dbms, the database names are strings composed by your project name and Port without any space and your project name and Serv without any space as shown below:

.. code:: bash

   create database project-namePort
   create database project-nameServ

issue the command 

.. code:: bash

   mvn clean jetty:run


