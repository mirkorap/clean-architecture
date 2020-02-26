# Architettura "da urlo"

Le migliori architetture sono quelle basate sui casi d'uso. Il framework, il database, l'interfaccia web e così via devono essere solo "_opzioni da lasciare aperte_". La nostra architettura non deve dipendere da questi dettagli, ma bensì dalle regole operative su cui si basa la nostra applicazione.

### E il web?

Il fatto che la vostra applicazione venga fornita tramite Web non dovrebbe influire sull'architettura del vostro sistema. L'architettura del sistema dovrebbe ignorare il più possibile il modo in cui deve essere fornita \(via Web, console o app client\).

### I framework sono strumenti, non stili di vita

I framework sono strumenti molto utili e potenti, ma spesso vengono utilizzati tanto da prevalere sull'architettura. Pensate a come dovreste utilizzare il framework per preservare la priorità dei casi d'uso della vostra applicazione.

### Architetture e test

Se l'architettura del vostro sistema è basata sui casi d'uso, senza che il framework prevalga su di essa, allora dovreste essere in grado di testare facilmente la vostra applicazione. I vostri oggetti entità e gli oggetti dei casi d'uso dovrebbero essere comuni oggetti che non hanno dipendenze dal framework, dal database o da altri dettagli.

