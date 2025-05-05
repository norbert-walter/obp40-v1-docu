Web-Flashtool
=============

Mit dem Web-Flashtool kann die Firmware für das OBP40 mit einem Webbrowser über eine USB-Verbindung in das Gerät übertragen werden. Dazu wird das OBP40 über die USB-C-Buchse mit einem PC oder Laptop verbunden und der **Chrome-** oder **Edge-Webbrowser** gestartet. Im OBP40 ist ein USB-Seriell-Konverter integriert, über den die Datenübertragung durchgeführt wird. Mit dem USB-C-Kabel lässt sich nur die Firmware übertragen.

.. note::
	Andere Webbrowser als **Chrome** oder **Edge** werden derzeit nicht unterstützt, da die Funktionalität für den Zugriff auf eine serielle Schnittstelle in anderen Webbrowsern nicht implementiert ist.
	
.. warning::
	Beachten Sie, dass das Web-Flashtool nur für ein OBP40 V1 verwendet werden kann, das als Prozessor einen **ESP32-S3 N8R8** und als E-Paper-Display ein **GDEY042T81** verwenden. Sofern Sie andere Hardware benutzen, müssen Sie sich eine angepasste Firmwareversion für ihre Hardware kompilieren. Folgen Sie den Anweisungen im Kapitel :ref:`Kompilieren und Download`.  
	
Für den Flash-Vorgang benötigt man folgende Dinge:
	* OBP40 (ESP32-S3 N8R8, E-Paper GDEY042T81)
	* USB-C zu USB-A Verbindungskabel < 1,5m
	* PC mit Chrome- oder Edge-Browser

**1. OBP40 in den Flash-Modus setzen**
	Als erstes stecken Sie das USB-Kabel in den PC, ohne es mit dem OBP40 zu verbinden. Danach öffnen Sie die Rückseite des OBP40. Auf der Platine befindet sich oben rechts ein Taster mit der Bezeichnung ``BOOT``. Drücken Sie die Taste ``BOOT``. Halten Sie die Taste gedrückt und stecken dann den USB-Stecker an die Platine. Danach können Sie die Taste ``BOOT`` loslassen.
	
	.. image:: ../pics/CrowPanel_4.2_ESP32_HMI_E-paper_Display.png
   :scale: 50%   
	Abb.: Platinen-Anschlussbelegung

	
	
**2. Flashtool starten**

	Rufen Sie als nächstes die Webseite des `Online-Flashtools`_ auf.

	.. _Online-Flashtools: https://norbert-walter.github.io/obp40-v1-docu/flash_tool/esp_flash_tool.html

	.. image:: ../pics/Web_Flasher1.png
	   :scale: 50%
	Abb.: Startseite Web-Flashtool

	Drücken Sie dann auf **Connect** und wählen die entsprechende serielle Schnittstelle aus. Je nachdem, welches Betriebssystem Sie verwenden, sind die Schnittstellen verschieden bezeichnet.

	* **Windows:** USB JTAG/serial debug unit COMx
	* **Linux:** /dev/ttyACMx

	.. image:: ../pics/Serial_Connection_Win.png
	   :scale: 50%
	Abb.: Auswahl der Schnittstelle

.. note::
	Beachten Sie, dass durchaus noch andere serielle Schnittstellen im System benutzt werden. Wählen Sie die Schnittstelle aus, die nach dem Anstecken des OBP40 an den USB-Port im System neu auftaucht. Bereits bestehende Schnittstellen dürfen Sie nicht nutzen, sie werden bereits anderweitig verwendet.
	
**3. Firmware übertragen**
	.. image:: ../pics/Web_Flasher2.png
	   :scale: 50%
	Abb.: Start Flashvorgang
	
	Starten Sie den Installationsvorgang über ``INSTALL OBP40 V2 FIRMWARE``. Nach erfolgreicher Übertragung wird eine Meldung ausgeben.
	
	.. image:: ../pics/Web_Flasher3.png
	   :scale: 50%
	Abb.: Übertragung der Firmware
	
	
**4. OBP40 starten**
	Entfernen Sie das USB-Verbindungskabel zurzzeitig von der Platine und stecken es wieder an. Nach kurzer Zeit sollte eine Anzeigeseite zu sehen sein. Je nach Einstellung wird vorher noch das OBP-Logo und der QR-Code für den WiFi-Zugang angezeigt.
	
	.. image:: ../pics/OBP40_Screen_2_t.png
             :scale: 55%
	Abb.: Anzeigeseite