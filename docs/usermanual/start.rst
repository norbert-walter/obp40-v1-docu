Inbetriebnahme
==============

Dieser Abschnitt hat die Erstinbetriebnahme Ihres OBP40 zum Inhalt. Das geht am einfachsten, wenn das Gerät noch nicht im Boot eingebaut ist. Dazu wird das Gerät mit Strom versorgt, um die ersten Einstellungen vorzunehmen. So können Sie die Funktionalität testen, bevor Sie das Gerät im Boot einbauen.

Schutzkonzept
-------------

Das OBP40 verfügt über ein mehrstufiges Schutzkonzept. Das soll verhindern, dass sich Störungen im Versorgungsnetz und auf den Datenleitungen im System ausbreiten. Damit wird sichergestellt, dass das OBP40 trotz Störungen nicht komplett ausfällt und in wichtigen Teilen weitestgehend funktionsfähig bleibt. Um dies zu erreichen, sind die Bussysteme:

* NMEA2000
* NMEA0182
* I2C

vom Bordnetz isoliert aufgebaut.

.. image:: ../pics/Safety_Concept.png
             :scale: 45%

Abb.: Sicherheitskonzept

Im OBP40 ist dazu eine zusätzliche 5V-Stromversorgung enthalten, die die isolierten Schaltungsteile versorgt. Die zusätzliche Stromversorgung hat die Ausgänge ``+5Viso`` und ``GND2``, die am Steckverbinder CN1 und CN2 anliegen. Über diese können auch externe Schaltungen bis 200 mA versorgt werden.

.. warning::
	Verbinden Sie die unterschiedlichen Massepotenziale ``GNDS``, ``GND``, ``GND2`` und ``Shield`` niemals miteinander! Dadurch geht die Isolations- und Schutzwirkung verloren. Die Massepotenziale dürfen nicht gleichberechtigt verwendet werden.
	
Die unterschiedlichen Massepotenziale haben folgende Bedeutung:

* ``GNDS`` - Masse der Versorgungsspannung
* ``GND`` - Interne Masse der Elektronik
* ``GND2`` - Masse der isolierten Bus-Elektronik
* ``Shield`` - Schutzleiter für die Kabelschirmung
	
Im folgenden Bild sind die geschützten und ungeschützten Anschlüsse zu sehen. 
	
.. image:: ../pics/Safe_Areas.png
             :scale: 45%

Abb.: Sichere und unsichere Bereiche

.. warning::
	Bitte beachten Sie, dass der 1Wire-Bus gegenüber Störungen nicht geschützt ist und entsprechend durch Schirmung geschützt werden muss. Daher sollten für die Leitungen des 1Wire-Bus nur abgeschirmte Kabel verwendet werden. ``GND`` darf mit keinen weiteren externen Schaltungsteilen verbunden werden, denn ``GND`` dient ausschließlich als Masseleitung für den 1Wire-Bus.

Stromversorgung 12V/24V
-----------------------

Die Stromversorgung des OBP40 erfolgt über den Steckverbinder CN2. Beim Zuschalten der Versorgungsspannung schaltet sich das OBP40 automatisch ein. Es gibt keinen gesonderten Ein- oder Ausschalter am Gerät. Benutzen Sie für die Stromversorgung die Anschlüsse ``+12V`` und ``GNDS``. Dabei wird ``+12V`` mit dem positiven Pol der Batterie verbunden und ``GNDS`` mit dem negativen Pol. Diese Anschlüsse für die Stromversorgung sind:

* verpolungssicher
* kurzschlussfest
* überspannungssicher
* ESD-geschützt

Der zulässige Spannungsbereich liegt zwischen 10V...28V.

.. image:: ../pics/Power_Connection.png
             :scale: 80%
Abb.: Stromversorgung

Das OBP40 kann in 12V- und in 24V-Bord-Versorgungsnetzen verwendet werden. Bei Spannungen höher als 28V wird die interne Sicherung im Gerät ausgelöst.

In einigen Situationen ist es günstiger, die Stromversorgung direkt über den NMEA2000-Bus vorzunehmen. Dann entfällt die Verkabelung der Stromversorgung zu einer Schalttafel. Nähere Details dazu finden Sie im Kapitel  :ref:`Bussysteme`.

.. note::
	Im Gerät ist eine selbst rückstellende Sicherung verbaut, die bei zu hohem Stromverbrauch die Versorgungsspannung selbständig trennt. Sie können die Sicherung zurücksetzen, indem Sie die Stromversorgung zum OBP40 trennen und den Grund des übermäßigen Stromverbrauchs beseitigen. Danach warten Sie einige Minuten und schalten dann die Versorgungsspannung wieder ein.

.. important::
	Die interne Sicherung im OBP40 schützt nur das Gerät und nicht die Versorgungsleitungen! Daher sollte die bereitgestellte Stromversorgung des OBP40 im Bordnetz mit einer zusätzlichen Sicherung von mindestens 5A abgesichert werden. Das erfolgt typischerweise über die Schalttafel, über die die Stromkreise im Boot geschaltet werden können. So vermeiden Sie Brände zum Beispiel durch aufgescheuerte oder überhitzte Versorgungsleitungen.
	
Stromversorgung USB-C
---------------------

Das OBP40 kann auch über USB-C mit Strom versorgt werden. Der USB-Anschluss muss aber ausreichend Spannung von 5.1V und Strom bis 500 mA liefern können. Der USB-Anschluss am OBP40 verfügt über einen Rücklaufschutz, so dass gleichzeitig 12V/24V und 5V über den USB-Port eingespeist werden können. 

.. note::
	Viele USB-Computeranschlüsse verfügen nicht über einen ausreichend hohen Ausgangsstrom und teilen sich den Strom mit mehreren Anschlüssen. Das kann dazu führen, dass das OBP40 nicht direkt von einem PC aus mit Strom versorgt werden kann. Auch die Kabelqualität und Kabellänge ist entscheidend. Einige Kabel haben zu geringe Querschnitte und erzeugen einen hohen Spannungsabfall auf den Leitungen. Die Spannung ist dann am USB-C-Ausgang zu gering. Benutzen Sie in solchen Fällen den zusätzlichen 12V-Eingang an **CN2** zur Stromversorgung. 

Einbau
------

Der Einbau des OBP40 erfolgt über die Rückseite. Zum Anzeichnen der Öffnung und der Löcher in der Cockpitwand kann die Moosgummidichtung als Schablone benutzt werden. Vor der Montage des OBP40 ist die Rückseite abzunehmen. Die 2 Sechskantschrauben werden in die dafür vorgesehenen Vertiefungen eingeführt und gegen Herausfallen gesichert. Prüfen Sie vor dem Einbau, ob die Länge der M5x25 Schrauben ausreichend ist. Gegebenenfalls ersetzen Sie die Schrauben in passiger Länge. 

.. warning::
	Die Köpfe der Sechskantschrauben sollten in den Vertiefungen eingeklebt werden, damit sie beim Einbau nicht in das Gehäuseinnere geschoben werden und dort einen Kurzschluss auf der Platine verursachen können.
	
Danach wird das Gehäuse wieder vollständig zusammen gebaut.

Vor der Montage wird zwischen Rückseite und Cockpitwand eine 2 mm dicke Moosgummidichtung platziert. Die Moosgummidichtung kann Unebenheiten der Oberfläche in gewissen Grenzen ausgleichen. Mit den Unterlegscheiben und den Muttern befestigt man das OBP40.

.. warning::
	Ziehen Sie die Muttern nicht zu fest an. Die Verdrehsicherung oder die Rückwand können beschädigt werden.

.. image:: ../pics/Mounting_OBP40.png
             :scale: 50%
Abb.: Geräteeinbau in Cockpitwand

.. hint::
	Die GPS-Antenne des GPS-Empfängers befindet sich links oben in der Ecke auf der Rückseite des OBP40 (von hinten gesehen). Hinter der Anbaufläche sollten sich keine großflächigen Metallteile befinden. Die Metallteile können den GPS-Empfang stören oder unmöglich machen. Wenn Sie Empfangsprobleme haben, können Sie eine externe GPS-Antenne benutzt.   
