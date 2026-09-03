Berechtigungskonzept
=======================

Gruppen / Rollen - Wie funktioniert das?
-------------------------------------------------

In hitobito können komplexe hierarchische Organisationen abgebildet werden. Alles basiert darauf, dass wir verschiedene Gruppentypen zulassen, welche auch definieren welche Rollen zur Verfügung stehen.

- Jede Organisation kann aus mehreren Ebenen bestehen, z. B. Dachverband, Kantonalverband (, optionale Zwischenstufen wie Regionen) und Ortsgruppen.
- Jede Ebene kann intern wieder ihre innere Struktur haben, es gibt einen Vorstand, Arbeitsgruppen, Mitgliederlisten, Kontaktlisten.
- Jede Person hat eine oder mehrere Rollen. Diese Rollen definieren, wen man sehen kann, und von vom man gesehen wird.

Grundsätzlich gilt in Hitobito aber:

- Wie viel jemand von einer sichtbaren Person sieht, hängt von der erreichten Sichtbarkeitsstufe ab (siehe `Sichtbarkeit einzelner Attribute`_)
- Kann jemand eine Person bearbeiten, kann er alle Attribute bearbeiten

Die Organisation sieht in seiner Grundform folgendermassen aus:

**Hauptebene**

- Administrator*in: [:admin, :layer_and_below_full, :impersonation]

- Vorstand

  - Präsident*in: [:layer_full, :contact_data]
  - Vizepräsident*in: [:layer_full, :contact_data]
  - Sekretär*in: [:layer_full, :contact_data]
  - Kassier*in: [:layer_read, :contact_data, :finance]
  - Vorstandsmitglied: [:layer_full, :contact_data]

- Geschäftsstelle

  - Leitung: [:layer_and_below_full, :admin, :contact_data, :approve_applications, :finance]
  - Kassier*in: [:layer_and_below_full, :contact_data, :layer_and_below_finance]
  - Mitglied: [:layer_and_below_full, :contact_data, :approve_applications]

- Gremium/Projektgruppe

  - Leitung: [:group_and_below_full, :contact_data]
  - Mitglied: [:group_and_below_read, :contact_data]

- Mitglieder

  - Adressverwaltung: [:group_and_below_full]
  - Aktivmitglied: []
  - Passivmitglied: []

- Kontakte

  - Adressverwaltung: [:group_and_below_full]
  - Kontakt: []

**Region/Kanton**

- Administrator*in: [:layer_and_below_full, :contact_data, :finance]

- Vorstand

  - Präsident*in: [:layer_full, :contact_data]
  - Vizepräsident*in: [:layer_full, :contact_data]
  - Sekretär*in: [:layer_full, :contact_data]
  - Kassier*in: [:layer_read, :contact_data, :finance]
  - Vorstandsmitglied: [:layer_full, :contact_data]

- Geschäftsstelle

  - Leitung: [:layer_and_below_full, :admin, :contact_data, :approve_applications, :finance]
  - Kassier*in: [:layer_and_below_full, :contact_data, :finance]
  - Mitglied: [:layer_and_below_full, :contact_data, :approve_applications]

- Gremium/Projektgruppe

  - Leitung: [:group_and_below_full, :contact_data]
  - Mitglied: [:group_and_below_read, :contact_data]

- Mitglieder

  - Adressverwaltung: [:group_and_below_full]
  - Aktivmitglied: []
  - Passivmitglied: []

- Kontakte

  - Adressverwaltung: [:group_and_below_full]
  - Kontakt: []

**Lokalgruppe/Sektion**

- Hauptleitung: [:layer_and_below_full]
- Adressverwaltung: [:group_and_below_full, :impersonation]
- Leitung: [:group_and_below_full, :contact_data]
- Aktivmitglied: [:group_and_below_read]

- Vorstand

  - Präsident*in: [:layer_full, :contact_data]
  - Vizepräsident*in: [:layer_full, :contact_data]
  - Sekretär*in: [:layer_full, :contact_data]
  - Kassier*in: [:layer_read, :contact_data, :finance]
  - Vorstandsmitglied: [:layer_full, :contact_data]

- Geschäftsstelle

  - Leitung: [:layer_and_below_full, :admin, :contact_data, :approve_applications, :finance]
  - Kassier*in: [:layer_and_below_full, :contact_data, :finance]
  - Mitglied: [:layer_and_below_full, :contact_data, :approve_applications]

- Gremium/Projektgruppe

  - Leitung: [:group_and_below_full, :contact_data]
  - Mitglied: [:group_and_below_read, :contact_data]

- Mitglieder

  - Leitung: [:group_and_below_full, :contact_data]
  - Adressverwaltung: [:group_and_below_full]
  - Aktivmitglied: [:group_and_below_read]
  - Passivmitglied: []

- Kontakte

  - Adressverwaltung: [:group_and_below_full]
  - Kontakt: []


Hier einige Beispiele, wie das aussehen kann:


Karin ist Geschäftsleiter direkt im Dachverband
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

technisch: ``layer_and_below_full`` direkt in Dachverband, inkl. ``contact_data``


Karin sieht: 
^^^^^^^^^^^^^^^^^^

.. image:: images/TopLayerFullRestrained.png

Karin hat vollen Zugriff auf ihrer Ebene und auf alle darunter liegenden Ebenen. Dadurch kann sie alle Personen im Dachverband, in Regionen und auf oberster Ebene der Ortsgruppen sehen und ändern.
Nicht sichtbar und änderbar sind für sie alle Personen, die innerhalb einer Ortsgruppe, also in einer Untergruppe unter der Ortsgruppe, aufgehängt sind. 
Da Karin's Rolle als kontaktrelevant geführt ist (sog. ContactData-Flag, siehe unten), kann sie alle anderen Personen mit Kontaktrelevanz sehen, unabhängig von deren Position innerhalb der Struktur. 



Karin sehen:  
^^^^^^^^^^^^^^^^^^

Karin ist für alle anderen Personen mit Rechten innerhalb der Ebene des Dachverbands sichtbar.
Auf Grund der Kontaktrelevanz von Karin's Rolle ist sie ebenfalls für alle anderen kontaktrelevanten Rollen sichtbar. 

Luca ist ein Mitglied in einem Gremium im Dachverband
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

technisch: ``group_read`` in Gremium ohne ``contact_data``

Luca sieht: 
^^^^^^^^^^^^^^^^^

.. image:: images/TopLayerSubgroup.png

Luca sieht alle Mitglieder und Leitung innerhalb des Gremiums. Sonst sieht er niemanden ausserhalb des Gremiums. 

Luca sehen:
^^^^^^^^^^^^^^^^

Luca ist für Personen mit vollen Rechten (``layer_full`` oder ``layer_and_below_full``) für die Dachverbandsebene sicht- und änderbar. Zusätzlich kann die Leitung innerhalb seines Gremiums seine Daten einsehen und ändern (``group_full``). Seine Kollegen mit gleicher Rolle im Gremium sehen seine Daten, können diese aber nicht ändern (``group_read``)

Maria hat eine Rolle in der Region
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

technisch: ``group_and_below`` inkl. ``contact_data``

Maria sieht
^^^^^^^^^^^^^^^

.. image:: images/MidlayerGroup.png

Maria kann alle Mitglieder ihrer Gruppe sehen, also alle Mitarbeitenden auf Regionsebene. 

Da Maria's Rolle als kontaktrelevant geführt ist (sog. ContactData-Flag, siehe unten), kann sie alle anderen Personen mit Kontaktrelevanz sehen, unabhängig von deren Position innerhalb der Struktur. 

Maria sehen
^^^^^^^^^^^^^^

Maria ist für alle anderen Personen mit Rechten innerhalb der Ebene des Dachverbands sichtbar.
Auf Grund der Kontaktrelevanz von Maria's Rolle ist sie ebenfalls für alle anderen kontaktrelevanten Rollen sichtbar. 

Petra leitet ein Gremium in der Region
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

technisch: ``layer_read`` inkl. ``contact_data``

Petra sieht: 
^^^^^^^^^^^^^^^^

.. image:: images/MidlayerFull.png


Petra sieht alle Personen in der Region inkl. Personen in allfälligen Untergruppen. Sie sieht jedoch keine Personen in Ortsgruppen, welche der Region angehängt sind. 

Da Petra's Rolle als kontaktrelevant geführt ist (sog. ContactData-Flag, siehe unten), kann sie alle anderen Personen mit Kontaktrelevanz sehen, unabhängig von deren Position innerhalb der Struktur. 

Petra sehen
^^^^^^^^^^^^^^^

Petra ist für Personen auf kantonaler oder Dachverbandsebene sichtbar, welche eine Rolle mit Zugriff auf untergeordnete Ebenen besitzen (``layer_and_below``). Zudem sehen alle Personen in der Region, die Rechte innerhalb der Gruppe oder der Ebene besitzen, ihre Daten.

Auf Grund der Kontaktrelevanz von Petra's Rolle ist sie ebenfalls für alle anderen kontaktrelevanten Rollen sichtbar. 

Anna leitet eine Ortsgruppe
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

technisch: ``layer_full`` incl. ``contact_data``

Anna sieht
^^^^^^^^^^^^^^

.. image:: images/LowLayerFull.png


Anna sieht alle Personen innerhalb der Ortsgruppe. 

Da Anna's Rolle als kontaktrelevant geführt ist (sog. ContactData-Flag, siehe unten), kann sie alle anderen Personen mit Kontaktrelevanz sehen, unabhängig von deren Position innerhalb der Struktur. 

Anna sehen
^^^^^^^^^^^^^

Anna ist für Personen oberhalb der Ortsgruppe sichtbar, falls diese das Recht besitzen, Personen unterhalb ihrer Ebene zu sehen.
Zudem können ihre Kolleginnen und Kollegen innerhalb der Ortsgruppe ihre Daten sehen, falls sie das Recht für die Gruppe oder die Ebene besitzen.
Auf Grund der Kontaktrelevanz von Anna's Rolle ist sie ebenfalls für alle anderen kontaktrelevanten Rollen sichtbar. 

Franz leitet eine Einheit innerhalb einer Ortsgruppe
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

technisch: ``layer_read`` (ohne ``contact_data``)

Franz sieht
^^^^^^^^^^^^^^^^^^^^^
.. image:: images/LowLayerFull.png

Franz sieht alle Personen innerhalb der Ortsgruppe, kann diese aber nicht ändern. 

Franz sehen
^^^^^^^^^^^^^^^^^^^^
Franz ist für Personen in der Ortsgruppe sichtbar, falls diese das Recht besitzen, Personen innerhalb der ganzen Ebene zu sehen. Personen oberhalb der Ortsgruppe können Franz nicht sehen. 


Jonas ist Mitglied innerhalb einer Gruppe in der Ortsgruppe
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

technisch: ``none``

Jonas sieht
^^^^^^^^^^^^^^^^^^^^

.. image:: images/LowLayerNone.png


Jonas sieht keine weiteren Personen. 

Jonas sehen
^^^^^^^^^^^^^^^^^^^^

Jonas ist für Personen in der Ortsgruppe sichtbar, falls diese das Recht besitzen, Personen innerhalb der ganzen Ebene zu sehen. Personen oberhalb der Ortsgruppe können Jonas nicht sehen. 

Kumulierung von Rollen innerhalb der Struktur
-------------------------------------------------

Die Zugriffe durch mehrere Rollen kumulieren sich. So ist ein Mitglied einer Ortsgruppe, das gleichzeitig in der Region aktiv ist, trotzdem für die Regionsleitung sichtbar. 

Sichtbarkeit einzelner Attribute
-------------------------------------------------

Ob eine Person überhaupt sichtbar ist, ist nur die eine Hälfte der Berechtigung. Wie viel man von ihr sieht, hängt von vier aufeinander aufbauenden Sichtbarkeitsstufen ab:

``kein Zugriff`` → ``show`` → ``show_details`` → ``show_full``

Welche Stufe man auf eine bestimmte Person erreicht, ergibt sich aus den Berechtigungen der eigenen Rollen:

.. list-table::
  :header-rows: 1
  :widths: 40 60

  * - Berechtigung der eigenen Rolle
    - Erreichte Stufe auf die betroffenen Personen
  * - ``contact_data``
    - ``show``
  * - ``group_read``, ``group_and_below_read``
    - ``show``, ``show_details``
  * - ``group_full``, ``group_and_below_full``, alle ``layer_*``
    - ``show``, ``show_details``, ``show_full``

Die Stufen werden pro Person ausgewertet. Es ist also normal, dass man auf der einen Person alle Angaben sieht und auf einer anderen nur den Namen und die Adresse.

Welche Angaben auf welcher Stufe sichtbar sind
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Im hitobito-Core sind die generischen Attribute wie folgt eingeteilt. Wagons können weitere Attribute ergänzen und diese eigenen Stufen zuordnen.

.. list-table::
  :header-rows: 1
  :widths: 25 75

  * - Stufe
    - Angaben
  * - ``show``
    - Vorname, Name, Übername, Firmenname, Adresse und Land, Haupt-E-Mail-Adresse, als öffentlich markierte weitere E-Mail-Adressen, Telefonnummern und Social Media, Hauptebene
  * - ``show_details``
    - Zusätzlich: nicht öffentliche weitere E-Mail-Adressen, Telefonnummern und Social Media, Geburtstag, Geschlecht, Korrespondenzsprache (nur wenn mehrere Sprachen aktiv sind), zusätzliche Angaben, Erstellungs- und Änderungsinformationen, die Tabs "Abos" und "Nachrichten"
  * - ``show_full``
    - Zusätzlich: Rollen, Tags, Anlass-Teilnahmen und Anmeldungen, Qualifikationen, Haushalt, Verantwortliche/Betreute, Verlauf

Der Login-Status wird auf der Personenseite zusätzlich nur angezeigt, wenn man die Person auch bearbeiten darf.

Einblendbare Spalten in Listen
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Über den Button "Spalten" lassen sich in Personenlisten und Anlass-Teilnahmelisten zusätzliche Spalten einblenden. Welche Spalten überhaupt zur Auswahl stehen, ist pro hitobito-Instanz bzw. Wagon festgelegt und unabhängig von den eigenen Berechtigungen.

Die Berechtigung wird jedoch beim Anzeigen pro Person und Spalte nochmals nach den obigen Stufen geprüft. Fehlt die nötige Stufe bei einer Person, steht in der Zelle "fehlende Berechtigung" statt des Werts.

.. note:: Eine Ausnahme bildet die feste Spalte "Rollen" in der Personenliste: Sie zeigt ohne zusätzliche Berechtigungsprüfung die Rollen der Person in der aktuellen Gruppe. Wer eine Person in einer Liste sieht, sieht dort also auch ihre Rollen in dieser Gruppe. Auf der Personenseite hingegen sind die Rollen erst ab ``show_full`` sichtbar.

Berechtigungen bei Exporten
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Jeder Export enthält nur diejenigen Personen, welche man in der jeweiligen Liste auch sehen kann. Welche Angaben exportiert werden, hängt vom gewählten Export ab:

.. list-table::
  :header-rows: 1
  :widths: 25 75

  * - Export
    - Inhalt
  * - Adressliste
    - Immer verfügbar. Enthält die ``show``-Angaben plus Hauptebene und Rollen.
  * - Spaltenauswahl
    - Wie die Adressliste, zusätzlich die aktuell eingeblendeten Spalten. Die Berechtigung wird dort pro Person und Spalte ausgewertet.
  * - Haushaltsliste
    - Immer verfügbar. Fasst Personen im gleichen Haushalt zusammen und exportiert eine feste, limitierte Spaltenauswahl (Anrede, Name, zusätzliche Adresszeile, Strasse, Hausnummer, Postfach, PLZ, Ort, Land, Hauptebene).
  * - Alle Angaben
    - Nur verfügbar, wenn man auf der Liste ``show_full`` hat. Exportiert alle Attribute bis zur Stufe ``show_full``.

.. note:: Die Haushaltsliste hat genau eine Namensspalte. Alle Haushaltsmitglieder werden darin zusammengefasst ("Andreas und Mara Mäder, Peter Muster"), ab einer gewissen Länge mit abgekürzten Vornamen. Die Spalte "Anrede" enthält eine generierte Briefanrede, kein Personenattribut.

In Abos ist der Export zusätzlich eingeschränkt: Umfasst das Abo Gruppen oder Rollen ausserhalb des eigenen Berechtigungsbereichs, kann man es gar nicht exportieren. Andernfalls stehen Adressliste, Spaltenauswahl und Haushaltsliste zur Verfügung. "Alle Angaben" ist in Abos nie verfügbar.

Berechtigungen in der API
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Auch in der API gelten dieselben Sichtbarkeitsstufen. Bei OAuth werden die Berechtigungen der angemeldeten Person verwendet. Service Tokens haben auf allen für sie zugänglichen Personen immer ``show_full``; feinere Abstufungen gibt es für Service Tokens nicht.

Daten in Anlässen (Lagern, Kursen)
-------------------------------------------------

Teilnehmer in einem Anlass können die Teilnehmerliste einsehen und sehen dort ihre gegenseitigen Kontaktdaten. Die Daten sind nur im Kontext "Anlass" sichtbar, wenn über die Teilnehmerliste zur Person navigiert wird. 
Im Kontext einer "Gruppe", wenn über die Gruppenhierarchie zur Person navigiert wird, gelten die Zugriffsrechte gemäss den strukturbasierten Rechten oben. 

Spezialfall ``Contact_Data``
-------------------------------------------------

Ist die Rolle einer Person als kontaktrelevant markiert, so hat diese Person auf alle anderen Personen mit kontaktrelevanten Rollen Zugriff. Gleichzeitig ist sie auch für alle anderen Personen mit kontaktrelevanten Rollen sichtbar. 
Dies umfasst Rollen, welche häufig im Austausch mit Personen aus anderen Ortsgruppen stehen. 

Spezialfall ``finance``
-------------------------------------------------

Erlaubt auf der entsprechenden Ebene Rechnungen zu erstellen und einzusehen.

Spezialfall ``layer_and_below_finance``
-------------------------------------------------

Erlaubt auf allen unterliegenden Ebenen Rechnungen zu erstellen und einzusehen.

Spezialfall ``impersonation``
-------------------------------------------------

Darf andere Accounts temporär übernehmen, z. B. für Support Aufgaben oder für Tests. Dies ist eine sehr mächtige Funktion und sollte nur an klar definierte Rollen vergeben werden.

Security: Zugriffsanfragen und manuelle Freigabe
-------------------------------------------------

Angenommen, Anna möchte unberechtigt Zugriff auf die persönlichen Daten von John bekommen. Dazu kann Anna John einfach in einer Gruppe, einem Anlass oder Abo hinzufügen, in der sie Zugriffsrechte hat. Dieses Datenschutz-Problem kann in hitobito mit den "manuellen Freigaben" verhindert werden.

Beim Hinzufügen von John in Gruppen, Anlässen und Abos überprüft hitobito Johns Haupt-Rolle (die Rolle die mit einem Stern markiert ist). Falls John keine aktive Rolle mehr hat, überprüft hitobito stattdessen die letzte Rolle die noch aktiv war.
Es wird überprüft, ob in der Ebene dieser Rolle die manuellen Freigaben aktiviert sind. Beispiel: John hat seine Haupt-Rolle in der Arbeitsgruppe "Saturn" des Vereins "Sterngucker Luzern". Die manuellen Freigaben können bei der Ebene (Verein Sterngucker Luzern) auf dem Anfragen-Tab aktiviert werden.

Sind manuelle Freigaben in der Ebene aktiviert, dann wird John nicht direkt in die neue fremde Gruppe, Anlass oder Abo hinzugefügt, sondern es wird eine Zugriffsanfrage ausgelöst. Anna sieht dann folgende Nachricht:

.. image:: images/pending_role_approval.png

Alle Personen die auf dem Anfragen-Tab ausgewählt sind, sowie John falls er einen Login hat, bekommen ein E-Mail welches darüber informiert dass Anna John an einem neuen Ort hinzufügen will. Von diesem E-Mail aus oder auf dem Anfragen-Tab der Gruppe kann die Zugriffsanfrage akzeptiert oder abgelehnt werden.

.. image:: images/approvals_tab.png

So bekommt Anna nie unberechtigten Zugriff auf die Personendaten von John. Das Ganze funktioniert aber nur, wenn die manuellen Freigaben auf der Ebene aktiviert sind. Es wird keine Zugriffsanfrage ausgelöst wenn Anna bereits vorher Zugriff auf John hat (z.B. wenn beide eine Rolle mit `contact_data` haben).
