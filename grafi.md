# Grafi
!! recupera la prima parte di lezione !!

è una **sequenza di vertici**. La lunghezza del cammino è il numero di 
archi che lo compongono. Per x (partenza) e y (arrivo), ci possono essere
*diversi cammini* anche di *diverse lunghezze*.
Chiamo **cammino semplice** un cammino che non contiene *vertici ripetuti*.
Y è **raggiungibile** da x se esiste un cammino da x a y.
Un **ciclo** è un cammino da un vertice v a v stesso.
- **ciclo semplice**: solo il vertice iniziale è ripetuto.

Una **catena** tra x e y, è una sequenza di vertici con cammino "non 
orientato", ovvero non considero la direzione degli archi.
Un **circuito** è una catena chiusa.

Un grafo è **connesso**, quando tra ogni coppia di vertici esiste almeno 
una *catena*.

Un grafo è **fortemente connesso**, quando tra ogni coppia di vertici 
esiste un *cammino*. 

G'=(V', E') è un **sottografo** di G =(V, E) quando V'
Il **sottografo indotto** è molto simile, ma devo prendere *tutti* gli
archi.

Una **componenete fortemente connessa** è un sottografo indotto fortemente
connesso *massimale*.
Un grafo può essere scomposto in un unico modo in componenti fortemente
connesse.

Un **circuito hamiltoniano** è un circuito che passa per ogni vertice del 
grafo una e una sola volta. 

Un **circuito euleriano** è un circuito che passa per ogni arco del grafo
una e una sola volta.

`teorema di eulero`: esiste un circuito euleriano se e solo se il grado di 
ogni vertice è pari.


## Alberi
Un ***albero*** è un grafo non orientato, connesso e **privo di cicli**. 
-> tra ogni coppia di vertici esiste **uno e un solo cammino**.
La differenza con la struttura dati albero è che **non ha radice**.

Una ***foresta*** è un insieme di alberi.

Sia G=(V,E) un albero. allora il numero degli archi è uguale al numero dei
vertici meno uno.

`teorema`: Un grafo G=(V,E) non orientato e connesso, è un albero 
sse #E = #V-1.


## Cricca (o clique)
è un grafo non orientato completo.
**cricca in un grafo** se ha dei sottografi completi.


## Rappresentazione dei grafi
- #V = n
- #E = m 
0 <= m <= n<sup>2</sup>

### Lista di archi
1. struttura per i **veritici**
2. struttura per gli **archi**

Lo spazio occupato è &#U+03B8 (n+m)

### Lista di adiacenza
1. struttura principale dei **vertici**

