
# Journal

## Day 1
  Creazione terreno stanza(sono i due blocchi bianchi "tipo marmo" che fanno da basamento alla stanza), con relative textures e
  costruzione clessidre. Sia il terreno della stanza che le clessidre possono essere ingrandite tramite un parametro di scalatura.
  ### Problemi
  Ci serviva un parametro per scalare gli oggetti e fare in modo che gli oggetti potessero essere scalati o meglio creati delle
  dimenzioni necessarie.
  ### Soluzioni
  Per risolvere il problema della scalatura abbiamo aggiunto un parametro m di scalatura tale che modificando solo quel parametro
  era possibile ingrandire o rimpicciolire gli oggetti senza ridimensionare ogni singolo oggetto.

## Day 2
  Sono stati  aggiunti tutti le componenti "statiche" della scene come le pareti della stanza, le due clessidre, i due pilastri
  con sopra i palloncini. Sono state aggiunte molte texture ad ogni elemento fin'ora creato (queste texture poi sono state tolte
  perchè diventava troppo pesante caricare il file).
  In contemporanea è stata sviluppata la prima parte animata della scena, l'animazione delle clessidre.
  ### Problemi
  Per l'animazione delle clessidre abbiamo optato non ad un semplice scorrimento verticale della sabbia come avviene nelle 
  clessidre normali ma ad uno scorrimento a spirale (lo scorrimento avviene in maniera opposta tra le due clessidre).Il primo
  problema è stato cercare di calcolare una funzione per lo spostamento a spirale.
  ### Soluzioni
  Per lo spostamento a spirale abbiamo deciso di partire da un movimento circolare, pian piano ridurre il raggio della 
  circonferenza su cui la sabbia si sposta e contemporaneamente far salire (o scendere) la sabbia in modo tale che raggiunga 
  il basamento opposto.

## Day 3
  Miglioramento clessidre, e aggiunta clessidre con l'animazione al progetto.
  ### Problemi
  Abbiamo riscontrato diversi problemi con le clessidre: la spirale non era centrata perfettamente con il centro della 
  clessidra,il numero di granelli di sabbia era troppo elevato all'inizio e quindi la renderizzazione della scena era pesante
  (FPS bassi) ed infine quando abbiamo aggiunto la clessidra migliorata al progetto non veniva mostrata l'animazione
  ### Soluzioni
  Il problema della spirale era dovuto ad un problema di pivot risolto quello la spirale era perfettamente centrata. Abbiamo
  dovuto ridurre il numero di granelli di sabbia ed aumentarne le dimensioni per un compromeso tra "riempimento" della 
  clessidra, buone prestazioni e che mostri una spirale più o meno corretta. Poi è stato necessario fare un refactoring di tutto 
  il codice delle clessidre per creare delle funzioni che potessero essere richiamate per la costruizone delle clessidre e
  l'animazione

## Day 4
  Aggiustatamento posizione finale della sabbia, aggiunta personaggi "Goku" e "Vegeta" la descrizione dettagliata è stata 
  inserita nel ReadMe.md
  ## Problemi
  La sabbia una volta che raggiungeva una certa altezza bisognava farla ritornare nello stadio di partenza (come cquando si usa 
  una clessidra).
  ## Soluzioni
   Per aggiustare la posizione della sabbia abbiamo usato un vettore che contenesse le posizioni x,z iniziali dei granelli (che
   non vengono modificati) e poi andare a modificare la posizione y in base su quale basamento si vuole "appogiare" la sabbia

## Day 5
  Aggiunta le animazioni ai personaggi. Goku e Vegeta simulano un combattimento per un tot di tempo dopo Goku si distanzia e
  scaglia la sfera di energia verso Vegeta
   ### Problemi
  problemi riscontrati nello spostamento ed allontanamento dei due, poichè non si trovava una condizione per fermare il loro allotnaamento 
  ### Soluzioni
  abbiamo optato per porre come condizione la distanza di vegeta rispetto all'asse x e z, mantenendo il fatto che Vegeta non                           andasse sotto il terreno con il valore y.
## Day 6
  Aggiunta l'animazione alla sfera genkidama si ingrandisce ed "assorbe" energia dello spazio circostante, aggiunta l'animazione 
  del final flesh di Vegeta. L'animazione si svolge in modo tale che la sfera e il raggio si scontrino, ma poi la sfera contionua
  il suo avanzamento verso Vegeta
  ### Problemi
  IL primo problema riscontrato è stato che la sfera Genkidama quando assorbiva le sferette esse all'inizio avevano l'effetto 
  desiderato (ovvero convergevano verso il centro), ma dopo un po quando la sfera iniziava ad ingrandirsi esse andavano in un 
  unica direzione (verso l'alto divergenti dal centro della sfera).
  Il secondo problema era fare in modo che il final flash (raggio giallo) e la sfera genkidama(cubo blu) si scontrassero e non 
  si intersecassero a vicenda.
  ### Soluzioni
  Il primo problema è stato risolto utilizzando un pivot fittizio attaccato al centro della sfera, il secondo è stato risolto
  mediante calcoli in base alla distanza della meta del final flash e la meta della sfera genkidama

## Day 7
  Abbiamo aggiunto il terreno, su cui siamo andati a posizionare la camera, è stata aggiunta l'animazione del colpo subito da
  parte di Vegeta e la "scomparsa" di quest'ultimo.
  ### Problemi
  Quando abbiamo aggiunto il terreno abbiamo avuto problemi di FPS bassi dovuti alla pesantezza del terreno.
  ### Soluzioni
  Su consiglio esterno abbiamo creato il terreno mettendo il materiale e la costruione di un pixel (cubo) del terreno fuori dal
  ciclo for che effettivamente costruiva il terreno, e poi abbiamo ingrandito i cubi usufruendo di una scalatura.
  (abbiamo guadagnato una decina di FPS, comunque non riusciamo ad raggiungere i 30 FPS)
