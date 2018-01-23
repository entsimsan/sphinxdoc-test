**********************************
Create a new Page Model
**********************************

This activity will complete the creation of a new page model from scratch.

* Select UX Pattern then Page Models from the main menu
* Click the Add button
* Assign a Code and a Name
* Fill the Xml Configuration window with the XML code which defines the page structure
* Fill the Template window with the template Freemarker code which defines the page rendering


**XML Code**

In the XML configuration of a page model are defined all frames which make up the page, each frame has a <frame> tag, with a parameter pos which defines its ordinal position, descr which defines a description and sketch which defines the position and extension of the frame. The coordinate x1 and y1 sets the position of the top left vertex of the frame, while the  coordinate x2 and y2 sets the position of its bottom right vertex. Refer to the code below and to 
:ref:`page-model-figure1` for details.

.. code::

 		<?xml version="1.0" encoding="UTF-8"?>
	<frames>
		<frame pos="0">
			<descr>Navbar1</descr>
		        <sketch x1="0" y1="0" x2="5" y2="0" />
		</frame>
		<frame pos="1">
		 	<descr>Navbar2</descr>
			<sketch x1="6" y1="0" x2="11" y2="0" />
		</frame>
		<frame pos="2">
			<descr>Frame1</descr>
			<sketch x1="0" y1="1" x2="3" y2="4" />
		</frame>
		<frame pos="3">
			<descr>Frame2</descr>
			<sketch x1="8" y1="1" x2="11" y2="4" />
		</frame>
	</frames>


.. _page-model-figure1:
.. figure:: media/template-preview.png
   :scale: 100 %
   :alt: Page Model Template Preview
   :align: center
   
   *Figure 1: Page Model Template Preview*


Insert into the template window the following code:

**Template Code**

.. code:: bash

	<#assign wp=JspTaglibs["/aps-core"]>
	<#assign c=JspTaglibs["http://java.sun.com/jsp/jstl/core"]>
	<!DOCTYPE html>
	<html lang="en">
	<head>
	<title>Bootstrap Example</title>
	<meta charset="utf-8">
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
	<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
	<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
	<style>
	/* Remove the navbar's default margin-bottom and rounded borders */ 
	.navbar {
	margin-bottom: 0;
	border-radius: 0;
	}

	/* Set height of the grid so .sidenav can be 100% (adjust as needed) */
	.row.content {height: 450px}

	/* Set gray background color and 100% height */
	.sidenav {
	padding-top: 20px;
	background-color: #f1f1f1;
	height: 100%;
	}

	/* Set black background color, white text and some padding */
	footer {
	background-color: #555;
	color: white;
	padding: 15px;
	}

	/* On small screens, set height to 'auto' for sidenav and grid */
	@media screen and (max-width: 767px) {
	.sidenav {
	height: auto;
	padding: 15px;
	}
	.row.content {height:auto;} 
	}
	</style>
	</head>
	<body>

	<nav class="navbar navbar-inverse">
	<div class="container-fluid">
	<div class="navbar-header">
	<button type="button" class="navbar-toggle" data-toggle="collapse" data-target="#myNavbar">
	<span class="icon-bar"></span>
	<span class="icon-bar"></span>
	<span class="icon-bar"></span>                        
	</button>

	</div>
	<div class="collapse navbar-collapse" id="myNavbar">
	<ul class="nav navbar-nav navbar-right">
	 **<li><@wp.show frame=0 /></li>**
	  <li><@wp.show frame=1 /></li>
	  </ul>
	</div>
	</div>
	</nav>

	<div class="container-fluid text-center">    
	<div class="row content">
	<div class="col-sm-2 sidenav">
	<p><a href="#">Link</a></p>
	<p><a href="#">Link</a></p>
	<p><a href="#">Link</a></p>
	</div>
	<div class="col-sm-8 text-left"> 
	<@wp.show frame=2 />
	</div>
	<div class="col-sm-2 sidenav">
	<div class="well">
	<@wp.show frame=2 />
	</div>
	<div class="well">
	<@wp.show frame=3 />
	</div>
	</div>
	</div>
	</div>

	<footer class="container-fluid text-center">
	<p>Footer Text</p>
	</footer>

	</body>
	</html>


* Click on Save

You will be redirected to Page Models list view, which now shows the page model just created.

