# Livelli e delimitazioni

Finora abbiamo parlato dei sistemi facendo riferimento sempre alla presenza di tre componenti: UI, regole operative e database. Ma è davvero tutto così semplice? Ogni sistema è formato da solo questi tre componenti? Purtroppo no...

### Architettura clean

Per la maggior parte dei sistemi il numero di componenti è maggiore. Anche il più semplice dei sistemi potrebbe nascondere un numero non indifferente di delimitazioni. In qualità di architetti dobbiamo fare attenzione a riconoscere quando e come implementare tali delimitazioni. Dobbiamo considerare che implementare una delimitazione completa è molto costoso. Al contempo, ignorare una delimitazione potrebbe diventare problematico nel momento in cui ci occorre implementarla. Dobbiamo essere bravi ad individuare le delimitazioni, capire se implementarle completamente, parzialmente o semplicemente ignorarle. Queste decisioni non possono essere prese tutte già all'inizio del progetto. Esse devono essere prese man mano che il sistema evolve. L'obiettivo è quello di implementare le delimitazioni esattamente nel momento in cui i costi di implementazione scendono sotto i costi dovuti al fatto di ignorarle.

