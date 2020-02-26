# Il Web è un dettaglio

Il Web fa parte di quella lista di dettagli che dovrebbero essere irrilevanti per la vostra applicazione. Esso fa parte di quella lista di "oscillazioni" che hanno caratterizzato la storia dell'informatica. Queste oscillazioni vanno e vengono, ed è per questo motivo che non dobbiamo far dipendere le nostre regole operative da questi dettagli.

### La morale

La morale è che il Web non è altro che una GUI. Un semplice device di I/O. Pertanto il Web non è altro che un dettaglio. La nostra applicazione dovrebbe essere _device independent_. Un'indipendenza totale sembra di fatto impraticabile, in un certo senso è vero, ma c'è una parte della nostra applicazione che possiamo astrarre e renderla indipendente dalla UI. Stiamo parlando dei casi d'uso. Ogni caso d'uso può essere descritto sulla base dei dati di input, dell'elaborazione svolta e dei dati di output. Da dove provengono questi dati di input e come essi poi verranno fatti visualizzare una volta elaborati, non deve interessare ai casi d'uso. Questi dati di input e output possono essere collocati in strutture semplici e scambiati all'interno dell'applicazione. In questa maniera rendiamo i casi d'uso device independent.

