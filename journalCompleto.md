# Inizio progetto
Creazione della stanza dello spirito e del tempo

##interazioni
-La creazione della Stanza dello spirito e del tempo è partita dalla costruzione del basamento a T sulla quale sono stati posti in successioni gli oggetti quali le clessidre, i palloncini, la stanza e la cupola sovrastante
### costruzione generale
La costruzione generale di ogni oggetto della scena parte dalle due funzioni base creaQuadrilatero e creaQuadrilateroTrasparente, le quali creano semplici cubi in base alle dimensioni che ricevono, il loro colore e le loro eventuali texture. Le due si dinstinuongo nella creazione o meno di cubi trasparenti, passando il valore di opacità da porre nel Material dei cubi.
#### costruzione clessidre
-Le clessidre sono un insieme di cubi che formano rispettivamento la base, la parte superiore e la parte di vetro, creata tramite l'unione di due identici blocchi di vetro, di cui uno ruotato di 180 gradi rispetto all'asse x. Lo stesso meccanismo è stato adottato anche per la costruzione della parte superiore della  clessidra e del basamento dei palloncini. Inizialmente la scelta del colore era ricaduta sull'uso di una texture Oro, poi rimossa per questione di calcolo computazionale. La costruzione della clessidra si basa su queste funzioni:
-costruzioneClessidra, che riceve i parametri pivotClessidra, che permette lo spostamento dell'intera clessidra; altezzaCl, ovvero l'altezza della parte di vetro della clessidra; mul, utilizzato in tutti i successivi parametri per poter scalare la clessidra in basse alle esigenze; colSabbia, il colore della sabbia; clessClass   
-creaBaseClessidra, che riceve il solo pramentro m, cioè la mul precedente, e crea le due basi da porre sopra e sotto la zona di vetro.
-creaVetroClessidra, che riceve il solo paramentro mul e crea tutta la parte centrale di vetro della clessidra, facendo uso anche della funzione metaVetroClessidra, la quale restituisce una metà del vetro della clessidra, che si compone di due identiche metà, una ribaltata di 180 gradi sul suo asse x ed entrambe poi poste tra un piccolo cubo posto al centro che completa il vetro della clessidra.
#### animazione clessidre
-in un file a parte mi sono crato la clessidra e ci ho lavorato sopra
-se muovo la clessidra nel file non ho problemi (file spostamentoSabbia.html)
-problema non riesco a visualizzare il cambiamento della sabbia all'interno delle clessidre nella scena finale
giorno # finalmente siamo riusciti a caricare le clessidre con l'animazione. Molti problemi sono stati riscontrati soprattutto il fatto di aver lavorato in un file separato e poi aver dovuto caricare la clessidra con l'animazione in un'altro file.
Alla fine una pulizia del codice è stata necessaria per rendere più chiaro cosa bisognasse fare.
Dopo la pulizia comunque quando provavo ad aggiungere una clessidra in piu e fare l animazione su entrame le clessidre una sorta di bug grafico usciva perche le due clessidre condividevano una variabile ("count" inizialmente pensata per ridurre ed aumentare la velocita della serpentina nella clessidra) dopo che la variabile count e stata legata ad ogni clessidra ogni problema è stato risolto.
Il merging dei due file dopo la pulizia di quello singolo non è stato troppo complicato  un copia incolla un po generale e il risultato andava.
-alla fine abiamo ridotto il numero dei granelli all'interno delle clesside per avere una fluibilità migliore della scena.
#### costruzione palloncini
