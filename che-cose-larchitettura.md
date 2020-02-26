# Che cos'è l'architettura?

L'architettura di un sistema software è la forma data a tale sistema da coloro che l'hanno realizzato. Lo scopo dell'architettura è quello di facilitare lo sviluppo, il deployment, il funzionamento e la manutenzione del software. In sintesi, l'obiettivo principale dell'architettura è quello di supportare il ciclo di vita del sistema, riducendo al minimo i costi e massimizzando la produttività.

### Sviluppo

L'architettura deve rendere un sistema facile da sviluppare. Spesso si tende ad adottare un tipo di architettura rispetto ad un'altra in base alle dimensioni del team. Nei piccoli team composti da cinque sviluppatori, si preferisce utilizzare un sistema monolitico senza componenti e interfacce ben definite. Questo è il motivo principale per cui molti sistemi non possono contare su una buona architettura. Si parte pensando che una buona architettura sia solo un impedimento e si finisce col ritrovarsi un sistema difficile da modificare.

### Deployment

Un altro obiettivo dell'architettura dovrebbe essere quello di facilitare il deployment del sistema. Sfortunatamente, la strategia di deployment non viene molto considerata nelle fasi iniziali di sviluppo. Per esempio, se un team decidesse di utilizzare un'architettura a micro-servizi e commettesse l'errore di creare un elevato numero di servizi, quest'ultimi potrebbero diventare difficili da gestire, configurare e fornire.

### Operatività

L'impatto dell'architettura sull'operatività di un sistema, in genere, è meno pesante rispetto alle altre tre fasi. I sistemi software che hanno architetture inefficienti spesso possono essere messi in opera in modo efficace semplicemente aumentando la memoria dei server. Il fatto che l'hardware sia più economico del lavoro di uno sviluppatore, ha fatto sì che l'architettura venisse pregiudicata in favore di un hardware più potente. Tuttavia, l'architettura gioca un ruolo importante sull'operatività di un sistema. Essa mette in risalto le esigenze operative, poiché evidenzia le funzionalità e i comportamenti richiesti dal sistema stesso.

### Manutenzione

La manutenzione è l'aspetto più costoso di un sistema software. L'aggiunta di nuove funzionalità o la correzione di bug rappresenta da sempre un costoso rischio. Mentre si apportano tali modifiche, la probabilità di creare nuovi bug è sempre presente. Una buona architettura dovrebbe ridurre questi rischi, grazie alla suddivisione del sistema in componenti ben isolati tramite l'utilizzo di interfacce.

### Lasciare aperte le opzioni

Tutti i sistemi software possono essere decomposti in due grandi elementi: **politiche** e **dettagli**. Le politiche sono tutte quelle regole operative su cui si basa la nostra applicazione. I dettagli sono tutte quelle cose che servono per comunicare con le politiche, ma che non hanno alcun impatto sul loro comportamento. L'obiettivo dell'architetto è quello di rendere i dettagli irrilevanti ****per le politiche, in modo che le decisioni su tali dettagli possono essere differite. 

Ecco alcuni esempi:

* **Il database**: le politiche di alto livello non si devono preoccupare del tipo di database utilizzato. Non è necessario che esso venga scelto nella fasi iniziali dello sviluppo.
* **Server web**: le politiche di alto livello non si devono preoccupare di come il sistema verrà presentato sul Web. Per assurdo, potreste anche non aver più bisogno che il sistema venga fornito tramite Web.
* **REST API**: le politiche di alto livello dovrebbero essere agnostiche in termini di interfaccia con il mondo esterno.
* **Framework**: le politiche di alto livello dovrebbero essere agnostiche rispetto al tipo di framework che si intende utilizzare.

Se riuscite a sviluppare le politiche di alto livello senza considerare i dettagli, potete differire le decisioni relative a tali dettagli. **Più a lungo attendete a prendere tali decisioni, più informazioni avrete a disposizione per prendere meglio tali decisioni.**

