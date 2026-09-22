EBICS Schnittstelle
===================

Allgemeines
-----------
Hitobito lässt sich mit einem Bank- oder Postkonto verbinden. Dies bedeutet folgendes:

Wird eine Zahlung über Hitobito ausgelöst und vom Empfänger bezahlt, ist diese Information nicht mehr nur
im Bankkonto ersichtlich, sondern wird auch in Hitobito ausgewiesen. Hitobito kann so die Buchhaltung
unterstützen, somit können die Zahlungseingänge zentral und personifiziert überwacht werden.

Als Schnittstelle verwendet Hitobito die Technologie EBICS. EBICS ist eine standardisierte Schnittstelle zu
Finanzapplikationen und wird in der Schweiz von beinahe allen Banken angeboten (Ausnahmen sind
möglich, uns aber nicht bekannt). Mehr Informationen zu EBICS findet ihr auf den Webseiten der
verschiedenen Banken.


Über die `EBICS Schnittstelle <https://www.six-group.com/de/products-services/banking-services/payment-standardization/standards/ebics.html>`_ können camt054 Dateien regelmässig von einem Finanzinstitut bezogen werden. Mittels Referenznummer werden die Zahlungen einer Rechnung von der Ebene zugewiesen. Zahlungen die keiner Rechnung zugewiesen werden können, werden ignoriert.

In den Rechnungseinstellungen kann pro Ebene die EBICS Schnittstelle definiert werden. Zugangsdaten werden verschlüsselt in Hitobito abgelegt.

Wir richte ich die Schnittstelle ein?
-------------------------------------

1) Über die eigene Bank/Post muss ein EBICS Vertrag angefordert werden.
	a) Der Vertrag regelt, welche Konten mit Hitobito verknüpft werden. Es können mehrere Konten gleichzeitig über EBICS mit Hitobito verknüpft werden.
	b) Im Vertrag muss EBICS als Schnittstelle ausgewählt werden, falls Euch der Vertrag mehrere Optionen gibt.
	c) Im Vertrag muss eine Software angegeben werden, damit ist Hitobito gemeint. Angegeben werden soll als Software «Hitobito» und als Hersteller «Puzzle ITC»
	d) Die Buchungsart ist Sammelbuchung, die Periodizität ist Euch selbst überlassen.
2) Der Vertrag wird der Bank/Post zurückgeschickt. Von Seiten der Bank/Post wird nun ein Dokument mit der Vertrags-ID und der Kunden-ID für EBICS erstellt und Euch zur Verfügung gestellt. (Die genaue Bezeichnung kann variieren und auch als Teilnehmer-ID / Partner-ID o.Ä. bezeichnet sein.)
3) Mit diesem Dokument der Bank/Post könnt Ihr in hitobito unter den Rechnungseinstellungen->Zahlungsschnittstellen die Vertrags-ID und die Kunden-ID eingeben. Sobald dies gemacht ist, erscheint in Hitobito ein Button zur Generierung des Initialisierungs-Dokuments (INI-Brief).
4) Dieses Dokument muss dem Bankinstitut unterschrieben zurückgeschickt werden, damit die Verbindung zwischen Konto und Hitobito erstellt werden kann.
5) Die Bank informiert Euch, sobald die Schnittstelle eingerichtet und aktiv ist.
6) Ist dies der Fall, werden Zahlungen, die in Hitobito ausgelöst wurden, auch in Hitobito abgebucht.


ACHTUNG: Für die Zuordnung einer Zahlung an eine Person ist die Referenznummer das einzige relevante
Merkmal. Macht Eure Mitglieder darauf Aufmerksam, dass Zahlungen nicht mit alten Referenznummern
gemacht werden sollen. Fehlerquellen sind hauptsächlich falsch eingegebene oder alte Referenznummern.
In solchen Fällen muss über die Bank die Nachforschung zur entsprechenden Zahlung gemacht werden. Weder Puzzle ITC noch Hitobito kann in solchen Fällen unterstützen.


Unterstützte Finanzinstitute
----------------------------

Folgende Banken können via EBICS angebunden werden.

- BancaStato
- Banque Cantonale Neuchâteloise
- Banque Cantonale Vaudoise
- BEKB | BCBE
- Credit Suisse
- Luzerner Kantonalbank
- Postfinance
- Raiffeisen Schweiz
- Schwyzer Kantonalbank
- St.Galler Kantonalbank
- Thurgauer Kantonalbank
- UBS
- Urner Kantonalbank
- Valiant
- Walliser Kantonalbank
- Zürcher Kantonalbank
- Zuger Kantonalbank

Gerne ergänzen wir diese Liste mit weiteren Banken. 
Dafür werden die EBICS Verbindungsparameter der Bank benötigt, diese kann man direkt bei der Bank anfragen.
