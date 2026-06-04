---
title: " "
description: " "
---
# Repetition Softwareentwicklung

Repetition der wichtigsten Themen des Fachs Softwareentwicklung. Ihr habt insgesamt 6x 45 Minuten Zeit, um die Aufgaben zu lösen und Punkte zu sammeln.
Insgesamt gibt es 60 Punkte. Die einzelnen Aufgaben müssen vor Ort abgegeben und Fragen zu den Aufgaben beantwortet werden.
Anhand der gesammelten Punkte wird die Note berechnet.

---

## Softwareentwicklung (5 Punkte)

Erstelle ein kurzes Softwarekonzept für ein IoT-System, das Büropflanzen vor dem Verdorren schützt.
Ein Sensor misst die Feuchtigkeit im Topf und schlägt bei Trockenheit Alarm.

Gehe auf die folgenden Phasen der Softwareentwicklung ein und halte die Antworten kurz (Stichworte genügen).

### Analyse und Spezifikation
1. Erstelle eine konkrete User Story aus Sicht eines Mitarbeiters im Büro.
2. Definiere das Erfolgskriterium für das System (Wann gilt das Projekt als erfolgreich abgeschlossen?).

### Design und Architektur
1. Zeige in 3–4 Schritten auf, wie der Messwert vom analogen Sensor bis zur Benachrichtigung des Nutzers kommt.
2. Definiere den API-Endpunkt (HTTP-Methode und URL) sowie die JSON-Datenstruktur, mit der die Informationen vom Microcontroller an den Server übermittelt werden.

### Implementation
Skizziere die logischen Schritte als Stichworte, wie der Ablauf auf dem Microcontroller in C++ aussehen müsste.

### Test und Fehlerbehebung
Nenne ein kritisches Risiko oder einen potenziellen Fehler und beschreibe kurz, wie die Software in diesem Fall reagieren sollte, um einen Systemabsturz zu verhindern.

### Dokumentation
Letzte bzw. andauernde Phase der Softwareentwicklung, da fortlaufend dokumentiert werden muss. Für diese Aufgabe wird diese Phase ignoriert.

---

## UML  und Klassen erstellung (10 Punkte)

1. Zeichne ein Klassendiagramm mit den Informationen aus den beschriebenen Anforderungen. 
    Die Klassen mit ihren Attributen und Methoden müssen identifiziert und die Beziehungen dazwischen aufgezeichnet werden.
2. Implementiere die Klassen mit den Attributen und Methoden in C++. Dies kann am Computer oder auf einem Blatt Papier gemacht werden.
3. Erstelle ein GitHub-Repository und pushe den Code. Füge auch das Klassendiagramm in das Repository und pushe auf einen zusätzlichen Branch namens Klassendiagramm.
```
Im Portal sind Personen erfasst, die eine ID, einen Namen und eine E-Mail-Adresse besitzen. 
Es wird zwischen Lehrpersonen und Schülern unterschieden. Lehrpersonen können Noten eintragen. 
Ein Schüler besucht mindestens ein Fach (z. B. Mathematik). Ein Fach besteht aus mehreren Leistungsnachweisen (Prüfungen). 
Jeder Leistungsnachweis enthält eine Note (als Dezimalzahl), ein Datum, eine Gewichtung und kann seinen Notendurchschnitt berechnen.
```

---

## HTTP-Requests (10 Punkte)

Löse den HTTP-Quest. Alle Informationen zur nächsten Aufgabe sind jeweils in der Antwort der vorherigen Aufgabe zu finden.

Öffne das Terminal und verwende folgendes Kommando, um die HTTP-Anfrage an die API zu senden:

```
curl -X GET "https://http-quest.onrender.com/start?name=NAMEEINFUEGEN"
```

Hilfestellung für Aufgabe 3:

```
CURL-UND-METHODE-HINZUFUEGEN -H "Content-Type: application/json" -d "{\"name\":\"Anna\"}" "https://http-quest.onrender.com/ENDUNG-ANPASSEN"
```

Notiert alle Lösungssätze und die verwendeten Kommandos.

## Flussdiagramm (5 Punkte)
1. Zeichne ein Flussdiagramm für den klassischen Anmeldeprozess auf einer Webseite. Wichtig ist, dass der Benutzer das Passwort nur dreimal eingeben kann und dann der Account für 15 Minuten gesperrt wird. Versucht die Person es nach 15 Minuten nochmals und gibt es wieder falsch ein, wird das Konto für immer gesperrt und die Person muss sich telefonisch beim Administrator melden. Diese Information soll der Nutzer von dem System bekommen.

2. Implementiere das Flussdiagramm genau so wie aufgezeichnet in C++. Verwende mindestens eine Funktion in der Implementierung. Das Flussdiagramm und der Code sollen möglichst genau übereinstimmen.

### Coding (20 Punkte)

Die Aufgabe ist es, eine Art „Hot Potato“-Spiel zu implementieren und den Code auf GitHub zu veröffentlichen.

#### Teil 1:
Das Spiel ist für zwei Personen und jede Person hat 15 Leben. Die zwei Personen würfeln nacheinander und die gewürfelte Zahl wird dem Gegner von den Leben abgezogen.

#### Teil 2:
Wenn eine 6 gewürfelt wird, werden dem Gegner nicht nur 6 Punkte abgezogen, sondern dieser wird auch für eine Runde gesperrt und kann nicht würfeln.

#### Teil 3:
Nachdem eine 6 gewürfelt wurde, hat der Gegner die Chance, sich frei zu würfeln. Wenn er auch eine 6 würfelt, ist er frei und kann normal weiterspielen.

---

#### Aufgabe: Teil 1
* Zu Beginn wird nach den zwei Namen von den Spielern gefragt.
* Für beide Spieler wird ein Objekt vom Typ Spieler erstellt.
    * Dies bedeutet, dass ihr eine Klasse namens Spieler erstellen müsst.
    * Ihr könnt zwei Spieler erstellen und müsst diese NICHT in einer Liste speichern (könnt aber, falls ihr dies möchtet). Das Leben der Spieler wird in der Klasse Spieler gespeichert.
    * Name und Leben müssen private Variablen sein.
* Nun können die Personen nacheinander durch die Eingabe der Zahl 1 würfeln.
    * Mit diesem Ausdruck `rand() % 6 + 1` kann eine zufällige Zahl zwischen 1 und 6 ausgegeben werden. Um `rand()` zu verwenden, benötigt ihr die folgende Library: `#include <stdlib.h>`
* Die gewürfelte Zahl wird dem Gegner vom Leben abgezogen.
    * Es muss ein Getter und Setter verwendet werden, um das Leben von dem Spieler anzupassen.
* Verwendet Funktionen, wenn es Teile im Code gibt, die öfter wiederholt werden.
* (Es wird so lange gespielt, bis eine Person kein Leben mehr hat. Dann wird ausgegeben, wer der Gewinner ist.)

---

#### Aufgabe: Teil 2
* Wenn eine 6 gewürfelt wird, wird der Gegner für eine Runde gesperrt.
    * Um Spieler zu sperren, soll ein Enum verwendet werden:
        * normal, gesperrt
    * Diese Information soll auch im Spieler gespeichert werden.
* Nachdem die Person eine Runde gesperrt war, wird der Zustand wieder auf normal gesetzt.
* (Es wird so lange gespielt, bis eine Person kein Leben mehr hat. Dann wird ausgegeben, wer der Gewinner ist.)

---

#### Aufgabe: Teil 3 (Bonus)
* Wenn ein Spieler gesperrt wurde, hat dieser die Möglichkeit, sich frei zu würfeln.
    * Der gesperrte Spieler kann durch die Eingabe von 1 würfeln. Falls eine 6 gewürfelt wird, kann der Spieler normal weiterspielen, und sonst ist dieser für eine Runde gesperrt.
* Es wird so lange gespielt, bis eine Person kein Leben mehr hat. Dann wird ausgegeben, wer der Gewinner ist.
---

#### Aufgabe: GitHub
* Erstelle ein GitHub-Repository und pushe den Code.