Technische Daten
================

.. image:: ../pics/OBP40_Front_View_2_t.png
   :scale: 50%

Funktionen
----------

* E-Paper Display (tageslichttauglich)
* Numerische Anzeigeseiten für 1, 2, 3 und 4 Werte (Werte frei wählbar)
* Grafische Anzeigeseiten (feste Werte)
* Trendanzeige für Werte
* 1 Auswahlrad mit Drucktaster und 2 Auswahltasten
* Magnet-Dock für Stromversorgung über Pogo-Pins
* Magnet- und Kletthalterung
* USB-Dockingstation zum Laden und zum Datenaustausch
* NMEA2000 (über Hardwareerweiterung)
* NMEA0183 (über WiFi oder über Hardwareerweiterung)
* NMEA2000/NMEA0183 Gateway (bidirektional)
* I2C (über Erweiterungsport)
* 1Wire (über Erweiterungsport)
* USB-C (OTG, Debug, NMEA0183)
* WiFi 2.4GHz (HTTP, TCP, UDP)
* Bluetooth (aktuell ungenutzt)
* LiPo-Akku-Tiefentladeschutz < 3,65V (erfordert LiPo-Akku)
* Low Power Modus (Deep Sleep)


Aufbau
------

.. image:: ../pics/OBP40_Explode_View.png
   :scale: 50%


Spezifikation
-------------

+----------------------+-----------------------------+
| Versorgungsspannung  | 5 V, USB-C                  |
+----------------------+-----------------------------+
| Stromverbrauch       | 0.5 W                       |
+----------------------+-----------------------------+
| Prozessor            | ESP32-S3, Dual Core         |
+----------------------+-----------------------------+
| Clock Speed          | 80, 160, 240 MHz            |
+----------------------+-----------------------------+
| RAM                  | 512 kB                      |
+----------------------+-----------------------------+
| Flash                | 8 MB                        |
+----------------------+-----------------------------+
| PSRAM                | 8 MB                        |
+----------------------+-----------------------------+
| Displaygröße         | 400 x 300 pix, 120 dpi      |
+----------------------+-----------------------------+
| Refreshrate          | 1 Hz                        |
+----------------------+-----------------------------+
| Sensortasten         | kapazitiv                   |
+----------------------+-----------------------------+
| Schutzgrad           | IP20                        |
+----------------------+-----------------------------+
| Abmessungen          | 110 x 115 x 30 mm           |
+----------------------+-----------------------------+
| Gewicht              | 110 g                       |
+----------------------+-----------------------------+

Anschlussbelegung
-----------------
.. image:: ../pics/OBP40_Side_View_2_t.png
   :scale: 50%
   
.. image:: ../pics/Logo_ESP32-S3_t.png
   :scale: 60%
   
Abb.: USB-Port
   
.. image:: ../pics/CrowPanel_4.2_ESP32_HMI_E-paper_Display.png
   :scale: 50%
   
Abb.: Platinen-Anschlussbelegung
   
Schaltplan
----------

* `Schaltplan V2.1 [PDF] <../_static/files/CrowPanel_ESP32_Display-4.2(E)_Inch.pdf>`_


Maßbilder
---------

* `Maßbild [PDF] <../_static/files/Drawing_OBP40_V2.pdf>`_

   
Nutzbare und konvertierbare Telegramme
--------------------------------------

**NMEA0183**
    * AIVDM, AIVDO, DBK, DBS, DBT, DPT, GGA, GLL, GSA, GSV, HDG, HDM, HDT, MTW, MWD, MWV, RMB, RMC, ROT, RSA, VHW, VTG, VWR, XDR, XTE, ZDA
    
**NMEA2000**
    * 126992, 127245, 127250, 127251, 127257, 127258, 127488, 127489, 127505, 127508, 128259, 128267, 128275, 129025, 129026, 129029, 129033, 129038, 129039, 129283, 129284, 129539, 129540, 129794, 129809, 129810, 130306, 130310, 130311, 130312, 130313, 130314, 130316
	
Nutzbare I2C-Sensorik
---------------------

**Umgebungssensoren**
	* BMP085, BMP180, BMP280, BME280, SHT20, HTU21
	
**Spannungs- und Stromsensoren**
	* INA226, INA219 (in Vorbereitung)
	
**Winkelsensoren**
	* AS5600, MT6701 (in Vorbereitung)
	
**Port-Erweiterungen**
	* PCF8574 (in Vorbereitung)
	
**Echtzeit-Uhren**
	* DS1388
	
Nutzbare 1Wire-Sensorik
-----------------------

**Temperatursensoren**
	* DS18B20
