# La programmazione ad oggetti

Che cos'è la programmazione ad oggetti? Per alcuni è "la combinazione di dati e funzioni". Per altri è "un modo per modellare il mondo reale". Infine, quando si tende a spiegare questo paradigma, si finisce sempre a parlare di tre concetti: **incapsulazione**, **ereditarietà** e **polimorfismo**.

### L'incapsulazione

L'incapsulazione viene citata per definire la programmazione ad oggetti, ma in realtà questo concetto era già presente anche in linguaggi come il C, il quale non è un linguaggio Object Oriented. Nel C, le strutture e le funzioni venivano dichiarati nei file header, mentre l'implementazione veniva definita in un file a parte.

**point.h**

```text
struct Point;
struct Point* makePoint(double x, double y);
double distance (struct Point* p1, struct Point* p2);
```

**point.c**

```text
#include "point.h"
#include <stdlib.h>
#include <math.h>

struct Point {
    double x,y;
};

struct Point* makePoint(double x, double y) {
    struct Point* p = malloc(sizeof(struct Point));
    p->x = x;
    p->y = y;
    return p;
}

double distance(struct Point* p1, struct Point* p2) {
    double dx = p1->x - p2->x;
    double dy = p1->y - p2->y;
    return sqrt((dx*dx)+(dy*dy));
}
```

Oggi nei linguaggi l'incapsulazione è certamente più semplificata, ma non possiamo attribuire il merito di questo concetto alla programmazione ad oggetti.

### L'ereditarietà

Un'altro aspetto dei linguaggi OO è l'ereditarietà. Con essa si intende la capacità di una struttura/classe di ereditare lo stesso gruppo di variabili e/o funzioni definite ad un livello più alto. Tuttavia, ancora una volta, questo concetto era già presente nel C, il quale non è un linguaggio Object Oriented.

**namedPoint.h**

```text
struct NamedPoint;
struct NamedPoint* makeNamedPoint(double x, double y, char* name);
void setName(struct NamedPoint* np, char* name);
char* getName(struct NamedPoint* np);
```

**namedPoint.c**

```text
#include "namedPoint.h"
#include <stdlib.h>

struct NamedPoint {
    double x,y;
    char* name;
};

struct NamedPoint* makeNamedPoint(double x, double y, char* name) {
    struct NamedPoint* p = malloc(sizeof(struct NamedPoint));
    p->x = x;
    p->y = y;
    p->name = name;
    return p;
}

void setName(struct NamedPoint* np, char* name) {
    np->name = name;
}

char* getName(struct NamedPoint* np) {
    return np->name;
}
```

**main.c**

```text
#include "point.h"
#include "namedPoint.h"
#include <stdlib.h>

int main(int ac, char** av) {
    struct NamedPoint* origin = makeNamedPoint(0.0, 0.0, "origin");
    struct NamedPoint* upperRight = makeNamedPoint(1.0, 1.0, "upperRight");
    printf("distance=%f\n", distance(
        (struct Point*) origin,
        (struct Point*) upperRight
    ));
}
```

Se osservate, `NamedPoint` è una derivata di `Point`, in quanto possiede gli stessi membri \(x e y\) presenti anche in `Point`. E' vero, per farlo era necessario adottare un "trucco", ovvero fare il casting alla struttura desiderata \(oggi invece non sarebbe necessario fare una cosa del genere\), ma era pur sempre un qualcosa molto vicino al concetto di ereditarietà che siamo abituati ad utilizzare oggi. Pertanto, ancora una volta, non possiamo attribuire il merito di aver introdotto il concetto di ereditarietà alla programmazione ad oggetti.

### Polimorfismo

Anche il polimorfismo era un concetto già presente prima dei linguaggi Object Oriented. Nel linguaggio C veniva applicato tramite i puntatori a funzione. Quello che però ci hanno fornito i linguaggi OO è un polimorfismo molto più sicuro e facile da impiegare. L'uso dei puntatori a funzione per ottenere un comportamento polimorfico era molto pericoloso, poiché bisognava seguire una serie di convenzioni difficili da ricordare e questo spesso era fonte di bug. I linguaggi OO hanno eliminato queste convenzioni rendendo tutto più semplice. Pertanto, seppur i linguaggi OO non hanno introdotto nulla di nuovo, possiamo dire che essi hanno imposto la disciplina del trasferimento indiretto del controllo.

### L'inversione della dipendenza

Prima che il polimorfismo diventasse facile e sicuro da impiegare, i moduli erano fortemente dipendenti tra loro. I moduli di alto livello dipendevano dai moduli di basso livello, di conseguenza le dipendenze presenti nel codice sorgente erano governate dal comportamento del sistema. Con l'utilizzo del polimorfismo, i moduli di alto livello non dipendono più dalle classi concrete, ma da astrazioni. Attraverso l'utilizzo delle interfacce abbiamo la possibilità di applicare **l'inversione delle dipendenze**, ovvero di cambiare facilmente l'implementazione che dovrà utilizzare il nostro modulo di alto livello. Così facendo abbiamo il controllo assoluto sulla direzione di tutte le dipendenze presenti nel codice sorgente. Questa è la vera potenza della programmazione ad oggetti! Per esempio, possiamo cambiare la direzione delle dipendenze affinchè il tipo di DBMS utilizzato sia differente. Ad esempio possiamo facilmente passare da un database MySQL ad un MongoDB, semplicemente utilizzando un'implementazione piuttosto che un'altra dell'interfaccia. Di conseguenza i moduli di alto livello rimangono indipendenti rispetto al tipo di DBMS utilizzato. In breve, quando cambia il codice sorgente di un componente, dovrà essere fornito solo tale componente. Questa si chiama **indipendenza di deploy.** Se i moduli possono essere forniti in modo indipendente, allora possono essere anche sviluppati in modo indipendente. Questa si chiama **indipendenza di sviluppo.**

