---
{"dg-publish":true,"permalink":"/droni/teoria-dei-grafi/","dg-note-properties":{}}
---

**La teoria dei grafi** è un ramo della matematica (e dell'informatica) che studia le **strutture relazionali** tra oggetti. È uno degli ambiti più belli e utili della matematica discreta perché è estremamente intuitivo visivamente ma anche molto profondo.

### 1. Cos'è un grafo?

Un **grafo** è una coppia $G=(V,E)$ dove:

- V è un insieme di **vertici** (o nodi), che rappresentano gli oggetti.
- E è un insieme di **archi** (o spigoli), che rappresentano le relazioni tra gli oggetti.

**Esempio semplice**:

- Vertici: persone in una festa.
- Archi: "si conoscono".

Puoi immaginarlo come un insieme di punti collegati da linee.

### 2. Tipi principali di grafi

| Tipo di grafo           | Caratteristica principale                  | Esempio tipico                  |
| ----------------------- | ------------------------------------------ | ------------------------------- |
| **Non orientato**       | Gli archi non hanno direzione (A-B = B-A)  | Amicizie su Facebook            |
| **Orientato (digrafo)** | Gli archi hanno direzione (A → B ≠ B → A)  | Follower su Instagram/Twitter   |
| **Pesato**              | Ogni arco ha un numero (peso/costo)        | Distanza tra città su una mappa |
| **Semplice**            | Nessun cappio, nessun arco multiplo        | La maggior parte dei grafi base |
| **Multigrafo**          | Permette archi multipli tra stessi vertici | Reti stradali con più strade    |
| **Completo** ($K_n$)    | Ogni vertice è collegato a tutti gli altri | $K_5$​ ha 10 archi              |

### 3. Concetti fondamentali

- **Grado** di un vertice: numero di archi incidenti su di esso.
    - In un grafo non orientato: grado = "quante persone conosci".
    - Somma dei gradi = 2 × numero di archi (teorema della stretta di mano).
- **Cammino** (path): sequenza di vertici collegati da archi.
- **Ciclo**: cammino che torna al vertice di partenza.
- **Grafo connesso**: esiste un cammino tra ogni coppia di vertici.
- **Componente connessa**: porzione massima connessa del grafo.
- **Albero**: grafo connesso e senza cicli. Ha esattamente $n−1$ archi se ha n vertici. È la struttura più "economica" per connettere tutto.
- **Grafo bipartito**: i vertici sono divisi in due gruppi, e gli archi vanno solo tra i gruppi (non all'interno). Esempio: uomini-donne in un ballo, o partite di calcio (squadre-giocatori).

### 4. Problemi classici della teoria dei grafi

1. **Problema di Eulero** (1736) – nascita della teoria dei grafi Quando esiste un cammino che attraversa **ogni arco esattamente una volta**? → Regola: grafo connesso e al massimo 2 vertici di grado dispari.
2. **Problema di Hamilton** Esiste un cammino che visita **ogni vertice esattamente una volta**? (Molto più difficile, è NP-completo).
3. **Colorazione** Quanti colori servono per colorare i vertici in modo che vertici adiacenti abbiano colori diversi? Il **numero cromatico** $χ^G$. Per i grafi planari: bastano 4 colori (Teorema dei quattro colori).
4. **Cammino più corto** Algoritmi famosi: Dijkstra (pesi positivi), Bellman-Ford, A*.
5. **Flusso massimo** Quanto "flusso" (acqua, traffico, dati) può passare da una sorgente a un pozzo?
6. **Matching** (accoppiamento) Quante coppie posso formare senza che due condividano lo stesso vertice?

### 5. Teoremi importanti (senza troppa formalità)

- **Teorema di Ramsey**: in un grafo abbastanza grande, è inevitabile trovare o un gruppo completamente connesso o un gruppo completamente sconnesso.
- **Teorema di Menger**: la connettività è uguale al numero minimo di vertici/archi da rimuovere per disconnettere due punti.
- **Formula di Eulero** per grafi planari: $V−E+F=2$  (dove F = facce, inclusa quella esterna).

### 6. Applicazioni (tantissime!)

- **Reti sociali** (Facebook, LinkedIn)
- **Reti di computer** e internet
- **Trasporti** (Google Maps, logistica)
- **Bioinformatica** (reti metaboliche, interazioni proteiche)
- **Chip design** e circuiti elettronici
- **Intelligenza Artificiale** (**Knowledge Graph**, Graph Neural Networks)
- **Chimica** (molecole come grafi)
- **Analisi di epidemie** (diffusione dei virus)

### Come iniziare a studiarla praticamente

1. Disegnare grafi a mano.
2. Usare Python con **NetworkX** (libreria perfetta):
```
import networkx as nx
G = nx.Graph()
G.add_edges_from([('A','B'), ('B','C'), ('A','C')])
print(nx.is_connected(G))
```
3. Usare il *multigrafo non orientato* presente in [[Droni/Droni e Tromboni\|questo sito]]