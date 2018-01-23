.. getting_started:

###############
Getting Started
###############


Start using Entando its easy, here below the guide to start using it.

Environment Setup
==================

To run a web application based on Entando v4.3.2 you need a system that
meets the following hardware and software requirements.


Hardware Configuration
-----------------------

The minimum hardware requirements are

-  4 GB of RAM
-  Dual core CPU ~ 2.2 Ghz
-  ~ 10 Gb of free space on disk (the vast majority of the disk space is
   for Maven dependencies)


Software Configuration
-----------------------

Entando is based on Java, so you can run it on any operating system,
platform or architecture that supports a Java environment.

Here below what you need to have installed on your system to run an Entando web application

**Java Oracle JDK, version >= 1.8** (Entando has been tested with Oracle JDK up to jdk-8u151) [1]_

You can easily check your installed JDK version issuing the command

.. code:: bash

	$ java -version

**Maven, version >= 3.5.0** (Entando has been tested with Maven up to version v3.5.0) [2]_

Issue this command to check your version

.. code:: bash

	$ mvn -version

**Ant**, version up to 1.10.1 (if you need a development ready
environment) [3]_

**NOTE**: Follow “Java Environment Setup” section, if you need any help
on how to get a Java environment correctly set up, depending on your
operating system.

.. rubric:: Run the Entando Application
      :name: run-the-entando-application

With JDK and Maven installed let’s start creating a new web application
based on Entando bootstrap archetype. First create a new directory which
will host the Entando project, move into that folder and issue the
command

.. code:: bash

	$ mvn archetype:generate -Dfilter=entando-archetype-portal-bootstrap

you will be prompt for:

-  **archetype**: a list of archetypes corresponding to the supplied filter;
-  **version**: a list of versions, with the last one set as the default;
-  **groupId**: this is generally unique amongst an organization or a project (e.g. *mycompany*);
-  **artifactId**:  this is generally the name of the project you are going to create (e.g. *mysample*);
-  **version**:  this is the version of the project that is being built;
-  **package**: this is the package name where to place your project’s source code.

For the archetype you will, generally, be presented with several
projects’ choices, you can choose any of those typing the corresponding
number; for the version, a list will be proposed to you, just choose
one, typing its number or accept the default; for the others parameters
you can insert bogus data.

Maven will create a new folder named as your artifactId parameter entry.

To start the project using the *Jetty* server, get into the newly
created folder, where the .\ *pom* file resides and launch it issuing
the command

.. code:: bash

	$ mvn clean jetty:run

Open your browser and point it to
`*http://localhost:8080/* <http://localhost:8080/>`__

**NOTE**: Ignore the error and click on the link shown on that page.

Log into the web application with **username**: *admin* and
**password**: *adminadmin*

Java Environment Setup

The Java Environment Setup may vary depending on your operating system,
here some tips to help you in that task.


Java Setup on OS X 10.9
~~~~~~~~~~~~~~~~~~~~~~~~

-  Download the Java JDK >= 8 from the Oracle website and install the
   provided package
-  Set the JAVA\_HOME environment variable

.. code:: bash
	
	$ echo "export JAVA\_HOME=\\\`/usr/libexec/java\_home\\\`" \| tee -a ~/.bash\_profile

-  Install XCode from the App Store
-  Install Homebrew [4]_ or Macports [5]_ (choose what you prefer)
-  Run brew doctor and fix any warning you get from it
-  Install Maven and Ant with Homebrew:

.. code:: bash

   $ brew install maven
   $ brew install ant



Java Setup on Linux
~~~~~~~~~~~~~~~~~~~~~
      

The procedure is supposed to work with all major Linux distributions,
although your mileage may vary depending on your specific distribution
or settings.

Let’s assume that Oracle Java is not installed, or you have OpenJDK
installed on your system.

-  Download jdk-8u151-linux-x64.tar.gz from Oracle site
-  Download Apache maven apache-maven-3.5.0-bin.tar.gz from Apache site
-  Download Apache Ant apache-ant-1.10.1-bin.tar.gz from Apache site

We are going to install Oracle JDK, Maven and Ant into */opt* directory.

-  copy the jdk tarball into it

.. code:: bash

	$ sudo cp jdk-8u151-linux-x64.tar.gz /opt/

-  move into /opt and issue the following command to untar the packed
   JDK you have already copied there

.. code:: bash

	$ sudo tar xvzf jdk-8u151-linux-x64.tar.gz

-  copy the apache-maven-3.5.0-bin.tar.gz tarball into /opt and untar it
-  copy the apache-ant-1.10.1-bin.tar.gz tarball into /opt and untar it

.. code:: bash

	$ sudo cp apache-maven-3.5.0-bin.tar.gz /opt/
	$ sudo cp apache-ant-1.10.1-bin.tar.gz /opt/
	$ cd /opt/
	$ sudo tar xvfz apache-maven-3.5.0-bin.tar.gz
	$ sudo tar apache-ant-1.10.1-bin.tar.gz

-  Now let's set the PATH for Java, Maven and Ant and some Environment
   variables, globally, we will do that adding a new file in
   /etc/profile.d directory.
-  Create a file named java\_env.sh in /etc/profile.d, with the editor
   of your choice and with the following content

.. code:: bash

	PATH=$PATH:/opt/jdk1.8.0\_151/bin:/opt/jdk1.8.0\_151/db/bin:/opt/jdk1.8.0\_151/jre/bin:/opt/apache-maven-3.5.0/bin:/opt/apache-ant-1.10.1/bin
	J2SDKDIR=/opt/jdk1.8.0\_151
	J2REDIR=/opt/jdk1.8.0\_151/jre
	JAVA\_HOME=/opt/jdk1.8.0\_151
	DERBY\_HOME=/opt/jdk1.8.0\_151/db
	export PATH;
	export J2SDKDIR;
	export J2REDIR;
	export JAVA\_HOME;
	export DERBY\_HOME;

-  Save the file, log out and log in again.

-  Enter the following commands to inform the system about Java's
   location

.. code:: bash

	$ sudo update-alternatives --install "/usr/bin/java" "java" "/opt/jdk1.8.0\_151/bin/java" 0

	$ sudo update-alternatives --install "/usr/bin/javac" "javac" "/opt/jdk1.8.0\_151/bin/javac" 0

	$ sudo update-alternatives --set java /opt/jdk1.8.0\_151/bin/java

	$ sudo update-alternatives --set javac /opt/jdk1.8.0\_151/bin/javac

-  Check that java and javac point to the previous defined paths

.. code:: bash

	$ update-alternatives --list java
	$ update-alternatives --list javac


or

.. code:: bash

	$ update-alternatives –list

for RedHat derived Linux distributions.

-  Than check the JDK with

.. code:: bash

	$ java -version

If you get the installed Oracle java version, you have done it right and
the JDK is correctly installed.

-  Also check whether Maven and Ant are available issuing the commands

.. code:: bash

	$ mvn -version
	$ ant -version

If you get an answer Java is now correctly set up to run an Entando
project or start working with it.

Note that for some environments (Linux distributions, Window Managers),
the environment variables won’t be visible in a graphical terminal, in
this case, adding the same script java\_env.sh to the directory
/etc/X11/Xsession.d/ will do the trick.


Java Setup on Windows
~~~~~~~~~~~~~~~~~~~~~~

-  Install Java JDK >= 1.8

Download and install the .exe installer Download and install the .exe
installer
`j <javascript: void(0)>`__\ `dk-8u151-windows-x64.exe <javascript: void(0)>`__

-  Create the environment variable

 JAVA\_HOME -> C:\\Program Files\\Java\\jdk1.8.0\_151

-  Install Maven

 apache-maven-3.5.0-bin

-  Set the Maven environment variable

 MVN\_HOME -> C:\\Program Files\\apache-maven-3.5.0

-  Install Ant

 apache-ant-1.10.1-bin

-  Set the Ant environment variable

ANT\_HOME -> C:\\Program Files\\apache-ant-1.10.1

.. [1]
   http://www.oracle.com/technetwork/java/javase/downloads/index.html

.. [2]
   http://maven.apache.org/download.cgi

.. [3]
   http://ant.apache.org/bindownload.cgi

.. [4]
    https://brew.sh/

.. [5]
    https://www.macports.org/
