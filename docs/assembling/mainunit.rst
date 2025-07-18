Montage OBP40
=============

Zusammenbauzeichnung
--------------------

.. image:: ../pics/OBP40_Explode_View_Main_Unit_2.png
	:scale: 45%
Abb.: Montage OBP40 Main Unit

Stückliste
----------

+------+--------+-----------------+--------------+----------------+
| Pos. | Anzahl | Bezeichnung     | Material     | Bezugsquelle   |
+======+========+=================+==============+================+
|  1   |   1    | Front Case      | ABS / ASA    |`Filamentworld`_| 
+------+--------+-----------------+--------------+----------------+
|  2   |   1    | Backside Case   | ABS / ASA    |`Filamentworld`_| 
+------+--------+-----------------+--------------+----------------+
|  3   |   1    | Crow Panel 4.2  | FR4          |`Elecrow`_      | 
+------+--------+-----------------+--------------+----------------+
|  4   |   1    | LiPo-Akku [#f1]_| 3.7V, 1200mA |`Ebay 1`_       | 
+------+--------+-----------------+--------------+----------------+
|  5   |   1    | Magnet Dock     | 4 pol.       |`Aliexpress`_   | 
+------+--------+-----------------+--------------+----------------+
|  6   |   4    | Magnete D5x3    | Neodym       |`Ebay 2`_       | 
+------+--------+-----------------+--------------+----------------+
|  7   |   1    | Velcro D 3 mm   | 50 x 40 mm   |`Ebay 3`_       | 
+------+--------+-----------------+--------------+----------------+
|  8   |   4    | M2.5x4          | Stahl/Nickel |                | 
+------+--------+-----------------+--------------+----------------+
.. [#f1] LiPo-Akku: 52 x 43 x 6 mm

.. _Filamentworld: https://filamentworld.de/
.. _Elecrow: https://www.elecrow.com/crowpanel-esp32-4-2-e-paper-hmi-display-with-400-300-resolution-black-white-color-driven-by-spi-interface.html?srsltid=AfmBOop2GlNZoGPKRSSgsEbjJsjm_UUejsKLcMl8AgrbSMgXZkk0wmqY
.. _Ebay 1: https://www.ebay.de/itm/255510046348?var=555706977193
.. _Ebay 2: https://www.ebay.de/itm/184323747008?var=692014131466
.. _Ebay 3: https://www.ebay.de/itm/267017971020
.. _Aliexpress: https://de.aliexpress.com/item/1005007348770116.html?spm=a2g0o.order_list.order_list_main.5.54d95c5ftn0cyU&gatewayAdapt=glo2deu

Montageanleitung
----------------

Die Gehäusemontage erfolgt nach der Montageanleitung in folgender Reihenfolge:

1. Gehäuseteile drucken
	Die Gehäuseteile lassen sich mit einem gewöhnlichen 3D-Drucker drucken. Verwenden Sie folgende Einstellungen:
	
	* 0.4 mm Düse
	* Wanddicke 1 mm
	* Wanddicke der Ober- und Unterseite 1 mm
	* Füllgrad 30 %
	* Support eingeschaltet
	
	.. hint::
		Die Frontschale ist als zweifarbiger Druck ausgelegt. Die schwarzen Flächen sind als 0.2 mm dicke Einlagen realisiert. Konsultieren Sie die Dokumentation des Druckers für einen zweifarbigen Ausdruck. Wenn Ihr Drucker keinen zweifarbigen Ausdruck zulässt, können Sie die Frontschale auch in einer durchgängigen Farbe drucken. Benutzen Sie dazu einfach die STL-Datei.
	
2. Rückseite und Spacer des Crow Panel 4.2 abschrauben
	.. image:: ../pics/CrowPanel_4.2_Top_Side.png
		:scale: 45%
	Abb.: Crow Panel 4.2 Mainboard Oberseite (Elecrow)
	
3. Crow Panle 4.2 Platine in Frontschale einlegen
	Platine seitlich beginnend mit den Tastern in die Frontschale einlegen.
	
	.. image:: ../pics/OBP40_Assembling_1_t.png
		:scale: 45%

4. Magnet Dock mit Heißkleber in Rückwand einkleben
	Darauf achten, dass der Magnet Dock mittig sitzt und mit reichlich Heißkleber umschlossen ist, Darauf achten, dass kein Heißkleber nach außen dringt. Gegebenenfalls überschüssigen Heißkleber entfernen.
	
	.. image:: ../pics/OBP40_Assembling_6_t.png
		:scale: 45%

5. Magnete mit Heißkleber in Rückwand einkleben
	Vor dem Einlegen der Magnete einen Klecks Heißkleber in die Vertiefung geben und zügig den Magneten einlegen, damit der Kleber nicht frühzeitig erstarrt. Darauf achten, dass nicht zu viel Heißkleber in der Vertiefung verwendet wird.

6. Klettband auf 50 x 40 mm zuschneiden und in Vertiefung der Rückwand einkleben
	Das Klettband so einkleben, dass es nicht an den Kanten übersteht und vollständig in der Vertiefung ist.
	
	.. image:: ../pics/OBP40_Back_Side_2_t.png
		:scale: 45%

7. LiPo-Akku, Magnet Dock und Spannungsteiler einbauen und Kabel anlöten
	.. hint::
		Das Anlöten der Kabel erfordert gute Lötkenntnisse und qualitativ hochwertiges Lötwerkzeug, da die Anschlüsse sehr klein sind. Verwenden Sie einen regelbaren Lötkolben mit einer feinen Spitze und Lötzinn mit 0.5 mm Durchmesser. Flussmittel und Kupferband zum Aufnehmen von überschüssigem Lötzinn vereinfachen die Arbeiten. Wenn Sie sich die Arbeiten nicht zutrauen, kontaktieren Sie eine Fachkraft, die ihnen behilflich ist. 
	.. warning::	
		Achten Sie darauf, dass sie keine Kurzschlüsse auf der Platine mit anderen Bauelementen verursachen. Löten sie nicht zu lange an den betreffenden Stellen, da sie sonst u.U. Bauelemente entlöten oder Leiterbahnen beschädigen. Kontrollieren Sie alle Lötstellen bevor Sie die Platine wieder in Betrieb nehmen. Prüfen Sie mit einem Digitalvoltmeter auf Kurzschlüsse an den Lötungen. Bedenken sie, dass Sie durch die Lötarbeiten die Garantie des Herstellers verlieren.

	Löten Sie die Kabel entsprechend der Tabelle und der Bilder an.
	
	+------------+-----------+-------------+
	| Lötpunkt   | Aderfarbe | Bauteil     |
	+============+===========+=============+
	| C5 oben    | rot, 3.7V | LiPo Akku   |
	+------------+-----------+-------------+
	| C5 unten   | schwarz   | LiPo Akku   |
	+------------+-----------+-------------+
	| C4 links   | rot, 5 V  | Magnet Dock |
	+------------+-----------+-------------+
	| R2 links   | weiß, D-  | Magnet Dock |
	+------------+-----------+-------------+
	| U1 Pin 5   | gelb, D+  | Magnet Dock |
	+------------+-----------+-------------+
	| C4 rechts  | schwarz   | Magnet Dock |
	+------------+-----------+-------------+
	| C5 oben    | rot       | V-Teiler    |
	+------------+-----------+-------------+
	| IO3        | grün      | V-Teiler    |
	+------------+-----------+-------------+
	| USB-C, GND | schwarz   | V-Teiler    |
	+------------+-----------+-------------+
	
	.. image:: ../pics/Schematic_USB_LiPo.png
		:scale: 45%
	Abb.: Lötpunkte für Anschlusskabel
	
	.. image:: ../pics/Voltage_Measurement.png
		:scale: 50%
	Abb.: Spannungsteiler für Ladezustandsmessung
	
	.. image:: ../pics/OBP40_Assembling_4_t.png
		:scale: 45%
	Abb.: Lötpunkt für IO3
	
	.. image:: ../pics/OBP40_Assembling_5_t.png
		:scale: 45%
	Abb.: Lötpunkte für USB-C GND
	
	.. image:: ../pics/OBP40_Assembling_7_t.png
		:scale: 45%
	Abb.: Position des LiPo-Akku auf der Platine
	
	.. note::
		Achten Sie darauf, die Anschlusskabel am Magnet Dock mit 3 mm Schrumpfschlauch zu isolieren. So vermeiden Sie Kurzschlüsse mit der Platine.
		
	.. image:: ../pics/OBP40_Assembling_3_t.png
		:scale: 45%

8. Rückwand auf Frontschale auflegen und mit Schrauben M2.5 verbinden
	Verwenden Sie die Schrauben, die sie beim Crow Panel 4.2 an der Rückseite abgeschraubt haben. Die Löcher im Kunststoff sind so dimensioniert, dass sie die Schrauben mit etwas Druck einschrauben können. Das Geinde schneidet sich dann selbständig in den Kunststoff.

	.. hint::
		Wenn Sie die Schrauben erneut hereinschrauben wollen, drehen sie die Schrauben zuerst nach links bis das Gewinde spürbar einrastet und ziehen erst danach die Schraube rechts herum an. So vermeiden Sie eine Beschädigung des Gewindes.

9. Firmware flashen
	Im letzten Punkt wird die Firmware geflasht. Dazu gehen Sie nach der Anleitung im Kapitel :ref:`Web-Flashtool` vor.
	
10. Firmware modifizieren

	.. note::
		Damit die Firmware den LiPo-Akku und den Ladezustand anzeigen kann, müssen in der Firmware die entsprechenden Compiler-Flags ``LIPO_ACCU_1200`` und ``VOLTAGE_SENSOR`` in der `platformio.ini`_ gesetzt sein. Sie müssen sich dazu eine angepasste Firmware erstellen und diese Firmware im OBP60 als :ref:`Update` aktivieren. Details zur Firmwareerstellung finden Sie im Kapitel :ref:`Gitpod`. 

	.. _platformio.ini: https://github.com/norbert-walter/esp32-nmea2000-obp60/blob/master/lib/obp60task/platformio.ini	