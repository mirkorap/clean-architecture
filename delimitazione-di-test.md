# Delimitazione di test

Dal punto di vista dell'architettura tutti i test sono uguali. Che si tratti di test unitari, funzionali o di accettazione, essi seguono tutti la regola della dipendenza. I test sono molto dettagliati e concreti, inoltre nessun elemento del sistema dipende da essi. Pertanto, possiamo considerare i test come il cerchio più esterno del sistema.

### Progettare per la collaudabilità

L'estremo isolamento dei test spesso porta a pensare che tali test non rientrino nella struttura del sistema. Questo è un errore che può portare alla creazione di test fragili che contribuiscono a rendere il sistema rigido e difficile da modificare. I test devono cambiare insieme al sistema. Se essi vengono accoppiati in maniera errata con il sistema, anche la più piccola modifica di un componente può pregiudicare il funzionamento di centinaia di test. Per esempio, se i test per collaudare le regole operative utilizzano la GUI, basta una semplice modifica all'interfaccia utente per pregiudicare il funzionamento di un'enorme quantità di test. La soluzione è sempre la stessa: **non dipendete da elementi volatili**. Pertanto progettate il sistema e i test in modo tale che le regole operative possano essere collaudate senza usare la GUI.

