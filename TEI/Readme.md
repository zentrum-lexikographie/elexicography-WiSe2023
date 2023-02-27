# Übung zur lexikografischen Auszeichnung nach TEI Lex-0

## Aufgabe

1. Schauen Sie sich die Beispiele unter `WDG/` und `Kluge-Lutz/` an.
2. Für die Übung nutzen Sie:
  - **entweder** `Uhlenbeck-1900/` (ganze Seite); das gesamte Buch finden Sie z. B. hier:
    - https://archive.org/details/KurzgefasstesEtymologischesWrterbuchDerGotischenSprache
    - https://archive.org/details/bub_gb_cy0QAAAAYAAJ
  - **oder** `Walde-1910/` (ganze Seite); das gesamte Buch finden Sie hier:
    - https://archive.org/details/1057917.0001.001.umich.edu
3. Laden Sie sich die Dateien `TEILex0.rng` und `template.xml` herunter und legen Sie beide gemeinsam in einem Verzeichnis ab. Die Datei `template.xml` können Sie gern als Gerüst beziehungsweise Ausgangspunkt für Ihre Lösung verwenden. Nennen Sie die Datei `template.xml` geeignet um.
4. Übernehmen Sie aus der gescannten Seite eines der beiden unter 2. genannten Werke **alle** vollständigen Wörterbuchartikel. Kodieren Sie sie als XML-Datei entsprechend der Richtlinien der TEI (Kapitel 9) und der Spezifizierungen von TEI Lex-0.
5. Die Datei, die Sie als Lösung einreichen muss valide entsprechend dem heruntergeladenen Schema `TEILex0.rng` sein.
6. **Abgabetermin ist der 10. März 2023** – bitte per E-Mail an `herold[AT]bbaw.de` und `geyken[AT]bbaw.de`.
7. Fragen: per E-Mail an `herold[AT]bbaw.de` oder [hier als Issue anlegen](https://github.com/zentrum-lexikographie/elexicography-WiSe2023/issues).

## Nähere Hinweise

1. Nicht-lateinische Zeichen können Sie in Oxygen über den Menüpunkt `Edit` → `Insert from Character Map` oder bei Verwendung anderer Editoren über eine Zeichentabelle Ihres Betriebssystems eingeben (z. B. `gucharmap` unter Linux oder `Zeichentabelle` unter Windows). Wenn Sie bei einem Zeichen nicht genau wissen, wie sie es eingeben sollen, hinterlassen Sie einfach einen entsprechenden Kommentar (siehe unten Punkt 4). Die exakte Transkription der Seite ist zum Bestehen der Aufgabe nicht zwingend notwendig.
2. Für die Arbeit an der XML-Datei verwenden Sie am besten einen XML-Editor (wir empfehlen Ihnen den [Oxygen-XML Editor](https://www.oxygenxml.com/xml_editor/download_oxygenxml_editor.html) z. B. mit [30-Tage-Testversion](https://www.oxygenxml.com/xml_editor/register.html?p=editor)). Oxygen prüft die Validität automatisch und wird Sie informieren, wenn sie vom Schema nicht erlaubte Strukturen verwenden möchten. Oxygen wird Ihnen auch kontextabhängig zulässige Elemente und Attribute samt deren Beschreibungen vorschlagen. Sie können aber auch einen beliebigen Texteditor nutzen (z. B. `vim`, `emacs` unter Linux, `Notepad` unter Windows usw.) und die Datei mit Hilfe des Kommandozeilentools `jing` (https://github.com/relaxng/jing-trang) auf Validität prüfen: `jing TEILex0.rng <meine_Datei.xml>`. Auch dadurch werden Ihnen Validitätsfehler in Ihrer Datei ausgegeben.
3. Formangaben, Etyma und Kognate (siehe `tei-lex-0.pdf`, Folie 31 ff.), grammatische Angaben, Definitionen und Sprachennamen **müssen** mindestens ausgezeichnet werden. Vererbungsrelationen (siehe `tei-lex-0.pdf`, Folie 34), Verweise und alle anderen Angaben müssen Sie **nicht** auszeichnen.
4. Sie können uns Kommentare im XML hinterlassen (`<!-- ... Kommentar ... -->`), wenn Sie möchten, z. B. um auf Probleme hinzuweisen, die Sie bei der Auszeichnung hatten.

## Links zu TEI und TEI Lex-0

- https://www.tei-c.org/ – Homepage der TEI
- https://github.com/TEIC – Codebasis der TEI
- https://github.com/DARIAH-ERIC/lexicalresources – Codebasis von TEI Lex-0
- https://dariah-eric.github.io/lexicalresources/pages/TEILex0/TEILex0.html – TEI Lex-0 Dokumentation
