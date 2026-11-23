# ZIMT Agent Contract — Doctrine 7.0

**Verbindlich:** `docs/DEVELOPMENT_DOCTRINE.md`, neuester ausdrücklicher Nutzerauftrag, `docs/ACTIVE_SCOPE.md`, `docs/WORK_QUEUE.md`, tatsächlicher Code und Testbelege. Historische Pläne sind keine aktive Autorisierung.

## Kontinuierliche Ausführung
1. Prüfe Repository, Branch/HEAD, aktuellen Nutzerauftrag, ACTIVE_SCOPE, Doctrine, Architektur, Queue und vorhandene Evidenz; lies nur das für die nächste Entscheidung Nötige.
2. Trenne **Produkt-Soll** (Auftrag/Scope), **technisches Ist** (Code/Tests) und **Regeln** (Doctrine/Verträge). P0: kein Datenverlust, keine Geheimnisoffenlegung, keine erfundenen Tests/Artefakte.
3. Ermittele alle unerfüllten autorisierten Akzeptanzkriterien und bekannten Bugs; decke jedes durch eine offene Aufgabe oder begründetes BLOCKED/DEFERRED ab. **Prioritäten begrenzen niemals die Zahl der autorisierten Funktionen.**
4. Wähle die wertvollste READY-Aufgabe nach Nutzen, Risiko, Abhängigkeit und Aufwand. Implementiere einen kleinen vollständigen vertikalen Slice mit allen betroffenen UI-, State-, Daten-, Motion-/Haptik-, Lifecycle- und Fehlerpfaden.
5. Führe risikogerechte Tests wirklich aus, lies Logs, korrigiere Fehler. Dokumentiere exakte SHAs und echte Belege. Trenne READY/IN_PROGRESS/BLOCKED/IMPLEMENTED/VERIFIED/DEFERRED von UNVERIFIED/CI_VERIFIED/DEVICE_VERIFIED.
6. Gleiche danach **gesamten Scope** und Queue erneut ab und arbeite unmittelbar an der nächsten wertvollen READY-Aufgabe. **Ein Commit, Build, Checkpoint, Agentenbericht oder eine leere Queue ist kein Endsignal.**
7. Bei Blockern sichere Alternativen prüfen, unabhängige Arbeit fortsetzen; nicht endlos dieselbe fehlgeschlagene Aktion wiederholen. Nur bei echter Unsicherheit Alternativen vergleichen; keine Entscheidungen ohne neue Evidenz erneut öffnen.
8. Parallel nur disjunkte Arbeit mit Owner, Vertrag, Merge-Reihenfolge und frischem HEAD. Keine unbewiesene Integration behaupten.
9. Refactoring nur mit konkretem Nutzen oder Risiko; keine spekulativen Universalframeworks. Vorhandene UI-Technologie, Daten, IDs, Signatur, Android-Kompatibilität und spätere ZIMT-Integration schützen.
10. Gesten: eine maßgebliche Zustandsmaschine. Animationen dürfen keine destruktiven Datenoperationen besitzen. Semantische Haptik; reale Geräte statt API-Erfolgsbehauptungen. Reduced Motion und Accessibility beachten.
11. Vor jedem Stopp: **alle** autorisierten Akzeptanzkriterien, Bugs, Prüfungen, Abhängigkeiten und unabhängigen READY-Aufgaben prüfen. Nur `DONE`, `NO_READY_WORK`, `NEEDS_DECISION`, `SAFETY_STOP`, `ENVIRONMENT_LIMIT` als Endgrund; reale Grenzen ehrlich benennen.
12. Kein autonomes Fortsetzen ohne tatsächlich eingerichteten und überprüften erneuten Agentenaufruf behaupten.

## Projektkontext
**Lab 4:** Konkreter Produktbrief und Android-Technologie sind bislang nicht bestätigt. Keine Produktdetails oder SDK-Werte aus anderen Labs kopieren. Governance/Scope-Klärung und vorhandene Struktur sicher pflegen; danach erst autorisierte Features umsetzen. Eigenständig installierbar und später ZIMT-integrierbar.


## Engineering Legibility Protocol 1.0
Verbindlich ergänzend zur Development Doctrine: [ELP 1.0](docs/ENGINEERING_LEGIBILITY_PROTOCOL.md). Bei jeder relevanten Änderung verständliche Verantwortlichkeiten, explizite Datenwirkungen und nachvollziehbare Übergaben sicherstellen. Bestehende Dokumente und Nachweise nutzen; konkrete Probleme in der kanonischen Queue priorisieren. Keine separate Aufräumphase, keine zusätzlichen pauschalen Gates; Doctrine 7.0 bleibt unverändert maßgeblich.
