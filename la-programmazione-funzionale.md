# La programmazione funzionale

La programmazione funzionale è nata prima ancora che nascesse la programmazione in sè. Questo paradigma deriva fortemente dal lambda-calcolo inventato da Alonzo Church negli anni Trenta.

### Quadrati di interi

Immaginate di dover scrivere un programma per calcolare i quadrati dei primi 25 numeri interi. In PHP avreste qualcosa del genere:

```text
<?php
for ($i = 0; $i < 25; $i++) {
    print_r(pow($i, 2) . PHP_EOL);
}
```

Usando un linguaggio funzionale come Clojure avreste:

```text
(println (take 25 (map (fn [x] (* x x)) (range))))
```

Come potete vedere, a differenza del PHP in cui abbiamo dovuto utilizzare **una variabile mutabile**, ovvero `$i`, nell'esempio in Clojure tale variabile mutabile non esiste. Questo ci porta ad affermare una delle caratteristiche più importanti di questo paradigma: nei linguaggi funzionali, le variabili non variano!

### Immutabilità e architettura

Cos'è che rende così importante la programmazione funzionale? Ogni giorno affrontiamo problemi di concorrenza all'interno delle nostre applicazioni. Questi problemi sono dati proprio dalla mutabilità delle variabili. Se le variabili fossero immutabili, non dovremmo più preoccuparci dei problemi relativi all'aggiornamento concorrente dello stato e questo ne risulterebbe nell'avere delle applicazioni molto più solide. E' proprio questo il concetto che sta dietro la programmazione funzionale!

### L'origine degli eventi

Per fare un semplice esempio, immaginate di avere un'applicazione bancaria che conservi il saldo dei suoi clienti. Quello che deve fare è aggiornare lo stato del saldo ad ogni operazione di prelievo e deposito, ovvero ad ogni transazione. Ora immaginate che invece di memorizzare ogni volta lo stato del saldo, vada a memorizzarsi soltanto le transazioni. Ogni volta che un cliente vuole conoscere lo stato del suo saldo, basta sommare tutte le transazioni eseguite sul suo conto, dall'inizio dei tempi. Questo approccio, che non richiede alcuna variabile mutabile, si chiama **event sourcing**, e pur sembrando assurdo, in quanto man mano che passa il tempo il numero delle transazioni si accumulerebbe a tal punto da rendere la nostra operazione di calcolo del saldo più lenta, è perfettamente praticabile adottando delle "scorciatoie". Per esempio, possiamo salvare lo stato del saldo ogni mezzanotte, così da dover calcolare le transazioni solo a partire dalla mezzanotte. Applicando questo approccio, non avremmo più operazioni di cancellazione o aggiornamento. Le nostre applicazioni non saranno più CRUD \(Create, Read, Update, Delete\), ma solo CR \(Create, Read\). Questo è il modo in cui lavorano i sistemi di controllo versione come Git.



