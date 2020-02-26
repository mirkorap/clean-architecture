# Due diversi oggetti di valore

Ogni sistema software fornisce due diversi oggetti di valore: il **comportamento** e la **struttura**.

### Comportamento

Il primo valore del software è nel suo comportamento. In qualità di programmatori, noi scriviamo il codice che consente alle macchine di comportarsi in un determinato modo sulla base di una serie di requisiti. Quando la macchina viola questi requisiti, i programmatori azionano i sistemi di debugger per scovare l'errore e correggerlo. Molti programmatori sono convinti che il loro lavoro consista solo in questo. Purtroppo si sbagliano.

### Architettura

Il secondo valore ha a che fare con la parola stessa: soft-ware \(prodotto leggero\), ovvero un prodotto la cui forma dovrebbe essere facile da modificare. Quando un cliente chiede una modifica sul prodotto, questa modifica dovrebbe essere semplice da realizzare. **La difficoltà nell'apportare tale modifica dovrebbe essere proporzionale solo all'ampiezza e non alla caratteristica della modifica.** Tuttavia spesso i costi nello sviluppo di software sono sproporzionati rispetto alla modifica richiesta. Il problema è legato all'architettura del sistema.

### Che cosa conta di più?

Se fate questa domanda ai manager, vi risponderanno che è più importante che il software funzioni. Ma ciò è sbagliato! Meglio un programma che funziona perfettamente, ma che è impossibile da modificare e pertanto rende difficile l'aggiunta di nuove funzionalità, oppure è meglio un programma che non funziona, ma che è facile da modificare e che rende altrettanto semplice l'aggiunta di nuove funzionalità? E' facile intuire che la risposta corretta è la seconda. Pertanto noi sviluppatori abbiamo la responsabilità di far comprendere al team management che la flessibilità di oggi è più importante della funzionalità di domani.

### La matrice di Eisenhower

> Io ho due tipi di problemi: quelli urgenti e quelli importanti. Quelli urgenti non sono importanti e quelli importanti non sono mai urgenti.

Il primo valore del software, il comportamento, è urgente, ma non sempre importante. Il secondo valore del software, l'architettura, è importante, ma mai particolarmente urgente. Esistono poi anche cose urgenti e importanti e anche cose che non sono nè urgenti e nè importanti. Alla fine abbiamo questa matrice:

|  |  |
| :--- | :--- |
| **IMPORTANTI -** **URGENTI** | **IMPORTANTI -** **NON URGENTI** |
| **NON IMPORTANTI** **- URGENTI** | **NON IMPORTANTI** **- NON URGENTI** |

L'errore che compiono i manager è quello di dare maggiore priorità al comportamento rispetto all'architettura. Pertanto rientra nelle responsabilità dei team di sviluppo far comprendere al team management l'importanza dell'architettura rispetto all'urgenza della funzionalità.

### Difendete l'architettura

Questo spesso si tradurrà in una "lotta" tra le due parti. In qualità di sviluppatori abbiamo la responsabilità di proteggere il software e l'architettura. Se ciò non verrà fatto, lo sviluppo del sistema diverrà sempre più costoso e alla fine ogni modifica diverrà praticamente impossibile da applicare.

