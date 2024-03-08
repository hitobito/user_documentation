# EBICS Schnittstelle

## Allgemeines

Hitobito lässt sich mit einem Bank- oder Postkonto verbinden. Dies bedeutet folgendes:

Wird eine Zahlung über hitobito ausgelöst und vom Empfänger bezahlt, ist diese Information nicht mehr nur
im Bankkonto ersichtlich, sondern wird auch im hitobito ausgewiesen. Hitobito kann so die Buchhaltung
unterstützen, da damit die Zahlungseingänge zentral und personifiziert überwacht werden können.

Als Schnittstelle verwendet hitobito die Technologie EBICS. EBICS ist eine standardisierte Schnittstelle zu
Finanzapplikationen und wird in der Schweiz von beinahe allen Banken angeboten (Ausnahmen sind
möglich, uns aber nicht bekannt). Mehr Informationen zu EBICS findet ihr auf den Webseiten der
verschiedenen Banken.

Über die [EBICS Schnittstelle](https://www.six-group.com/de/products-services/banking-services/payment-standardization/standards/ebics.html) können camt054 Dateien regelmässig von einem Finanzinstitut bezogen werden. Mittels Referenznummer werden die Zahlungen einer Rechnung von der Ebene zugewiesen. Zahlungen die keiner Rechnung zugewiesen werden können, werden ignoriert

In den Rechnungseinstellungen kann pro Ebene die EBICS Schnittstelle definiert werden. Zugangsdaten werden verschlüsselt in Hitobito abgelegt.

## Wir richte ich die Schnittstelle ein?

1. Über die eigene Bank/Post muss ein EBICS Vertrag angefordert werden.
   : 1. Der Vertrag regelt, welche Konten mit hitobito verknüpft werden. Es können mehrere Konten gleichzeitig über EBICS mit hitobito verknüpft werden.
     2. Im Vertrag muss EBICS als Schnittstelle ausgewählt werden, falls Euch der Vertrag mehrere Optionen gibt.
     3. Im Vertrag muss eine Software angegeben werde, damit ist hitobito gemeint. Angegeben werden soll als Software «hitobito» und als Hersteller «Puzzle ITC»
     4. Die Buchungsart ist Sammelbuchung, die Periodizität ist Euch selbst überlassen.
2. Der Vertrag wird der Bank/Post zurückgeschickt. Von Seiten der Bank/Post wird nun ein Dokument mit der Vertrags-ID und der Kunden-ID für EBICS erstellt und Euch zur Verfügung gestellt. (Die genaue Bezeichnung kann variieren und auch als Teilnehmer-ID / Partner-ID o.Ä. bezeichnet sein.)
3. Mit diesem Dokument der Bank/Post könnt Ihr in hitobito unter den Rechnungseinstellungen->Zahlungsschnittstellen die Vertrags-ID und die Kunden-ID eingeben. Sobald dies gemacht ist, erscheint in Hitobito ein Button zur generierung des Initialisierungs-Dokuments (INI-Brief).
4. Dieses Dokument muss dem Bankinstitut unterschrieben zurückgeschickt werden, damit die Verbindung zwischen Konto und hitobito erstellt werden kann.
5. Die Bank informiert Euch, sobald die Schnittstelle eingerichtet und aktiv ist.
6. Ist dies der Fall, werden Zahlungen, die in hitobito ausgelöst wurden, auch in hitobito abgebucht.

ACHTUNG: Für die Zuordnung einer Zahlung an eine Person ist die Referenznummer einziges relevantes
Merkmal. Macht Eure Mitglieder darauf Aufmerksam, dass Zahlungen nicht mit alten Referenznummern
gemacht werden sollen. Fehlerquellen sind hauptsächlich falsch eingegebene oder alte Referenznummern.
In solchen Fällen muss über die Bank die Nachforschung zur entsprechenden Zahlung gemacht werden. Weder Puzzle ITC noch Hitobito kann in solchen Fällen unterstützen.

## Einrichten

- Beim Einrichten der Schnittstelle wird ein HTML File generiert das ausgedruckt und per Post an die Bank gesendet wird.
- Anschliessend kann Teilnehmer-ID und Kunden-ID ausgefüllt werden
- Das Passwort wird verwendet um die Kommunikation zu verschlüsseln. Wenn dieses Passwort geändert wird, muss die ganze Einrichtung der Schnittstelle wiederholt werden.

## Unterstützte Finanzinstitute

Folgende Banken können via EBICS angebunden werden.

- Postfinance
- Raiffeisen Schweiz

Vorhanden, jedoch noch keine abschliessende Verifikation:

- Credit Suisse
- UBS
- Luzerner Kantonalbank
- St.Galler Kantonalbank
- Thurgauer Kantonalbank
- Zürcher Kantonalbank
- BancaStato
- BEKB | BCBE
- Valiant
- Zuger Kantonalbank

Gerne ergänzen wir diese Liste mit weiteren Banken.
