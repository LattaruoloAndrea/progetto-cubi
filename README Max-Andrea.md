# Inizio progetto
Il progetto definitivo prevede la costruzione della stanza dello spirito e del tempo, con un'animazione di combattimento tra Goku e Vegeta, con sullo sfondo l'animazione delle clessidre a scandire il tempo.

<a href="https://ibb.co/mRT7sH"><img src="https://preview.ibb.co/kusYXH/Screenshot_3.png" alt="Screenshot 3" border="0" /></a>

## costruzione generale
La creazione della Stanza dello spirito e del tempo è partita dalla costruzione del basamento a T sulla quale sono stati posti in successioni gli oggetti quali le clessidre, i palloncini, la stanza e la cupola sovrastante, con ulteriori dettagli. Successivamente ci siamo dedicati ai personaggi, alle loro animazioni e al loro combattimento.
La costruzione generale di ogni oggetto della scena parte dalle due funzioni base creaQuadrilatero e creaQuadrilateroTrasparente, le quali creano semplici cubi in base alle dimensioni che ricevono, il loro colore e le loro eventuali texture. Le due si dinstinuongo nella creazione o meno di cubi trasparenti, passando il valore di opacità da porre nel Material dei cubi.

### Costruzione degli oggetti della scena
#### Clessidre
Le clessidre sono un insieme di cubi che formano rispettivamento la base, la parte superiore e la parte di vetro, creata tramite l'unione di due identici blocchi di vetro, di cui uno ruotato di 180 gradi rispetto all'asse x. Lo stesso meccanismo è stato adottato anche per la costruzione della parte superiore della  clessidra e del basamento dei palloncini. Inizialmente la scelta del colore era ricaduta sull'uso di una texture Oro, poi rimossa per questione di calcolo computazionale. La costruzione della clessidra si basa su queste funzioni:
- costruzioneClessidra, che riceve i parametri pivotClessidra, che permette lo spostamento dell'intera clessidra; altezzaCl, ovvero l'altezza della parte di vetro della clessidra; mul, utilizzato in tutti i successivi parametri per poter scalare la clessidra in basse alle esigenze; colSabbia, il colore della sabbia; clessClass   
- creaBaseClessidra, che riceve il solo pramentro m, cioè la mul precedente, e crea le due basi da porre sopra e sotto la zona di vetro.
- creaVetroClessidra, che riceve il solo paramentro mul e crea tutta la parte centrale di vetro della clessidra, facendo uso anche della funzione metaVetroClessidra, la quale restituisce una metà del vetro della clessidra, che si compone di due identiche metà, una ribaltata di 180 gradi sul suo asse x ed entrambe poi poste tra un piccolo cubo posto al centro che completa il vetro della clessidra.

<a href="https://ibb.co/dDL96c"><img src="https://preview.ibb.co/jcQbmc/photo_2018_04_05_10_36_10.jpg" alt="photo 2018 04 05 10 36 10" border="0" /></a>

#### Terreno
Il terreno è stato costruito partendo dal codice fornito. E' stata aggiunta una procedura creazione terreno che dato l 'array delle altezze crea delle colonne che formano il terreno.
L altezza delle colonne corrisponde al colore dell'immagine in scala di grigi fornita.
E' stato necessario spostare la riga di codice "img.src = "textures/heightmap2.png";" fuori dalla procedura img.onload = function() perchè sennò non era possibile caricare il terreno.

#### Palloncini
I pallocini sono un insieme di cubi le cui dimensioni man mano vanno a crescere fino al cubo centrale. Vengono creati tramite le seguenti funzioni:
- creaSfera, che crea  l'intero palloncino;
- creaMetaSfera, che crea i due blocchi. Successivamente il secondo viene ruotato di 180 gradi e poi posto sopra il primo. A concludere il tutto le funzioni:
- creaAstaPalloncino, che costruisce l'asta su cui poggia il palloncino
- creaBasePalloncino che costruisce le due basi poste sopra e sotto l'asta , di colore oro.

<a href="https://ibb.co/dn65ex"><img src="https://preview.ibb.co/dYPrKx/photo_2018_04_05_10_36_16.jpg" alt="photo 2018 04 05 10 36 16" border="0" /></a>

#### Stanza
La costruzione della stanza è partita dall'unione della parte di superficie circolare sottostante e la cupola sovrastante. Per la costruzione della stanza abbiamo fatto uso delle funzioni:
- costruzioneSuperficie, la quale crea la superficie circolare con piccolissimi cubi molto alti posti tramite una position con seno e coseno per un certo angolo a nostro piacimento ( nel nostro caso 210 gradi totali). Successivamente, con analogo metodo, ma per tutta la dimensione del cerchio (360 gradi), è stato costruito un piccolo bordo sopra la superficie, dove poi va a poggiare la Cupola.
- costruzioneCupola che crea la cupola tramite lo stesso meccanismo precedente all'interno di un while, che una volta eseguito un primo cerchio della cupola, alza il valore di y per porre il successivo cerchio della cupola sopra il precedente con un raggio inferiore, fino al cerchio finale che ciude la cupola. Poi sono stati aggiunte alla stanza le due camere laterali con tetti tramite le funzioni
- costruzioneCamera, che csotruisce le due camere laterali alla stanza circolare, facendo uso di un cubo
- costruzioneTetto, infine, costruisce il tetto sovrastante le due camere.

<a href="https://ibb.co/f28wmc"><img src="https://preview.ibb.co/hhRSsH/photo_2018_04_05_10_36_08.jpg" alt="photo 2018 04 05 10 36 08" border="0" /></a>

#### Personaggi
 I personaggi sono stati costruiti con la funzione creaPersonaggio, che riceve le texture da porre sul corpo, sulle braccia e sulle gambe e crea una persona con vari cubi che vanno a formare rispettivamente le due braccia, le due gambe, il viso, i capelli, gli occhi e la bocca e il corpo. le rotazioni delle braccia sono state fatte tramite un pivot di ancoraggio posto in posizione iniziale del braccio. Per una migliore struttura abbiamo deciso di sistemare tutti i cubi che vanno a formare il personaggio tramire una funzione separata chiamata posizionamento, che pone i cubi nelle giuste posizioni a formare il personaggio.

<a href="https://ibb.co/iAPDXH"><img src="https://preview.ibb.co/nmSBKx/photo_2018_04_05_10_36_14.jpg" alt="photo 2018 04 05 10 36 14" border="0" /></a>

#### Foresta
La foresta è stata costrutita tramite la funzione creaForesta, la quale, in base ad un numero fissato, pone tanti alberi quanto il valore del numero all'interno della scena, facendo uso della Funzione
- creaAlbero, la quale tramite un cubo crea il tronco e per la parte superiore dell'albero fa uso della funzione
- creaFogliame, la quale tramite un for pone cubi di colore verde uno sopra l'altro che man mano vanno a ridursi.

<a href="https://ibb.co/gUKQex"><img src="https://preview.ibb.co/dtGSsH/photo_2018_04_05_10_36_12.jpg" alt="photo 2018 04 05 10 36 12" border="0" /></a>

### Animazioni
#### animazione clessidre
 -in un file a parte mi sono crato la clessidra e ci ho lavorato sopra
 -se muovo la clessidra nel file non ho problemi (file spostamentoSabbia.html)
 -problema non riesco a visualizzare il cambiamento della sabbia all'interno delle clessidre nella scena finale
 giorno # finalmente siamo riusciti a caricare le clessidre con l'animazione. Molti problemi sono stati riscontrati soprattutto il fatto di aver lavorato in un file separato e poi aver dovuto caricare la clessidra con l'animazione in un'altro file.
 Alla fine una pulizia del codice è stata necessaria per rendere più chiaro cosa bisognasse fare.
 Dopo la pulizia comunque quando provavo ad aggiungere una clessidra in piu e fare l animazione su entrame le clessidre una sorta di bug grafico usciva perche le due clessidre condividevano una variabile ("count" inizialmente pensata per ridurre ed aumentare la velocita della serpentina nella clessidra) dopo che la variabile count e stata legata ad ogni clessidra ogni problema è stato risolto.
 Il merging dei due file dopo la pulizia di quello singolo non è stato troppo complicato  un copia incolla un po generale e il risultato andava. Alla fine abiamo ridotto il numero dei granelli all'interno delle clesside per avere una fluibilità migliore della scena.

#### Animazione Combattimento
L'animazione del combattimento è stata trattata tramite la funzione animazioneCombattimento, la quale fa uso di diverse funzioni più elementari, descritte in seguito, volte a semplificare e struttrare meglio il lavoro. In generale la funzione prevedeve un "passaggio" da uno stato di combattimento ad un'altro tramite la variabile statoCombattimento, la quale viene aggiornata a +1 ogni qual volta il combattimento cambiava. Le fasi del coombattimento sono 8:
- statoCombattimento == -1 : qui inizialmente i due combattenti sono fermi uno di fronte all'altro per un tempo fissato.
- statoCombattimento == 0  : inizia il vero e proprio combattimento, fatti di molteplici pungni e rapidissime fasi di teletrasporto, che spiegheremo nel dettaglio successivamente. Questa fase è caratterizzata dall 'uso delle due funzioni animazioneBracciaPersonaggio e Teletrasporto, che tramite degli if e degli else if vengono usate in maniera alternata.
-statoCombattimento == 1  : I due combattenti concludono il combattimento fisico. Avviene uno spostamento dei due personaggi sugli assi y e z che li vede man mano allontanarsi.
- statoCombattimento == 2  : Una volta allontanati, i due iniziano a creare le loro rispeettivamente sfere: la sfera Genkidama per Goku; il final Flash per Vegeta.
- statoCombattimento == 3  : Terminata la creazione dei due attacchi energetici, vegnono lanciati.
- statoCombattimento == 4  : In questa fase le due "onde" si toccano e man mano la sfera Genkidama prevale sul final Flash
- statoCombattimento == 5  : Fase finale, Vegeta viene polverizzato dalla sfera Genkidama
- statoCombattimento == 6  : Combattimento concluso: la sfera Genkidama lentamente si dissolve.
- statoCombattimento == 7  : la sfera viene completamente rimossa, Goku ha vinto e si pone al centro della Stanza.

Le animazioni interne al combattimento sono le seguenti:

- ##### Animazione Pugni
L'animazione dei pugni è stata fatta tramite la funzione animazioneBracciaPersonaggio, la quale contemporaneamente sposta le braccia sull'asse z e ruota l'ancoraggio delle braccia di un angolazione random.

<a href="https://ibb.co/ehsyzx"><img src="https://preview.ibb.co/gt2LCH/Screenshot_4.png" alt="Screenshot 4" border="0" /></a>

- ##### Animazione Teletrasporto
L'animazione del teletrasporto è stata fatta tramite lo spostamento randomico di un pivot chiamato arena, il quale contiene entrambi ii personaggi dello scontro: questo simula il loro spostamento rapidissimo e pertanto il teletrasporto.

- Animazioni sfera Genkidama
- ##### Animazione  crescita sfera Genkidama
Abbiamo riprodotto la sfera genkidama che pian piano si ingrandisce (attraverso uno scale), per renderla simile a quella reale abbiamo fatto in modo da far veicolare delle mini sfere di energia verso il centro della sfera.
Le sfere una volta arrivate nel centro vengono spostate in una posizione esterna (al posto di eliminare ogni sfera e crearne una nuova). Alla fine dell' "ingrandimento" della sfera genkidama queste sfere di energia vengono rimosso dalla scena.

<a href="https://ibb.co/e15kex"><img src="https://preview.ibb.co/iOQU6c/Screenshot_5.png" alt="Screenshot 5" border="0" /></a>

<a href="https://ibb.co/ewXbmc"><img src="https://preview.ibb.co/eg6fCH/Screenshot_6.png" alt="Screenshot 6" border="0" /></a>

<a href="https://ibb.co/nBC96c"><img src="https://preview.ibb.co/jUAwmc/Screenshot_7.png" alt="Screenshot 7" border="0" /></a>

- ##### Animazione disgregamento sfera Genkidama
In seguito alla caduta della sfera verso Vegeta, abbiamo simulato la sua disgregazione partendo dal centro del corpo di Vegeta in direzione dell'asse z di quest'ultimo, dando idea del colpo che trapassa il suo corpo. Per fare questo abbiamo usato la funzione esplosioneCono, la quale creati un numero fissato di piccoli cubi li sposta idealmente dentro un Cono molto velocemente. Alcuni problemi sono sorti nell'eliminazione di questi piccoli cubi una volta terminata l'animazione. La soluzione è stata sfruttare il paramentro children per trovare l'elemento pivotCono che faceva parte dell'oggetto Vegeta ed eliminarlo tramite un for.

<a href="https://ibb.co/b4mrKx"><img src="https://preview.ibb.co/nF4dzx/Screenshot_8.png" alt="Screenshot 8" border="0" /></a>

- ##### Animazione final flash
Il final flash è stato fatto tramite l únione di due cubi che vengono trasformati in un raggio energetico tramite uno scale solo sull'asse y, il quale simula l'allungarsi del raggio
