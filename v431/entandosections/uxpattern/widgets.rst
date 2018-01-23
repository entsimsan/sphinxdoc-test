*********************************
Widgets
*********************************



Add a new widget
-----------------

New widgets can be added from the backoffice.
To do that access the UX patterns >> Widgets section and push the Add button.

Fill up the form with:

* Code
* Title
* Group
* Custom UI

The Custom UI is a Freemarker piece of code which provides the definition of the widget UI.
Examples of UI configurations can be found clicking on a widget name from the UX Patterns >> Widget section, then selecting Default UI.
Here below an example of code taken from Entando widget *Contents - Publish a Content* which is a CMS widget:

.. code::

 <#assign jacms=JspTaglibs["/jacms-aps-core"]>
 <#assign wp=JspTaglibs["/aps-core"]>
 <@jacms.contentInfo param="authToEdit" var="canEditThis" />
 <@jacms.contentInfo param="contentId" var="myContentId" />
 <#if (canEditThis?? && canEditThis)>
	<div class="bar-content-edit">
		<a href="<@wp.info key="systemParam" paramName="applicationBaseURL" />do/jacms/Content/edit.action?contentId=<@jacms.contentInfo param="contentId" />"    class="btn btn-info">
		<@wp.i18n key="EDIT_THIS_CONTENT" /> <i class="icon-edit icon-white"></i></a>
	</div>
 </#if>
 <@jacms.content publishExtraTitle=true />





The new added widget will be included in the list of User widgets.

A new record will be added to the Entando Port database in the widgetcatalog and guiform tables.



