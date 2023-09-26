# Tesi

## Introduzione
Nell‘era in cui viviamo l‘analisi dei dati riveste un ruolo cruciale in molti settori della nostra società. In questo contesto il Machine Learning si è dimostrato un potente strumento per estrarre informazioni utili e conoscenza da dati complessi e voluminosi. Il Machine Learning (ML) è un sottoinsieme dell’intelligenza artificiale (AI) che si occupa di creare sistemi che apprendono e migliorano le proprie performance in base ai dati che utilizzano. L’implementazione di algoritmi di ML su dispositivi IoT ed edge risulta ancora in uno stato di sviluppo incompleto, rappresentando un’area di ricerca aperta. L’uso di algoritmi di ML su questi dispositivi può servire a renderli consapevoli del proprio comportamento, ad esempio attraverso l’uso di rilevatori di anomalie, che permettano ai dispositivi di capire quando si ha un comportamento anomalo, agendo di conseguenza in caso di attacco o intrusione. In particolare, il presente lavoro di Tesi fa riferimento al lavoro di ricerca qui citato, dove sono stati monitorati degli indicatori di performance da un dispositivo chiamato ARANCINO, che è il nome commerciale per una famiglia di schede IoT e embedded che risiedono sull’omonima architettura. Dal sistema di monitoraggio utilizzato sono stati restituiti dei dati tabulari, ovvero un insieme di righe (osservazioni del set di dati) e di colonne (features, in questo caso indicatori di performance), ordinati rispetto al tempo. Lo scopo del lavoro di Tesi è stato confrontare l’approccio classico all’analisi dei dati con un approccio time series. Una time series può essere definita come un insieme di osservazioni ordinate rispetto al tempo. La differenza sostanziale tra i due approcci è che con un approccio time series si hanno informazioni non solo sull‘istante di tempo corrente, ma anche su un numero di istanti di tempo precedenti scelto arbitrariamente. Il fine ultimo del presente lavoro di Tesi è stato quello di comparare le performance di 4 algoritmi di machine learning in condizioni diver- se: Logistic Regression, Linear Discriminant Analysis, Random Forest, XGBoost. Le condizioni diverse sopracitate sono state date dall’addestramento dei modelli su set di dati differenti in base all’approccio utilizzato, classico o time series. L’analisi sperimentale si è basata sull’analisi di dati provenienti da dispositvi ARANCINO e si è voluto indagare su come un approccio time series possa migliorare o meno le performance dei modelli rispetto all’approccio classico, avendo a dispozione informazioni anche su una finestra di istanti di tempo precedenti e non solo sull’istante di tempo corrente, quindi più dati disponibili durante l‘apprendimento. Le principali conclusioni del lavoro di Tesi indicano come l’utilizzo di un approccio time series porti a un significativo miglioramento delle prestazioni dei modelli, con conseguente maggiore efficacia nella rilevazione di anomalie.

## Conclusioni
L’obiettivo del presente lavoro di Tesi è stato quello di esplorare degli approcci time series nel campo dell’anomaly detection e valutare i potenziali benefici dell’applicazione di tali approcci. L’indagine sperimentale ha portato ad ottimi risultati, rivelando che un approccio time series risulta essere molto più efficace di un approccio classico all’analisi dei dati. In particolare possiamo concludere che:
###
Un approccio time series determina un aumento delle performance dei modelli. In particolare, si ha un ottimo aumento dei valori di MCC e un error rate più che dimezzato. Tra tutti gli approcci analizzati, l’approccio time series con differenze risulta essere il migliore.
###
La validità dei risultati ottenuti vale anche per istanze diverse del problema, come è stato verificato con il dataset my-all3, tenendo però in considerazione che la generalità dei modelli è stata testata usando un feature set limitato e sottoposto ad operazioni di preprocessing.
###
L’ampiezza della finestra temporale è il parametro da ottimizzare. Una maggiore ampiezza garantisce più informazioni in fase di addestramento dei modelli portando a performance migliori, a discapito però di un maggior numero di features e quindi di un maggior costo computazionale.
###
L’introduzione di una metrica come lo Speed Score (SS) nella valutazione di anomaly detectors può essere un buon indice da affiancare a metriche più robuste, come l’MCC.


In conclusione, un approccio time series si è dimostrato essere una valida, ma soprattutto migliore, alternativa all’approccio classico all’analisi dei dati nell’ambito dell’anomaly detection.
