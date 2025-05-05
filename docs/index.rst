######################
OBP40 V1 Dokumentation
######################
Letzte Aktualisierung |today|

.. image:: https://readthedocs.org/projects/obp40-v1-docu/badge/?version=latest
    :target: https://obp40-v1-docu.readthedocs.io/de/latest/?badge=latest
    :alt: Documentation Status

.. note::
   Diese Seiten sind noch in Bearbeitung.

.. image:: /pics/OBP40_Front_View_2_t.png
             :scale: 50%

Das Multifunktionsdisplay OBP40 basiert auf dem `Crow Panel 4.2`_ von Elecrow und dient zur Anzeige von Daten aus Boots-Netzen wie NMEA0183, NMEA2000. Es ist primär als günstige Einstiegslösung zum OBP60 gedacht, unterliegt aber einigen Einschränkungen in der Benutzung. Ohne Hardware-Modifikationen am Crow Panel 4.2 kann das Display zu einem OBP40 mit entsprechender Firmware umgebaut werden. Open Boat Projects stellt mit dem `Web-Flashtool`_ eine einfache Möglichkeit zum Flashen der Firmware bereit. Es wird lediglich ein Wenbrowser und ein USB-Kabel benötigt. Mit optionaler Zusatzhardware können Daten aus dem 1Wire-Bus und dem I2C-Bus ausgelesen werden. Das OBP40 enthält ein Gateway, das Daten bidirektional zwischen NMEA0183 und NMEA2000 austauschen kann. Über WiFi lassen sich die Daten importieren oder exportieren und können auf anderen Geräten oder in Drittanbietersoftware verwendet werden. Die Konfiguration erfolgt über eine Webseite. Darüber lassen sich vordefinierte Anzeigeseiten auswählen, und es können dessen Anzeigeinhalte festgelegt werden. Das OBP40 basiert auf Open Hardware, Open Software und Open Data. Das Gerät lässt sich durch die Offenheit an beliebige Anforderungen über die Software anpassen.

.. _Crow Panel 4.2: https://www.elecrow.com/crowpanel-esp32-4-2-e-paper-hmi-display-with-400-300-resolution-black-white-color-driven-by-spi-interface.html
.. _Web-Flashtool: https://norbert-walter.github.io/obp40-v1-docu/flash_tool/esp_flash_tool.html

.. toctree::
   :maxdepth: 3
   :caption: Einführung
   :name: sec-intro

   Technische Daten <intro/specification>
   
.. toctree::
   :maxdepth: 3
   :caption: Bedienung
   :name: sec-usermanual

   Funktionsweise <usermanual/functionality>
   Bedienelemente <usermanual/elements>
   Inbetriebnahme <usermanual/start>
   Konfiguration <usermanual/configuration>
   Datenaustausch <usermanual/dataexchange>
   Erweiterte Sensorik <usermanual/sensors>
   Beispielkonfiguration <usermanual/samples>
   Sicherheitshinweise <usermanual/safety>

.. toctree::
   :maxdepth: 3
   :caption: Zusammenbau
   :name: sec-assembling
   
   Geräteaufbau <assembling/device>
   
.. toctree::
   :maxdepth: 3
   :caption: Programmierung
   :name: sec-programming   

   Programmierumgebung <programming/environment>
   Seitenerstellung <programming/pages>
   Kompilieren und Download <programming/activating>
   Web-Flashtool <programming/webflashtool>
   
.. toctree::
   :maxdepth: 3
   :caption: Hilfe
   :name: sec-help   

   Fragen und Antworten <help/faq>
   Meinungen und Tipps <help/opinions>
   Bekannte Fehler <help/errors>
   Technische Unterstützung <help/support>
   Service <help/service>
   Mitarbeit <help/cooperation>
   Spenden <help/donation>
   Glossar <help/glossar>
