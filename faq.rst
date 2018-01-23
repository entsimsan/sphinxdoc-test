*************
Entando FAQs
*************

In this section are available the answers to Entando Frequently Asked Questions (FAQs)

Q: Is Entando free?

A: Yes. It is free to use and modify under the terms of the LGPL v2.1 License for the Core and under the MIT License for the components

Q: Is Entando supported?

A: Yes. We support Entando in open source terms. You can report bugs and expect the same order of responsiveness that you get from any open source project.

Q: Where is the code?

A: The code is here

Q: Where can I get more help? A: Entando offers different support level and feature development. Visit us at our website for more information.

Q: I have a problem with the installation. Where do I go?

A: There is a Getting Started page in this wiki. If your problem is not solved, you may contact us via our website.

Q: How can I change the pages of an Entando web application?

A: Simply enter in the Admin Console of your application. You will be able to modify all the pages templates and contents.

Q: Does Entando allow to use external authentication systems?

A: Yes. In addition to internal users management system, there are several plugins to connect with external Users Management System such as LDAP, Active Directory, Kerberos, CAS, ...

Q: Does Entando allow the management of multilanguage content?

A: Yes. The platform allows the management of multilanguage content, with the possibility of adding or removing languages, and provides the opportunity of selecting the language in which you want to translate the contents.

Q: Does an internal search engine exist in Entando?

A: Yes. Entando provides indexing and searching features. The search engine integrated in the platform is Lucene. In some projects also third-party owners search engines have been integrated.

Q: Is there content versioning in Entando?

A: Yes. A specific plugin allows content versioning.

Q: How to stay tuned with the latest version?

A: Follow those steps

* create a generic folder and go to the generic folder just created may I suggest entandoGitHub
* Download from Github all required package in the following order:
* in a terminal type git clone https://github.com/entando/entando-core
* in a terminal type git clone https://github.com/entando/entando-components
* in a terminal type git clone https://github.com/entando/entando-archetypes this will create three new folders: entando-core record, entando- components and entando-archetypes for each package be sure to use the branch Master, in each folder use git checkout master
* check update in entando-core
* go to the folder entando-core
* git pull
* mvn clean install –DskipTests (this will update your local Maven Repository)
* go to the generic folder
* check update in entando-components
* go to the folder entando-components
* git pull
* mvn clean install –DskipTests (this will update your local Maven Repository)
* go to the generic folder
* check update in entando-archetype
* go to the folder entando-archetype
* git pull
* mvn clean install –DskipTests (this will update your local Maven Repository)
* go to the generic folder

Q: How can I install ImageMagick to create, edit, compose, or convert bitmap images?

A: To install ImageMagick on your OS, you have to:

    For Linux and Mac OSX:

    Install ImageMagick using your package manager

    Open the file ./myprojectexample/src/main/config/systemParams.properties (After the first starting project and extract the archive)

    Locate the line imagemagick.enabled=false and set it to "true"

    For Linux and Windows:

        Install ImageMagick

        Open the file ./myprojectexample/src/main/config/systemParams.properties (After the first starting project and extract the archive)

        Locate the line imagemagick.enabled=false set it to "true"

        Locate the line imagemagick.windows=false set it to "true"

        Locate the line imagemagick.path=null and specify the installation path of ImageMagick


