Fragen und Antworten
==============================================

Hitobito meldet, dass die IBAN Nummer ungültig ist
-------------------------------------------------------

Falls als Einzahlungschein QR Rechnungen ausgewählt sind, muss eine spezielle QR-IBAN (https://www.moneytoday.ch/lexikon/qr-iban/) hinterlegt werden. Diese unterscheidet sich von der bestehenden IBAN Nummer.

Die Haupt-E-Mail kann nicht geändert werden
--------------

Wenn Personen beispielsweise bei einer Ortsgruppe und im Dachverband eine aktive Rolle hat, kann die **Hauptmailadresse** nur von einer Person geändert werden, welche Schreibrechte in beiden Gruppen hat. Folgende Nachricht wird dann jeweils angezeigt: "Die Haupt-E-Mail Adresse einer Person mit mehreren Rollen kann nur von einem über alle diese Rollen übergeordneten Benutzer geändert werden"

Ein Beispiel: Ich bin in der Ortsgruppe Wabern und habe eher wenig Rechte im System. Ich kann aber in meiner Gruppe einen Admin zu meiner Gruppe hinzufügen, der auf dem Dachverband sehr viele Rechte hat. Dadurch erhalte ich Schreibrechte auf dieser Person. Ich könnte die primäre Mailadresse auf eine mir zugängliche Adresse ändern, ein Passwortreset auf dem User machen und mich anschliessend als Dachverbands-Admin einloggen. Um das Ganze zu vertuschen, könnte ich danach die Mailadresse wieder zurückändern. Aus diesem Grund ist das Ändern der primären Mailadresse nur zugelassen wenn ich die Berechtigung über alle Gruppen des Admins habe.

Mailadressen Export für Outlook
--------------

Der Export "Mailadressen" gibt eine Liste aller Mailadressen getrennt durch Kommas aus. Outlook erkennt standardmässig die einzelnen Mailadressen nicht. Bei den meisten Mailprogrammen, ausser Outlook, funktioniert Komma als Trennzeichen. Outlook kann konfiguriert werden, dass auch Kommas funktionieren: https://www.officetooltips.com/outlook_365/tips/how_to_use_commas_as_separators_for_multiple_email_recipients.html

Wann wird welche Referenznummer verwendet
-------

Hitobito unterstützt sowohl die QR-Referenz wie die Creditor Reference (SCOR). Die QR-Referenz entspricht im Aufbau der ESR-Referenz (immer 26 numerische Zeichen gefolgt von einer Prüfziffer nach Modulo 10 rekursiv) und kann vom Rechnungssteller als strukturierte Referenz verwendet werden. 
Creditor Reference ist gemäss ISO-11649-Standard implementiert. Die Prüfziffer der Creditor Reference muss mit Modulo 97-10 berechnet werden. Weitere Infos unter 
https://www.paymentstandards.ch/dam/downloads/ig-qr-bill-de.pdf 

Wenn keine QR-IBAN in Hitobito erfasst wurde, wird eine Creditor Reference (SCOR) bei der generierung von Rechnungen verwendet.

Was bedeutet Hitobito 人人
--------------------------

Hitobito kommt aus dem Japanischen und bedeutet Mensch. Durch die beiden 人人 ist die Mehrzahl gemeint: Menschen oder auch Gemeinschaft. Quelle: https://www.wordsense.eu/%E4%BA%BA%E4%BA%BA/
