# Das Vermächtnis des Wolfes

Ein digitales Dungeons-&-Dragons-Kampagnenbuch als browserbasierte Web-App.  
Das Projekt dient als interaktiver Begleiter für eine laufende D&D-Gruppe: Quests, Orte, NPCs, Gruppengold, Kampagnennotizen und Charakterinformationen werden an einem Ort gesammelt und direkt im Browser verwaltet.

Die Anwendung ist bewusst leichtgewichtig gehalten: kein Backend, keine Datenbank, keine Frameworks. Alle wichtigen Kampagnendaten werden lokal im Browser gespeichert. Damit eignet sich das Projekt sowohl als persönliches Spielleiter-Werkzeug als auch als Grundlage für ein erweiterbares Open-Source- oder Hobbyprojekt mit Fantasy-Flair.

## Features

### Aktuell umgesetzt

- **Dashboard**
  - Übersicht über zentrale Kampagneninformationen
  - Verwaltung des Gruppengolds
  - Speicherung des Goldwerts im `localStorage`

- **Kampagnentagebuch**
  - Freie Notizen für Ereignisse, Hinweise und Spielleitergedanken
  - Persistente Speicherung im Browser
  - Geeignet für fortlaufende Kampagnenchroniken

- **Questlog**
  - Neue Quests hinzufügen
  - Quests als erledigt oder offen markieren
  - Quests löschen
  - Speicherung aller Questdaten im `localStorage`

- **Orte-System**
  - Wichtige Schauplätze der Kampagne erfassen
  - Orte löschen
  - Lokale Speicherung im Browser

- **NPC-Verzeichnis**
  - Nichtspielercharaktere hinzufügen
  - NPCs löschen
  - Persistente Verwaltung über `localStorage`

- **Heldengruppe**
  - Mehrere Charakterkarten für die Spielergruppe
  - Darstellung grundlegender Charakterdaten wie Level, Werte und weitere Kampagneninformationen
  - Bearbeitbare Felder sind teilweise vorhanden und werden weiter ausgebaut

- **Lokale Datenspeicherung**
  - Keine externe Datenbank erforderlich
  - Keine Benutzerkonten oder Serverlogik
  - Daten bleiben auf dem jeweiligen Gerät und im jeweiligen Browserprofil

## Technologie-Stack

Das Projekt setzt auf klassische Webtechnologien und bleibt dadurch einfach zu starten, zu verstehen und zu erweitern.

| Bereich | Technologie |
| --- | --- |
| Struktur | HTML5 |
| Styling | CSS3 |
| Logik | Vanilla JavaScript |
| Speicherung | LocalStorage API |
| Architektur | Statische Web-App ohne Backend |
| Laufzeit | Browser |

Es werden keine Frameworks, Build-Tools oder serverseitigen Komponenten benötigt. Die App kann direkt lokal geöffnet oder komfortabel über eine lokale Entwicklungsumgebung wie VS Code mit Live Server ausgeführt werden.

## Projektstruktur

Eine typische Struktur für dieses Projekt sieht wie folgt aus:

```text
Das-Vermaechtnis-des-Wolfes/
|-- index.html
|-- style.css
|-- script.js
`-- README.md
```

### Dateiübersicht

- `index.html`  
  Enthält die Grundstruktur der Web-App, die sichtbaren Bereiche des Kampagnenbuchs und die Verbindung zu Stylesheet und JavaScript.

- `style.css`  
  Definiert das visuelle Erscheinungsbild der Anwendung, darunter Pergament-Optik, Fantasy-Farben, Layout, Karten, Buttons und responsive Anpassungen.

- `script.js`  
  Enthält die interaktive Logik der App: Eingaben verarbeiten, Daten im `localStorage` speichern, Listen rendern, Elemente aktualisieren und gelöschte Einträge entfernen.

- `README.md`  
  Dokumentiert Zweck, Nutzung, technischen Aufbau und geplante Weiterentwicklung des Projekts.

Falls das Projekt später größer wird, kann die Struktur modular erweitert werden:

```text
Das-Vermaechtnis-des-Wolfes/
|-- assets/
|   |-- images/
|   `-- icons/
|-- css/
|   `-- style.css
|-- js/
|   |-- app.js
|   |-- storage.js
|   |-- quests.js
|   |-- npcs.js
|   |-- locations.js
|   `-- characters.js
|-- index.html
`-- README.md
```

Diese Aufteilung ist besonders sinnvoll, sobald einzelne Bereiche wie Quests, NPCs, Orte oder Charakterbögen umfangreicher werden.

## Nutzung / Installation

### Voraussetzungen

- Ein moderner Browser, zum Beispiel Chrome, Firefox, Edge oder Brave
- Optional: [Visual Studio Code](https://code.visualstudio.com/)
- Optional: VS-Code-Erweiterung **Live Server**

### Projekt lokal starten

1. Repository oder Projektordner lokal öffnen.
2. Die Datei `index.html` im Browser starten.
3. Alternativ in VS Code:
   - Projektordner öffnen
   - Erweiterung **Live Server** installieren
   - Rechtsklick auf `index.html`
   - **Open with Live Server** auswählen

Die App läuft anschließend lokal im Browser. Änderungen an HTML, CSS oder JavaScript können direkt im Projekt vorgenommen und nach dem Neuladen der Seite betrachtet werden.

### Nutzung im Spiel

Das Kampagnenbuch kann während einer Session als digitale Spielleiter- oder Gruppenübersicht genutzt werden:

- Gruppengold nach Beute oder Einkäufen aktualisieren
- Quests während des Abenteuers ergänzen oder abschließen
- Neue Orte und NPCs direkt eintragen
- Notizen im Kampagnentagebuch festhalten
- Charakterinformationen als schnelle Referenz verwenden

## Speicherungskonzept

Die Anwendung speichert ihre Daten lokal im Browser über die **LocalStorage API**.

`localStorage` ist ein einfacher Speicherbereich des Browsers, in dem Schlüssel-Wert-Paare dauerhaft abgelegt werden können. Im Gegensatz zu normalen JavaScript-Variablen bleiben diese Daten auch nach einem Neuladen der Seite oder dem Schließen des Browsers erhalten.

### Vorteile

- Keine Datenbank notwendig
- Keine Serverkosten
- Sehr einfache technische Architektur
- Daten bleiben lokal beim Nutzer
- Ideal für kleine bis mittlere persönliche Kampagnenprojekte

### Einschränkungen

- Daten sind an Browser und Gerät gebunden
- Kein automatischer Sync zwischen mehreren Geräten
- Beim Leeren der Browserdaten können Kampagnendaten verloren gehen
- Mehrere Nutzer können nicht gleichzeitig an denselben Daten arbeiten
- Für Backups ist ein späterer Export sinnvoll

### Empfohlene Speicherbereiche

Die App kann ihre Daten zum Beispiel unter getrennten Schlüsseln speichern:

```text
campaignGold
campaignNotes
quests
locations
npcs
characters
```

Komplexere Daten wie Quests, Orte, NPCs oder Charaktere sollten als JavaScript-Objekte beziehungsweise Arrays verwaltet und per `JSON.stringify()` gespeichert werden. Beim Laden der Seite können sie mit `JSON.parse()` wiederhergestellt werden.

## Geplante Features / Roadmap

Die folgenden Erweiterungen bilden die nächsten Kapitel im Ausbau von **Das Vermächtnis des Wolfes**.

### Charaktere und Heldengruppe

- Vollständig editierbare Charakterbögen
- Anpassbare Namen, Level, Attribute, Trefferpunkte und Hintergrundinformationen
- Charakterbilder
- Ausrüstung und persönliche Notizen
- HP-, XP- und Level-System mit Buttons
- Inventar-System pro Charakter
- Zauberlisten für Magier, Kleriker und andere zauberwirkende Klassen

### Kampagnenverwaltung

- Sitzungsprotokoll-System für Session Recaps
- Bessere Trennung zwischen aktiven, abgeschlossenen und gescheiterten Quests
- Drag-and-Drop Quest-Management
- Erweiterte Notizbereiche für Spielleiterinformationen
- Export und Import der gesamten Kampagne als JSON-Datei

### Welt und Inhalte

- Erweiterte NPC-Datenbank
- NPC-Beschreibungen, Beziehungen, Fraktionen und Bilder
- Interaktive Weltkarte mit klickbaren Orten
- Detailseiten oder ausklappbare Panels für wichtige Orte
- Verknüpfungen zwischen Quests, Orten und NPCs

### Spieltisch-Werkzeuge

- Würfelroller für `d20`, `d12`, `d10`, `d8`, `d6` und `d4`
- Modifikatoren für Proben und Angriffe
- Schnellzugriff auf häufige Würfe
- Optionale Zufallstabellen für Begegnungen, Beute oder Gerüchte

### UI und Atmosphäre

- Stärkeres Dark-Fantasy-Buchgefühl
- Überarbeitete Pergament- und Lederoptik
- Bessere mobile Darstellung
- Klarere Navigation zwischen Kapiteln des Kampagnenbuchs
- Visuelle Hervorhebung wichtiger Kampagnenereignisse

## Ziel des Projekts / Vision

**Das Vermächtnis des Wolfes** soll mehr sein als eine Sammlung von Formularen. Die App soll sich anfühlen wie ein lebendiges Kampagnenbuch: ein digitales Artefakt, das mit jeder Session wächst, alte Entscheidungen bewahrt und neue Abenteuer vorbereitet.

Die Vision ist ein leicht bedienbares Werkzeug für D&D-Runden, das Spielleitern und Spielern hilft, den Überblick über die Kampagne zu behalten:

- Was ist passiert?
- Welche Quests sind noch offen?
- Welche NPCs spielen eine Rolle?
- Welche Orte wurden entdeckt?
- Wie entwickelt sich die Heldengruppe?
- Welche Spuren führen tiefer in die Geschichte?

Dabei bleibt das Projekt bewusst lokal, transparent und einfach wartbar. Es soll ohne komplexe Infrastruktur funktionieren und trotzdem genug Raum bieten, um Schritt für Schritt zu einem vollwertigen digitalen Kampagnenarchiv zu wachsen.

## Hinweise für Entwickler

### Bestehende Struktur respektieren

Da das Projekt ohne Framework arbeitet, ist eine klare Trennung der Verantwortlichkeiten besonders wichtig:

- HTML für Struktur
- CSS für Darstellung
- JavaScript für Logik und Daten
- `localStorage` für Persistenz

Neue Features sollten möglichst so gebaut werden, dass sie einen eigenen klaren Bereich im Code haben. Wenn `script.js` zu groß wird, lohnt sich eine Aufteilung in mehrere JavaScript-Dateien.

### Datenmodelle früh definieren

Für wiederkehrende Inhalte wie Quests, NPCs, Orte und Charaktere sollten einheitliche Datenstrukturen verwendet werden.

Beispiel für eine Quest:

```js
{
  id: "quest-001",
  title: "Die Spur des Wolfes",
  description: "Die Gruppe folgt alten Zeichen im Grenzwald.",
  done: false,
  createdAt: "2026-06-15"
}
```

Beispiel für einen NPC:

```js
{
  id: "npc-001",
  name: "Alaric Graumantel",
  role: "Waldläufer",
  description: "Ein schweigsamer Führer mit Wissen über die alten Pfade.",
  relationship: "Verbündeter"
}
```

Stabile IDs erleichtern später Funktionen wie Bearbeiten, Verknüpfen, Sortieren, Exportieren und Importieren.

### LocalStorage kapseln

Speicherlogik sollte nach Möglichkeit nicht überall im Code verstreut sein. Eine kleine Hilfsschicht kann wiederkehrende Aufgaben vereinfachen:

```js
function saveData(key, value) {
  localStorage.setItem(key, JSON.stringify(value));
}

function loadData(key, fallback) {
  const saved = localStorage.getItem(key);
  return saved ? JSON.parse(saved) : fallback;
}
```

Dadurch bleiben spätere Änderungen leichter umsetzbar, zum Beispiel wenn Export/Import, Validierung oder Versionsnummern für gespeicherte Daten hinzukommen.

### Render-Funktionen klein halten

Jeder größere Bereich sollte eine eigene Render-Funktion erhalten:

- `renderQuests()`
- `renderLocations()`
- `renderNpcs()`
- `renderCharacters()`

So bleibt nachvollziehbar, welcher Teil der Oberfläche nach einer Datenveränderung aktualisiert werden muss.

### Datenmigration einplanen

Wenn sich Datenstrukturen ändern, können alte `localStorage`-Einträge inkompatibel werden. Für größere Erweiterungen ist deshalb eine einfache Versionslogik sinnvoll:

```text
campaignDataVersion = 1
```

Bei zukünftigen Updates kann die App prüfen, ob gespeicherte Daten aktualisiert oder mit Standardwerten ergänzt werden müssen.

### Export und Backup priorisieren

Da alle Daten lokal im Browser liegen, ist ein Export-Feature langfristig besonders wichtig. Ein JSON-Export kann als Sicherung dienen und erlaubt später auch den Umzug auf ein anderes Gerät.

Empfohlener Ansatz:

- Alle relevanten Daten aus `localStorage` sammeln
- Als JSON-Datei herunterladen
- Import-Funktion mit Validierung ergänzen
- Optional eine Versionsnummer in die Exportdatei schreiben

### UI konsistent erweitern

Neue Oberflächenelemente sollten das vorhandene Fantasy-/Pergament-Design aufnehmen:

- Wiederverwendbare Kartenlayouts
- Einheitliche Buttons
- Lesbare Kontraste
- Klare Formularfelder
- Zurückhaltende Animationen
- Responsive Layouts für kleinere Bildschirme

Das Ziel ist eine Atmosphäre wie ein altes Kampagnenbuch, aber mit der Bedienbarkeit eines modernen Webtools.

## Status

Das Projekt befindet sich in aktiver Entwicklung. Die Grundfunktionen für Kampagnenverwaltung und lokale Speicherung sind vorhanden oder teilweise umgesetzt. Der nächste große Schritt ist der Ausbau der Charakterverwaltung und die stärkere Strukturierung der gespeicherten Kampagnendaten.

---

Möge das Rudel seine Spuren bewahren.
