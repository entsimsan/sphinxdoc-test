

.. index::
   single: New Content Model

.. _new-content-model:

***************************************************
Create a new Content Model
***************************************************

The following steps describe how to create a new Content Model

From APPS >> CMS >> Content Models

* Click the Add button

In the new view

* Select a Content type from the dropdown list
* Click Set button on the side
* Assign a code
* Assign a name
* Insert the text which defines the model which is a velocity piece of code.

Here below you can find an example of code which defines the model, it refers to the "Full-Default" content model already present in Entando.


.. code::

 <article>
   <h1>$content.Title.text</h1>
      #if ( $content.Picture.getImagePath("0") != "" )
         <figure class="well well-small text-center">
         <img src="$content.Picture.getImagePath("0")" alt="$content.Picture.text" />
      #if ( $content.Caption.text != "" )
         <figcaption><p class="margin-medium-all">$content.Caption.text</p></figcaption>
      #end
        </figure>
      #end
    #if ( $content.MainBody.text != "" )
    $content.MainBody.text
    #end
 #if ($content.Attaches.size()>0)
  <h2>$i18n.getLabel("CNG_ATTACHMENTS")</h2>
  <ul>
  #foreach ($item in $content.Attaches )
    <li><a href="$item.attachPath">$item.text</a></li>
  #end
  </ul>
 #end
 #if ($content.Links.size()>0)
  <h2>$i18n.getLabel("CNG_LINKS")</h2>
  <ul>
  #foreach ($item in $content.Links)
    <li><a href="$item.destination">$item.text</a></li>
  #end
  </ul>
 #end
 </article>


.. Note:

The inline editing assist functionaly help you in the creation of the Content Model.

Optionally: Define a style sheet by adding its name in the  Style Sheet field.

* Click the Save button.

Pressing the Save button the XML representing the configuration will be saved in the Port Database in the table contentmodels.

The content Model instantiate a content Type, but a content type may have multiple models associated.


