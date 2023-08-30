# Tesi

## Preprocessing

Le operazioni di preprocessing effettuate sono state:
1) Eliminazione delle feature costanti
2) Trasformato le diverse etichette delle anomalie tutte in 'anomaly'
3) Traformato 'normal' in 0 e 'anomaly' in 1
4) Divisione delle colonne in Numeriche e Categoriche e trasformate rispettivamente con uno Scaler (standard scaler) e un Encoder (one hot encoder)

## Training

È stato eseguito il training di 3 modelli: LogisticRegression, RandomForest, XGB.
Gli approcci usati sono stati 3: Classico, Time Series con Differenze, Time Series con Media Mobile (MA).
Per un totale di 9 modelli.

## MCC, Accuracy

Per ogni modello è stato valutato e salvato in un dictionary il valore dell'MCC e dell'accuracy.

## Speed Score

Per ogni modello è stato calcolato uno score per valutare la velocità di riconoscimento delle anomalie da parte dei modelli. 
Lo score è stato calcolato come media pesata delle frequenze di rilevamento (decrescita quadratica).
Anche in questo caso lo score è stato salvato in un dictionary.

## MCC, Accuracy, Speed Score Progression

Tramite matplotlib è stato graficato l'andamento per ogni modello dell'MCC, dell'accuracy e dello speed score confrontati con i 3 approcci differenti.

## all3

Infine sono state valutate le performance del modello (MCC) su un dataset diverso (all3) per verificare la robustezza dei modelli.
È stato fatto un grafico per comparare l'MCC sul test set originale e l'MCC su all3.

