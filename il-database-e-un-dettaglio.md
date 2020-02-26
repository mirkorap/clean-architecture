# Il database è un dettaglio

Dal punto di vista dell'architettura, il database è un dettaglio di basso livello. Pertanto, esso deve essere considerato irrilevante per l'architettura del sistema. Attenzione, non ci stiamo riferendo al modello dei dati. Quello è importante ai fini dell'architettura. Il database non è il modello dei dati, ma un servizio che fornisce l'accesso ai dati.

### Database relazionali

I database relazionali hanno rappresentato per un lunghissimo periodo \(e lo sono tutt'ora\) la forma dominante di memorizzazione dei dati. Questa popolarità è dovuta al fatto che il modello relazionale è disciplinato e robusto. Tuttavia, ai casi d'uso della nostra applicazione non gli interessa questo dettaglio. La conoscenza della struttura delle tabelle deve far parte del cerchio più esterno dell'architettura. Il database è solo un meccanismo per salvare e leggere i dati. Dal punto di vista dell'architettura, non dovremmo preoccuparci troppo di dove e come vengono salvati i dati.

### E le prestazioni?

Le prestazioni sono certamente importanti per l'architettura di un sistema software. Certamente dobbiamo fare in modo che i dati vengono salvati e caricati in maniera rapida, ma questo è un problema di basso livello, che non ha nulla a che fare con l'architettura generale del nostro sistema.

