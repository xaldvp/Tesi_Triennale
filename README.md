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

## Bozza Conclusioni
With/Without Unreliable Features \n
XGB= grande differenza (18 punti) \n
Logistic= non grande differenza (6 punti) \n
Random Forest= pressoché nessuna differenza, le features sono molto simili cambia un po’ l’ordine \n
LDA= grande differenza (14 punti) \n

Commento: sono molte features, io ho guardato le prime 20 ma noto che massimo dopo le prime 5 c’è un andamento asintotico dell’importanza delle features \n



MCC

Shuf=True/False Win=5
La tendenza è la stessa (TS-Diff,TS-MA,Classic)
MCC migliore in Shuf=true, ma quasi identico nel caso di TS-Diff soprattutto nei modelli basati su alberi.

Win=5 Win=4 (shuf=false)
Pressoché identici i valori di MCC, peggiorano soprattutto i modelli TS-MA

Win=4 Win=3 (shuf=false)
Pressoché identici i valori di MCC. Inversione di tendenza nel modello LDA, ovvero —> TS-MA,TS-Diff,Classic

Win=3 Win=2 (shuf=false)
Pressoché identici i valori di MCC. Ritorno alla tendenza di fondo per LDA, ovvero —> TS-Diff, TS-MA, Classic




MCC Comparison Uni-All3

Con Shuf=True si ha che tendenzialmente i modelli performano meglio sul test set di Uni.

Con Shuf=False i modelli hanno performance simili sia sul test set di Uni che su All3, ma spesso sono migliori sul set Uni (forse perche parzialmente i dati di All3 sono anche dati di training dei modelli trainati su Uni)




SPEED 

Non grandi differenze nei valori di score. La tendenza nei modelli basati su alberi rimane sempre la stessa TS-Diff, TS-MA, Classic. Nei modelli lineari in win2 c’è un’inversione di tendenza, mentre in win4 e win5 solo per i modelli LDA.

