# I framework sono un dettaglio

I framework sono strumenti utili e, per questo, anche piuttosto popolari. Tuttavia gli autori di framework non conoscono i vostri problemi. Chi scrive i framework lo fa per risolvere i problemi **generali** della community. Certamente alcuni vostri problemi si andranno un po' a sovrapporre a quelli generali, ma non del tutto.

### Un matrimonio su basi non paritarie

Quando utilizzate un framework, spesso, non fate altro che far "_sposare"_ la vostra applicazione con quel framework. Nella documentazione del framework, l'autore vi consiglia di creare delle classi che derivano dalle classi base del framework. L'autore vi induce ad accoppiare la vostra applicazione con il framework. Una volta accoppiati, i due sistemi diventano difficilmente separabili e questo può portare a dei rischi.

### I rischi

Ecco alcuni rischi che si incorrono "_sposando_" un framework:

* I framework tendono a violare la regola della dipendenza. Vi inducono ad ereditare il loro codice nei cerchi più interni della vostra architettura, le entità!
* Man mano che la vostra applicazione cresce, potrebbe finire per non accontentarsi più delle funzionalità fornite dal framework.
* Il framework potrebbe evolvere in una direzione apposta rispetto alle esigenze della vostra applicazione. Aggiornando il framework alcune funzionalità potrebbero sparire, altre potrebbero essere modificate tanto da renderle inutilizzabili.
* Potrebbe uscire un nuovo framework più adatto alle vostre esigenze.

### La soluzione

> Non sposate il framework!

Intendiamoci, i framework sono utili, ma evitate che essi posso addentrarsi nei cerchi più interni della vostra applicazione. Se il framework vi chiede di derivare le vostre entità dalle sue classi base: dite di no! Derivate da classi Proxy e inseritele all'interno di componenti che fungono da _plugin_ per le vostre regole operative. Per esempio, se il framework vi chiede di usare le annotazioni all'interno delle vostre entità, evitatelo. Spesso i framework offrono anche soluzioni alternative, come l'utilizzo di file di configurazione \(yml, xml ecc.\)

### Conclusioni

In generale, cercate di tenere a debita distanza il framework dalle regole operative della vostra applicazione. Mantenete il framework dietro una delimitazione della vostra architettura.

