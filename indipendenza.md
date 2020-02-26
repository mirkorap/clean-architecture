# Indipendenza

Una buona architettura deve supportare:

* I casi d'uso e l'operatività del sistema
* Lo sviluppo del sistema
* Il deployment del sistema
* La manutenzione del sistema

### Casi d'uso

Sebbene l'architettura non può avere una grande influenza sul comportamento del sistema, essa può comunque supportare i casi d'uso andando ad evidenziare e chiarire i comportamenti dell'applicazione. In questa maniera gli sviluppatori non dovranno andare alla ricerca dei comportamenti, in quanto essi saranno resi ben visibili dall'architettura del sistema.

### Operatività

L'architettura gioca un ruolo più sostanziale nel supportare l'operatività. Per esempio, se un sistema ha la necessità di gestire 100.000 clienti al secondo, l'architettura deve supportare quel livello di produttività. Per alcuni sistemi, questo significherà disporre di piccoli servizi che possono essere eseguiti in parallelo su più server. Altri sistemi, invece, possono sopravvivere anche come semplici programmi monolitici. Ciò che è importante è isolare correttamente i componenti del sistema. Un sistema che parte inizialmente come un monolite, in futuro potrebbe espandersi per passare ad una struttura a micro-servizi.

### Sviluppo

L'architettura gioca un ruolo significativo nel supportare l'ambiente di sviluppo. Un sistema che deve essere sviluppato da un'organizzazione dotata di molti team deve essere suddiviso in componenti ben isolati, così che possano essere assegnati a team differenti, i quali operano in maniera indipendente gli uni rispetto agli altri.

### Deployment

Una buona architettura aiuta il sistema a essere facilmente distribuibile. Questo si ottiene attraverso una corretta suddivisione e un apposito isolamento dei componenti.

### Lasciare aperte le opzioni

Ottenere questo equilibrio in un sistema è piuttosto difficile. Spesso abbiamo un'idea poco chiara del sistema, soprattutto nelle fasi iniziali, e anche se avessimo la conoscenza di come esso dovrebbe funzionare, la cosa non cambierebbe, perché il sistema evolve durante il suo ciclo di vita. Per questa ragione dobbiamo creare un'architettura che lasci aperte quante più opzioni possibili, così da rendere il sistema facile da modificare.

### Disaccoppiamento dei livelli

La struttura di un'applicazione deve supportare tutti i casi d'uso. Tuttavia, è impossibile conoscere a prescindere tutti i casi d'uso. Pertanto dobbiamo essere bravi ad applicare il principio SRP e il principio CCP per separare quegli elementi che cambiano a frequenze e per motivi differenti. Ad esempio, la UI cambia per motivi differenti rispetto alle regole operative. Le stesse regole operative possono essere particolarmente legate all'applicazione o più generali. La validazione dei campi di input è una regola operativa legata all'applicazione. Il calcolo dell'interesse di un conto è una regola operativa più legata al dominio. Queste regole cambiano a frequenze e per motivi differenti. Il database è un altro dettaglio che cambia per motivi differenti rispetto la UI o le regole operative. Pertanto il sistema può essere suddiviso in **livelli orizzontali** disaccoppiati, così che possano essere modificati in maniera indipendente.

### Disaccoppiamento dei casi d'uso

Gli stessi casi d'uso cambiano per motivi differenti. Il caso d'uso per l'aggiunta di un ordine cambierà per motivi differenti rispetto al caso d'uso che cancella un ordine. I casi d'uso sono come delle linee verticali che attraversano i livelli orizzontali del sistema. Ogni caso d'uso impiegherà un po' di UI, alcune regole operative e il database. Per mantenere il disaccoppiamento dobbiamo separare la UI del caso d'uso per l'aggiunta di un ordine dalla UI del caso d'uso per la cancellazione di un ordine. Mantenendo questo disaccoppiamento renderemo il sistema più facile da modificare.

### Modalità di disaccoppiamento

Il disaccoppiamento che abbiamo svolto per i casi d'uso è utile anche per l'operatività. I componenti che abbiamo creato possono essere forniti come servizi indipendenti posti su server differenti, che comunicano attraverso un qualche protocollo di rete. Questi componenti prendono il nome di "micro-servizi". Un'architettura basata sui servizi viene definita **architettura orientata ai servizi**. Questo non vuol dire che tutti i sistemi devono adottare un'architettura a servizi, ma la creazione di componenti ben isolati lascia aperta questa possibile opzione.

### Duplicazione

Durante il disaccoppiamento del codice possiamo cadere nella trappola della "finta duplicazione" ed essere tentati ad eliminarla. Tuttavia ci sono vari tipi di duplicazioni. Vi è una vera duplicazione quando ogni modifica ad un elemento obbliga ad apportare la stessa modifica ad un altro elemento. Se invece ci sono due sezioni, apparentemente duplicate nel codice, che cambiano a frequenze e per motivi differenti, allora vuol dire che non sono vere duplicazioni. Con gli anni potrebbero benissimo cambiare ed essere molto differenti tra loro.

### Modalità di disaccoppiamento \(di nuovo\)

Vi sono tre modalità di disaccoppiamento:

* **A livello di codice sorgente**: i moduli sono disaccoppiati a livello di codice sorgente. I componenti vengono tutti eseguiti nello stesso server e comunicano tra di loro attraverso semplici chiamate a funzione. Spesso si parla di struttura monolitica.
* **A livello di deployment**: alcuni componenti disaccoppiati sono suddivisi in unità di deploy indipendenti, come file jar, gem o dll. La comunicazione con questi componenti avviene tramite socket o memoria condivisa.
* **A livello di servizi**: tutti componenti disaccoppiati vengono forniti come servizi su server differenti. La comunicazione avviene tramite lo scambio di pacchetti di rete.

Quale modalità è meglio impiegare? La risposta è: dipende. Un progetto che parte in modo semplice può benissimo impiegare una struttura monolitica. Tuttavia, esso potrebbe evolversi nel corso del tempo a tal punto da richiedere un disaccoppiamento a livello di servizi. Allo stesso tempo, partire con un'architettura a micro-servizi può risultare controproducente in termini di tempi di sviluppo e costi dovuti all'infrastruttura server. Pertanto, il mio consiglio è quello di creare dei componenti ben disaccoppiati a livello di codice sorgente, così se un domani il progetto necessita di evolversi, la migrazione ad un'architettura a servizi sarà molto più semplice.

