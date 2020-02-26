# Il principio ISP \(Interface Segregation Principle\)

Questo principio esorta a dividere le interfacce più grandi in interfacce più piccole e specifiche \(chiamate anche **interfacce di ruolo**\). In questo modo le classi concrete implementeranno solo i metodi delle interfacce che effettivamente vengono utilizzati.

### Violazione del principio ISP

Quando il codice client dipende da metodi che non utilizza, generalmente significa che c'è qualche problema a livello di astrazione e pertanto si sta violando il principio ISP. Per evitare ciò dobbiamo decomporre il problema in modo tale da identificare i ruoli che entrono in gioco all'interno del nostro dominio. Questa operazione non può essere effettuata a priori, ma bensì quando ci accorgiamo di poter astrarre delle funzionalità, altrimenti andremmo incontro ad un problema di over-engineering.

### Conclusioni

In sintesi il principio ISP ci esorta a creare dei componenti dal basso accoppiamento e da un'elevata coesione.

