# Principi di progettazione

In questa parte del libro affronteremo i famosi principi [SOLID](https://williamdurand.fr/2013/07/30/from-stupid-to-solid-code/) e le implicazioni che essi hanno in termini di architettura software. I principi SOLID ci dicono come disporre le nostre funzioni e le nostre strutture nelle classi e come queste classi dovrebbero essere interconnesse \(per termine "classe" qui si intende un semplice raggruppamento di funzioni e dati. I principi SOLID si dovrebbero applicare a prescindere se si tratta di programmazione ad oggetti\). L'obiettivo di questi principi è quello di avere un software:

* Facile da modificare
* Facile da comprendere
* Facile da riutilizzare

L'acrostico SOLID viene utilizzato per descrivere questi cinque principi:

* **SRP \(Single Responsibility Principle\):** La struttura di un software è fortemente influenzata dalla struttura dell'organizzazione che la impiega, in modo che ogni modulo software abbia un solo motivo per cambiare.
* **OCP \(Open-Closed Principle\):** Affinchè i sistemi siano facili da modificare, essi devono essere progettati in modo tale da permettere la modifica del comportamento aggiungendo del nuovo codice, invece di modificare il codice esistente.
* **LSP \(Liskov Substitution Principle\):** Affinchè le parti di un software siano intercambiabili, queste parti devono aderire ad un "contratto", che consenta a queste parti di essere sostituite l'una con l'altra.
* **ISP \(Interface Segregation Principle\):** Questo principio esorta a evitare di dipendere da cose che poi non si usano.
* **DIP \(Dependency Inversion Principle\):** Il codice di alto livello non dovrebbe dipendere dal codice che implementa i dettagli di basso livello.

