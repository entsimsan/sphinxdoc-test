.. installation:

Environment Setup
=================

In order to develop and build from the last source code of Entando, you
need the following hardware and software configurations.

Hardware Configuration
----------------------

The minimum hardware requirements are:

-  4 GB of RAM

-  Dual core CPU ~ 2.2 Ghz

-  ~ 10Gb of free space on disk (the vast majority of the disk space is
   for Maven dependencies)

Software Configuration
----------------------

Entando is based on Java, so you can run it on any operating system,
platform or architecture that supports a Java environment.

Here below what you need to have installed on your system to run an
Entando web application:

**Java Oracle JDK, version >= 7** (Entando has been tested with Oracle JDK up to jdk-8u151) [1]_

You can easily check your installed JDK version issuing the command:

.. code:: bash

	$ java -version

**Maven, version >= 2.2.1** (Entando has been tested with Maven up to version v3.5.0) [2]_

Issue this command to check your version:


.. code:: bash
	
	$ mvn -version


**Ant**, version up to 1.10.1 (if you need a development ready environment) [3]_

**NOTE**: see the “\ **Getting Started**\ ” document for more
information details about the environment setup

Build From the Source Code
==========================

To develop a web application based on Entando or to build Entando you
need to install the following open source projects:

-  **entando-core**, provides the basic structure, functionality, and
   services to build an instance of an Entando application. The project
   is available in the Github repository at the following link
   https://github.com/entando/entando-core

-  **entando-components**, provides software components that extend the
   basic functionality of the core platform. The project is available in
   the Github repository at the following link
   https://github.com/entando/entando-components

-  **entando-archetypes**, provides original pattern/models from which
   building other Entando applications or projects. The project is
   available in the Github repository at the following link
   https://github.com/entando/entando-archetypes.

Download the projects 
----------------------

To download the last source code version of the projects

-  Open your terminal

-  Create an empty directory for your project


.. code:: bash

	$ mkdir ~/my_new_project

-  Move to a directory of your choice

.. code:: bash

	$ cd ~/my_new_project

-  Clone in the following sequence entando-core, entando-components,
   entando-archetypes projects

.. code:: bash

   -  $ git clone https://github.com/entando/entando-core

   -  $ git clone https://github.com/entando/entando-components

   -  $ git clone https://github.com/entando/entando-archetypes

Install the projects
--------------------

In order to build from the last source code version of the Entando, you
should to

-  Install, in the following sequence, entando-core, entando-components,
   and entando-archetypes projects

.. code:: bash

    $ cd entando-core
    $ mvn clean install –DskipTests

.. code:: bash

    $ cd entando-components
    $ mvn clean install –DskipTests

.. code:: bash

    $ cd entando-archetypes
    $ mvn clean install -DskipTests

-  Create an empty directory and generate a test web application, for
   instance, based on the Entando bootstrap archetype, and type bogus
   data when asked

.. code:: bash

    $ mvn archetype:generate -Dfilter=entando-archetype-portal-bootstrap

Otherwise, if you want to enjoy with a ready application sample, you can
clone (e.g. in the same directory ~/my\_new\_project) and then run an
application included in the entando ux-packages


.. code:: bash

    $ git clone https://github.com/entando/entando-ux-packages
    $ cd entando-ux-packages
    $ cd XXXXXXXXXX

and run the jetty server with:

.. code:: bash

    $ mvn clean jetty:run

Finally:

-  Open your browser at
   `*http://localhost:8080/* <http://localhost:8080/>`__

-  Ignore the 404 error and click on the link you will find on that page

.. note:: The **entando-ux-package** (see
	`*https://github.com/entando/entando-ux-packages* <https://github.com/entando/entando-ux-packages>`__
	) is a project that provides ready-made application samples.

.. [1]
   http://www.oracle.com/technetwork/java/javase/downloads/index.html

.. [2]
   http://maven.apache.org/download.cgi

.. [3]
   http://ant.apache.org/bindownload.cgi
