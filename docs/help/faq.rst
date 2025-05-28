Fragen und Antworten
====================

**Warum flackert der Bildschirm in regelmäßigen Abständen?**

	Das Flackern des Bildschirmes dienst zum Auffrischen des Bildschirminhaltes. In regelmäßigen Abständen muss das Display den Bildschirminhalt durch einen Voll-Refresh komplett erneuern, um Geisterbilder zu entfernen und den Kontrast aufzufrischen. Dazu wird der Bildinhalt invertiert, mehrmals gelöscht und wieder vollständig aufgebaut.
	
**Ich habe zwei CrowPanel 4.2 für mein OBP40. Warum flackert der Bildschirm des einen Displays anders als beim anderen?**

	Elecrow verkauft die CrowPanel 4.2 mit ePaper-Displays in zwei Versionen. Das Display der neueren Version hat ein Display verbaut, dass eine sehr schnelle Refresh-Abfolge verwendet. Das Display ist nicht defekt. Es verhält sich nur anders als das Display der ersten Version. Das Verhalten der Refresh-Abfolge kann nicht durch Software geändert werden, da die Funktion fest im Display-Controller verbaut ist. Leider werden die Displays unter der selben Bestellnummer vertrieben und man kann bei der Bestellung nicht herausfinden welches Display man erhält. Wenn das Refresh-Verhalten störend ist, kann es nur durch Austausch des Displays gegen die erste Version beseitigt werden. Besorgen Sie sich dann ein Display des Typs **GDEY042T81** von Good Display. Der Austausch des ePaper-Displays ist nicht ganz einfach, da das Display direkt auf die Platine geklebt ist. Damit das Display einfacher von der Platine abgelöst werden kann, legen Sie vor der Demontage das CrowPanel 4.2 für 20 min bei 70°C in den Backofen. Dadurch wird der Kleber weich und das Display lässt sich besser ablösen. Entfernen Sie danach alle Kleberreste und kleben Sie das neue Display mit einem neuen doppelseitigen Klebeband wieder an.

**Wie kann ich das flackern des Bildschirms reduzieren?**

	Die Zeitpunkt eines Voll-Refreshes hängt von einigen Faktoren ab. In den ersten 5 Minuten nach einem Neustart des Gerätes erfolgt jede Minute ein Voll-Refresh, um eine Temperaturanpassung des Displays aus einem kalten Zustand heraus zu ermöglichen. Nach jedem Seitenwechsel wird ebenfalls ein Voll-Refresh ausgeführt. Das gilt für die Seite die zu letzt aufgerufen wurde und die mindestens 4s lang angezeigt wird. Dieses Verhalten bei Seitenwechsel lässt sich über den Parameter **Refresh** abstellen. Das ist aber mit dem Nachteil verbunden, dass sich Geisterbilder alter Seiten nicht vollständig entfernen lassen. Zusätzlich lässt sich festlegen in welchen Intervallen ein Voll-Refresh generell ausgeführt wird. Die Zykluszeit kann im Bereich von 1...10 min über den Parameter **Full Refresh Time** eingestellt werden. Der Voll-Refresh lässt sich zusätzlich über den Parameter **Fast Refresh** beschleunigen. Dann laufen die Voll-Refreshes schneller ab. Die Beschreibungen zu den Refresh-Einstellungen finden Sie im Kapitel :ref:`Config - OBP Display`. Die Einstellungen zum Bildschirm-Refresh haben auch Auswirkungen auf den Bildschirmkontrast unter Sonneneinwirkung.

**Warum verblasst das Display unter Sonneneinwirkung?**

	Bei extremer Sonneneinwirkung erhitzt sich das e-Paper-Display auf und verursacht einen Kontrastverlust bei der partiellen Bildschirmaktualisierung. Das Bild wird zunehmend grau und es entstehen einige Streifen im Display. Das Display ist nicht defekt. Der Zustand lässt sich durch einen Voll-Refresh beseitigen.

**Was kann man dagegen tun?**

	Der Effekt kann reduziert werden, indem direkte Sonnenstrahlung auf das Display vermieden wird. Eine andere Möglichkeit zur Verbesserung besteht darin, die Voll-Refreshes in kürzeren Zyklen ausführen zu lassen. Im Kapitel :ref:`Config - OBP Display` finden Sie eine Tabelle zu sinnvollen Einstellungen unter verschiedenen Bedingungen. Auch der Stromverbrauch des Gerätes hat einen Einfluss auf den Kontrastverlust, da die Verlustwärme im Gerät ebenfalls zur Temperaturerhöhung beiträgt.

**Welche Möglichkeiten bestehen den Stromverbrauch zu reduzieren?**

	Der Stromverbrauch lässt sich reduzieren, indem der Access Point standardmäßig nach einer vorgegebenen Zeit abgeschaltet wird. Zusätzlich kann der Prozessortakt reduziert werden. Einige Geräte wie das OBP60 verfügen über spezielle Stromsparfunktionen über den Parameter **Power Mode**. Details zu Stromsparfunktionen finden Sie im Kapitel :ref:`Config - OBP Hardware`.

**Warum funktionieren WiFi-Verbindungen nicht richtig?**

	WiFi-Verbindungen sind auf das 2,4 GHz Frequenzband begrenzt. Andere Teilnehmer außerhalb des eigenen Access Point nutzen das selbe Frequenzband und müssen sich die Bandbreite mit anderen Teilnehmern teilen. In größeren Häfen kann es dazu kommen, dass die Bandbreite aller Kanäle durch zu viele Teilnehmer ausgelastet ist. In diesem Fall kommt es zu Verzögerungen bei der Datenübertragung. Sie müssen dann mit einem trägen Ansprechverhalten der Messdaten im Display rechnen, wenn die Daten über WiFi-Verbindungen übertragen werden. Leitungsgebundene Datenübertragungen aus Bussystemen wie NMEA2000 oder NMEA0183 sind davon nicht betroffen. Etwas Abhilfe kann die Auswahl der Übertagungskanäle Kanäle 1 und 13 bewirken, da sie sich an den Rändern des 2,4 GHz Frequenzbereiches befinden und nur einen Nachbarkanal haben.
	
	.. image:: ../pics/WiFi_Channels.png
             :scale: 35%