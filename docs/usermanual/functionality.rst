Funktionsweise
==============

Gateway
-------

.. image:: ../pics/NMEA_Gateway.png
             :scale: 20%

Im OBP40 ist ein Gateway integriert, das Daten zwischen NMEA0183 und NMEA2000 bidirektional austauschen kann. Dabei werden die Daten des einen Busses in die Daten des anderen Busses übersetzt. Die Übersetzung funktioniert dabei in beide Richtungen.

.. note::
   Dabei ist zu beachten, dass nicht alle NMEA2000-Daten in NMEA0183-Daten übersetzt werden können, weil dafür nicht immer geeignete Telegramme in NMEA0183 existieren.
   
WiFi-Verbindung
---------------

Das OBP40 verfügt über eine WiFi-Funktionalität im 2.4 GHz Funkbereich. Darüber hinaus kann das Gerät mit dem Internet oder mit anderen WiFi-Netzwerken verbunden werden und so mit anderen Geräten kommunizieren. So lassen sich z.B. Daten aus den Bussystemen an einen Laptop, einen PC oder ein Handy übertragen oder von dort beziehen. Damit ist es möglich, die Sensordaten auch in Drittanbieter-Software wie SignalK, OpenPlotter, Navionics, NMEA-Remote oder WinGPS zu verwenden.

Konfiguration
-------------

Das OBP40 hat einen Access Point und einen kleinen Webserver integriert, mit denen das Gerät konfiguriert werden kann. Im Gegensatz zu anderen kommerziellen Geräten erfolgt die Konfiguration des OBP40 ausschließlich webbasiert. Dazu kann z.B. ein Handy benutzt werden. So ist die Konfiguration des Gerätes deutlich einfacher und komfortabler. Im Gerät lassen sich bis zu 10 Anzeigeseiten frei definieren. Der Anwender kann zwischen numerischen und grafischen Anzeigeseiten auswählen. Für jede numerische Anzeigeseite können beliebige Daten der Bussysteme angezeigt werden. Bei den grafischen Anzeigeseiten sind die Dateninhalte vorgegeben, da sie spezielle Funktionalitäten bieten.

Anzeige und Bedienung
---------------------

.. image:: ../pics/OBP40_Side_View_Buttons_2_t.png
             :scale: 50%

Als Anzeige wird ein E-Paper Display verwendet. Es besitzt einen hohen Kontrast und eine gute Ablesbarkeit auch bei starkem Sonnenlicht. Zudem verbraucht es sehr wenig Energie.

Die Auswahl der Anzeigeseiten erfolgt über ein Jogdail-Auswahlrad mit Druckpunkt und zwei zusätzliche Tasten an der rechten Seite. Je nach Anzeigeseite können einige Einstellungen auch über die Tasten vorgenommen werden. Die Einstellungen gelten dann ausschließlich für die Anzeigeseite und werden gespeichert, sodass die Einstellungen beim Seitenwechsel erhalten bleiben.

USB-Ports
---------
.. image:: ../pics/OBP40_Side_View_2_t.png
   :scale: 50%

Das OBP40 verfügt auf der linken Seite über einen USB-Port, der parallel über Kontakte auf der Rückseite auf die Docking-Station übertragen wird. Die Docking-Station verfügt über ein eigenes USB-Kabel, das mit anderen Geräten verbunden werden kann. Solange sich das OBP40 in der Docking-Station befindet, erfolgt die USB-Verbindung über das USB-Kabel der Docking-Station.

.. hint::
	Es darf nur eine USB-Verbindung zum OBP40 bestehen. Verwenden Sie entweder die linke USB-Buchse am OBP40 **oder** das USB-Kabel der Docking-Station. Beide USB-Verbindungen dürfen nicht gleichzeitig benutzt werden.

Erweiterungsport
----------------

.. image:: ../pics/CrowPanel_4.2_ESP32_HMI_E-paper_Display.png
   :scale: 50%
   
Abb.: Platinen-Anschlussbelegung

Die Platine verfügt über einen 20-poligen Erweiterungsport an der oberen Seite. Darüber lässt sich optional Zusatzhardware anschließen wie z.B.:

* CAN-Bus (NMEA0183)
* RS485-Bus (NMEA0183)
* I2C-Bus
* 1Wire-Bus
* Buzzer
* GPS-Empfänger (RS232)
* Analoger Eingang zur Spannungsmessung

.. warning::
	Der Anschluss von Zusatzhardware erfordert Kenntnisse in Elektronik, um die Zusatzhardware korrekt anschließen zu können. Die Signalpegel an der Anschlüssen dürfen 3.3 V nicht übersteigen und es ist darauf zu achten, ob die Anschlüsse als Eingang oder Ausgang verwendet werden. Die herausgeführten Anschlüsse sind ungeschützt. Der Prozessor kann bei falscher Benutzung der Anschlüsse irreparabel beschädigt werden.