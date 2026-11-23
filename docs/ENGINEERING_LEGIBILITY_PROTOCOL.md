# Engineering Legibility Protocol 1.0

**Verständlicher Code. Sichere Übergabe. Kontinuierliche Entwicklung.**

Verbindlicher Entwicklungsstandard nach Einführung im Projekt · Version 1.0

**Leitsatz:** Schreibe für den nächsten Entwickler. Maximiere Verständlichkeit, nicht Dokumentationsmenge.

## 01. Zweck und Geltung

Dieses Protokoll gilt für menschliche Entwickler und KI-Agenten in neuen und bestehenden App-Projekten. Es ergänzt die Development Doctrine und das Global Development Orchestration Protocol: Es regelt Verständlichkeit und Übernahmefähigkeit, nicht Priorisierung oder Release-Freigabe. Bestehende Sicherheits-, Daten- und Produktanforderungen bleiben maßgeblich.

## 02. Code als verständlicher Vertrag

Verwende fachlich aussagekräftige Namen für Funktionen, Typen, Zustände und Parameter. Eine Funktion soll eine erkennbare Verantwortung haben; Eingaben, Ergebnisse, Fehler und relevante Seiteneffekte müssen aus ihrer Schnittstelle oder ihrem unmittelbaren Kontext hervorgehen. Bevorzuge direkte, idiomatische Lösungen gegenüber cleveren Abkürzungen und unnötiger Indirektion. Folge den etablierten Konventionen des Projekts.

## 03. Architektur und Zustände

Halte Fachlogik, Darstellung, Eingabe, Persistenz und externe Dienste dort getrennt, wo dies Verständnis, Tests oder Integration erleichtert. Jede fachliche Information besitzt eine maßgebliche Quelle; abgeleitete Zustände werden nicht unabhängig gepflegt. Mache Zustandsübergänge, Datenmutationen, asynchrone Grenzen, Abbruch und Fehlerpfade nachvollziehbar. Verstecke keine wichtigen Abhängigkeiten in globalem Zustand oder impliziten Seiteneffekten. Animationen dürfen keine destruktiven Datenoperationen besitzen.

## 04. Erkläre das Warum

Kommentare erläutern nicht offensichtliche Gründe, Invarianten, Kompatibilitätsgrenzen, Workarounds und Risiken. Beschreibe bei öffentlichen Schnittstellen nur Verträge, die der Code nicht eindeutig ausdrückt. Entferne irreführende Kommentare bei Änderungen. Halte wichtige, langlebige Architekturentscheidungen knapp am passenden Ort fest: Entscheidung, Grund, relevante Konsequenz. Keine Dokumentation offensichtlicher Syntax.

## 05. Orientierung ohne Sucharbeit

Nutze vorhandene Dateien statt neuer paralleler Dokumente. README: Zweck, Voraussetzungen, Start-, Build- und Testbefehle. AGENTS.md: verbindliche Arbeitsregeln und Verweis auf dieses Protokoll. Architekturübersicht bei komplexeren Projekten: Einstiegspunkte, Modulverantwortung, zentrale Datenflüsse und relevante Integrationsgrenzen. ACTIVE_SCOPE und WORK_QUEUE bleiben die maßgeblichen Quellen für Ziele und offene Arbeit. Verweise auf konkrete Pfade und Symbole statt Code zu kopieren.

## 06. Änderungen nachvollziehbar machen

Erstelle kohärente Änderungen mit aussagekräftigen Commit-Nachrichten. Erkläre bei nicht offensichtlichen Änderungen kurz Anlass und Auswirkung. Tests sollen beobachtbares Verhalten und wichtige Invarianten zeigen, nicht interne Implementierungsdetails festschreiben. Nutze Git-Diffs, Testprotokolle und CI als Nachweise; dupliziere sie nicht in Statusdateien. Kennzeichne ungetestete Annahmen und bekannte Einschränkungen ausdrücklich. Keine Geheimnisse oder privaten Nutzerdaten in Code, Logs oder Übergaben.

## 07. Developer Takeover Rule

Ein qualifizierter Nachfolger muss ohne Wissen aus einem privaten Chat erkennen können, wo eine Funktion beginnt, welche Daten sie verändert, welche Verträge gelten, wie sie geprüft wird und welche Arbeit offen ist. Bei einem tatsächlichen Verantwortungswechsel oder Sitzungsende genügen: Branch und HEAD, relevante offene Aufgabe, ungewöhnliche Entscheidung oder Risiko, vorhandene Prüfbelege und nächste konkrete Aktion. Verlinke vorhandene Informationen statt sie zu wiederholen. Uncommittete Änderungen und Blocker nur nennen, wenn vorhanden.

## 08. Verständlichkeit ohne Entwicklungsbremse

Wende das Protokoll während normaler Produktarbeit an. Verbessere berührten Code, wenn der Nutzen konkret und der Umfang vertretbar ist. Kein flächendeckendes Aufräumen, keine starren Zeilenlimits, keine erzwungenen Abstraktionen, keine künstlichen Dokumentations- oder Testquoten. Unabhängige Arbeit läuft bei lokalen Problemen weiter. Ein Übergabevermerk ist kein automatisches Ende eines Agentenlaufs.

## 09. Prüfung am geänderten Code

Vor Abschluss einer relevanten Änderung prüfe proportional zum Risiko: Sind Verantwortlichkeiten, Namen und Datenwirkungen verständlich? Sind ungewöhnliche Entscheidungen und Verträge auffindbar? Sind betroffene Tests, Einstiegspunkte und Dokumentationsverweise aktuell? Kann ein Nachfolger den nächsten Schritt ohne Rückfrage erkennen? Behebe konkrete Verständnis- oder Sicherheitsprobleme; rein kosmetische Wünsche blockieren keine funktionierende Änderung. Bei kritischen Daten- oder Sicherheitsrisiken gelten die strengeren Qualitätsgates der Development Doctrine.

## 10. Einführung in bestehende Projekte

Verankere einen kurzen Verweis in AGENTS.md und halte die versionierte Markdown-Fassung zugänglich. Prüfe zunächst vorhandene Konventionen und Dokumente; ersetze widersprüchliche Regeln gezielt. Erfasse tatsächliche Verständlichkeitsprobleme in der bestehenden Queue und priorisiere sie nach Risiko und Nutzen. Keine separate Clean-Code-Kampagne. Bei neuen Projekten genügen verständliche Einstiegspunkte, reproduzierbare Befehle und klare Verantwortlichkeiten; zusätzliche Dokumente entstehen erst bei Bedarf.

## 11. Direkt einsetzbare Agentenanweisung

Wende das Engineering Legibility Protocol 1.0 auf jede relevante Änderung an. Schreibe fachlich verständlichen, idiomatischen Code mit klaren Verantwortlichkeiten, expliziten Datenwirkungen und nachvollziehbaren Zuständen. Erkläre nur nicht offensichtliche Gründe und Verträge. Nutze vorhandene Architektur-, Scope-, Queue- und Git-Nachweise; halte betroffene Informationen aktuell. Ermögliche einem Nachfolger die sichere Weiterarbeit ohne privaten Chat-Kontext. Refaktoriere nur bei konkretem Nutzen, prüfe risikogerecht und arbeite anschließend an der nächsten sinnvollen Aufgabe weiter. Erfinde keine Nachweise und führe keine redundanten Dokumente.