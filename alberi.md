# alberi binari
Ad ogni `nodo` sono associati due **successori** detti figlio sinistro e destro.
Il nodo più in alto è detto **radice**. Una struttura ad albero che 
segue un nodo superiore è detta **sottoalbero**. I nodi che non hanno
figli sono detti **foglie**, gli altri **nodi interni**. Le "linee" sono
chiamate **archi**.
**profondità**:
- la radice ha profondità 0
- i figli di un nodo di profondità *i* hanno profondità *i+1*
L'**altezza** dell'albero è la max profondità dei nodi.

Ricorda che l'albero può essere visto ricorsivamente:
- vuoto
- nodo + albero sx + albero dx 

Se ho un albero binario di altezza `h` con tutti i nodi possibili, il numero di nodi è $$\sum_{i=0}^h i$$

## alberi binari quasi completi
Un albero binario è **completo** sse ogni nodo di profondità < h-1 possiede entrambi i figli.
In un albero binario quasi completo l'altezza è la parte intera inferiore del logaritmo in base
2 del numero dei nodi. 

## visite ad alberi binari
1. visito la radice
2. ogni volta che visito un nodo, memorizzo in un insime S i suoi figli
3. prelevo un elemento di S

### visite in ampiezza 
S è una coda, ogni visita a un nodo metto in coda i puntatori ai suoi figli.
Continuo a farlo finché la coda non è vuota.
Metto in coda anche i null.

### visita in profondità 
Viene utilizzata la *pila*. All'inizio pusho il puntatore alla radice, 
finché la pila non è vuota faccio pop del nodo e pusho i puntatori ai figli.
Potendo usare la pila dell'albero come la pila della ricorsione, posso 
visitare ricorsivamente visitando la `radice` e richiamando la visita in 
profondità per `(r.sx)` e `(r.dx)`.
**n.b:** ha fatto anche la versione in cui chiami ricorsivamente i sottoalberi
e l'ultima cosa che fai è visitare la radice. (**ordine posticipato**).
Questo metodo permette di rappresentare correttamente le espressioni, 
mediante la *notazione polacca inversa*.


# alberi generici (con radice)
Ogni nodo ha un numero arbitrario di figli.
La nomenclatura è identica a quella degli alberi binari, tranne che adesso 
possiamo parlare di **fratelli**, il **grado del nodo** è il numero di figli,
il **grado dell'albero** è il massimo grado dei nodi presenti nell'albero.

Per comodità con questo tipo di alberi utilizziamo un puntatore al padre.


## alberi di decisione
*recuperare la prima parte della lezione del 03/11*
anche negli algoritmi di ordinamento, ci sono domande binarie che sono i confronti.

