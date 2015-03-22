WifiScanAndMap
==============

A simple 802.11 mapping application for Linux written in Python.

Url
---

* [http://gmigdos.wordpress.com/2010/04/04/wifiscanandmap-a-wifi-mapping-application-for-linux/](http://gmigdos.wordpress.com/2010/04/04/wifiscanandmap-a-wifi-mapping-application-for-linux/)

Authors
-------

* Δόβα Φιλία (Dova Filia) <filia_do@hotmail.com>
* Μίγδος Γεώργιος (Migdos George) <cyberpython@gmail.com>

License
-------

* The source code is available under the [Apache v2.0 license](http://www.apache.org/licenses/LICENSE-2.0.html).
* The artwork is available under the [Creative Commons Attribution-Share Alike 3.0 Unported license](http://creativecommons.org/licenses/by-sa/3.0/).
* The 3rd party [Bluff Javascript library](http://bluff.jcoglan.com/) is available under the [MIT license](http://www.opensource.org/licenses/mit-license.php).

Description
-----------

WiFiScanAndMap is a Python WiFi mapping application for Linux.

You can use it to scan areas for wireless networks, collect information about them and then generate a web page displaying these information on a map.


The application was created as an assignment for the “Wireless Networks And Mobile Communcations” course at the Computer Science Department of the Athens University Of Economics And Business, by:

* Filia Dova
* Georgios Migdos


The application consists of two programs, the scanner and the map generator.

The user runs the scanner on a mobile device (laptop/netbook) which collects information about the wireless networks within range. The program relies on `iwlist` output for the scanning process. After the user is done, they can save the collected information as an XML file.

The scanner can be run as a GTK+ application or as a command line application (with the `–no-gui` parameter).

This process can be repeated any number of times, resulting in a number of XML files. These XML files are used as the input of the map generator program which parses the XML files and produces an HTML web page.



The map data used is obtained from OpenStreetMap and the tiles are from Yahoo! Maps. The graph is displayed using the Bluff Javascript library.



Requirements
------------

To run the scanner you need:

* A Linux system with wireless tools for Linux installed
* Wireless card supporting scanning
* GPS receiver
* Python 2.6.4
* gpsd (+python bindings)
* PyGTK+ 2.16 (if you want to use the GUI)

To display the map you need:

* A web browser supporting CSS with Javascript enabled
* An active internet connection
	

Usage
-----

You can run the scanner (GTK+ GUI) with the command :

        python scanner/scanner.py

You can run the scanner (GTK+ GUI) with the command :

        python scanner/scanner.py –no-gui

You can run the map generator with the command:

        python mapgenerator/mapgenerator.py <longitude> <latitude> <output directory> <input XML file 1> <input XML file 2> … <input XML file n>

where:

* `<longitude>` and `<latitude>` are the geographic coordinates of the resulting map’s original center
* `<output directory>` is the directory where the result files will be saved
* `<input XML file 1>` `<input XML file 2>` … `<input XML file n>` are the XML files generated by the scanner.
