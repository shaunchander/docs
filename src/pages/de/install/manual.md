---
title: Manuelle Installation von Astro
description: So installierst du Astro manuell mit NPM, PNPM oder Yarn.
layout: ~/layouts/MainLayout.astro
setup: import InstallGuideTabGroup from '~/components/TabGroup/InstallGuideTabGroup.astro';
---
Bist du bereit, Astro zu installieren? In dieser Installationsanleitung findest du alle Informationen, um direkt loszulegen.

#### Voraussetzungen

- **Node.js** - `14.15.0`, `v16.0.0` oder höher.
- **Texteditor** - Wir empfehlen [VS Code](https://code.visualstudio.com/) mit unserer [offiziellen Astro-Erweiterung](https://marketplace.visualstudio.com/items?itemName=astro-build.astro-vscode).
- **Terminal** - Astro wird über seine Befehlszeilenschnittstelle (CLI) gesteuert.

<InstallGuideTabGroup />

#### So funktioniert die manuelle Installation

Falls du keine [automatische Installation](/de/install/auto/) mit unserem Assistenten `create-astro` durchführen möchtest, kannst du dein Astro-Projekt mit dieser Anleitung selbst einrichten.


## 1. Erstelle ein Projektverzeichnis

Erstelle ein leeres Verzeichnis mit dem Namen deines Projekts und wechsle dann hinein.

```bash
mkdir mein-astro-projekt
cd mein-astro-projekt
```

Sobald du dich in deinem neuen Verzeichnis befindest, erstelle die Projektdatei `package.json`. Damit verwaltest du die für dein Projekt erforderlichen Pakete, einschließlich Astro. Wenn du mit diesem Dateiformat nicht vertraut bist, führe den folgenden Befehl aus, um die Datei für dich erstellen zu lassen:

```bash
npm init --yes
```


## 2. Installiere Astro

Füge zuerst Astro zu den erforderlichen Paketen deines Projekts hinzu:

```bash
npm install astro
```

Ersetze dann jegliche Platzhalter im Abschnitt `scripts` der Datei `package.json` mit folgenden Astro-Skripts:

```diff
  "scripts": \{
-    "test": "echo \"Error: no test specified\" && exit 1"
+    "dev": "astro dev",
+    "start": "astro dev",
+    "build": "astro build",
+    "preview": "astro preview"
  },
```

Du kannst diese Skripts später verwenden, um Astro zu starten und seine verschiedenen Befehle auszuführen.


## 3. Erstelle deine erste Seite

Verwende deinen Texteditor, um im Projektverzeichnis eine neue Datei mit dem Pfad `src/pages/index.astro` zu erstellen. Sie wird die erste Astro-Seite deines Projekts.

Kopiere im Rahmen dieser Anleitung den folgenden Code-Schnipsel (einschließlich der Bindestriche `---`) und füge ihn in deine neue Datei ein:

```astro
---
// Willkommen bei Astro! Alles innerhalb dieses mit drei Bindestrichen
// vom Rest getrennten Abschnitts nennt man "Komponenten-Frontmatter".
// Der Code hier wird nie im Browser ausgeführt.
console.log('Das wird in deinem Terminal ausgeführt, nicht im Browser!');
---
<!-- Nun folgt deine "Komponenten-Vorlage". Sie besteht aus HTML,
     ergänzt durch einen Hauch an Magie, um dir beim Erstellen
     großartiger Vorlagen zu helfen. -->
<html>
  <body>
    <h1>Hallo Welt!</h1>
  </body>
</html>
<style>
  h1 {
    color: orange;
  }
</style>
```


## 4. Erstelle deine erste statische Ressource

Du solltest auch ein `public/`-Verzeichnis erstellen, um deine statischen Ressourcen zu speichern. Astro kopiert diese Ressourcen beim Buildvorgang immer unverändert in das Ausgabeverzeichnis, sodass du sie sicher aus deinen Komponentenvorlagen heraus referenzieren kannst.

Erstelle in deinem Texteditor eine neue Datei mit dem Pfad `public/robots.txt`. Die Datei `robots.txt` wird von den meisten Websites verwendet, um Suchmaschinen wie Google mitzuteilen, wie sie die Website behandeln sollen.

Kopiere im Rahmen dieser Anleitung den folgenden Code-Schnipsel in die Datei:

```
# Beispiel: Erlaube allen Suchmaschinen, diese Website zu scannen
# und in den Suchindex aufzunehmen.
# Volle Syntax: https://developers.google.com/search/docs/advanced/robots/create-robots-txt
User-agent: *
Allow: /
```


## 5. Erstelle `astro.config.mjs`

Astro wird über die Datei `astro.config.mjs` konfiguriert. Diese Datei ist optional, aber für den Fall, dass du später Änderungen an der Konfiguration vornehmen willst, kannst du sie schon jetzt erstellen.

Erstelle die Datei `astro.config.mjs` im Stammverzeichnis deines Projekts und kopiere den folgenden Code hinein:

```
import { defineConfig } from 'astro/config';

// https://docs.astro.build/de/reference/configuration-reference/
export default defineConfig({});
```

Falls du [UI-Frameworks](/de/core-concepts/framework-components/) wie React, Svelte usw. einsetzen möchtest, oder dein Projekt um praktische Tools wie Tailwind oder Partytown erweitern willst, ist dies die richtige Stelle, um die manuelle [Einbindung und Konfiguration von Integrationen](/de/guides/integrations-guide/) vorzunehmen.

📚 Weitere Informationen findest du in unserer [Konfigurationsreferenz](/de/reference/configuration-reference/).


## 6. Nächste Schritte

Wenn du alle Schritte befolgt hast, sollte dein Projektverzeichnis nun so aussehen:

```
├── node_modules/
├── src/
│   └── pages/
│       └── index.astro
├── public/
│   └── robots.txt
├── astro.config.mjs
├── package.json
└── package-lock.json (oder yarn.lock, pnpm-lock.yaml usw.)
```

Herzlichen Glückwunsch, du hast Astro eingerichtet und kannst jetzt loslegen!

Wenn du diese Anleitung komplett befolgt hast, kannst du direkt fortfahren und zum ersten Mal [Astro starten](/de/install/auto/#3-starte-astro-).
