EBICS Schnittstelle
========================

Über die `EBICS Schnittstelle <https://www.six-group.com/de/products-services/banking-services/standardization.html#scrollTo=ebics/>`_ können camt054 Dateien regelmässig von einem Finanzinstitut bezogen werden. Mittels Referenznummer werden die Zahlungen einer Rechnung von der Ebene zugewiesen. Zahlungen die keiner Rechnung zugewiesen werden können, werden ignoriert

In den Rechnungseinstellungen kann pro Ebene die EBICS Schnittstelle definiert werden. Zugangsdaten werden verschlüsselt in Hitobito ablegen.

Einrichten
--------------

- Beim Einrichten der Schnittstelle wird ein HTML File generiert das ausgedruckt und per Post an die Bank gesendet wird.
- Anschliessend kann Teilnehmer-ID und Kunden-ID ausgefüllt werden
- Das Passwort wird verwendet um die Kommunikation zu verschlüsseln. Wenn dieses Passwort geändert wird, muss die ganze Einrichtung der Schnittstelle wiederholt werden.

Unterstützte Finanzinstitute
--------------

Folgende Banken können via EBICS angebunden werden.

- Postfinance

Vorhanden, jedoch noch keine abschliessende Verifikation:

- Credit Suisse
- Raiffeisen Schweiz
- UBS
- Luzerner Kantonalbank
- St.Galler Kantonalbank
- Thurgauer Kantonalbank
- Zürcher Kantonalbank
- BancaStato
- BEKB | BCBE
- Zuger Kantonalbank

Gerne ergänzen wir diese Liste mit weiteren Banken. 
