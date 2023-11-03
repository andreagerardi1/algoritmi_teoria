# CODA

## Implementazione tramite array

Dobbiamo pensare all'array come una struttura **circolare**.
Il limite di questa implementazione è la *capacità* dell'array.
Quindi va bene solo se conosco già il numero di elementi della coda.

## Implementazione tramite liste

Il primo puntatore è il puntatore al primo elemento della coda.
Per aggiungere elementi, devo aggiungere *in fondo*, quindi aggiungo 
un puntatore all'ultimo elemento.

**Operazioni disponibili**:
- isEmpty() -> boolean
- first() -> elemento
- dequeue() -> elemento
- enqueue(elemento x) 
