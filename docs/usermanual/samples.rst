Beispielkonfiguration
=====================

OBP40 mit Yachta und M5Stack
----------------------------

Im folgenden Beispiel wird gezeigt wie man mit einem **OBP40** eine Datenübertragung zum **Windsensor Yachta** und zu einem **M5Stack CAN Unit** mit `NMEA2000-Gateway`_ aufbauen und die Daten in der Navigationsapp AvNav auf einem Tablett nutzen kann. Die M5Stack CAN Unit dient dabei als zentrale Datenbasis in der alle Daten zusammenlaufen. Die Datenübertragung erfolgt über WiFi-Netzwerkverbindungen, die ein LTE-Router zur Verfügung stellt. Der Vorteil eines LTE-Routers besteht darin, dass sie alle Geräte an Bord mit einer WiFi-Internetverbindung versorgen können und die Geräte im WiFi-Netzwerk untereinander kommunizieren können. Der LTE-Router schottet das eigen WiFi-Netzwerk gegenüber dem Internet ab, so dass von außerhalb niemand auf Ihr internes Netzwerk Zugriff erhält. Somit lassen sich auch Geräte wie Handys, Tabletts oder Laptops an Bord mit dem Internet verbinden und alle Geräte haben Zugriff auf die Daten der Sensoren und können über einen Web-Browser darauf zugreifen. Die Naviationssoftware AvNav wird dabei auf einem Android-Tablett installiert und zur Navigation genutzt.

.. _NMEA2000-Gateway: https://open-boat-projects.org/de/nmea2000-gateway-mit-m5stack-atom/

.. image:: ../pics/SeaSmart2_OBP40.png
             :scale: 60%	
Abb.: Beispielkonfiguration OBP40, Yachta, M5Stack, AvNav

Die Konfiguration läuft in folgenden Schritten ab:

* LTE-Router einrichten
* M5Stack mit NMEA2000-Netzwerk und OBP40 verbinden
* OBP40 mit Windsensor Yachta verbinden
* AvNav mit dem M5Stack verbinden

LTE-Router einrichten
---------------------

Als LTE-Router können Sie sowohl mobile Geräte als auch stationäre Geräte verwenden. Mobile Geräte haben den Vorteil, dass sie autark über eine Batterie über einen längeren Zeitraum funktionieren und auch außerhalb des Bootes an Land bei Ausflügen benutzt werden können. Stationäre Geräte bieten sich an, wenn man maximale Empfangsleistung benötigt und in Küstennähe unterwegs ist und große Entfernungen zur nächsten Mobilfunk-Basisstation überbrücken möchte. In solchen Fällen bietet es sich an, Mobilfunkantennen oben im Mast zu installieren und die Antenne per Kabel mit dem stationären Router zu verbinden.

.. tip::
	Achten Sie beim Kauf des LTE-Routers, dass der Router im Dualband-Modus in den zwei WiFi-Frequenzbereichen 2.4 GHz und 5 GHz arbeiten kann und über 4G/5G-Mobilfunk-Standard verfügt. So profitieren sie von einer leistungsfähigen Internet- und WiFi-Verbindung im 5 GHz Bereich und umgehen die meist überfüllten 2.4 GHz Ferquenzbereiche. Solche Router können Daten zwischen beiden Frequenzbereichen problemlos austauschen.

.. image:: ../pics/LTE-Router_TP-Link_M7450.png
             :scale: 30%	
Abb.: Mobiler 4G-LTE-Dualband-Router TP-Link M7450

	* Leistungsdaten
		- 4G/LTE Mobilfunkstandard 50 MBit/scale
		- WiFi Dualband 2.4 GHz **oder** 5 GHz 300 MBit/s [#f2]_
		- 3000 mAh LiPo-Akku
		- 15 Stunden autarke Laufzeit
		- 32 WiFi-Geräte einbindbar
		- 32 GB SD-Card-Speicher
		- USB-, SMB- und FTP-Share für Filme und Musik von SD-Card
		- `Dokumentation <../_static/m7450.pdf>`_
	.. [#f2] Kein gleichzeitiger Dualbetrieb	
		
.. image:: ../pics/LTE-Router_RUT360.png
             :scale: 40%	
Abb.: Stationärer 4G-LTE-Dualband-Router RTU360

	* Leistungsdaten
		- 4G/LTE Mobilfunkstandard 50 MBit/scale
		- WiFi Dualband 2.4 GHz und 5 GHz 300 MBit/s
		- 2x LAN CAT6 100 MBit/s
		- Externe Antennen für LTE und WiFi
		- 12V Versorgungseingang
		- 230V AC-Netzteil
		- `Online-Dokumentation`_
		- `Quick-Installation Guide`_
		
.. _Online-Dokumentation: https://wiki.teltonika-networks.com/view/RUT360_Manual
.. _Quick-Installation Guide: https://wiki.teltonika-networks.com/view/QSG_RUT360

Der verwendete LTE-Router wird entsprechend der Bedienungsanleitung in Betrieb genommen. Für eine Internetverbindung benötigen Sie einen Mobilfunk-Datenvertrag. Die meisten Mobilfunkfirmen bieten preisgünstige Datentarife an. Empfehlenswert sind Volumenverträge, die ein festes Datenvolumen für eine vorgegebene Zeitdauer bieten. Wählen Sie einen Tarif aus, der Ihrem Datenverbrauch entspricht. Das Datenvolumen können Sie ebenfalls in allen Ländern der EU uneingeschränkt nutzen, so wie Sie das in Ihrem Heimatland gewohnt sind.

Für das Konfigurationsbeispiel gehen wir davon aus, dass die Geräte folgende IP-Adressen vom Router zugewiesen bekommen:

	* MyBoat - WiFi-SSID
	* MySecret - WiFi Passwort
	* 192.168.1.1   - LTE-Router
	* 192.168.1.100 - OBP40
	* 192.168.1.101 - M5Stack
	* 192.168.1.102 - Windsensor Yachta
	* 192.168.1.103 - Android-Tablett mit AvNav
	* 192.168.1.104 - Handy

.. hint::
	In Ihrem konkreten Fall können die IP-Adressen abweichen. Verwenden Sie dann die IP-Adressen, die den Geräten vom Router zugewiesen worden sind.
	
Konfiguration M5Stack
---------------------

Der M5Stack CAN Unit wird der Systemname M5Stack zugewiesen und mit dem WiFi-Netzwerk des LTE-Routers verbunden. Der TCP-Server ist so konfiguriert, dass zu einem Tablett Daten übertragen werden können. Die TCP-Client-Verbindung dient zur Kommunikation mit dem OBP40. Der M5Stack ist per Kabel über die CAN-Unit mit dem NMEA2000-Netzwerk des Bootes verbunden. Sensordaten die im M5Stack vorliegen, wie z.B. die Windsensor-Daten, werden auch in den NMEA2000-Bus übertragen.

Nehmen Sie folgende Einstellungen vor:

+---------------------------+---------------------+
|Einstellung                |M5Stack              |
+===========================+=====================+
|:ref:`Config - System`     |                     |
+---------------------------+---------------------+
|System Name                |M5Stack              |
+---------------------------+---------------------+
|:ref:`Config - WiFi Client`|                     |
+---------------------------+---------------------+
|WiFi Client                |on                   |
+---------------------------+---------------------+
|WiFi Client SSID           |MyBoat               |
+---------------------------+---------------------+
|WiFi Client Password       |MySecret             |
+---------------------------+---------------------+
|:ref:`Config - Converter   |                     |
+---------------------------+---------------------+
|NMEA2000 Out               |on                   |
+---------------------------+---------------------+
|:ref:`Config - TCP Server` |                     |
+---------------------------+---------------------+
|TCP Port                   |10110                |
+---------------------------+---------------------+
|NMEA0183 Out               |on                   |
+---------------------------+---------------------+
|NMEA0183 In                |on                   |
+---------------------------+---------------------+
|To NMEA2000                |on                   |
+---------------------------+---------------------+
|SeaSmart Out               |on                   |
+---------------------------+---------------------+
|:ref:`Config - TCP Client` |                     |
+---------------------------+---------------------+
|Enable                     |on                   |
+---------------------------+---------------------+
|Remote Port                |10110                |
+---------------------------+---------------------+
|Remote Address             |192.168.1.100        |
+---------------------------+---------------------+
|NMEA0183 Out               |on                   |
+---------------------------+---------------------+
|To NMEA2000                |on                   |
+---------------------------+---------------------+
|SeaSamart Out              |on                   |
+---------------------------+---------------------+

Nach der Konfiguration sollten Sie im Status nachfolgende Informationen sehen. Der M5Stack ist als WiFi-Client beim LTE-Router angemeldet und hat die IP-Adresse 192.168.1.101 zugewiesen bekommen. Der M5Stack ist als TCP-Client mit dem OBP40 verbunden. Über diese Verbindung können NMEA0183- und NMEA2000-Daten ausgetauscht werden. Der NMEA2000-Status wird als Oline angezeigt, wenn Daten mit dem NMEA2000-Bus ausgetauscht werden. Die NMEA2000-Daten werden mit SeaSmart zum OBP40 über die WiFi-Verbindung übertragen. Die Anzahl der ausgetauschten NMEA2000-Telegramme sieht man unter NMEA2000 In/Out. Wenn ein OBP40 oder ein Tablett mit dem M5Stack per TCP verbunden ist, sieht man die Anzahl der ausgetauschten NMEA0183-Telegramme unter TCP In/Out.

+---------------------------+---------------------+
|Statusmeldungen            |OBP40                |
+===========================+=====================+
|:ref:`Status`              |                     |
+---------------------------+---------------------+
|WiFi Client Connected      |true                 |
+---------------------------+---------------------+
|WiFi Client IP             |192.168.1.101        |
+---------------------------+---------------------+	
|NMEA2000 State             |[0] Online           |
+---------------------------+---------------------+	
|NMEA2000 In                |Telegrammeanzahl     |
+---------------------------+---------------------+
|NMEA2000 Out               |Telegrammeanzahl     |
+---------------------------+---------------------+
|TCP In                     |Telegrammeanzahl     |
+---------------------------+---------------------+
|TCP Out                    |Telegrammeanzahl     |
+---------------------------+---------------------+	

Konfiguration OBP40
-------------------

Dem Anzeigegerät OBP40 wird der Systemname OBP40V1 zugewiesen und mit dem WiFi-Netzwerk des LTE-Routers verbunden. Der TCP-Server ist so konfiguriert, dass über SeaSmart NMEA2000-Telegramme zur M5Stack CAN Unit übertragen werden können. Die TCP-Client-Verbindung dient zur Kommunikation mit dem Windsensor Yachta. Die Daten des Yachta Windsensors werden über den TCP-Server an die M5Stack CAN Unit übertragen. Über sie selbe Verbindung können auch Daten aus dem NMEA2000-Bus zum OBP40 über SeaSmart übertragen werden.

Folgende Einstellungen sind vorzunehmen:

+---------------------------+---------------------+
|Einstellung                |OBP40                |
+===========================+=====================+
|:ref:`Config - System`     |                     |
+---------------------------+---------------------+
|System Name                |OBP40V1              |
+---------------------------+---------------------+
|:ref:`Config - WiFi Client`|                     |
+---------------------------+---------------------+
|WiFi Client                |on                   |
+---------------------------+---------------------+
|WiFi Client SSID           |MyBoat               |
+---------------------------+---------------------+
|WiFi Client Password       |MySecret             |
+---------------------------+---------------------+
|:ref:`Config - TCP Server` |                     |
+---------------------------+---------------------+
|TCP Port                   |10110                |
+---------------------------+---------------------+
|NMEA0183 Out               |on                   |
+---------------------------+---------------------+
|NMEA0183 In                |on                   |
+---------------------------+---------------------+
|To NMEA2000                |on                   |
+---------------------------+---------------------+
|SeaSmart Out               |on                   |
+---------------------------+---------------------+
|:ref:`Config - TCP Client` |                     |
+---------------------------+---------------------+
|Enable                     |on                   |
+---------------------------+---------------------+
|Remote Port                |6666                 |
+---------------------------+---------------------+
|Remote Address             |192.168.1.102        |
+---------------------------+---------------------+
|NMEA0183 Out               |off                  |
+---------------------------+---------------------+
|To NMEA2000                |on                   |
+---------------------------+---------------------+
|SeaSamart Out              |off                  |
+---------------------------+---------------------+

Nach der Konfiguration sollten Sie im Status nachfolgende Informationen sehen. Das OBP40 ist als WiFi-Client beim LTE-Router angemeldet und hat die IP-Adresse 192.168.1.100 zugewiesen bekommen. Der M5Stack ist als TCP-Client mit dem OBP40 verbunden. Über diese Verbindung können NMEA0183- und NMEA2000-Daten ausgetauscht werden. Der NMEA2000-Status wird als Offline angezeigt, weil keine direkte Kabelverbindung zum NMEA2000-Netzwerk existiert. Die NMEA2000-Daten werden mit SeaSmart über die WiFi-Verbindung übertragen.

+---------------------------+---------------------+
|Statusmeldungen            |OBP40                |
+===========================+=====================+
|:ref:`Status`              |                     |
+---------------------------+---------------------+
|WiFi Client Connected      |true                 |
+---------------------------+---------------------+
|WiFi Client IP             |192.168.1.100        |
+---------------------------+---------------------+	
|#Clients                   |1                    |
+---------------------------+---------------------+	
|NMEA2000 State             |[32] Offline         |
+---------------------------+---------------------+	

Konfiguration Yachta
--------------------

Der Windsensor Yachta ist so konfiguriert, dass er im WiFi-Netzwerk des LTE-Routers eingebucht ist. Der Windsensor stellt über den Port 6666 dem OBP40 Winddaten zur Verfügung. Es werden dabei nur Daten vom Windsensor Yachta zum OBP40 übertragen. 

Folgende Einstellungen werden für den Windsensor Yachta vorgenommen:

+---------------------------+---------------------+
|Einstellung                |Yachta               |
+===========================+=====================+
|**Network Settings**       |                     |
+---------------------------+---------------------+
|WLAN Client SSID           |MyBoat               |
+---------------------------+---------------------+
|WLAN Client IP             |MySecret             |
+---------------------------+---------------------+
|Connection Timeout         |30s                  |
+---------------------------+---------------------+
|WLAN Sever SSID            |Yachta               |
+---------------------------+---------------------+
|WLAN Server Password       |********             |
+---------------------------+---------------------+
|AP Channel                 |1                    |
+---------------------------+---------------------+
|Server Mode                |HTTP (JSON/NMEA)     |
+---------------------------+---------------------+
|mDNS Service               |on                   |
+---------------------------+---------------------+
|**Device Settings**        |                     |
+---------------------------+---------------------+
|Wind Sensor Type           |Yachta 2.0           |
+---------------------------+---------------------+

.. tip::
	Der Windsensor Yachta lässt sich in einen Demo-Mode versetzen. So kann die Funktionalität am Schreibtisch getestet werden. Der Windsensor leifert dann simulierte Winddaten. Über **Server Mode** kann der Simulationsmodus mit der Einstellung ``Demo Mode`` aktiviert werden.

Nach der Konfiguration sollten unter **Device Info** im Windsensor Yachta folgende Statusmeldungen zu sehen sein:

+---------------------------+---------------------+
|Statusmeldungen            |Yachta               |
+===========================+=====================+
|**Network Parameter**      |                     |
+---------------------------+---------------------+
|WLAN Client SSID           |MyBoat               |
+---------------------------+---------------------+
|WLAN Client IP             |192.168.1.102        |
+---------------------------+---------------------+
|Connection Quality         |>50%                 |
+---------------------------+---------------------+	

Tablett Konfiguration
---------------------

Das Android-Tablett wird in das WiFi-Netzwerk des LTE-Routers hinzugefügt und anschleißend die App AvNav aus dem Play-Sore installiert. Details zur Konfiguration entnehmen Sie dem Handbuch zum Tablett. Die Daten eines GPS-Empfangers im Tablett lassen sich ebenfalls im NMEA0183- und NMEA2000-Netzwerk nutzen.

+---------------------------+---------------------+
|Einstellung                |Android-Tablett      |
+===========================+=====================+
|**Einstellungen WiFi**     |                     |
+---------------------------+---------------------+
|WiFi                       |on                   |
+---------------------------+---------------------+
|WiFi Client SSID           |MyBoat               |
+---------------------------+---------------------+
|WiFi Client Password       |MySecret             |
+---------------------------+---------------------+
|App-Installation           |AvNav                |
+---------------------------+---------------------+

Nachfolgend wird gezeigt, wie man Busdaten über ein Tablett in AvNav nutzen kann. Die Datenübertragung erfolgt über WiFi. Das Tablett tauscht dabei die Daten mit dem M5Stack über einen TCP-Verbindung aus. Dabei wird das Tablett als TCP-Client an die M5Stack CAN Unit angedockt. Eine TCP-Client-Verbindung wird unter AvNav als TCPReader-Verbindung eingerichtet.

.. image:: ../pics/Android_Start_Page.jpg
             :scale: 40%	
Abb.: Startseite AvNav für Android

Unter AvNav kicken Sie auf der Startseite oben rechts das Symbol mit den 3 Strichen.

.. image:: ../pics/AVnav_Server_Status_Icon.png

Sie gelangen dann auf die Seite zum Serverstatus. Dort können Sie über das Plus-Symbol weitere Verbindungen zum AvNavServer einrichten.

.. image:: ../pics/AVnav_Add_Icon.png

Für die bidirektionale Kommunikation über USB wählen Sie **TCPReader**.

.. image:: ../pics/Android_Select_Handler.jpg
             :scale: 40%	
Abb.: Verbindungstypen

Unter **IP-Address** tragen Sie die IP-Adresse desM5Stack ein und als **Port** die 10110. Um nicht nur Daten senden, sondern auch empfangen zu können, aktivieren Sie **SendOut**.

.. image:: ../pics/Android_Select_Handler_TCPReader.jpg
             :scale: 40%	
Abb.: Einstellungen zur TCPReader-Verbindung

Nach der Übernahme aller Daten ist die neue Verbindung im Server-Status als TCPReader-Verbindung zu sehen.

.. image:: ../pics/Android_Server_Status_2.jpg
             :scale: 40%	
Abb.: Server-Status
