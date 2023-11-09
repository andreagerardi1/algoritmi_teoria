# Partizioni (union-find)
Le operazioni principali sono:
- `makeSet`:
- `find`:
- `union`:

Ogni insieme sono rappresentati da un albero con radice
- nodi: elementi dell'insieme
- radice: nome dell'inisieme.
La partizione intera di questi alberi si chiama **foresta**.

## QuickFind
Algoritmo che privilegia l'operazione di **find**.
Alberi tutti di altezza 1
Costi delle operazioni:
- `makeSet`: O(1)
- `find`: O(1)
- `union`: O(n), il caso peggiore è quando uno ha un solo elemento e 
l'altro n-1. In questo caso però conviene cambiare solo un puntatore e 
cambiare il nome. 

Conviene anche memorizzare la `size` nella radice.

## QuickUnion
Alberi di altezza variabile.
Riguarda le slide, ma sembra che la radice non sia un nodo ripetuto.
Costi:
- `makeSet`: devo solo creare un nodo
- `union`: O(1), devo far diventare B figlio di A. La altezza può rimanere
identica o aumentare.
- `find`: O(n), devo risalire dal nodo interessato fino alla radice. posso
migliorare migliorando la union (union by rank). In questo modo ottengo
O(logn).
Ogni albero QuickUnion costruito con Union bilanciate, contiene almeno 
2<sup>rank(x)</sup>, dove x è la *radice*.

Esiste anche una QuickUnion con **compressione di cammino**.
