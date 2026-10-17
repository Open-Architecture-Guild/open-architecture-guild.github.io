# open-architecture-guild.github.io

Webseite der Open Architecture Guild: https://open-architecture-guild.github.io

Jekyll-Seite, gebaut vom eingebauten GitHub-Pages-Build. Es gibt keinen Workflow und keine Anfragen an Dritte. Das Aussehen kommt aus dem Theme-Repo [`guild-theme`](https://github.com/Open-Architecture-Guild/guild-theme), die Inhalte stehen hier in `_data/` und in den Seiten.

## Wo man was ändert

| Was | Wo |
|---|---|
| Texte der Startseite (Projekte, Entscheidungen, Mitmachen …) | `_data/home.yml` |
| Menü, Hinweisband, Fußzeile | `_data/navigation.yml`, `_data/notice.yml`, `_data/footer.yml` |
| Titel, Beschreibung, Theme-Version | `_config.yml` |
| Impressum, Datenschutz, weitere Textseiten | Markdown-Dateien mit `layout: page` |
| Farben, Layout | im Repo `guild-theme` |

Jede Seite hat unten einen Link „Diese Seite auf GitHub bearbeiten“; auf der Startseite führt er zu `_data/home.yml`.

## Einstellungen im Repo

*Settings → Pages → Source* muss auf **Deploy from a branch** stehen (Branch `main`, Ordner `/ (root)`). Steht sie auf „GitHub Actions“, wird nichts veröffentlicht, weil es keinen Workflow mehr gibt. Eine Datei `.nojekyll` darf es nicht geben.

Das Theme-Repo muss öffentlich sein. Die Version steht in `_config.yml` bei `remote_theme` (aktuell `@v0.1.0`). Für ein Theme-Update im Theme-Repo einen neuen Tag setzen und hier eintragen.

## Lokal ansehen

Braucht Ruby und Internetzugang (das Theme wird von GitHub geladen):

```
bundle install
bundle exec jekyll serve
```

Dann `http://localhost:4000` öffnen. Zum Ändern des Themes ohne Veröffentlichung `_layouts/`, `_includes/` und `assets/` aus dem Theme-Repo hierher kopieren; lokale Dateien haben Vorrang. Vor dem Einchecken wieder entfernen und im Theme-Repo ändern.

## Vor dem Go-live

1. `impressum.md` und `datenschutz.md` ausfüllen, rechtlich prüfen lassen und danach `noindex` und `sitemap: false` entfernen. Wer Anbieter der Seite ist, ist offen.
2. `capabilities/index.md` ist ein Platzhalter. Sobald die Map dort gebaut wird, diese Datei löschen.
3. Das Band „Stand des Katalogs“ zeigt einen Hinweistext. Zahlen aus dem Katalog-Build gibt es noch nicht.
4. Reifegrade und offene Entscheidungen in `_data/home.yml` bei Änderungen am Stand aktualisieren.
5. Die Aussage „setzt keine Cookies und lädt nichts von Dritten“ stimmt nur, solange das Theme keine Schriften oder Skripte von Dritten einbindet.

## Nicht enthalten

Englische Fassung, Wissens- und Governance-Seiten, Suche, Kennzahlen aus dem Katalog-Build (Roadmap W2 bis W4). Für den Build der Map nach `/capabilities/` braucht es später eine eigene Action oder das Einchecken der gebauten Dateien; der Branch-Build von GitHub führt kein Node aus.

## Lizenz

Vorläufig MIT wie die übrigen Repos der Organisation, bis ADR-0001 entschieden ist.
