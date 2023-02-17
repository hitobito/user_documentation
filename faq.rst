Fragen und Antworten
====================

Hitobito meldet, dass die IBAN Nummer ungültig ist
--------------------------------------------------

Falls als Einzahlungschein QR Rechnungen ausgewählt sind, muss eine spezielle QR-IBAN (https://www.moneytoday.ch/lexikon/qr-iban/) hinterlegt werden. Diese unterscheidet sich von der bestehenden IBAN Nummer.

Die Haupt-E-Mail kann nicht geändert werden
-------------------------------------------

Wenn ein Account beispielsweise bei einer Ortsgruppe und im Dachverband eine aktive Rolle hat, kann die **Haupt-E-Mail** nur von einer Person geändert werden, welche Schreibrechte in beiden Gruppen hat. Folgende Nachricht wird dann jeweils angezeigt: "Die Haupt-E-Mail Adresse einer Person mit mehreren Rollen kann nur von einem über alle diese Rollen übergeordneten Benutzer geändert werden"
Der Account selbst kann seine Haupt-E-Mail immer ändern.

Ein Beispiel: Ich bin in der Ortsgruppe Wabern und habe eher wenig Rechte im System. Ich kann aber in meiner Gruppe einen Admin zu meiner Gruppe hinzufügen, der auf dem Dachverband sehr viele Rechte hat. Dadurch erhalte ich Schreibrechte auf dieser Person. Ich könnte die primäre Mailadresse auf eine mir zugängliche Adresse ändern, ein Passwortreset auf dem User machen und mich anschliessend als Dachverbands-Admin einloggen. Um das Ganze zu vertuschen, könnte ich danach die Mailadresse wieder zurückändern. Aus diesem Grund ist das Ändern der primären Mailadresse nur zugelassen wenn ich die Berechtigung über alle Gruppen des Admins habe.


Geänderte Haupt-E-Mail muss bestätigt werden
--------------------------------------------

Wird die Haupt-E-Mail einer Person mit Login geändert, so wird ein Mail mit Bestätigungslink an die **neue** E-Mail-Adresse gesendet. So wird sichergestellt, dass die neue Adresse funktioniert und die Person hinter der E-Mail-Adresse mit der Verwendung einverstanden ist. Die Haupt-E-Mail von Personen ohne aktiviertem Login lassen sich sofort ändern.

Die Bestätigung ist wichtig, da Hitobito als OAuth Provider genutzt werden kann und viele OAuth Dienste die E-Mail zur Identifikation nutzen. Ohne Bestätigung würde folgendes Angriffsszenario funktionieren:

1. Eine Person A loggt sich via hitobito bei einem Drittservice ein
2. Der Drittservice merkt sich A anhand der Haupt-E-Mailadresse
3. Eine Person X mit Schreibzugriff auf A bearbeitet A und löscht die Haupt-E-Mailadresse
4. Person X füllt bei sich selber die ehemalige Haupt-E-Mailadresse von Person A ein. *Dieser Schritt wird durch die aktuelle E-Mail-Verifikation verhindert.*
5. Person X verwendet beim Drittservice den "Login via hitobito" und kann nun den dortigen Account von Person A übernehmen.


Mailadressen Export für Outlook
-------------------------------

Der Export "Mailadressen" gibt eine Liste aller Mailadressen getrennt durch Kommas aus. Outlook erkennt standardmässig die einzelnen Mailadressen nicht. Bei den meisten Mailprogrammen, ausser Outlook, funktioniert Komma als Trennzeichen. Outlook kann konfiguriert werden, dass auch Kommas funktionieren: https://www.officetooltips.com/outlook_365/tips/how_to_use_commas_as_separators_for_multiple_email_recipients.html

Wie werden Personen-Duplikate erkannt?
--------------------------------------

Wenn eine Person mehrfach erfasst wurde, dann kann man die Duplikate zusammenführen. Dazu gibt es auf dem "Personen"-Tab einer :doc:`Ebene</access_concept>` (z.B. Dachverband, Region, Ortsgruppe) einen Button "Duplikate". Der Button ist nur für Personen mit sehr hohen Berechtigungen (``layer_and_below_full`` oder ``admin``) sichtbar.

Hitobito analysiert jede Nacht die Einträge in der Datenbank und ergänzt die Liste von Duplikaten. Zwei Personen zählen als Duplikate, wenn die Felder Vorname, Nachname, Firmenname, Postleitzahl und Geburtsdatum übereinstimmen (bei Postleitzahl und Geburtsdatum zählt es auch, wenn das Feld bei einer der Personen leer ist). Ein Beispiel: Anna Berger (PLZ 1000, Geburtsdatum 01.01.1970) wird als Duplikat von Anna Berger (ohne PLZ oder Geburtsdatum) erkannt. Anna (PLZ 1000, Geburtsdatum 01.01.1970) ohne Nachname ist hingegen kein Duplikat, der Nachname muss zwingend übereinstimmen oder bei beiden Personen leer sein.

Dieselbe Duplikatserkennung wird auch schon direkt während dem Import einer CSV-Datei angewendet. Dort bekommt man gleich während dem Import noch die Möglichkeit, auszuwählen welche Zeilen eine bestehende Person aktualisieren sollen und welche Zeilen wirklich neue Personen sind.


Wann wird welche Referenznummer verwendet?
------------------------------------------

Hitobito unterstützt sowohl die QR-Referenz wie die Creditor Reference (SCOR). Die QR-Referenz entspricht im Aufbau der ESR-Referenz (immer 26 numerische Zeichen gefolgt von einer Prüfziffer nach Modulo 10 rekursiv) und kann vom Rechnungssteller als strukturierte Referenz verwendet werden. 
Creditor Reference ist gemäss ISO-11649-Standard implementiert. Die Prüfziffer der Creditor Reference muss mit Modulo 97-10 berechnet werden. Weitere Infos unter 
https://www.paymentstandards.ch/dam/downloads/ig-qr-bill-de.pdf 

Wenn keine QR-IBAN in Hitobito erfasst wurde, wird eine Creditor Reference (SCOR) bei der generierung von Rechnungen verwendet.

Was bedeutet Hitobito 人人
--------------------------

Hitobito kommt aus dem Japanischen und bedeutet Mensch. Durch die beiden 人人 ist die Mehrzahl gemeint: Menschen oder auch Gemeinschaft. Quelle: https://www.wordsense.eu/%E4%BA%BA%E4%BA%BA/
