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
### With/Without Unreliable Features


XGB= grande differenza (18 punti)  


Logistic= non grande differenza (6 punti)  


Random Forest= pressoché nessuna differenza, le features sono molto simili cambia un po’ l’ordine 


LDA= grande differenza (14 punti)  



Commento: sono molte features, io ho guardato le prime 20 ma noto che massimo dopo le prime 5 c’è un andamento asintotico dell’importanza delle features \n



### MCC & Error Rate
Shuffle=True/False: i valori di MCC e Error Rate sono di gran lunga migliori per shuffle=True, soprattutto negli approcci Classic e TS-MA ci sono le maggiori differenze.

Con shuffle=False:


L'andamento in generale dell' MCC in ordinte crescente è: Classic, TS-MA, TS-Diff.


L'error rate è decisamente più basso con l'approccio TS-Diff.


L'error rate con l'approccio TS-MA è sempre minore, o alle volte uguale, all'error rate dell'approccio Classic (a parte nella Logistic Regression in cui si ha un valore maggiore di error rate nell'approccio TS-MA rispetto all'approccio classico).


L'error rate migliore si ottiene sempre con il modello XGBoost.


### MCC Comparison Uni-All3

ATTENZIONE: grande modifica rispetto all'altra volta.

Cambiando il dataset All3 (escludendo quindi i dati X_train usati per addestrare i modelli su Uni) i modelli si dimostrano molto meno robusti su All3, come effettivamente ci saremmo potuti aspettare. La scorsa volta alcune volte l'MCC sul dataset All3 era maggiore che su quello di Uni. Con la modifica sul dataset All3 l'andamento è chiaro: meno robustezza dei modelli su All3 rispetto ad Uni. Cosa importante è che l'andamento dell'MCC è sempre lo stesso, in ordine crescente: Classic, TS-MA, TS-Diff.

### MCC Comparison With/Without Unreliable su All3:
Fatto solo per i modelli classic. A parte per Random Forest, in cui i valori di MCC con o senza feature inaffidabili non cambia, i valori di MCC sono sempre più alti nei modelli addestrati senza feature inaffidabili.


### SPEED 
Tra i modelli con shuffle=False con finestre temporali differenti non ci sono grandi differenze nei valori di score. La tendenza di base segue quella dell'MCC, in ordine crescente: Classic, TS-MA, TS-Diff. Piccola eccezione il modello LDA ha una tendenza diversa e anche la Logistic Regression con win=2.

