Rechnungen
================

In Hitobito können Debitoren verwaltet, Rechnungen erstellt und Zahlungen verbucht werden. Hitobito hat keine Buchhaltungsfeatures. Bei Bedarf können die Rechnungs- und Zahlungsdaten exportiert, oder eine Buchhaltungssoftware via Schnittstellen angebunden werden.

.. note:: Rechnungen sind ein Feature welches pro Instanz aktiviert werden kann.
Ob eine Person Rechnungen verwalten kann hängt davon ab, ob sie eine entsprechende Rolle hat. Welche Rollen `:finance` Berechtigungen haben hängt von der jeweiligen Organisation ab.


Rechnungen erstellen
--------------------------

.. note:: Rechnungen werden nicht auf der Ansicht Rechnungen erstellt, sondern ausgehend von Personenlisten oder auf der Ansicht einer bestimmten Person.

Rechnungen können aus folgenden Ansichten erstellt werden:

- Personenlisten
- Teilnehmerlisten von einem Event, Lager oder Kurs
- Einzelperson
- im Abo an die jeweiligen Empfänger, dies erstellt eine Sammelrechnung

Rechnung
---------------------------------------
Hier finden Sie die Übersicht über alle erstellten Rechnungen und hier können diese verschickt, bearbeitet, gelöscht oder gedruckt werden. Pro Rechnung ist der Status sichtbar. Zahlungen können manuell auf der jeweiligen Rechnung erfasst oder mittels camt.054 XML-Datei [#f2]_ eingelesen werden.

Bei Bedarf können die Rechnungen auch als CSV exportiert und in eine Buchhaltungsapplikation eingelesen werden.

An dieser Stelle können auch **externe** Rechnungen erstellt werden, d.h. Rechnungen, welche an externe Empfänger geschickt werden, welche nicht in hitobito erfasst sind.

Sammelrechnungen
--------------------------------------

Werden Rechnungen aus dem Abo generiert, wird eine Sammelrechnung erstellt. Dies fasst die Rechnungen zu einem Eintrag zusammen. Dabei wird neben der Anzahl Rechnungen auch die offenen und bezahlten Beträge angezeigt.


Rechnungsartikel
--------------------------------------

Häufig verwendete Rechnungspositionen (z.B. Mitgliederbeitrag, Jahresabo, etc.) können hier vordefiniert werden. Diese Artikel können beim Erstellen von Rechnungen ausgewählt und individuell angepasst werden.

Einstellungen
---------------------------------------

In den Rechnungseinstellungen können allgemeine Angaben gemacht werden, wie die Absenderadresse, Absender-E-Mail, Tage bis Fälligkeit, MwSt.-Nummer etc. Hier können auch die Texte für die erste, zweite und dritte Mahnung definiert werden.

Diese Einstellungen können pro Ebene individuell vorgenommen werden.

Du kannst rote und orange Einzahlungsscheine für Post und Bank erstellen. Zusätzlich stehen noch QR Rechnungen zur Verfügung. Für QR Rechnungen muss eine spezielle QR-IBAN (https://www.moneytoday.ch/lexikon/qr-iban/) hinterlegt werden. Diese unterscheidet sich von der bestehenden IBAN Nummer.




.. [#f2] Eine camt.054 XML-Datei ist die Sammelbuchungs-auflösung und Belastungs- und Gutschriftsanzeige. Diese enthält eine Reihe verschiedene Buchungspositionen welche automatisiert auf Basis der ESR-Nummer bestehenden Rechnungen zugeordnet werden.
