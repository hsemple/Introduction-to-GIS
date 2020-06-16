---
permalink: /mapwinViewer2/
title: "Extending the MapWinGIS Viewer"
sidebar:
  nav: "docs"
---



In this section, we will improve the design of the Map Viewer application by including more functionalities. These features are simple to include, but they will significantly improve the look and feel of the application.  We will include the following features:

* a menu bar with several menu items: 
* buttons for selecting and deselecting features 
*	menu item for adding and removing shapefile labels 
*	Exporting Map Layer as a jpg.


### Adding a Menu Bar and Menu items and Sub-Items

1. Top-level menus (the type of menus that run across the top of forms) are created using the Menu Strip control.  Add the MenuStrip to the main form by going to the Toolbar section and looking for the MenuStrip Control.  Drag the Menu Strip Control to the Form.  

2. After dragging the Menu Strip control on to the form, you will notice that it is added to the panel beneath the form, and that a Type Here field appears at the top of the form, as shown below. 

3.  Use the Properties panel to change the name of the Menu Strip object to mainMenu. Click in the Type Here field at the top of the form and enter &File. This has the effect of creating a menu item object labeled "File". The ampersand (&) is added to instruct Visual Basic to use the 'F' at the beginning of the file as the accelerator key for this menu item. As such, pressing Alt+F when the application is running will be equivalent to clicking on the menu item with the mouse pointer. The location of the ampersand dictates the accelerator key. For example, H&elp will declare 'e' as the accelerator for this particular menu item. Windows indicates the accelerator for a menu item by underlining the letter, as you will see by the underlined 'F' on your File menu item.
Once the File menu item has been added, Visual Studio will create both a drop-down menu and a field to add another menu item.

4.  Click on the Type Here field under File and type &Open File.... When you enter this text, Visual Studio will add another Type Here field beneath the "Open File" entry. Click in this field and enter &Export Layer.... Once again, Visual Studio provides the opportunity to add another item. This time, however, we are going additional top-level menus.
Click on the menu item next to “File” and add a menu named “&Layer”. Continue with this process and enter menu items for “&Geographic” and “&Help. You should remember to place to place a separator after groups of related menus.


5. Assigning Keyboard Shortcuts to Menu Items
It is conventional to allow menu items to be selected keyboard shortcuts. These are key sequences that typically involve pressing a key whilst holding down the Ctrl, Alt or Shift key.
Keyboard shortcuts are defined by setting the ShortcutKeys property of a menu item object. For example, to configure the Exit menu item to use Ctrl-X, select the menu item and click in the value field of the ShortcutKeys property in the Visual Studio Properties panel. A panel will appear providing the option to select Ctrl, Shift or Alt and also the key to be pressed in conjunction. Use this panel to configure the Ctrl+X key sequence for this menu item.
Now, run the application to see how it looks.  In the illustration below, I added a Washtenaw County Layer and a streets layer. The default OSM layer has also been added. Notice the menu at the topic of the application.  
Now that the basics are in place, you can extend the application by adding more buttons and menu and submenu items. Once these are added, you can research and code the functions accordingly. 


 

### Sources for Code Sample

1. A good starting point to look for code samples is the document below.  The codes are written in Visual Basic and are written in a very straightforward manner.   Although the document is somewhat dated, fortunately most of the class are still used.  

 * [MapWinGIS Reference Manual](http://read.pudn.com/downloads152/ebook/662579/MapWinGIS%20Reference%20Manual.pdf)


2. Since the library is being updated continually, you should also look at the MapwinGIS website to look at the latest documentation (https://www.mapwindow.org/documentation/mapwingis4.9/index.html)


3. Don’t forget to browse Google for code samples.





