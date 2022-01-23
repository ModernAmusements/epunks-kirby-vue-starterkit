# epunks Kirby + Vue.js Bootstrap 5 starterkit 
---

The frontend:

1. **NUXT** - der [vue-nuxt](vue-nuxt) Ordner. Schließlich verwendet auch dieses Projekt JSON-Inhaltsrepräsentationen, um den Inhalt zu holen, enthält aber auch viele der Goodies, die [Nuxt.js](https://nuxtjs.org) zu bieten hat (einschließlich der statischen Seitengenerierung)!
1. **Bootstrap 5** -[bootstrap5](bootstrap5) [Bootstrap.css](https://getbootstrap.com/docs/5.0/getting-started/introduction/)


## Anforderungen

- Node.js mit npm ist für die Installation der Projekte erforderlich
- Kirby läuft auf PHP 7.1+
  - Kirby ist **nicht** eine freie Software. Sie können es kostenlos auf Ihrem lokalen Rechner ausprobieren, aber um Kirby auf einem öffentlichen Server zu betreiben, müssen Sie eine gültige Lizenz unter https://getkirby.com/buy erwerben.

## Setup
1. copy and rename .env.production -> .env
1. `cd` into its folder frontend (vue-nuxt)
2. run `npm install`
5. run `npm run dev`
6. Kirby running at: http://127.0.0.1:8000  
7. Create Admin
shady@epunks.de
epunks2011

## Verwendung

#### Frontend

Beachten Sie unbedingt die README im Projektordner Ihrer gewählten Variante.

#### Backend

Das Backend wird bei der Entwicklung mit dem eingebauten PHP-Entwicklungsserver automatisch bedient.

#### Mehrsprachige Website

Folgen Sie einfach dieser Anleitung, um mehrere Sprachen in Kirby zu aktivieren: https://getkirby.com/docs/guide/languages/introduction, und vergessen Sie nicht, Ihren Nutzern die Möglichkeit zu geben, zwischen diesen Sprachen zu wechseln (https://getkirby.com/docs/guide/languages/switching-languages) :)

Ich empfehle, neue Sprachen über das Panel hinzuzufügen, und zwar wegen dieses netten kleinen Details:

> Das Panel benennt automatisch alle vorhandenen Inhalts- und Metadatendateien um und fügt die Spracherweiterung hinzu.

## Konfig

Die gesamte Kirby-bezogene Konfiguration befindet sich in der Datei [kirby.config.js](kirby.config.js):

- `serve` gibt an, ob das Backend während der Entwicklung automatisch bedient werden soll
  - `host` und `port` gibt die Adresse an, unter der das Backend betrieben werden soll
- `inject` gibt an, ob die erstellte Vue-App direkt in Kirby injiziert werden soll
  - Dies ist nützlich, wenn Sie das Frontend von Kirby durch Ihre Vue-Anwendung _ersetzen_ wollen (z.B. wenn Sie wollen, dass Ihre Vue-Anwendung im gleichen Verzeichnis und unter der gleichen URL wie Kirby liegt und Ihr Frontend _anstatt_ der Templates von Kirby bedient wird)
  - wenn dies **true** ist, denken Sie daran, auch `kirby-vue-starterkit.plugin.useVueIndex` in [kirby/site/config/config.php](kirby/site/config/config.php) auf **true** zu setzen, so dass alles zu Ihrer Vue-App umgeleitet wird, anstatt zu Kirbys Templates
  - `base`, `assetsDir` und `indexPath` geben an, wo Sie die Teile der erstellten Vue-Applikation einbinden wollen

## Bereitstellen

Stellen Sie den Inhalt des Ordners "Kirby" auf dem Produktionsserver bereit.

> ⚠️ Wenn Sie auch in Kirby injizieren, stellen Sie sicher, dass Sie die Vue-App _zuerst_ bauen, so dass der Ordner "Kirby" alles Notwendige enthält.

> ⚠️ Vergessen Sie nicht, `debug` und `allowInsecure` (wenn Sie auf https deployen) auf **false** in [kirby/site/config/config.php](kirby/site/config/config.php) zu setzen

