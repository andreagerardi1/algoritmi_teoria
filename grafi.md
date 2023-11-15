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

### Lista di archi
1. struttura per i **veritici**
2. struttura per gli **archi**

Lo spazio occupato è &#03B8 (n+m)

### Lista di adiacenza
1. struttura principale dei **vertici**
2. Liste di lunghezza diversa di **vertici adiacenti**

$$\sum lunghezze$$ liste = 
- `2m` se grafo *non orientato* 
- `m` se grafo *orientato*

occhio che nei grafi orientati è costoso vedere gli archi entranti.


### Lista di incidenza
1. **lista di archi** (implementata come *array*)
2. **struttura per i vertici**, con liste di puntatori alla lista di archi.
il vantaggio è la rappresentazione esplicita degli archi


### Matrice di adiacenza
m[u,v] == 1 sse (u,v) appartiene al grafo.
Lo spazio occupato è n<sup>2</sup> 
Occupa troppo spazio quindi non si usa molto, però vedi gli archi entranti.


### Matrice di incidenza
- **grafi non orientati**
    + 0 se
    + 1 se 

- **grafi orientati**
    + 0 se non c'è arco
    + 1 se arco uscente
    + -1 se arco entrante


## Attraversamento dei grafi

### Visita in ampiezza
1. si visita un vertice S
2. si visitano i veritici adiacenti a S
3. si visitano i vertici adiacenti ai vertici adiacenti ad S.
(si costruisce un albero ricoprente).

**Prestazioni**:
- se rappresentato con *lista di archi* -> tempo Θ(n*m) = O(n<sup>2</sup>)


### Visita in profondità
1. inizio da un vertice S
2. partendo da S si percorre un cammino di vertici non ancora raggiunti
visitandoli tutti, terminando su un vertice privo di vicini non ancora 
raggiunti
3. si ripete dal paso precedente partendo dall'ultimo vertice sul cammino 
precedent


### Visita in profondità
1. inizio da un vertice S
2. partendo da S si percorre un cammino di vertici non ancora raggiunti
visitandoli tutti, terminando su un vertice privo di vicini non ancora 
raggiunti
3. si ripete dal paso precedente partendo dall'ultimo vertice sul cammino 
precedente.

## Ottimizzazione

### Colorazione dei grafi
...
recupera l'inizio
...


### Zaino monodimensionale
zaino altezza h, k contenitori, ciascuno con la propria altezza.
devo scegliere quali mettere nello zaino in modo da riemprlo più che posso.
- **soluzione ammissibile**: sottoinsieme S dei contenitori disponibili
tale che f(S)<= h con f(S) =  $$\sum_{ci} hi$$
- **soluzione ottima**: sottoinsieme ammissibile S* tale che 
f(S*)>= f(S) per ogni S ammissibile.

Con questa tecnica, l'unica tecnica possibile è provare tutti gli input
possibili, ma raggiungo tempo di 2<sup>n</sup>.

Possiamo però utilizzare la `tecnica greedy`.
Parte dall'**insieme vuoto** e cerca a ogni passo di espanderlo con:
- *soluzione ammissibile*
- *scelta dell'ottimo locale* tra i candidati
- *scelta irrevocabile*

a ogni iterazione, cerco il contenitore più alto, verifico che ci stia 
nello zainetto, e in caso lo metto.
**non trova sempre l'ottimo**, ma è **molto veloce**.


### Sacco del ladro
Il sacco ha un **vincolo di peso**, e il suo obiettivo è rubare roba per 
guadagnare il più possibile.
La `tecnica greedy` è di prendere le cose che hanno più valore possibile.


### Distributore di resto
Quì c'è anche il **vincolo del numero di monete** disponibile per ciascun 
taglio.
La `tecnica greedy` in questo caso potrebbe consistere nel scegliere per
prima la moneta dal valore più alto senza eccedere il resto che devo dare,
ovviamente considerando anche la *disponibilità*.



## Albero ricoprente minimo
Dato un grafo non orientato connesso, un albero ricoprente di G è un albero
G'=(V',E') con V'=V e E' sottoinsieme di E.

**problema**: trovare l'albero ricoprente di peso minimo
dato G' = (V, E') -> w(G') = &&\sum_{e c E'} w(e)$$
T= (V, E<sub>t</sub>) è un albero con E<sub>t</sub> ⊆ E
per ogni albero T' con E<sub>t</sub> ⊆ E.

Se volessi controllare tutte le combinazioni di archi, sarebbe super
inefficiente.
Utilizzerò quindi una `tecnica greedy`.


