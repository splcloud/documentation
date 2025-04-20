---
title: "Quick start guide SPL Sense"
linkTitle: "Quick start guide SPL Sense"
weight: 100
description: >-
     Kurzanleitung SPL Sense
---

## Überblick Dashboard
![Dashboard](Dashboard.png) <br>
•	**Logo in der linken oberen Ecke:** Klickt man auf das Logo, gelangt man zurück zum Dashboard.<br>
•	**Statusanzeige (rechts oben):** Zeigt den aktuellen Status an (keine Messung geladen / Messung gestoppt / Messung läuft).<br>
•	**Einstellungen (Zahnradsymbol rechts oben):** Öffnet die Einstellungen.<br>
•	**Neue Messung erstellen:** Klicken Sie auf den «+»-Knopf neben "Gespeicherte Messungen", um eine neue Messung zu erstellen.<br>
•	**Verbundenen Sensor anzeigen:** Auf der rechten Seite wird der verbundene Messsensor angezeigt. Ein Klick darauf zeigt den detaillierten Status des Sensors.<br>
## Sensor-Status / Einstellungen
![Sensorübersicht](Sensor.png) <br>
Im Sensor-Detailbildschirm kannst du die Kompensation für den Wetterschutz aktivieren. Ist diese Option aktiv, wird der Wetterschutz durch einen FIR-Filter im Sensor kompensiert.<br>
## Verbindung zur SPL Cloud (optional)
Jedes SPL Sense kann mit der SPL Cloud verbunden werden, um Daten in Echtzeit einzusehen und zu speichern.<br>
1.	**Einstellungen öffnen:** Klicke auf das Zahnradsymbol oben rechts.<br>
![Übersicht Einstellungen](Einstellungen.png) <br>
2.	**Cloud auswählen:** Wähle die Option "Cloud".<br>
![Cloud Verbindung](ConnectCloud.png) <br>
3.	**Verbindung herstellen:** Klicke auf den Link oder scanne den QR-Code. (Das SPL Sense muss mit dem Internet verbunden sein, und ein persönlicher Zugang zur SPL Cloud muss erstellt werden.)
Nach Abschluss der Schritte ist das SPL Sense mit der SPL Cloud verbunden.<br>
![Cloud verbunden](ConnectCloudCloudstatus.png) <br>
## Messung erstellen
1.	**Neue Messung erstellen:** Klicke auf den «+»-Knopf neben „Gespeicherte Messungen“.<br>
2.	**Name eingeben:** Gebe einen Namen für die Messung ein. Dieser Name wird später als Überschrift der Messung angezeigt.<br>
3.	**Tagesgrenze festlegen:** Stelle die Tagesgrenze ein. Diese kann von Mitternacht bis 06:00 Uhr am Morgen verschoben werden. So wird z. B. ein Konzert oder eine Party in einer Tagesübersicht angezeigt und nicht durch den Tageswechsel auf zwei Tage verteilt. Wir empfehlen, die Grenze etwa 2 Stunden nach dem erwarteten Ende des Events zu setzen.<br>
4.	**Cloud-Uplink aktivieren:** Aktiviere den Cloud-Uplink, um diese Messung in die Cloud zu übertragen. Diese Option ist nur verfügbar, wenn das SPL Sense mit der SPL Cloud verbunden ist. Wenn keine Verbindung besteht, wird dies entsprechend angezeigt.<br>
![Cloud Uplink](CloudUplink.png) <br>
5.	**Werteprofil auswählen:** Wähle ein Werteprofil, das definiert, welche Werte mit welchen Filtern (A/C/Z) und welchen Integrationszeiten aufgezeichnet werden. Zudem können Grenzwerte für drei verschiedene Stufen (Benachrichtigung, Warnung, Limit) eingestellt werden. Das Ereignisprotokoll wird entsprechend diesen Stufen sortiert. Neben den vorgespeicherten Profilen, die sich an der V-NISSG orientieren, können auch eigene Profile erstellt werden.<br>
![Werteprofil auswählen](NeueMessungWerteprofil.png) <br>
6.	**Messung speichern:** Speicher die Messung.<br>
![Messung auf dem Dashbard mit Cloud](MessungAngelegtMitCloud.png) <br>
Nach dem Speichern erscheint die Messung auf dem Dashboard. Eine Wolke neben der Messungsüberschrift zeigt an, ob die Messung in die SPL Cloud übertragen wird.<br>
## Messung öffnen und bearbeiten
1.	**Messung öffnen:** Klicke im Dashboard auf die gewünschte Messung, um sie zu öffnen.<br>
![Messung Übersicht](MessungDetailsOhneDaten.png) <br>
2.	**Messung aktivieren:** Aktiviere die Messung mit dem Knopf auf der rechten Seite. Beachte, dass immer nur eine Messung gleichzeitig aktiv sein kann.<br>
![Akitiverte Messung](MessungAktiviert.png) <br>
3.	**Grundeinstellungen anpassen:** Unter „Messung bearbeiten“ auf der rechten Seite können die Grundeinstellungen der Messung angepasst werden. Zusätzlich zu den bereits erwähnten Parametern können hier auch Offsets eingestellt und ein PIN für das Verlassen des Livescreens eingetragen werden. Außerdem besteht die Möglichkeit, die Messung dauerhaft mit allen Daten vom Rechner zu löschen.<br>
![Messung Bearbeiten](MessungBearbeiten.png) <br>
## Offset tune
Der Offset kann mithilfe der Funktion „Offset tune“ auf der rechten Seite festgelegt werden. Alle Messwerte, die während dieses Prozesses erfasst werden, werden nicht in die Messung gespeichert. Wir empfehlen, den Offset (die Pegeldifferenz zwischen dem lautesten Punkt und dem Standort des Sensors während der Messung) mit einem Testsignal, z. B. Pink Noise, einzustellen. Gehe dazu wie folgt vor:<br>
![Offset tune](Offsettune.png) <br>
1.	**Pink Noise abspielen:** Verwende eine Lautstärke, die während des Konzerts oder der Veranstaltung zu erwarten ist.<br>
2.	**Maximalwert zurücksetzen:** Drücke den Knopf „Max zurücksetzen“.<br>
3.	**Publikumsfläche ablaufen:** Bewege dich mit dem Rechner und dem Sensor durch die Publikumsfläche.<br>
4.	**Sensor platzieren:** Stelle den Sensor an der vorgesehenen Messposition auf.<br>
5.	**Offset anpassen:** Justiere den Offsetwert so, dass der „Level inkl. Offset“ dem „Max inkl. Offset“ entspricht.<br>
6.	**Einstellungen speichern:** Speicher die vorgenommenen Anpassungen.<br>
Alternativ kann der Differenzpegel auch mit einem zusätzlichen Handmessgerät ermittelt werden. Weitere Informationen zum Thema Sensorstandort und Offset findest du unter folgendem Link: [Branchenempfehlung für das Messverfahren](https://www.bag.admin.ch/dam/bag/de/dokumente/str/schall/emfehlungen_messverfahren.pdf.download.pdf/Branchenempfehlung%20Messverfahren%20DE.pdf) <br>
## Leveler Plugin für den Audioprozessor
Das Plugin für den Audioprozessor kann auf der Website unter „SPL Sense Leveler“ heruntergeladen werden. Nach dem Einfügen in das Audioprozessor-Design müssen im Plugin die IP-Adresse des Rechners, auf dem SPL Sense läuft, sowie Port und API-Key eingegeben werden. Wenn die Eingaben korrekt sind, zeigt das Plugin den aktuellen Zustand und die Messwerte aus SPL Sense an. Im SPL Sense muss unter „Einstellungen“ - „API“ der Modus „Nur externer Leveler“ oder „Vollzugriff“ aktiviert werden. Der API-Key kann ebenfalls eingestellt werden.<br>
**Wichtig:** Für einen funktionierenden Leveler mit Publikumserkennung dürfen nach dem Einmessen keine Linepegelanpassungen zwischen dem Plugin und dem Lautsprecher vorgenommen werden. Audiokompressoren oder ähnliche Komponenten dürfen in diesem Signalabschnitt nicht angewendet werden.<br>
## Leveler Einstellungen
Entscheidend für ein gutes Leveler-Ergebnis ist eine gute Sensorposition sowie korrekt eingestellte Offsets für die A-, C- und Z-Werte. Eine gute Sensorposition bedeutet, dass der Schalldruckpegel vom Mittel-/Hochtonlautsprecher sowie vom Basslautsprecher in einem natürlichen Verhältnis stehen. Die eingestellten Offsets sollten generell zwischen -10 dB und +2 dB liegen.<br>
![Leveler Einstellungen](LevelerEinstellungen.png) <br>
1.	**Leveler Einstellungen öffnen:** Öffne das Einstellungsfeld für den Leveler. Dies ist während einer laufenden oder gestoppten Messung möglich. Um die Grundeinstellungen vorzunehmen, sollte die Messung gestoppt sein.<br>
2.	**Leveler Modus auswählen:** Wähle zwischen „Aus“ (Leveler inaktiv), „Einfacher Leveler“ (Leveler regelt immer langsam – das Publikum wird nicht berücksichtigt), „Leveler mit Panikfunktion“ (bei einem schnellen Schalldruckpegelanstieg, der zu einer Überschreitung führt, regelt der Leveler schnell zurück – das Publikum wird nicht berücksichtigt) sowie „Leveler mit Panikfunktion und Publikumskompensation“ (bei einem schnellen Schalldruckpegelanstieg, der zu einer Überschreitung führt, regelt der Leveler schnell zurück – das Publikum oder andere externe Geräuschquellen werden berücksichtigt und herausgerechnet).<br>
3.	**Limit Werte einstellen:** Trage die gewünschten Limiten ein. Der Leveler kann gleichzeitig eine Limite für die Gewichtungen A, C und Z berücksichtigen. Die Limiten können jederzeit auch während der laufenden Messung angepasst werden.
**Schritt 4 und 5 sind nur für den Modus mit Publikumskompensation notwendig.** <br>
![Leveler Einstellungen Einmessvorgang](LevelerEinstellungenEinmessvorgang.png) <br>
4.	**Pinknoise einspielen:** Spiele Pinknoise als Audioquelle mit dem zu erwartenden Pegel ein. Verwende dabei die effektive Signalkette. Das heißt, wenn ein DJ-Pult die Quelle ist, speise einen Pinknoise-Generator am DJ ein. Wenn während der Party eine Limite von 96 dB gilt, messe auch mit 96 dB.<br>
5.	**Line Offset messen:** Drücke den „Line Offset messen“-Button. Das System ermittelt nun während 3 Sekunden den Line Offset. Dabei wird das Verhältnis zwischen dem Line Level und dem Schalldruckpegel ermittelt. Während dieser kurzen Zeit darf es keine Störgeräusche geben. Der Prozess kann beliebig oft wiederholt werden. Sobald die Messung erfolgt ist, sollte der Korrelationswert bei den Gewichtungen A, C und Z möglichst genau 1.000 betragen.<br>
6.	**Speichern:** Bestätige die Einstellungen mit „Speichern“.<br>
Während einer laufenden Messung können die Limiten sowie der Line Offset manuell angepasst werden. Der automatische Einmessvorgang ist nur möglich, wenn die Messung gestoppt ist. Die Korrelation zeigt an, ob die Einstellung korrekt ist. Wenn kein Fremdlärm vorhanden ist, sollte der Wert möglichst exakt bei 1 liegen. Bei einer manuellen Korrektur ist äußerste Vorsicht geboten. Schon eine geringe Fehleinstellung kann dazu führen, dass der Leveler Fremdlärm ignoriert oder zu stark eingreift.<br>
Bei korrekt eingestellten Line Offsets weisen Korrelationswerte kleiner 1 auf einen abgedämpften Sensor oder auf eine Manipulation am Lautsprechersystem hin. Korrelationswerte größer 1 weisen auf Fremdlärm hin.
## Messung starten
1.	**Messung starten:** Starte die Messung über die Schaltfläche auf der rechten Seite.<br>
![übersicht laufende Messung](Messunglaeuft.png) <br>
2.	**Aktuelle Lautstärke anzeigen:** Die aktuelle Lautstärke wird ebenfalls auf der rechten Seite angezeigt.<br>
3.   **Aktuelle Leveler Anzeige:** Wenn der Leveler aktiv ist, wird während einer laufenden Messung die aktuelle Pegelreduktion sowie die SPL Line Korrelationen angezeigt. Der fett geschriebene und mit einem „>“ markierte Wert weist dabei auf die momentan für den Leveler relevante Gewichtung hin. Wenn zum Beispiel der A-Korrelationswert markiert ist, ist zu diesem Zeitpunkt die Limite von der A-Gewichtung für die Pegelreduktion dominant.<br>
4.   **Leveler Überbrücken:** Mit dem „Leveler bypassen“ kann der Leveler jederzeit überbrückt werden. Hier ist die aktuelle Pegelreduktion zu beachten. Wenn zum Beispiel aktuell eine Pegelreduktion von 15 dB erfolgt, wird die Lautstärke beim Aktivieren des Bypass-Knopfes um 15 dB ansteigen.<br>
5.	**Lautstärkenverlauf verfolgen:** Eine Grafik dokumentiert den Verlauf der Lautstärke im Zeitverlauf. Wenn Du in die Grafik klickst, werden zusätzliche Details wie Spektraldaten sowie das Unterschreiten oder Überschreiten des Messbereichs angezeigt.<br>
6.   **Levelerverlauf verfolgen:** In der laufenden Messübersicht wird nebst dem Schalldruckpegel auch der Verlauf des Line Signalpegels (hellbraun) sowie die Pegelreduktion (rot) angezeigt. Auch die Korrelation ist ersichtlich. Neben dem Minutenmittel der Pegelreduktion und der Korrelation werden auch die Minimal- und Maximalwerte, respektive die Streuung visualisiert.<br>
7.	**Cloud-Verbindungsstatus:** Der Verbindungsstatus zur Cloud wird auf der rechten Seite angezeigt.<br>
8.	**Überschreitungen anzeigen:** Unter „Überschreitungen“ werden Pegelüberschreitungen gemäß den im Werteprofil definierten Gewichtungen und Integrationszeiten aufgelistet. Durch Anklicken der einzelnen Kategorien werden in der Grafik die definierten Stufengrenzwerte als gelbe, orange und rote Linien angezeigt.<br>
9.	**Ereignisprotokoll:** Im Feld „Ereignisse“ auf der rechten Seite werden Aktionen wie Starten und Stoppen der Messung sowie Anpassungen am Offset oder Anpassungen und Ereignisse des Levelers mit der jeweiligen Zeit aufgelistet.<br>
10.	**Live-Ansicht aufrufen:** Durch Klicken auf „Live Ansicht“ auf der rechten Seite wird die Liveansicht angezeigt.<br>
![Liveansicht](LiveScreen.png) <br>
11.	**Liveansichten umschalten:** Oben rechts kannst Du zwischen verschiedenen Liveansichten umschalten. Es können auch eigene Live Ansichten erstellt werden. Die Liveansicht bietet eine übersichtliche Darstellung der gewünschten Messwerte während des Events und ist besonders hilfreich für Techniker oder DJs. <br>
12.	**Zurück zur Messungsübersicht:** Um zur Messübersicht zurückzukehren, klickst Du auf „Zurück zur Messung“. Wenn ein PIN für das Verlassen der Live-Ansicht unter „Messung bearbeiten“ festgelegt wurde, wird dieser nun abgefragt, um sicherzustellen, dass nur berechtigte Personen die Einstellungen in der Messung ändern können.<br>
