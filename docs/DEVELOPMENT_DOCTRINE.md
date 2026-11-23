# ZIMT DEVELOPMENT DOCTRINE 7.0
## Autonome Entwicklung mit maximaler sinnvoller Kontinuität
**Verbindliches Handbuch für ZIMT, alle Labs und KI-Entwicklungsagenten · 23.11.2026**

**Leitsatz:** Arbeite sauber und arbeite weiter, solange du sinnvoll arbeiten kannst. Außen maximalistisch, innen minimalistisch: erstklassiges Nutzererlebnis, einfache robuste Architektur, echte Qualitätsnachweise und so wenig Prozessaufwand wie möglich.

**Geltung:** Diese Doctrine ersetzt die allgemeinen Arbeitsregeln der Version 6.1. Sie ist ein Onboarding- und Regelwerk, kein Beleg für ausgeführte Repository-Änderungen, Tests oder Builds. Neuere ausdrückliche Nutzerentscheidungen gelten unter Wahrung nicht verhandelbarer Daten- und Sicherheitsanforderungen.

## 0. Schnellstart: innerhalb eines Laufs sofort produktiv werden
1. Repository, Branch, HEAD und Arbeitsbaum prüfen. `AGENTS.md`, `docs/ACTIVE_SCOPE.md`, `docs/DEVELOPMENT_DOCTRINE.md`, `docs/ARCHITECTURE.md`, `docs/WORK_QUEUE.md` und vorhandene Nachweise nur so weit lesen, wie für die nächste Entscheidung nötig.
2. Aktuellen ausdrücklichen Nutzerauftrag, Produktziele, Akzeptanzkriterien und Nicht-Ziele bestimmen. Historische Ideen nicht stillschweigend aktivieren.
3. Unerfüllte Kriterien und bekannte Defekte mit der Queue abgleichen; fehlende notwendige Aufgaben ergänzen. Keine numerische Obergrenze für den autorisierten Arbeitsumfang.
4. Höchste sinnvolle ausführbare Aufgabe auswählen; einen kleinen, vollständigen vertikalen Slice implementieren und risikogerecht prüfen.
5. Relevante Nachweise und Zustand minimal sichern. Danach unmittelbar weiterarbeiten, statt einen Zwischenbericht als Abschluss zu behandeln.
6. Nur nach der Abschlussprüfung in §5 stoppen; reale Laufzeit-, Berechtigungs- und Werkzeuggrenzen ehrlich benennen.

## 1. Autorität und Wahrheit: Soll, Ist und Regeln unterscheiden
**A. Nicht verhandelbare Schranken:** Keine Geheimnisoffenlegung, kein stiller Datenverlust, keine erfundenen Prüfungen, Freigaben oder Artefakte. Sicherheitsrelevante Konflikte ausdrücklich eskalieren.

**B. Produkt-Soll:** Neueste ausdrückliche Nutzeranweisung bestimmt den aktuellen Auftrag. `docs/ACTIVE_SCOPE.md` konkretisiert autorisierte Ziele, beobachtbare Abnahme, Nicht-Ziele und Grenzen; bei Abweichungen zum neuen Auftrag aktualisieren.

**C. Technische Regeln:** Diese Doctrine, `AGENTS.md`, Architektur-, Daten- und Integrationsverträge steuern die Umsetzung, soweit sie nicht dem aktuellen autorisierten Produktziel oder den nicht verhandelbaren Schranken widersprechen.

**D. Technisches Ist:** Code, Tests, Git-HEAD und CI-/Geräteprotokolle belegen ausschließlich, was tatsächlich existiert und geprüft wurde. Der Code definiert nicht stillschweigend, was gewünscht ist; ein Dokument beweist keine Implementierung.

**E. Momentaufnahme:** `DEVELOPMENT_STATUS.md` und `QUALITY_EVIDENCE.md` sind belegte Berichte, keine konkurrierenden Produktpläne. Alte Pläne sind Historie.

Bei Konflikt: Soll/Ist-Abweichung offen markieren, kleinste sichere Korrektur bestimmen, maßgebliche Datei aktualisieren. Keine konkurrierenden Masterpläne schaffen.

**Prioritäten:** P0 Daten, Sicherheit, ehrliche Nachweise; P1 Nutzererlebnis einschließlich Bedienbarkeit, Design, Motion, Haptik und Accessibility; P2 robuste Architektur, Tests, Kompatibilität und Performance; P3 nur notwendige Abstimmung, Infrastruktur und Dokumentation. P0 ist Schutzbedingung, kein Freibrief für unbegrenzte Prozessarbeit.

## 2. Scope: Priorität begrenzt nicht den Auftrag
Aktiver Arbeitsumfang sind **alle** vom aktuellen Auftrag autorisierten Funktionen, Fehlerbehebungen, Verbesserungen und erforderlichen Folgearbeiten. Die Queue priorisiert, aber beschränkt nicht die Anzahl. Technische und gestalterische Folgeschritte innerhalb dieses Scopes eigenständig aufnehmen: etwa Unterbrechungsverhalten, Datenpersistenz, Haptik, Accessibility und Tests.

Neue Produktziele außerhalb des Scopes als Vorschlag markieren, nicht ungefragt implementieren. Bei unklarer Autorisierung nur den betroffenen Teil pausieren und unabhängige sichere Arbeit fortsetzen. Reversible Verbesserungen nach erwarteter Wirkung, Risiko und Aufwand priorisieren.

## 3. Continuous Execution Loop
**Jeder autonome Lauf folgt dieser Schleife:**
1. Zustand und unerfüllte Akzeptanzkriterien lesen; Queue gegen reale Code- und Testergebnisse abgleichen.
2. Nächste wertvolle READY-Aufgabe anhand Nutzen, Risiko, Abhängigkeit und Aufwand wählen. Nur bei echter Unsicherheit 1–3 technische Alternativen vergleichen; bereits entschiedene Fragen ohne neue Evidenz nicht wieder öffnen.
3. Kleinsten kohärenten Slice über relevante UI-, Zustands-, Daten-, Animations-/Haptik- und Fehlerpfade implementieren.
4. Passende Tests ausführen, Logs auswerten, Fehler beheben. Nicht getestete Aussagen als UNVERIFIED kennzeichnen.
5. Änderungen und vorhandene Git-/CI-/Testbelege sichern; Queue nur bei relevanten Zustandsänderungen aktualisieren.
6. Unerfüllte Kriterien und notwendige Folgearbeiten erneut abgleichen; nächste READY-Aufgabe bearbeiten.
7. Wiederholen, solange autorisierte, ausführbare, wertvolle Arbeit und reale Ressourcen vorhanden sind.

Ein Commit, erfolgreicher Build, abgeschlossener Slice, Statusbericht oder Checkpoint ist **niemals für sich** ein Endsignal. Keine künstlichen Wartezeiten, Endlosplanung oder redundanten Fortschrittsmeldungen.

## 4. Queue, Akzeptanzabdeckung und Status
**Kanonischer Pfad:** `docs/WORK_QUEUE.md` (oder vorhandener, ausdrücklich dokumentierter äquivalenter Pfad; keine zweite konkurrierende Queue). Pro Aufgabe: ID, Ziel, Scope-/Akzeptanzbezug, Priorität, Abhängigkeiten, Status, Nachweis, Blocker und nächste Aktion. Kein eigenes Task-Framework ohne konkreten Bedarf.

**Aufgabenstatus:** `READY` (autorisiert, ausführbar); `IN_PROGRESS` (eindeutig zugewiesen); `BLOCKED` (konkrete Ursache, benötigte Entscheidung oder Ressource); `IMPLEMENTED` (Code vorhanden, noch nicht vollständig abgenommen); `VERIFIED` (alle geforderten Akzeptanzkriterien belegt); `DEFERRED` (bewusst verschoben, mit Autorität und Begründung).

**Separates Verifikationsniveau je Kriterium:** `UNVERIFIED`, `CI_VERIFIED` (automatisierte Prüfungen für exakten SHA), `DEVICE_VERIFIED` (benanntes Gerät, OS, Build und Szenario). Einzeltests haben `PASS`, `FAIL` oder `UNVERIFIED`. `VERIFIED` als Aufgabenstatus ist nur zulässig, wenn alle für diese Aufgabe geforderten Nachweise vorliegen; CI allein ersetzt keine vorgeschriebene Geräteprüfung.

**Abdeckungsinvariante:** Jedes unerfüllte autorisierte Akzeptanzkriterium muss entweder mindestens einer offenen Queue-Aufgabe zugeordnet sein oder ausdrücklich mit gültigem Grund DEFERRED/BLOCKED sein. Auch bekannte Bugs, notwendige Migrationen und fehlende Prüfungen müssen abgedeckt sein. Keine Fortschrittsbewertung nach Commit-Anzahl oder Agentenmeldungen.

## 5. Abschlussprüfung: Schutz vor leerer Queue
**Vor jedem Stopp zwingend:**
1. Gesamten autorisierten Scope gegen beobachtbare Akzeptanzkriterien prüfen; nicht nur die Queue überfliegen.
2. Alle offenen Kriterien, bekannten Fehler, fehlenden Prüfungen und notwendigen Folgearbeiten erfassen. Fehlende Aufgaben ergänzen und Abhängigkeiten neu bewerten.
3. Blockierte Arbeiten auf unabhängige ausführbare Teilaufgaben prüfen; bei Problemen eine begründete Alternative versuchen, aber keine identischen Wiederholungen ohne neue Hypothese.
4. Sicherstellen, dass keine sinnvolle READY-Aufgabe verbleibt, die mit real verfügbaren Ressourcen verantwortbar bearbeitet werden kann.
5. Nur dann einen der fünf Endgründe ausweisen:

- `DONE`: Alle autorisierten Kriterien erfüllt; verbleibende Ideen sind außerhalb des Scopes oder ausdrücklich aufgeschoben.
- `NO_READY_WORK`: Nach vollständiger Abdeckungsprüfung existiert keine sinnvolle autorisierte ausführbare Arbeit; verbleibende Blocker und Voraussetzungen konkret benannt.
- `NEEDS_DECISION`: Eine notwendige Nutzerentscheidung verhindert **sämtliche** sonstigen sinnvollen Arbeiten.
- `SAFETY_STOP`: Fortsetzung würde nicht vertretbare Sicherheits-, Daten- oder Release-Risiken erzeugen.
- `ENVIRONMENT_LIMIT`: Reale Zeit-, Kontext-, Berechtigungs- oder Werkzeuggrenze erreicht.

**Eine leere Queue ist niemals allein ein Stopgrund.** Ein fehlgeschlagener Build ist nicht automatisch globaler Stopp. Bei tatsächlicher Laufzeitgrenze keine unbegrenzte Fortsetzung behaupten: Ein weiterer Lauf braucht einen realen neuen Aufruf bzw. geprüften Scheduler.

## 6. Effizienz, Laufzeitbudget und Refactoring
Vor riskanten Änderungen kurz prüfen, ob Implementierung, angemessene Verifikation und Rückabwicklung mit den realen Ressourcen möglich sind. Bei knappen Ressourcen kleinere unabhängige READY-Aufgaben bevorzugen; keine unprüfbare Migration starten. Keine spekulative Restlaufzeit als Messwert darstellen.

**Refactoring-Regel:** Funktionierenden Code nicht aus Stilpräferenz oder Zukunftsangst großflächig umbauen. Refactoring nur bei konkretem Nutzen für das aktuelle Ziel, nachgewiesenem Defekt, Wartbarkeitsproblem, Sicherheitsrisiko oder unmittelbar notwendiger Integration; Auswirkungen und Regressionen risikogerecht prüfen. Keine universellen Frameworks, Render-Engines oder Event-Busse ohne wiederkehrenden Bedarf.

**Dokumentationsregel:** Git-Diffs, Commit-SHAs, CI-Protokolle und Testausgaben wiederverwenden. Status und Queue nur bei relevanter Änderung knapp aktualisieren. Sicherheits-, Datenmigrations- und Release-Nachweise bleiben Pflicht. Dokumentation darf nicht künstlich die nächste autorisierte Umsetzung verdrängen.

## 7. Parallelisierung und Zusammenarbeit
Ein klarer Verantwortlicher je Änderung. Unabhängige Aufgaben dürfen parallel bearbeitet werden, **wenn** Dateien/Module, Datenverträge, Build-Ressourcen und Integrationspunkte ausreichend getrennt sind und die Koordinationskosten niedriger als der erwartete Zeitgewinn bleiben. Sonst sequenziell arbeiten.

Vor parallelem Start Schnittstellen, Eigentümer und Merge-Reihenfolge festlegen; Konfliktbereiche auf getrennten Branches oder disjunkten Dateien bearbeiten. Vor Commit/Merge HEAD erneut prüfen und fremde Änderungen nicht überschreiben. Agentenrollen sind keine simulierte Freigabehierarchie; Design-, Engineering-, Kompatibilitäts- und Release-Prüfung nur bei betroffenem Risiko. Unverifizierte Parallel-Ergebnisse nicht als integriert melden.

## 8. Risikogerechte Qualitätsgates
**Creative Lab:** Assets, Materialstudien, dekorative Effekte: Herkunft/Lizenz und visuelle Prüfung, keine Nutzerdateneingriffe.

**Product Feature:** Navigation, Gesten, Animation, Haptik: Akzeptanzszenario, fokussierte Tests, Build, Abbruch und Accessibility.

**Safety Critical:** Löschen, Verschieben, Room, Sync, Berechtigungen: deterministische Zustände, Lifecycle-, Fehler- und Datenregression, nachvollziehbarer Undo-/Soft-Delete-Pfad.

**Release & Migration:** APK, App-ID, Signierung, Datenmigration: exakter SHA, CI, Signatur/Version, Upgrade über bestehende Installation mit Bestandsdaten.

Mehrfachzuordnung ist zulässig. Kein pauschal identisches Gate für jeden kleinen Arbeitsschritt; notwendige Prüfungen niemals weglassen.

## 9. Engineering-Verträge: Gesten, Daten, Sync
Pointer-/Sensoradapter wandeln Eingaben in Ereignisse um; eine maßgebliche Zustandsmaschine entscheidet Phasen; UI rendert Zustand; Use-Case/Repository führt bestätigte Datenänderungen aus. Keine redundanten Boolean-Kopien. Scrollkonflikte, Slop, Multitouch, Loslassen, Hintergrund, Rotation, Wiederholung und Accessibility-Alternative berücksichtigen.

Destruktive Aktionen benötigen expliziten Commit-Punkt, idempotente Ausführung und nachvollziehbares Undo/Soft Delete. Eine Animations-Coroutine darf niemals alleinige Besitzerin der Datenoperation sein. Animationen dürfen abbrechen, ohne Nutzerdaten zu verlieren.

Stabile IDs, versionierte Schemata, explizite Migrationen, kein destruktives Fallback. Lokale Daten über Prozessende, Offlinebetrieb und reguläre Updates erhalten. Vor relevanten Releases versionierten Export/Import und validierten Restore vorsehen; Backup nicht ausschließlich im Cache.

Sync nur bei konkretem Bedarf: Authentisierung, Mitgliedschaften, idempotente Operationen, Konfliktregeln, Tombstones und Offline-Reconnect. Eigenständige Lab-App-IDs erfordern getesteten Export/Import oder serverseitige Migration zur Haupt-App; keine automatische Übernahme annehmen.

Fachlogik sinnvoll von Activity, Navigation, Persistenzadapter und Rendering trennen. Java/Canvas und Kotlin/Compose dürfen koexistieren. Gemeinsame Module bei wiederholtem Bedarf oder konkret bevorstehender ZIMT-Integration.

## 10. Design, Motion und Haptik
Animation ist Produktqualität und darf nicht reflexhaft für Performance geopfert werden. Charaktervolle Bewegung: sofortige Reaktion, Hauptbewegung, materialabhängiger Nachlauf, optional spielerischer Akzent. Jede Animation braucht definierte Zustände, Unterbrechungs-/Wiederaufnahmeverhalten, Reduced-Motion-Alternative, Offscreen-/Background-Pause und ein Ende ohne verlorene Eingaben.

Haptik semantisch und geräteabhängig umsetzen; aus API-Erfolg niemals reale fühlbare Wirkung ableiten. Screenshots und kurze Aufnahmen sind Designbelege; ein grüner Build beweist keine visuelle Qualität.

## 11. Kompatibilität und Performance
Moto G6 als Referenz für ältere/schwächere Android-Hardware; Nothing Phone 3a als modernes Testgerät. Historischer Snapshot: Lab 1 Java/Canvas minSdk 23; Lab 2 Kotlin/Compose minSdk 26. Tatsächlicher Repository-Stand ist vor Änderungen zu prüfen. Neue Labs wählen minSdk nach API-Bedarf und Zielgeräten, nicht nach blind kopierter Vorlage.

Zuerst Eingabelatenz und Gestensicherheit, dann Overdraw, Transparenz/Redraw, Speicher und Temperatur optimieren. Release-nahe Builds auf echten Geräten messen; Debug-Ergebnisse nicht als Release-Leistung ausgeben. Szenarien nach Risiko: Kaltstart, 100 Interaktionen, parallele Animationen, Hintergrund/Rotation, 15 Minuten Dauerbetrieb, Persistenz nach Neustart. P50/P95/P99, verpasste Frames, Peak-/stabilen Speicher und thermische Hinweise erfassen, wenn sinnvoll mindestens drei vergleichbare Durchläufe. 16,67 ms bei 60 Hz ist nur Orientierung, kein Nachweis realer Eingabelatenz. Keine pauschale Adaptive-Motion-Engine oder automatische Effektreduktion.

## 12. Release- und Integrationsvertrag
Paketkennung, monoton steigenden `versionCode`, ursprüngliches Signaturzertifikat, APK-Signatur und Installation über bestehende App mit Datenbestand prüfen. Eine separat installierbare Debug-APK ersetzt kein signiertes Update. Fertigmeldungen nennen Artefaktpfad, SHA und tatsächlich erfolgte Prüfungen; nicht vorhandene Artefakte nie erfinden. Secrets niemals in Git, Issues, Chat oder Logs.

Jedes Lab bleibt eigenständig installierbar und später in ZIMT integrierbar: klare Modulgrenzen, wiederverwendbare Fachlogik, getrennte App-Hülle, dokumentierte Schnittstellen, Datenmigration und testbare Integrationsgrenzen.

## 13. Neues Lab: schlankes Bootstrap
**Minimal erforderlich:** Produktbrief (Ziel, Nutzerabläufe, Nicht-Ziele, Abnahme), `README.md`, `AGENTS.md`, `docs/ACTIVE_SCOPE.md`, `docs/WORK_QUEUE.md`, reproduzierbarer Build und passende erste Tests. Die Doctrine kann als versionierte zentrale Referenz eingebunden werden, statt überall redundante Vollkopien zu pflegen; für offline/unabhängige Agenten muss sie zugänglich sein.

**Bei tatsächlichem Bedarf ergänzen:** `docs/ARCHITECTURE.md`, `docs/DEVELOPMENT_STATUS.md`, `docs/QUALITY_EVIDENCE.md`, `docs/ZIMT_INTEGRATION_CONTRACT.md`, `docs/RELEASE_AND_DATA.md`, Design-/Motion-Pläne. Zusätzliche Dateien nicht nur der Vollständigkeit halber anlegen. Wenn ein Projekt schon eine etablierte Struktur besitzt, nicht ohne Nutzen umorganisieren.

Android-Sprache, UI-Stack, minSdk, eindeutige applicationId, Versionierung, Debug-/Release-Signierung und Keystore-Schutz passend festlegen. Persistenz, stabile IDs, Export/Import, Migration, Lifecycle und semantische Haptik nach Funktionsbedarf planen. Erste kleine vollständige Nutzerfunktion inklusive Design, Daten, Abbruch und Tests implementieren; danach weiter zur nächsten READY-Aufgabe.

## 14. Copy-Paste: `docs/ACTIVE_SCOPE.md`
```markdown
# ZIMT Lab [NUMMER] – [NAME]
Zweck: [Erlebnis und Zielgruppe]
Aktueller Nutzerauftrag: [konkrete Entscheidung, Datum/Referenz]
Nutzerabläufe: [Start → Aktion → Ergebnis]
Aktiver Arbeitsumfang: Alle autorisierten Funktionen und notwendigen Folgearbeiten; keine numerische Obergrenze.
Prioritäten und Abhängigkeiten: [Reihenfolge, keine Umfangssperre]
Nicht im Scope: [ausdrückliche Produktgrenzen]
Design, Motion und Haptik: [Identität und Verhalten]
Daten und Integration: [Persistenz, IDs, Migration, ZIMT-Portabilität]
Kompatibilität: [minSdk, Moto G6, weitere Zielgeräte]
Akzeptanzkriterien: [IDs, beobachtbare Ergebnisse]
Offene Entscheidungen und Risiken: [konkret]
```

## 15. Copy-Paste: `AGENTS.md`
```markdown
# ZIMT Agent Contract — Doctrine 7.0
1. Prüfe HEAD, aktuellen Nutzerauftrag, ACTIVE_SCOPE, Doctrine, Architektur, Queue und vorhandene Belege.
2. Trenne Produkt-Soll (Auftrag/Scope), technisches Ist (Code/Tests) und technische Regeln.
3. Halte P0-Schranken ein: Daten, Geheimnisse, ehrliche Nachweise.
4. Arbeite sauber und arbeite weiter, solange du sinnvoll arbeiten kannst.
5. Prioritäten ordnen Arbeit; sie begrenzen nicht die Zahl autorisierter Funktionen.
6. Gleiche unerfüllte Akzeptanzkriterien und Bugs laufend mit der Queue ab; ergänze fehlende Aufgaben.
7. Implementiere kleine vollständige Slices, prüfe risikogerecht und bearbeite unmittelbar die nächste READY-Aufgabe.
8. Bei Blockern begründete Alternativen prüfen und unabhängige Aufgaben fortsetzen.
9. Keine großflächigen Refactorings oder Frameworks ohne konkreten Nutzen.
10. Parallelisiere nur unabhängige Arbeiten mit klaren Eigentümern und geringer Konfliktgefahr.
11. Gesten besitzen eine maßgebliche Zustandslogik; Animationen besitzen keine destruktiven Datenoperationen.
12. Bewahre Daten, IDs, Assets, Signatur, Kompatibilität und spätere ZIMT-Integration.
13. Trenne Aufgabenstatus von CI-/Geräte-Verifikation; berichte nur reale Prüfungen für exakten SHA.
14. Nutze Git-/CI-Nachweise wieder und halte Dokumentation proportional zum Risiko.
15. Eine leere Queue ist kein Abschluss: prüfe vorher alle unerfüllten Kriterien und Folgearbeiten.
16. Stoppe nur mit DONE, NO_READY_WORK, NEEDS_DECISION, SAFETY_STOP oder ENVIRONMENT_LIMIT.
17. Commit, Build, Checkpoint und Statusmeldung sind keine automatischen Endsignale.
18. Behaupte technische Wiederaufnahme nur bei real geprüftem neuem Agentenaufruf/Scheduler.
```

## 16. Copy-Paste: `docs/WORK_QUEUE.md` und Übergabe
```markdown
# Work Queue
- ID: [TASK-001]
  Ziel: [beobachtbares Ergebnis]
  Akzeptanzbezug: [AC-001]
  Priorität/Abhängigkeiten: [P1 / TASK-000]
  Status: [READY | IN_PROGRESS | BLOCKED | IMPLEMENTED | VERIFIED | DEFERRED]
  Verifikation: [UNVERIFIED | CI_VERIFIED | DEVICE_VERIFIED]
  Nachweis: [SHA, Test, Build, Gerät/OS, PASS/FAIL/UNVERIFIED]
  Blocker/nächste Aktion: [konkret]

# Checkpoint (nur bei relevantem Wechsel oder Sitzungsgrenze)
Branch/HEAD/SHA: [exakt]
Uncommittete Änderungen: [Dateien und Zweck]
Offene Akzeptanzkriterien: [IDs]
READY/BLOCKED: [IDs und Ursachen]
Implementiert/verifiziert: [SHA und echte Belege]
Nächste ausführbare Aktion: [ID, Datei/Kommando]
Endgrund (nur falls beendet): [einer der fünf Codes]
```

## 17. Copy-Paste: Übergabe-Prompt
> Du entwickelst ZIMT bzw. ZIMT-Lab [NAME] als kritischer Senior-Entwickler und Designpartner. Prüfe zuerst den aktuellen Repository-Zustand und die autoritativen Dateien. Respektiere den aktuellen Nutzerauftrag, Scope und P0-Schranken. Arbeite kreativ, effizient und evidenzbasiert; implementiere statt unnötig neu zu planen. Halte Animation, Haptik, Datenintegrität, Kompatibilität und ZIMT-Portabilität hoch. Gleiche unerfüllte Akzeptanzkriterien stets mit der Queue ab und ergänze notwendige Aufgaben. Arbeite nach jedem Slice weiter, solange sinnvolle autorisierte Arbeit ausführbar ist. Wechsle bei Blockern zu unabhängigen Aufgaben. Vermeide unnötige Refactorings, doppelte Dokumentation und unbewiesene Erfolgsmeldungen. Berichte exakte SHAs und echte Tests. Stoppe ausschließlich nach der vollständigen Abschlussprüfung mit einem der fünf zulässigen Endgründe.

## 18. Historische Projektfakten (unverbindlicher Snapshot)
Lab 1: Java/Android Canvas, minSdk 23 laut früherem Audit. Lab 2: Kotlin/Jetpack Compose, minSdk 26; Eimer-Liste mit Room und historisch drei zweilagigen PNG-Eimern. Lab 3/4: Repositories laut früherem Snapshot vorhanden; konkrete Produkt-/SDK-Entscheidungen nicht erfinden. Lab 2 historisch: Flechtkorb, Holzkübel, Zinkeimer; REAR → Papier → FRONT; Tap, 700-ms-Lift, Drag, 1500-ms-Warnung, 2000-ms-Zündung, Undo. Dies sind **keine** aktuellen Code- oder Scope-Nachweise. Neueste autoritative Dateien und HEAD prüfen.

## 19. Pflege und Abschlussmaxime
Maßgebliche Repository-Familie laut früherer Doctrine: `github.com/shayohekmat-wq/Zimt-Lab-1` bis `Zimt-Lab-4`; tatsächliche Existenz und HEAD vor Verwendung prüfen. Relevante Dokumente je nach Bedarf: `docs/DEVELOPMENT_DOCTRINE.md`, `docs/ACTIVE_SCOPE.md`, `AGENTS.md`, `docs/ARCHITECTURE.md`, `docs/WORK_QUEUE.md`, `docs/DEVELOPMENT_STATUS.md`, `docs/QUALITY_EVIDENCE.md`, `docs/ZIMT_INTEGRATION_CONTRACT.md`, `docs/RELEASE_AND_DATA.md`, `docs/MOTION_FIRST_PLAN.md`, `docs/DESIGN_QA.md`.

Die autoritative Quelle zuerst ändern und erst danach PDF/Onboarding-Snapshot aktualisieren. Nicht mehrere widersprüchliche Kopien pflegen. Die beste Lösung liefert das gewünschte Erlebnis zuverlässig, kreativ und mit möglichst wenig unnötiger Komplexität. **Arbeite sauber und arbeite weiter, solange du sinnvoll arbeiten kannst.**