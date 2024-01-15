# Hitobito User Documentation

[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://GitHub.com/hitobito/user_documentation/graphs/commit-activity)
[![Documentation Status](https://readthedocs.org/projects/hitobito/badge/?version=latest)](https://hitobito.readthedocs.io/de/latest/?badge=latest)
[![GitHub](https://img.shields.io/github/license/hitobito/user_documentation)](https://github.com/hitobito/user_documentation/blob/master/LICENSE)

This is the source of https://hitobito.readthedocs.io a generic user documenation about Hitobito.

Die Benutzerdokumentation von Hitobito bringt einige Herausforderungen mit sich. So kann aufgrund der Struktur und Wagon die jeweilige Kundeninstanz unterschiedlich funktioniern. Dieser Herausforderung muss in der Dokumentation adressiert werden. Wir haben uns entschieden, gemeinsam eine generische Dokumentation zu führen welche einen Überblick von Hitobito gibt. Kundenspezifische Dokumentation und Anleitungen mit spezifischen Usecases werden durch die jeweiligen Organisation geführt.

## Generische Dokumentation

* Ziel: Allgemeine Dokumentation mit einem Überblick, was Hitobito alles kann. Ohne die spezifischen Anpassungen an den Wagons.
* Zielgruppe: Personen welche mehr über Hitobito wissen wollen und einen Überblick was alles möglich ist
* Diese Doku wird gemeinsam gepflegt
* Bemerkungen oder eine Infobox falls das Modul in mehreren Wagons oft oder gross abweicht. Analog der Dokumentation der [Rechnungen](https://hitobito.readthedocs.io/de/latest/access_concept.html)

## Kundenspezifische Dokumentation 
* Ziel: Usecase spezifische Anleitung (z.b. Wie erstelle ich als Scharleiterin ein Lager)
* Zielgruppe: Endbenutzer 
* Gepflegt durch entsprechende Organisationen in ihren Hilfsmittel
* Verweis oder Kopie von der generische Doku möglich

Hier eine Sammlung von User Dokumentation/Dokumente von den Community Mitgliedern:

* Hitobito generische [User Dokumentation](https://hitobito.readthedocs.io/de/latest/)
* SBV: [Benutzerhandbuch](https://hitobito-manual-sbv-de.readthedocs.io/de/latest/) und [Erklärvideos](https://www.youtube.com/watch?v=-XPwxKcvS4c&list=UUjGtTWlk8_HvhjCo8eVUmvw&index=13)
* Cevi: [Wiki Seite Cevi.DB](https://wiki.cevi.ch/index.php/Cevi.DB)
* Jubla: [Allgemeine Infos](http://jubla.ch/datenbank) und [Handbuch Jubladb](https://github.com/jubla-ch/handbuch-jubladb-hitobito)
* PBS: Einstieg in [Deutsch](http://info-de.scouts.ch/) oder [Franzöisch](http://info-fr.scouts.ch/) oder [Italienisch](https://pfadi.swiss/it/midata/)
* Die Mitte: Wir zur Zeit noch erstellt (Mehrsprachig)

## Contribute generic user documentation (this repo)
The [readthedocs](https://readthedocs.org/) page is rebuilt with each merged PR. You can check whether the build was successful [here](https://readthedocs.org/projects/hitobito/builds/). If you are unsure, you can first merge into the beta branch. This is also built and can be reached in the [beta page](https://hitobito.readthedocs.io/de/beta/)
A helpful overview over the restructured syntax that we use can be found [here](https://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html)

Manual building:

Ensure that you have virtualenv and rake installed. Then:

`rake build:all`

In case the translations cannot be pulled, you need to configure transifex correctly.
`rake tx:status` can help

## Developer documentation for Hitobito

If you are looking for the docs for development of hitobito head over to https://github.com/hitobito/hitobito/tree/master/doc
