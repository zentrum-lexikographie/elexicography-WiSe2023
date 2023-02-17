# Übung zur lexikografischen Auszeichnung nach TEI Lex-0

## Aufgabe

Schauen Sie sich die Beispiele unter `WDG/` und `Kluge-Lutz/` an. Für die Übung nutzen Sie entweder

- `Uhlenbeck-1900/` (_bōta_ bis _brōþrahans_); das gesamte Buch finden Sie z. B. hier:
  - https://archive.org/details/KurzgefasstesEtymologischesWrterbuchDerGotischenSprache
  - https://archive.org/details/bub_gb_cy0QAAAAYAAJ
- oder `Walde-1910/` (ganze Seite); das gesamte Buch finden Sie hier:
  - https://archive.org/details/1057917.0001.001.umich.edu
  
Übernehmen Sie aus der gescannten Seite eines der beiden Werke **alle** vollständigen Wörterbuchartikel. Kodieren Sie sie als XML-Datei entsprechend der Richtlinien der TEI (Kapitel 9) und der Spezifizierungen von TEI Lex-0. Die Datei muss valide entsprechend des Schemas `TEILex0.rng` sein. Nutzen Sie gern das `template.xml` als Ausgangspunkt.

**Abgabetermin: 3. März 2023** – bitte per E-Mail an `herold[AT]bbaw.de` und `geyken[AT]bbaw.de`

Fragen: per E-Mail an `herold[AT]bbaw.de` oder [hier als Issue anlegen](https://github.com/zentrum-lexikographie/elexicography-WiSe2023/issues).

## Hinweise

- Für die Erstellung der Datei verwenden Sie am besten einen XML-Editor (empfohlen: [Oxygen-XML](https://www.oxygenxml.com/xml_editor/download_oxygenxml_editor.html) z. B. mit [30-Tage-Testversion](https://www.oxygenxml.com/xml_editor/register.html?p=editor)). Sie können aber auch einen beliebigen Texteditor nutzen (z. B. vim, emacs, Notepad usw.) und die Datei mit Hilfe des Kommandozeilentools `jing` (https://github.com/relaxng/jing-trang) auf Validität prüfen: `jing TEILex0.rng <meine_Datei.xml>`
- Formangaben, Etyma und Kognate (siehe `tei-lex-0.pdf`, Folie 31 ff.), grammatische Angaben, Definitionen und Sprachennamen **müssen** mindestens ausgezeichnet werden. Vererbungsrelationen (siehe `tei-lex-0.pdf`, Folie 34) müssen Sie nicht auszeichnen.
- Nicht-Lateinische Zeichen können Sie in Oxygen über den Menüpunkt `Edit` → `Insert from Character Map` oder bei Verwendung anderer Editoren über eine Zeichentabelle Ihres Betriebssystems eingeben.
- Sie können uns Kommentare im XML hinterlassen (`<!-- ... Kommentar ... -->`), wenn Sie möchten.

## Links zu TEI und TEI Lex-0

- https://www.tei-c.org/ – Homepage der TEI
- https://github.com/TEIC – Codebasis der TEI
- https://github.com/DARIAH-ERIC/lexicalresources – Codebasis von TEI Lex-0
- https://dariah-eric.github.io/lexicalresources/pages/TEILex0/TEILex0.html – TEI Lex-0 Dokumentation
