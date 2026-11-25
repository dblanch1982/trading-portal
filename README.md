# Trading Portal

Angular-Grundgerüst für das Trading Portal mit Standalone-Komponenten und
Angular-Routing.

## Voraussetzungen

- Node.js 20.19+ oder 22.12+
- npm

## Entwicklung

```bash
npm install
npm start
```

Die Anwendung ist anschließend unter `http://localhost:4200` erreichbar.

## Projektstruktur

```text
src/
  app/
    features/
      dashboard/
    app.config.ts
    app.routes.ts
    app.ts
  index.html
  main.ts
  styles.css
```

Produktionsbuild: `npm run build`

## Container-Image

Bei jedem Push auf `main` baut GitHub Actions das Docker-Image und veröffentlicht
es in der GitHub Container Registry als `ghcr.io/<owner>/<repository>:latest`
und mit einem unveränderlichen Commit-Tag (`sha-<commit>`). Zum Abruf des Images
muss das GitHub-Paket gegebenenfalls in den Paket-Einstellungen auf öffentlich
gestellt werden.
