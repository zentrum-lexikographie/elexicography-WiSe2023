## Übungen für Leistungsnachweise
Sie haben zwei Übungen zur Auswahl.

(A) Kuratiere Satzbelege mit Hilfe der App https://evidence.bbaw.de 

(B) Trainieren Sie ihr eigenes Scoring-Modell


### (A) Kuratiere Satzbelege mit der Evidence-App
Die Übung (A) wird für die unbenotete Nebenleistung angeboten. 
~Bitte schreiben Sie eine E-Mail an `hamster [ät] bbaw [punct] de`, um ein Lemma zu bekommen.+

Suche Sie sich 1 Lemma aus:

   - Adj: grün, nachhaltig
   - Verb: pflegen, schmelzen
   - Nomen: Nase, Eis

(1) Öffne die Web-App auf https://evidence.bbaw.de

(2) Gehen Sie in die Einstellungen https://evidence.bbaw.de/#/settings
- Setze "Minimum Number of Offline BWS Sets" auf den Wert 20.
- Setze "Sample from N top scored sentences" ungefähr auf den Wert 100 bis 150.

Mit "Items per BWS set" können Sie einstellen, ob Sie 3, 4 oder 5 Satzbelege angezeigt bekommen möchten.

(3) Öffnen Sie das Ranking-Tool für die Beleggüte auf https://evidence.bbaw.de/#/bestworst4
- Tippen Sie oben links in das Suchfeld das Lemma ein (wird Ihnen per E-Mail mitgeteilt).
- Ranken Sie diverse Sets für ca. 5 bis 10 Minuten.
- Klicken Sie auf "Ranking Overview" und kopieren Sie die Top-5 Satzbelege in ein Word-/Text-Dokument (d.h. den Text, die Belegquelle, und Scores rechts auf der Card).


(4) Öffnen Sie das Tool für die Belegvariation auf https://evidence.bbaw.de/#/variation1
- Tippen Sie oben links in das Suchfeld das Lemma ein.
- Klicken Sie auf den Button "Preference Parameter" und modizieren Sie die Schieberegler je nachdem ob Sie eher unterschiedliche Lesarten (Semantic), Schreibstile (Grammar), oder Belegquellen (Bibliographic) suchen. 
- Kopieren sie die Top-10 Satzbelege in ein Word-/Text-Dokument (d.h. den Text und die Belegquelle)

(5) Schlagen Sie 5 von den 15 Satzbelegen als Verwendungsbeispiele für ein Wörterbuchartikel vor. Begründen Sie kurz ihre Auswahl.



### (B) Trainieren Sie ihr eigenes Scoring-Modell
Die Übung (B) wird für eine benotete Nebenleistung angeboten.
Bitte schreiben Sie eine E-Mail an `hamster [ät] bbaw [punct] de`, um eine Datensatz zu bekommen.

Bitte verwenden Sie ein Google Colab Notebook.
(Sollten Sie alternativ ein Python3-Skript abgeben, muss im Git-Repo eine `requirements.txt` Datei für ein Python Virtual Environment als auch Installatinshinweise vorliegen.)

Sie sollen die Satzbelege `X` mit einem Featureextraktor `g(X)` in Vektoren `e` 
umwandeln, und mit lezteren ein Modell `f(e)` mit Tensorflow2 trainieren.

```
y = f(e)
e = g(X)
```

**Schritt 1: Featureextraktion.**
Als Featureextraktor `g(.)` verwenden Sie das vortrainierte [SBert](https://www.sbert.net/)-Modell `paraphrase-multilingual-MiniLM-L12-v2` (https://www.sbert.net/docs/pretrained_models.html#model-overview).
Im Noteboook [Semantische Ähnlichkeit mit SBert.ipynb](https://github.com/zentrum-lexikographie/elexicography-WiSe2023/blob/main/Tag-1/Semantische%20%C3%84hnlichkeit%20mit%20SBert.ipynb) ist ein Beispiel enthalten, wie Sie SBert in Colab installieren.
Je 1 Satzbeleg erzeugt SBert 1 Vektor mit Floating-Point Zahlen. 

**Schritt 2: Annotation.**
Für das Modelltraining fehlt Ihnen `y`; das müssen Sie sich jetzt selber schrittweise annotieren.
Ziehen Sie per Zufall (z.B. `np.random.shuffle`) 10 Satzbelege und speichern Sie 
diese in einer Liste `X_train`.
Lesen Sie sich alle 10 Sätze durch und sortieren die vom besten bis schlechtesten Satzbeleg nach ihrer persönlichen Meinung.
Vergeben Sie Scores im Intervall `1.0 >= y >= 0` und speichern diese in der Liste `y_train`, z.B., `y_train = [.05, .15, ..., 0.95]`.

**Schritt 3: Modellierung & Training.**
Modellieren ein simples Regressionsmodell mit Tensorflows `tf.keras.models.Sequential` API (Siehe [TF2 Tutorial](https://www.tensorflow.org/tutorials/quickstart/beginner#build_a_machine_learning_model)). Hinweise: `Dense(1)`, MSE Loss, SGD, model.fit, nur 1 Batch vorhanden, wenige Epochen.

**Schritt 5: Prognose.**
Nachdem Sie nun ihr initiales Scoring-Modell trainiert haben, berechnen Sie die Modell-Scores `y_pred` für circa 100 zufällig ausgewählte nicht-annotierten Satzbelege aus `X`.

**Schritt 6: Fehlerkorrektur.**
Betrachte die Liste `(y_pred, X_zufall)` und suche nach 10 Satzbelegen, deren Modell-Score `y_pred` zu weit abweicht vom einem Score, den Sie persönlich für angemessen empfinden. Zum Beispiel, ein Satzbeleg mit hohen Modell-Score, die Eigennnamen als Lemma haben, Fehlformatierungen aufweisen, beleidigende Inhalte enthalten, u.a. Oder Satzbelege mit besonders niedrigen Modell-Score, die aber eher gute Verwendungsbeispiele sein könnten.
Fügen Sie die korrigierten Beispiele zum Trainingsdaten `(y_train, X_train)` hinzu und wiederholen die Schritte 3. bis 6.


Bonusfrage für Schritt 3 (Modellierung):
In Schritt 5./6. wird ihnen aufgefallen sein, dass die Modell-Scores außerhalb des Intervalls `[0.0, 1.0]` liegen können. Wie können Sie das Modell aus Schritt 3. modifizieren, um immer Scores zwischen Null und Eins zu erhalten (Es ist egal ob `1.0 > y > 0.0` oder `1.0 >= y >= 0.0`).

Bonusfrage für Schritt 2 (Datenqualität):
Sie sollen hier einen Trainingsdatensatz erstellen, welcher schlechte bis gut Satzbelege unterscheiden soll. Welche Datenquelle können Sie heranziehen von der Sie auch ohne lexikografisches Fachwissen davon ausgehen können, dass diese wenige aber gute bzw. sehr gute Satzbelege für ein Lemma enthalten müssten? Benenne Sie diese Datenquellen und bauen diese Satzbelege mit entsprechenden Trainingsscore in ihren Trainingsdatensatz ein.
