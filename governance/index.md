---
layout: page
title: Governance
lede: "Wie die Gilde Entscheidungen trifft, und welche gerade anstehen."
status: Entwurf
---

Diese Regeln sind ein Vorschlag, der sich am Aufbau des Katalogs ausrichtet. Sie gelten in dieser Form erst, wenn das Council sie beschlossen hat; das Council selbst ist noch nicht besetzt.

## Zweck

Die Gilde pflegt offene Referenzmodelle. Governance bedeutet hier nur: Jede Änderung ist öffentlich sichtbar, wird nach festen Regeln geprüft, und wichtige Entscheidungen sind mit Begründung nachlesbar.

## So läuft eine Änderung

1. **Vorschlag.** Ein Issue oder eine Diskussion beschreibt, was sich ändern soll und warum (bei größeren Änderungen als RFC).
2. **Pull Request.** Die Änderung wird als Pull Request eingereicht.
3. **Review.** Curators und andere prüfen sie anhand einer Checkliste. Automatische Prüfungen testen Schema, Namensregeln und Verweise.
4. **Übernahme.** Bei Zustimmung wird die Änderung in den Hauptzweig übernommen.
5. **Release.** Änderungen werden gebündelt und mit einer Versionsnummer veröffentlicht.

Für größere Änderungen ist eine Kommentierungsfrist von 14 Tagen als Startwert vorgesehen. Auch dieser Wert ist noch nicht beschlossen.

## Wer entscheidet

| Gremium | Aufgabe | Zusammensetzung |
|---|---|---|
| Curators | Prüfen Änderungen am Katalog und halten die Regeln ein | zu Beginn 2 bis 4 Personen |
| Council | Grundsatzentscheidungen, neue Projekte, Besetzung der Rollen | 3 bis 5 Personen, gestaffelte Amtszeiten |

Ausnahmen von den Regeln brauchen eine Begründung und einen Eintrag im Register.

## Entscheidungsregister {#register}

Wichtige Entscheidungen halten wir als Architecture Decision Records (ADR) fest: Frage, Optionen, Entscheidung, Begründung. Die Übersicht zeigt, was offen ist und was schon feststeht. Mitreden geht in den [Discussions](https://github.com/orgs/Open-Architecture-Guild/discussions).

### Offen

<table>
<thead><tr><th scope="col">Nr.</th><th scope="col">Thema</th><th scope="col">Frage</th></tr></thead>
<tbody>
{% for d in site.data.adrs.open %}
<tr><td>{% if d.ref %}{{ d.ref }}{% else %}–{% endif %}</td><td>{{ d.title }}</td><td>{{ d.question }}{% if d.note %} <em>{{ d.note }}</em>{% endif %}</td></tr>
{% endfor %}
</tbody>
</table>

### Entschieden

<table>
<thead><tr><th scope="col">Thema</th><th scope="col">Entscheidung</th></tr></thead>
<tbody>
{% for d in site.data.adrs.decided %}
<tr><td>{{ d.title }}</td><td>{{ d.text }}</td></tr>
{% endfor %}
</tbody>
</table>

Die Entscheidungen unter „Entschieden“ stammen aus dem Aufbaukonzept des Gründungsteams. Sie sind getroffen, aber noch nicht als einzelne ADR im Repository erfasst.

## Dokumente

- [Beitragsregeln des Katalogs](https://github.com/Open-Architecture-Guild/Capabilities/blob/main/CONTRIBUTING.md)
- [Verhaltenskodex](https://github.com/Open-Architecture-Guild/Capabilities/blob/main/CODE_OF_CONDUCT.md)
- [Roadmap](/roadmap/)
