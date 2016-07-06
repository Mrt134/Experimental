.. globalindex::
   :maxdepth: 4
   
.. _Lumina Desktop Plugins:

Lumina Plugins
**************

Lumina offers a wide variety of plugins which allow the user to 
customize their desktop experience. Plugins are divided between desktop,
menu, and panel plugins.

.. TODO: Create descriptions of every plugin: menu, and panel
   entry.

.. _desktop plugins:

Desktop Plugins
===============

Desktop plugins will add icons or widgets for display on the main screen
of the Lumina Desktop Environment. Right click on the main screen, then 
click :menuselection:`Preferences --> Desktop`. 

.. _Application Launcher:

Application Launcher
--------------------

info.ID = "applauncher"

.. _luminadesktopplugin1:

.. figure:: images/luminadesktopplugin1.png

:numref:`Figure %s: Application Launcher <luminadesktopplugin1>` This 
icon is the result of using the Application Launcher to add a link to 
the "Lumina Desktop Information" application on the desktop. Clicking 
the Application Launcher option allows the user to select a single 
application to add to the desktop area as a "quick launch" icon. 

Desktop button for launching an application.

.. _Audio Player:

Audio Player
------------

info.ID = "audioplayer"

.. _luminadesktopplugin2:

.. figure:: images/luminadesktopplugin2.png

:numref:`Figure %s: Audio Player <luminadesktopplugin2>` The Audio 
Player plugin will play user generated lists of audio files. Pressing 
the wrench icon in the upper left corner will open an options menu, 
while the green plus icon adds files to the playlist.

Play through lists of audio files.

.. _calendar:

Calendar
--------

info.ID = "calendar"

.. _luminadesktopplugin3:

.. figure:: images/luminadesktopplugin3.png

:numref:`Figure %s: Calendar <luminadesktopplugin3>` This is a calendar 
plugin which will display a calendar set to the current month and day. 
The arrows in the upper left and right of the plugin allow the user to 
view previous or upcoming months.

.. _Desktop Icons View:

Desktop Icons View
------------------

info.ID = "desktopview"

.. _luminadesktopplugin4:

.. figure:: images/luminadesktopplugin4.png

:numref:`Figure %s: Desktop Icons <luminadesktopplugin4>` This plugin 
will define an area on the desktop to display icons. If enough icons are
added to the plugin, a scroll bar will appear for the user to scroll 
through all available icons.

.. _Note Pad:

Note Pad
--------

info.ID = "notepad"

.. _luminadesktopplugin5:

.. figure:: images/luminadesktopplugin5.png

:numref:`Figure %s: Note Pad <luminadesktopplugin5>` is a simple plugin 
which adds a simple text creation widget to the desktop. The user needs 
to create a new note before they can type a message. The notes are saved
by default in the "Notes" folder.

.. _RSS Reader:

RSS Reader
----------

info.ID = "rssreader"

.. _luminadesktopplugin6:

.. figure:: images/luminadesktopplugin6.png

:numref:`Figure %s: RSS Reader <luminadesktopplugin6>` plugin displays a
connected RSS feed. The user can add their own custom RSS feeds to the 
plugin, but the default feed displayed is the Lumina Desktop Environment
blog.

.. note:: An active Internet connection is required for the RSS Reader 
          plugin to function properly.

.. _System Monitor:

System Monitor
--------------

info.ID = "systemmonitor"

.. _luminadesktopplugin7:

.. figure:: images/luminadesktopplugin7.png

:numref:`Figure %s: System Monitor Display <luminadesktopplugin7>` Shows 
the "Summary" tab of the System Monitor plugin. CPU Temperature (in 
Celsius), CPU Usage, and Memory Usage are displayed. Currently, there 
are no other options to display in the system monitor aside from these 
statistics and the read/write speed monitor, shown next.

.. _luminadesktopplugin8:

.. figure:: images/luminadesktopplugin8.png

:numref:`Figure %s: System Monitor I/O <luminadesktopplugin8>` Shows 
the "Disk I/O" tab of the System Monitor plugin. Displayed are the 
current read and write speeds of the connected hardware, which in this 
case is a hard drive and cd player. 

.. _menu plugins:

Menu Plugins
============

Menu plugins are the options which appear when the user right-clicks on 
the main desktop screen in Lumina. Two elements the right-click menu 
will always display are the name of the current virtual desktop at the 
top of the menu and the shutdown options on the bottom, as pictured 
in :numref:`Figure %s: Default Menu <luminamenuplugin1>`.

.. _luminamenuplugin1:

.. figure:: images/luminamenuplugin1.png

The user can customize what appears between these two elements of the 
menu however they wish. To customize the right-click menu, click 
:menuselection:`Start Menu --> Preferences --> Desktop --> Interface Configuration --> Context Menu and Plugins`.

.. _Menu Applications:

Applications
------------

info.ID = "applications"

.. _luminamenuplugin2:

.. figure:: images/luminamenuplugin2.png

:numref:`Figure %s: Applications <luminamenuplugin2>`

This plugin adds an application menu which can be navigated to open any 
installed application. The Control Panel and Application Management 
options will always be shown at the top, while the categories of 
applications are shown underneath.

.. _Custom App:

Custom App
----------

info.ID = "app"

.. _luminamenuplugin3:

.. figure:: images/luminamenuplugin3.png

:numref:`Figure %s: Custom Application <luminamenuplugin3>`

Adds a specific quickstart icon for a single application to the 
right-click menu. Pictured is the icon for the "About" application, 
which displays current system information.

.. _File Manager:

File Manager
------------

info.ID = "filemanager"

.. _luminamenuplugin4:

.. figure:: images/luminamenuplugin4.png

:numref:`Figure %s: File Manager <luminamenuplugin4>`

Opens the Insight File Manager (Default) to allow the user to browse the
system files. 

.. _JSON Menu:

JSON Menu
---------

info.ID = "JSON Menu"

The JSON Menu plugin give a more advanced user the flexibility to create
their own entries into the right-click menu. Selecting the JSON Menu 
plugin immediately brings up the 
:numref:`Figure %s: JSON Menu Configuration Window <luminamenuplugin5>`.

.. _luminamenuplugin5:

.. figure:: images/luminamenuplugin5.png

This window has three fields: Visible Name, Executable, and Icon. The 
Visible Name field will define the name of the right-click menu entry. 
Executable is the path to the custom script that is to be run for the 
entry. The Icon field is optional, but is used to assign a specific 
icon to the custom script.

.. _luminamenuplugin6:

.. figure:: images/luminamenuplugin6.png

:numref:`Figure %s: JSON Menu Example <luminamenuplugin6>`

After completing the configuration window, the resultant display shows 
the custom script in action. The Visible Name appears under "Workspace 2",
while the executable script has generated the menu of files and folders.

.. _Separator:

Separator
---------

info.ID = "line"

:numref:`Figure %s: Separator <luminamenuplugin1>`

A Separator is simply a horizontal line which can be used to divide 
entries in the right-click menu. When added to the menu, use the up and
down arrows in the plugin selection menu to place the Separator plugin 
between the plugins you wish to place a line between.

.. _Settings:

Preferences
-----------

info.ID = "Settings"

.. _luminamenuplugin7:

.. figure:: images/luminamenuplugin7.png

:numref:`Figure %s: Preferences <luminamenuplugin7>`

This plugin adds a shortcut to the right-click menu which points to the 
desktop settings menu.

.. _Terminal:

Terminal
--------

info.ID = "terminal"

.. _luminamenuplugin8:

.. figure:: images/luminamenuplugin8.png

:numref:`Figure %s: Terminal <luminamenuplugin8>`

A shortcut to the default system terminal.

.. _Window List:

Window List
-----------

info.ID = "windowlist"

.. _luminamenuplugin9:

.. figure:: images/luminamenuplugin9.png

:numref:`Figure %s: Window List <luminamenuplugin9>`

This plugin adds an entry to the right-click menu which, when hovered 
over with the mouse, will list all open application windows.

.. _panel plugins:

Panel Plugins
=============

Panels are a completely customizable option for Lumina users. By default,
Lumina users will have one panel stretched across the bottom of the 
primary screen and one smaller pop-up panel in the top middle of the 
primary screen. A simple panel centered at the top of the secondary 
screen was utilized to demonstrate the various plugins listed below. The
settings for this panel are pictured in :numref:`Figure %s: Panel Settings <luminapanelplugin1>`.

.. _luminapanelplugin1:

.. figure:: images/luminapanelplugin1.png

.. _panel application launcher:

Panel Application Launcher
--------------------------

info.ID = "applauncher"

.. _luminapanelplugin2:

.. figure:: images/luminapanelplugin2.png

:numref:`Figure %s: Panel Application Launcher <luminapanelplugin2>`

When you select this plugin, it will prompt you to select the 
application to launch. This will add a shortcut for launching the 
selected application to the panel.

.. _Application Menu:

Application Menu
----------------

info.ID = "appmenu"

.. _luminapanelplugin3:

.. figure:: images/luminapanelplugin3.png

:numref:`Figure %s: Application Menu <luminapanelplugin3>`

Adds an application menu that contains a shortcut to your home directory,
a shortcut to the operating system’s graphical software management 
utility (if there is one), a shortcut to the operating system’s Control 
Panel (if it provides one), and a list of installed software sorted by 
categories.

.. _Battery Monitor:

Battery Monitor
---------------

info.ID = "battery"

Hover over this icon (not pictured) to view the current charge status of
the battery. When the charge reaches 15% or below, the low battery icon 
will flash intermittently and will change to a low battery icon when 
there is less than 5% charge left.


.. _Desktop Bar:

Desktop Bar
-----------

info.ID = "desktopbar"

.. _luminapanelplugin4:

.. figure:: images/luminapanelplugin4.png

:numref:`Figure %s: Desktop Bar <luminapanelplugin4>`

Adds a “star” button for automatically displaying entries for anything
in the ~/Desktop folder and alternately launching the selected entry.

.. _Line:

Line
----

info.ID = "line"

.. _luminapanelplugin5:

.. figure:: images/luminapanelplugin5.png

:numref:`Figure %s: Line <luminapanelplugin5>`

Adds a separator line to the panel.

.. _Show Desktop:

Show Desktop
------------

info.ID = "homebutton"

.. _luminapanelplugin6:

.. figure:: images/luminapanelplugin6.png

:numref:`Figure %s: Show Desktop Button <luminapanelplugin6>`

This button will hide all open windows so that only the desktop is visible.
This is useful for touch screens or small devices.

.. _Spacer:

Spacer
------

info.ID = "spacer"

.. _luminapanelplugin7:

.. figure:: images/luminapanelplugin7.png

:numref:`Figure %s: Spacer <luminapanelplugin7>`

Adds a blank area to the panel.

.. _Panel Start Menu:

Start Menu
----------

info.ID = "systemstart"

.. _luminapanelplugin8:

.. figure:: images/luminapanelplugin8.png

:numref:`Figure %s: Start Menu <luminapanelplugin8>`

Adds a classic start menu as seen on other operating systems.

.. _System Dashboard:

System Dashboard
----------------

info.ID = "systemdashboard"

.. _luminapanelplugin9:

.. figure:: images/luminapanelplugin9.png

:numref:`Figure %s: System Dashboard <luminapanelplugin9>`

Used to view/modify audio volume, screen brightness, battery life, and 
virtual desktops.

.. _System Tray:

System Tray
-----------

info.ID = "systemtray"

Provides a display area for dockable applications.

.. _Task Manager (No Groups):

Task Manager (No Groups)
------------------------

info.ID = "taskmanager-nogroups"

.. _luminapanelplugin10:

.. figure:: images/luminapanelplugin10.png

:numref:`Figure %s: Task Manager (No Groups) <luminapanelplugin10>`

Ensures that every window gets its own button. This uses a lot more space
on the panel since it needs to put part of the window title on each button.

.. _Task Manager:

Task Manager
------------

info.ID = "taskmanager"

.. _luminapanelplugin11:

.. figure:: images/luminapanelplugin11.png

:numref:`Figure %s: Task Manager <luminapanelplugin11>`

Added by default. Its behavior is to group windows by application.

.. _Time Date:

Time/Date
---------

info.ID = "clock"

.. _luminapanelplugin12:

.. figure:: images/luminapanelplugin12.png

:numref:`Figure %s: Time/Date <luminapanelplugin12>`

Displays the current time and date.

.. _User Button:

User Menu
---------

info.ID = "userbutton"

.. _luminapanelplugin13:

.. figure:: images/luminapanelplugin13.png

:numref:`Figure %s: User Menu 1 <luminapanelplugin13>`

.. _luminapanelplugin14:

.. figure:: images/luminapanelplugin14.png

:numref:`Figure %s: User Menu 2 <luminapanelplugin14>`

.. _luminapanelplugin15:

.. figure:: images/luminapanelplugin15.png

:numref:`Figure %s: User Menu 3 <luminapanelplugin15>`

.. _luminapanelplugin16:

.. figure:: images/luminapanelplugin16.png

:numref:`Figure %s: User Menu 4 <luminapanelplugin16>`

.. _luminapanelplugin17:

.. figure:: images/luminapanelplugin17.png

:numref:`Figure %s: User Menu 5 <luminapanelplugin17>`

.. _luminapanelplugin18:

.. figure:: images/luminapanelplugin18.png

:numref:`Figure %s: User Menu 6 <luminapanelplugin18>`
Main button for accessing applications, directories, settings, and log 
out.

.. _Workspace Switcher:

Workspace Switcher
------------------

info.ID = "desktopswitcher"

.. _luminapanelplugin19:

.. figure:: images/luminapanelplugin19.png

:numref:`Figure %s: Workspace Switcher <luminapanelplugin19>`

Used to switch between virtual desktops.
