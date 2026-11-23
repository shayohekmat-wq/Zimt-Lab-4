# ZIMT DEVELOPMENT DOCTRINE 7.0
## Autonome Entwicklung mit maximaler sinnvoller Kontinuität
**Verbindlich für ZIMT und alle Labs · 23.11.2026.** Diese repositorylesbare Fassung übernimmt die operativen Regeln der vom Nutzer bereitgestellten Doctrine 7.0; das ursprüngliche Handbuch ist die maßgebliche ausführliche Referenz. Version 7.0 ersetzt ältere allgemeine Regeln, ohne bestehende Produktentscheidungen stillschweigend zu überschreiben.

**Leitsatz:** Arbeite sauber und arbeite weiter, solange du sinnvoll arbeiten kannst. **Außen maximalistisch, innen minimalistisch**: erstklassiges Erlebnis, einfache robuste Architektur, echte Qualitätsnachweise, minimaler Prozessaufwand.

## 0. Schnellstart
Prüfe Repository/Branch/HEAD, AGENTS, ACTIVE_SCOPE, diese Doctrine, Architektur, WORK_QUEUE und vorhandene Evidenz nur soweit entscheidungsrelevant. Ermittle aktuellen Auftrag, Nutzerabläufe, Akzeptanzkriterien und Nicht-Ziele; aktiviere keine historischen Ideen. Gleiche offene Kriterien und Defekte mit der Queue ab; ergänze fehlende Aufgaben. Implementiere den nächsten wertvollen vollständigen Slice, prüfe risikogerecht, sichere nur relevante Belege und arbeite unmittelbar weiter. Stoppe nur nach §5.

## 1. Autorität, Wahrheit, Priorität
**P0-Schranken:** Keine Geheimnisoffenlegung, kein stiller Datenverlust, keine erfundenen Tests, Freigaben oder Artefakte; Sicherheitskonflikte eskalieren. **Produkt-Soll:** neueste ausdrückliche Nutzerentscheidung und ACTIVE_SCOPE. **Technische Regeln:** Doctrine, AGENTS, Architektur-/Daten-/Integrationsverträge. **Technisches Ist:** aktueller Code, HEAD, Tests und tatsächliche CI-/Geräteprotokolle. **Momentaufnahmen:** Status/Evidence sind Berichte, keine konkurrierenden Produktpläne. Bei Konflikt Soll/Ist-Abweichung benennen und maßgebliche Quelle korrigieren. P0 Daten/Sicherheit/Ehrlichkeit; P1 UX/Design/Motion/Haptik/Accessibility; P2 Architektur/Tests/Kompatibilität/Performance; P3 nur nötige Prozesse. P0 legitimiert keine endlose Prozessarbeit.

## 2. Autorisierter Scope
Alle autorisierten Funktionen, Fehlerbehebungen, Verbesserungen und notwendigen Folgeschritte gehören zum Scope, **ohne numerische Obergrenze**. Die Queue priorisiert, begrenzt nicht den Auftrag. Neue Produktziele außerhalb des Scopes nur vorschlagen; bei unklarer Autorisierung allein betroffenen Teil pausieren und unabhängige sichere Arbeit fortsetzen.

## 3. Continuous Execution Loop
(1) Scope, offene Kriterien und Queue mit Code/Evidenz abgleichen. (2) Höchste sinnvolle READY-Aufgabe nach Nutzen/Risiko/Abhängigkeit/Aufwand wählen; nur bei echter Unsicherheit 1–3 Alternativen vergleichen. (3) Kohärenten Slice inklusive betroffener UI-, State-, Daten-, Motion-/Haptik-, Abbruchpfade implementieren. (4) Relevante Tests wirklich ausführen und Logs auswerten; fehlende Tests UNVERIFIED. (5) Relevante Git-/CI-Belege sichern, Queue bei Zustandswechsel aktualisieren. (6) Erneut gegen alle Akzeptanzkriterien abgleichen. (7) Fortsetzen, solange autorisierte wertvolle READY-Arbeit und reale Ressourcen vorhanden sind. **Commit, Build, Checkpoint oder Zwischenbericht sind keine Stoppsignale.** Keine künstlichen Wartezeiten oder redundante Berichte.

## 4. Kanonische Queue und Abdeckung
`docs/WORK_QUEUE.md` oder dokumentierter bereits etablierter äquivalenter Pfad; niemals zwei konkurrierende Queues. Pro Aufgabe ID, beobachtbares Ziel, Akzeptanzbezug, Priorität/Abhängigkeiten, Status, Verifikation, Evidenz, Blocker/nächste Aktion. Aufgabenstatus: READY, IN_PROGRESS, BLOCKED, IMPLEMENTED, VERIFIED, DEFERRED. Separat: UNVERIFIED, CI_VERIFIED (exakter SHA), DEVICE_VERIFIED (Gerät/OS/Build/Szenario); Einzeltests PASS/FAIL/UNVERIFIED. VERIFIED nur wenn **alle** erforderlichen Nachweise vorliegen. **Abdeckungsinvariante:** Jedes unerfüllte autorisierte Kriterium gehört zu einer offenen Aufgabe oder ist begründet BLOCKED/DEFERRED. Bekannte Bugs, Migrationen und fehlende Tests einbeziehen; keine Commit-Zählung als Fortschritt.

## 5. Abschlussprüfung
Vor jedem Stopp: Gesamten autorisierten Scope gegen beobachtbare Kriterien prüfen; fehlende Queue-Aufgaben und Folgearbeiten ergänzen; Blocker auf unabhängige ausführbare Teilaufgaben/Alternativen prüfen; verifizieren, dass keine verantwortbar ausführbare wertvolle READY-Aufgabe übrig ist. Nur diese Endgründe:
- **DONE:** alle autorisierten Kriterien erfüllt.
- **NO_READY_WORK:** vollständige Abdeckung, keine ausführbare wertvolle Arbeit, Blocker benannt.
- **NEEDS_DECISION:** eine Nutzerentscheidung blockiert *sämtliche* sinnvolle Arbeit.
- **SAFETY_STOP:** unverantwortbares Sicherheits-/Daten-/Release-Risiko.
- **ENVIRONMENT_LIMIT:** reale Zeit-, Kontext-, Berechtigungs- oder Werkzeuggrenze.
Eine leere Queue genügt nie. Kein Hintergrund-/Scheduler-Fortsetzen behaupten, wenn kein realer Folgeaufruf existiert.

## 6. Effizienz und Refactoring
Vor riskanter Änderung Ressourcen für Implementierung, angemessene Prüfung und Rückabwicklung einschätzen. Bei knappen Ressourcen kleine unabhängige READY-Aufgaben bevorzugen. Funktionierenden Code nur bei konkretem Defekt, Nutzen, Sicherheits-/Wartbarkeitsproblem oder unmittelbar nötiger Integration refaktorieren; keine spekulativen Frameworks, Renderer, Event-Busse. Diffs/SHAs/Logs wiederverwenden; Dokumentation proportional zum Risiko, nicht als Ersatz für Umsetzung.

## 7. Parallelisierung
Ein verantwortlicher Owner je Änderung. Parallel nur bei getrennten Dateien/Modulen, klaren Verträgen, geringer Koordination und gesicherter Merge-Reihenfolge; vor Merge HEAD prüfen, fremde Arbeit nicht überschreiben. Agentenrollen sind keine simulierte Freigabehierarchie. Unverifizierte Parallelarbeit nicht als integriert melden.

## 8. Risikogerechte Gates
**Creative Lab:** Herkunft/Lizenz und visuelle Prüfung. **Product Feature:** Szenario, fokussierte Tests, Build, Abbruch/Accessibility. **Safety Critical:** deterministische Zustände, Lifecycle/Fehler/Datenregression, Undo/Soft Delete. **Release & Migration:** exakter SHA, CI, App-ID, monotone Version, Originalsignatur, Upgrade über bestehende App mit Daten. Mehrere Gates können gelten; keine pauschale Bürokratie.

## 9. Engineering-Verträge
Pointer-/Sensoradapter → Ereignisse → **eine** maßgebliche Zustandsmaschine → UI → bestätigte Datenoperation im Use-Case/Repository. Slop, Scroll, Multitouch, Release, Rotation, Hintergrund, Wiederholung, Accessibility berücksichtigen. Destruktive Aktionen mit explizitem Commit-Punkt, Idempotenz, Undo/Soft Delete; Animations-Coroutine besitzt niemals allein die Datenoperation. Stabile IDs, versionierte Schemata, explizite nichtdestruktive Migration, Prozess-/Offline-/Update-Datenerhalt, versionierter Export/Import und Restore vor relevanten Releases. Sync nach Bedarf: Auth, Mitgliedschaften, Idempotenz, Konflikte, Tombstones, Reconnect. Andere App-ID braucht getesteten Export/Import oder serverseitige Migration. Java/Canvas und Kotlin/Compose dürfen koexistieren; Shared Modules nur bei echtem wiederkehrendem Bedarf.

## 10. Design, Motion, Haptik
Animation ist Produktqualität: sofortige Reaktion, Hauptbewegung, Materialnachlauf, optionaler spielerischer Akzent. Jede Animation braucht definierten Zustand, Unterbrechung/Wiederaufnahme, Reduced Motion, Offscreen-/Background-Pause und verlässliches Ende. Haptik semantisch und geräteabhängig; API-Erfolg beweist keine fühlbare Wirkung. Screenshots/Aufnahmen sind Designbelege; grüner Build allein nicht.

## 11. Kompatibilität und Performance
Moto G6 für ältere Hardware, Nothing Phone 3a als modernes Gerät. Historisch Lab 1 Java/Canvas minSdk23 und Lab 2 Compose minSdk26; **vor Änderungen aktuellen Build prüfen**. Neue Labs wählen minSdk bedarfsgerecht. Zuerst Eingabelatenz/Gestensicherheit, dann Overdraw, Redraw, Speicher, Temperatur. Release-nahe echte Geräte; Kaltstart, 100 Interaktionen, parallele Animationen, Hintergrund/Rotation, 15 Minuten, Neustart-Persistenz risikogerecht prüfen. Bei Bedarf P50/P95/P99, Frames, Speicher, Thermik über mindestens drei vergleichbare Läufe. 16,67ms bei 60Hz ist Orientierung, kein Messnachweis. Keine pauschale Adaptive-Motion-Engine.

## 12. Release und Integration
App-ID, steigender versionCode, Originalsignatur, APK-Signatur, Upgrade mit Bestandsdaten; Debug-APK ist kein signiertes Update. Artefakt/SHA/Prüfungen exakt benennen, keine Secrets committen. Jedes Lab bleibt eigenständig installierbar und später in ZIMT integrierbar: Modulgrenzen, getrennte Hülle, Schnittstellen, Datenmigration, testbare Integrationsgrenzen.

## 13. Neue Labs
Minimal: Produktbrief (Zweck/Abläufe/Nicht-Ziele/Abnahme), README, AGENTS, ACTIVE_SCOPE, WORK_QUEUE, reproduzierbarer Build und passende erste Tests. Architektur, Evidence, Integrations-/Release-Verträge und Designpläne **nur bei Bedarf**. Vorhandene Struktur nicht aus Formalismus umbauen. Sprache/UI/minSdk/App-ID/Signierung/Keystore/Persistenz bewusst wählen. Ersten vertikalen Nutzer-Slice samt Design/Daten/Abbruch/Tests implementieren, danach nächste READY-Aufgabe.

## 14–17. Vorlagen und Übergabe
ACTIVE_SCOPE: Zweck, aktueller Auftrag, Nutzerabläufe, gesamter autorisierter Scope ohne Zahlengrenze, Prioritäten/Abhängigkeiten, Nicht-Ziele, Design/Motion/Haptik, Daten/Integration, Kompatibilität, beobachtbare AC-IDs, Entscheidungen/Risiken.
AGENTS: HEAD und Autorität lesen; P0 schützen; fortlaufend wertvolle Slices liefern; Queue/Abdeckung pflegen; risikogerecht prüfen; keine unbegründeten Refactorings; sichere Integration; ausschließlich fünf Stopgründe.
WORK_QUEUE: ID, Ziel, AC-Bezug, Priorität/Abhängigkeiten, Status, Verifikation, Evidenz, Blocker/nächste Aktion.
Übergabe nur bei relevantem Wechsel: Branch/HEAD, uncommittete Änderungen, offene ACs, READY/BLOCKED, tatsächlich belegte Ergebnisse, nächste Aktion und gegebenenfalls Endgrund. Agenten arbeiten autonom und kreativ, ohne Erfolge zu erfinden.

## 18–19. Historische Fakten und Pflege
Lab 1/2 Technologie und Lab 2 Eimer-/Gestenbeispiele sind historische Snapshots, **keine** aktuellen Code- oder Scope-Beweise. Lab 3/4 keine Produktentscheidungen erfinden. Zuerst maßgebliche Repo-Dateien ändern, erst danach PDF/Onboarding-Snapshot. Keine konkurrierenden Masterpläne. **Arbeite sauber und arbeite weiter, solange du sinnvoll arbeiten kannst.**
