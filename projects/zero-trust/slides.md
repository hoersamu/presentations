---
# try also 'default' to start simple
theme: default
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
# page transition
transition: slide-left
# use UnoCSS
css: unocss
---

# Zero Trust Architecture (ZTA)

## Minimierung der TCB

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
transition: slide-left
layout: center
class: text-center
---

# Was ist ZTA?

---
transition: fade
---

# Was ist ZTA?

* Kein Intranet mehr
* Identity Management in der Cloud
* Gibt da nen NIST-Standard zu

---
transition: fade
---

# Was ist ZTA wirklich?

* Never trust always verify
* Perimeterless Security

---
transition: slide-left
layout: center
class: text-center
---

# Warum?

---
transition: slide-left
---

# Bedrohungen

* Ransomware <br>
(lange nichts)
* Datenverluste durch Softwarefehler oder Hardwareausfall
* Innentäter

---
transition: slide-left
---

# Wie bewertet man Security

1. Threat Model mit Datenflussdiagramm
2. Messung der TCB
3. Suche nach Möglichkeiten, um die TCB zu verkleinern
4. Suche nach Maßnahmen, um die Angriffe aus dem Threat Model zu verhindern

---
transition: slide-left
---

# Was ist ein Threat Model?

#### Liste möglicher Angriffe

---
transition: slide-left
---

# Was ist ein Datenflussdiagramm?

* Abbild der Infrastruktur, nach Datenflüssen und Berechtigungen
* Komponenten mit äquivalenten Zugriffsrechten bilden Inseln

Kommunikation über Inselgrenzen ("Trust Boundary") sind riskant -> Attack Surface

---
transition: slide-left
---

# Was ist die TCB?

* Trusted Computing Base
* "Tragende Wände" der Infrastruktur
* Ziel -> Minimierung der TCB

---
transition: slide-left
---

# Was ist in der TCB?

* Datenbank
* Webserver
* Clients
* Backupsoftware etc.

---
transition: slide-left
---

# Was mache ich mit der TCB?

* Ziel: Komponenten aus der TCB holen
* Selbst wenn sie will kann eine Komponente keinen Schaden anrichten
* Bsp: cp-Befehl unter Unix -> Prüfung erfolgt im Kernel
* Kernel ist in der TCB. cp nicht

---
transition: slide-left
---

# Wie minimiere ich die TCB

* Zugriffsprüfungen "nach hinten" schieben
* Vorgelagerte Komponenten konvertieren Anfragen
* Alle Operationen dieser Komponenten sind auch ohne Hack erreichbar
* -> Keine tiefen Zugriffsrechte

---
transition: slide-left
---

# Was hat das mit ZTA zu tun?

* Alle Anfragen werden behandelt als kämen sie aus dem Internet
* Authentifizierung auf User- und nicht Rechnerbasis
* Niemandem vertrauen, nur weil der Zugriff aus dem Intranet erfolgt
* Auch im Intranet ist Verschlüsselung wichtig

---
transition: slide-left
---

# Woher kommt ZTA eigentlich?

* 1994 von Stephen Paul Marsh geprägt
* 2009/10 von Google durch BeyondCorp popularisiert

---
transition: slide-left
---

# Was heißt das jetzt?

* Alles in die Cloud?
* Google schiebt alles in die Cloud -> in ihre eigene
* Amazon schiebt alles in die Cloud -> in ihre eigene
* Apple hat iCloud bei Azure und AWS -> nur Kundendaten

---
transition: slide-left
---

# Mögliche Lösungen

* Mikrosegmentierung
* Cloud Identity Provider
* Netzwerküberwachung
* Software Defined Perimeter

---
transition: slide-left
---

# Tatsächliche Lösungen

* public key Auth (macht Windows leider immer noch nicht) -> verhindert MitM
* Wieder mehr Terminals statt Clients (siehe Chromebooks)
* Verhindern das lokale Adminrechte auf die Organisation übertragbar sind
* Least privilege
* Geschäftsanwendungen ordentlich mit HTTPS und Logins absichern
