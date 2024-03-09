Rechnungen
================

In Hitobito können Debitoren verwaltet, Rechnungen erstellt und Zahlungen verbucht werden. Hitobito hat keine Buchhaltungsfeatures. Bei Bedarf können die Rechnungs- und Zahlungsdaten exportiert, oder eine Buchhaltungssoftware via Schnittstellen angebunden werden.

.. note:: Rechnungen sind ein Feature welches pro Instanz aktiviert werden kann. Ob eine Person Rechnungen verwalten kann hängt davon ab, ob sie eine entsprechende Rolle hat. Welche Rollen `:finance` Berechtigungen haben hängt von der jeweiligen Organisation ab.


Rechnungseinstellungen
--------------------------
In den Rechnungseinstellungen werden pro Ebene gültige Angaben gemacht. Hier werden die allgemeinen Rechnungseinstellungen verwaltet und Mahnungsfristen und -texte definiert. Zudem können Einstellungen zum Email-Versand und Rechnungslayout vorgenommen werden, sowie Zahlungsschnittstellen eingerichtet werden.

.. note:: Damit Rechnungen versendet werden können müssen gültige Rechnungseinstellungen vorhanden sein.

Rechnungsartikel
---------------------------------------
Häufig verwendete Rechnungspositionen (z.B. Mitgliederbeitrag, Jahresabo, etc.) können hier pro Ebene vordefiniert werden. Diese Artikel können beim Erstellen von Rechnungen ausgewählt und individuell angepasst werden.

.. note:: Die Felder Kostenstelle und Konto haben in Hitobito keine Funktion. Sie sind lediglich für einen allfälligen Export in eine Buchhaltungssoftware vorhanden.

Rechnungen erstellen
--------------------------------------
.. note:: Rechnungen werden nicht auf der Ansicht Rechnungen erstellt, sondern ausgehend von Personenlisten oder einer bestimmten Person.

Rechnungen können aus folgenden Ansichten erstellt werden:

- Personenlisten in einer Gruppe. Erstellt eine Einzelrechnung an die ausgewählten Personen.
- Teilnehmerlisten von einem Event. Erstellt eine Einzelrechnung an die ausgewählten Personen.
- Auf dem Profil einer Einzelperson. Erstellt eine Einzelrechnung an die ausgewählte Person.
- In einem Abo. Erstellt eine Sammelrechnung an die jeweiligen Empfänger des Abos.
- Externe Rechnungen erstellen in der Übersicht Einzelrechnungen. Erstellt eine Einzelrechnung. Diese wird keiner Person in Hitobito zugeordnet.


Rechnungen einsehen und bearbeiten
--------------------------------------

Rechnungen können in der Übersicht Rechnungen eingesehen und bearbeitet werden. Hier wird zwischen Einzelrechnungen und Sammelrechnungen unterschieden. 

Rechnungen können gestellt, gemahnt und per Email versendet werden. Dabei werden immer sämtliche ausgewählten Rechnungen gestellt oder gemahnt abhängig von ihrem aktuellen Status.

Hier können Rechnungen auch gedruckt oder exportiert werden, und es können Zahlungen erfasst werden.

Sammelrechnungen werden in der Übersicht zusätzlich pro Rechnungslauf zusammengefasst. Dabei wird die Anzahl Empfänger, so wie die Anzahl und der Betrag der bezahlten Rechnungen angezeigt.

Die Rechnungen einer spezifischen Person können auch auf der jeweiligen Personenansicht eingesehen werden.


Zahlungen Erfassen
---------------------------------------
Zahlungen können auf drei verschiedene Arten erfasst werden.

Auf jeder Einzelrechnung können manuelle Zahlungen für die jeweilige Rechnung erfasst werden.

In der Übersicht Einzelrechnungen können camt.54 XML-Datei [#f2]_  hochgeladen werden. Diese erfassen die jeweiligen Zahlungen auf den dazugehörigen Rechnungen. Die Zahlungen werden auch erfasst, wenn es sich dabei um eine Sammelrechnung handelt.

Ist in den Rechnungseinstellungen eine Zahlungsschnittstelle eingerichtet, werden die Zahlungen nächtlich über die EBICS Schnittstelle mit der Bank abgeglichen.
Anleitung zum einrichten der EBICS Schnittstelle: https://hitobito.readthedocs.io/de/latest/ebics.html

Buchungsbeleg
---------------------------------------
Unter Buchungsbeleg wird eine rudimentäre Übersicht über die eingegangenen Zahlungen gegeben. Diese werden nach Rechnungsartikel sortiert. Dabei wird davon ausgegangen, dass gleiche Rechnungsartikel auch immer den gleichen Betrag aufweisen. 


Häufig gestellte Fragen:
---------------------------------------
Q: Ich kann keine Rechnungen erstellen. Die Gruppe als welche ich Rechnungen stellen mögcht ist ausgegraut.

A: Für die ausgegraute Gruppe sind keine gültigen Rechnungseinstellungen vorhanden. Bitte aktuallisiere die Rechnungseinstellungen.


Q: Ich kann meine Rechnungseinstellungen nicht speichern? 

A: Vermutlich ist in einem anderen Tab der Rechnungseinstellungen noch eine falsche Information vorhanden. Probiere auf den verschiedenen Tabs die Rechnungseinstellungen zu speichern.


Q: Ich kann eine Rechnung nicht mehr löschen?

A: Eine Rechnung kann nur gelöscht werden, solange sie noch den Status "Entwurf" hat. Eine Sammelrechnung kann nur gelöscht werden, wenn noch alle darin enthaltenen Rechnungen den Status "Entwurf" haben. Hat eine Rechnung bereits einen anderen Status, kann diese nur noch storniert werden.


Q: Eine Rechnung mit dem Status "Gestellt" wird nicht gemahnt, obwohl ich diese bei Mahnen ausgewählt hatte.

A: Rechnungen werden nur gemahnt, wenn das Mahndatum erreicht wird. Sschaue in den Rechnungseinstellungen nach, wie lange nach Rechnungsdatum hier die Mahnfrist ist.


Q: Nach dem Speichern meiner Sammelrechnung werden keine Rechnungen erstellt.

A: Damit Sammelrechnungen erfolgreich erstellt werden können, muss mindestens eine Rechnungspositon einen Betrag aufweisen (Dieser Betrag kann 0 sein).

---------------------------------------
.. [#f2] Eine camt.054 XML-Datei ist die Sammelbuchungs-auflösung und Belastungs- und Gutschriftsanzeige. Diese enthält eine Reihe verschiedene Buchungspositionen welche automatisiert auf Basis der ESR-Nummer bestehenden Rechnungen zugeordnet werden.
