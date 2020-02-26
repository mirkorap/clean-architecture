# Il principio DIP \(Dependency Inversion Principle\)

Questo principio ci dice che un sistema è flessibile se le dipendenze presenti nel codice sorgente fanno riferimento ad astrazioni e non a concrezioni. In un linguaggio ad oggetti significa che il nostro codice deve dipendere da interfacce e classi astratte e non da classi concrete. Ciò non vuol dire che dobbiamo creare un'interfaccia per qualsiasi cosa, ma significa che dobbiamo evitare di avere delle dipendenze dirette con degli elementi concreti che sono sottoposti a frequenti modifiche. In questo modo si favorisce il disaccoppiamento del codice e si facilita la modifica dei moduli.

### Astrazioni stabili

Le architetture software stabili sono quelle che evitano di dipendere da classi concrete volatili \(ovvero che cambiano di continuo\) e favoriscono l'uso di interfacce astratte stabili. Questa implicazione si riassume in un insieme di tecniche di programmazione:

* **Non fate riferimento a classi concrete volatili:** al contrario, fate riferimento ad interfacce astratte stabili.
* **Evitate di creare derivate di classi concrete volatili:** l'ereditarietà crea una forte e rigida relazione nel codice sorgente; pertanto dovrebbe essere utilizzata con cautela.
* **Non eseguite l'override di funzioni concrete volatili:** le funzioni concrete spesso introducono dipendenze. Quando viene fatto l'override di queste funzioni, anche queste dipendenze vengono ereditate.
* **Non menzionate mai il nome di nulla di concreto e volatile:** questa è una semplice riaffermazione del principio stesso.

### Componenti Concreti

Chiaramente da qualche parte dobbiamo pur indicare le nostre dipendenze concrete. Le violazioni a questo principio non possono essere eliminate completamente, ma possono essere raccolte in un numero ristretto di componenti e mantenute separate rispetto al resto dell'applicazione. Spesso si ha il componente `Main` che si occupa di istanziare gli oggetti concreti e di passarli all'applicazione oppure si utilizza il pattern [Abstract Factory](https://it.wikipedia.org/wiki/Abstract_factory).

### Conclusioni

In sintesi il DIP ci dice che i componenti di alto livello non devono dipendere dai componenti di basso livello. Al contrario, sono i componenti di basso livello a dover dipendere dalle regole operative di alto livello. Di conseguenza i componenti dell'applicazione che contengono le regole operative devono utilizzare elementi astratti come le interfacce e le classi astratte che sono meno soggette alle modifiche rispetto alle classi concrete. In questa maniera abbiamo il pieno controllo delle nostre dipendenze e possiamo facilmente invertire la loro direzione. Da qui il nome Dependency Inversion Principle.

