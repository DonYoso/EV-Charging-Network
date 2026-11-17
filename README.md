# EV-Charging-Network

Requirements Engineering Project - Group 2

## Entwicklungsumgebung

- IntelliJ IDEA mit Java-Unterstuetzung
- OpenJDK 25 (fuer alle Teammitglieder dieselbe Hauptversion)
- Git
- Maven wird ueber den eingecheckten Maven Wrapper bereitgestellt.

Die Projektbasis wurde aus `io.cucumber:cucumber-archetype:8.1.0` erzeugt.
Sie enthaelt Cucumber, JUnit Platform und AssertJ fuer Fluent Assertions.

## Projekt in IntelliJ oeffnen

1. Repository klonen: `https://github.com/DonYoso/EV-Charging-Network.git`.
2. Den Repository-Ordner in IntelliJ oeffnen und `pom.xml` als Maven-Projekt laden.
3. Unter **File > Project Structure > Project SDK** ein OpenJDK 25 auswaehlen
   oder mit **Add SDK > Download JDK** installieren.
4. Maven-Projekt synchronisieren. Bei Bedarf auch den Maven Importer und Runner
   unter **Settings > Build Tools > Maven** auf das Project JDK einstellen.
5. Optional die IntelliJ-Plugins **Gherkin** und **Cucumber for Java** installieren.
6. Fuer die Entwicklung auf den Branch `development` wechseln.

## Ausfuehren und testen

Windows PowerShell (JAVA_HOME muss auf das JDK zeigen):

```powershell
.\mvnw.cmd test
.\mvnw.cmd package
java -cp target/classes at.technikum.evcharging.Main
```

macOS/Linux:

```sh
./mvnw test
./mvnw package
java -cp target/classes at.technikum.evcharging.Main
```

Alternativ `Main.main()` oder `RunCucumberTest` direkt in IntelliJ starten.
Der erste Maven-Aufruf benoetigt Internet fuer Maven und die Abhaengigkeiten.
Das mitgelieferte `example.feature` prueft nur die Cucumber-Einrichtung;
es deckt noch keine fachliche Anforderung ab.

## Struktur

- `src/main/java/at/technikum/evcharging`: Main-Klasse und kuenftige Business-Objekte/Manager
- `src/test/java/at/technikum/evcharging`: Cucumber-Runner und Step Definitions
- `src/test/resources/at/technikum/evcharging`: Gherkin-Feature-Dateien

## Zusammenarbeit

- `main`: kompilierbarer und lauffaehiger Abgabestand.
- `development`: gemeinsame Entwicklung; optional zusaetzliche Feature-Branches.
- Vor einem Merge nach `main` muessen die Tests erfolgreich durchlaufen und die
  Anwendung ausfuehrbar sein.
- Business-Objekte werden nur im Hauptspeicher gehalten. Kein permanenter
  Speicher, Login oder Security-Modul erforderlich.
- In MVP Part 1 folgen zehn Locations, ein bis fuenf Charging Points pro Location
  und zehn Customer mit Create, Read und `toString()`.
- Der Repository-Owner laedt Teammitglieder unter **Settings > Collaborators** ein.
  Private Repositories koennen erst nach Annahme der Einladung geklont werden.

Das Domain Model und die fachlichen Features werden als naechste Arbeitsschritte
gemeinsam erarbeitet.
