**********************************
Fragments
**********************************

Fragments are pieces of Freemarker templates used to render widgets, i.e. the GUI of a widget is rendered via a Fragment.
For every widget there is a corresponding Fragment which at the end is responsible of it GUI.
Fragments can be managed from the back-office.

Here an example of the gui code for a widget returning the value of a parameter:

.. code:: bash

	<#assign wp=JspTaglibs["/aps-core"]>
        Stored value for myParamName is: <@wp.currentWidget param="config" configParam="myParamName" />
