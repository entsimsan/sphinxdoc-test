.. _projects:


****************
Entando Projects
****************

Entando Core
-------------
Entando-core is the heart of the Entando Platform. It provides the basic structure, tools, and functionality to build an instance of the Entando application.

Entando-core is composed of the three following main core components:

* engine, includes core features and internal services of the platform
* admin-console, includes tools to manage administrative core features and WCMS functionality
* portal-ui, provides tools to create interactive web apps UI/UX


Entando Components
-------------------
Entando-components is one of the mainstays of the Entando Platform. It provides all functionality of specific software elements, called Entando components or Entando extensions, useful to extend the standard Entando platform features and/or use them to improve custom applications.

The Entando components are:

* Bundles extend functionality of portal-ui component and/or views’ functionality of the other Entando components.

* Plugins extend functionality of engine, and admin-console components.

The Entando components project, based on Apache Maven, is organized in two modules including all Entando extensions ready to use just now.

The following is a list of plugins released with entando-core version 4.3.1:
        * Action Logger
        * Avatar
        * Blog
        * CAS Client
        * Calendar
        * Cms Tag Cloud
        * Collaboration
        * Content Feedback
        * Content Scheduler
        * Content Versioning
        * Content Workflow
        * Email Sender
        * Faceted Navigation
        * Georeferenced Content
        * LDAP Connector
        * Newsletter
        * RSS
        * RSS Aggregator
        * Survey
        * Token API
        * User Registration
        * Web Dynamic Form
        * Widget Utils

The following is a list of main bundles released with entando-core version 4.3.1:
        * Content type - Generic Content
        * Content type - News
        * Content type - Download card
        * Content type - Generic government Resolution
        * Content type - Generic government Announcement
        * Content type - Blog Post Content
        * Page model - Twitter Bootstrap Hero unit (full width layout)
        * Page model - Classic 2 columns layout
        * Plugin default view - Avatar
        * Plugin default view - Blog
        * Plugin default view - Calendar
        * Plugin default view - Cms Tag Cloud
        * Plugin default view - Faceted Navigation
        * Plugin default view - Newsletter
        * Plugin default view - RSS
        * Plugin default view - Survey-Questionnaire
        * Plugin default view - Tag Cloud
        * Plugin default view - Token API
        * Plugin default view - User Registration
        * Plugin default view - Web dynamic form
        * Widget type - Choose a Language
        * Widget type - Classic breadcrumbs ("You are here") bar
        * Widget type - Classic vertical navigation menu
        * Widget type - Horizontal navigation menu
        * Widget type - Login form
        * Widget type - Search form
        * Widget type - Social media shortcuts buttons



Entando Archetypes
-------------------

Entando-archetypes is a project that provides basic templates/models that allows you to create easily and quickly your standard Entando web application, new Entando components such as Plugins, and Bundles (see entando-components project).

The Entando archetypes project includes the following modules:

    * bundle-content-type is the Maven archetype to build a bundle for a content type
    * bundle-theme is the Maven archetype to build a bundle for a theme
    * bundle-widget is the Maven archetype to build a bundle for a widget
    * plugin is the Maven archetype to build a new plugin component
    * entando-sample is the Maven archetype to build a web application based on Entando core components developed by Bootstrap
    * webapp-generic is the Maven archetype to build a generic web application based on Entando core components
    * webapp-app-bpm is the Maven archetype to build a generic web application based on Inspinia toolkit.




