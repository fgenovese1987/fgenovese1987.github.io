---
layout: post
title: Introduzione agli spazi topologici (italiano)
excerpt: "Una breve introduzione alla nozione di spazio topologico (post in italiano)"
tags: [topology, italiano]
mathjax: true
comments: true
category: blog
---

La parola "spazio" è sicuramente una di quelle a cui siamo più familiari. Però, concettualmente, cosa vuol dire davvero "spazio"? La matematica, tra le altre cose, si è occupata di rispondere a questa domanda, di indagare - si può dire, in un certo senso, filosoficamente - cosa sia davvero uno "spazio". Nella storia sono state date svariate risposte e tuttora sul tema viene svolta ricerca (in direzioni che potrebbero sembrare completamente fuori dalla realtà) ma per ora ci concentreremo su una proposta piuttosto intuitiva e (tutto sommato) familiare.

Uno *spazio*, intuitivamente, è un insieme (diciamo per comodità $X$) fatto di elementi $x \in X$ che pensiamo come *punti*. Però, questi punti non sono "isolati" (o, ecco, non lo sono per forza). Pensiamo ad esempio ad una retta, che viene modellizzata bene dall'insieme dei numeri reali $\mathbb R$, oppure ad un piano (che ci piace pensare come $\mathbb R \times \mathbb R = \mathbb R^2$), oppure addirittura ad un fantomatico spazio $n$-dimensionale (che sarà $\mathbb R^n$). Dati due punti di questi spazi è perlomeno possibile *misurare quanto distano*, con una semplice formula che nel caso del piano $\mathbb R^2$ è data da

$$
d((x_1,x_2),(y_1,y_2))= \sqrt{(x_1-y_1)^2+(x_2-y_2)^2},
$$

prendendo ispirazione dal teorema di Pitagora. (Potrete immaginare che una formula simile produrrà una misura di distanza soddisfacente per punti in $\mathbb R^n$).

La presenza di una distanza su $\mathbb R^2$ fa sì che possiamo introdurre una nozione dal sapore decisamente "topologico", ossia quella di *aderenza di un punto ad un certo insieme di punti*. Diamo una definizione "informale":

**Definizione**: sia $A \subseteq \mathbb R^2$ un sottoinsieme di punti del piano, e sia $x=(x_1,x_2) \in \mathbb R^2$ un punto del piano. Diciamo che *$x$ è aderente ad $A$* se $x$ è "arbitrariamente vicino" ad un qualche punto di $A$.

L'espressione tra virgolette "arbitrariamente vicino" non è banale da catturare in termini formali. Però, è possibile: significa che *per ogni $0 < \varepsilon < 1$ ($\varepsilon$ in matematica è solitamente una "incertezza", che possiamo prendere "piccola a piacere": potevamo anche chiedere che fosse $< \frac{1}{1000}$ o più piccolo ancora) esiste almeno un punto $y \in A$ tale che $d(x,y) < \varepsilon$*. Per capire un po' meglio di cosa si tratta, vale la pena fare un esempio. Disegnate un quadrato nel piano, però senza il bordo esterno: un esempio potrebbe essere il sottoinsieme $A=(-1,1) \times (-1,1) \subseteq \mathbb R^2$. Proviamo a chiederci: il punto $(0,0)$ è aderente ad $A$? Be', è già dentro $A$, quindi un punto che sia arbitrariamente vicino a $(0,0)$ e stia in $A$ esiste sicuramente: è lo stesso $(0,0)$. Ora, facciamoci guidare dall'intuizione: quali altri punti potrebbero essere *aderenti* a questo quadrato senza bordo? Proviamo a prendere un punto di "quello che sarebbe il bordo", per esempio il punto $x=(1,1)$. Sarà aderente? L'intuizione direbbe di sì, ci sembra certamente "arbitrariamente vicino" a un qualche punto del nostro $A$. E in effetti, se fissiamo $\varepsilon > 0$ sufficientemente piccolo (diciamo pure $\varepsilon <1$) e consideriamo il punto $y=(1-\varepsilon, 1-\varepsilon)$,  tale punto sta certamente in $A$, e del resto con un semplice calcolo:

$$
d(x,y) = \sqrt{\varepsilon^2 + \varepsilon^2} = \sqrt 2 \varepsilon,
$$

e questo ci basta a dire che $x$ è aderente ad $A$ (piccola osservazione: a vederla così, sembrerebbe che non abbia davvero ottenuto $d(x,y) < \varepsilon$ come volevo, ma la verità è che funziona lo stesso. Provate a pensare al perché!). Arrivati qui, l'intuizione sembra suggerire che l'insieme dei punti aderenti ad $A$ sia dato dal "quadrato chiuso" (quelli fuori da tale quadrato chiuso non sarebbero dunque aderenti). Come esercizio, provate a dimostrare questa affermazione!

A questo punto, un po' di linguaggio per aiutarci nel seguito. Dato un sottoinsieme $A \subseteq \mathbb R^2$, definiamo

$$
\overline{A} = \{x \in \mathbb R^2 : \text{$x$ è aderente ad $A$}\}
$$

Questo insieme di punti aderenti può di certo essere pensato come la *chiusura* di $A$, come nell'esempio visto sopra, e infatti è chiamato così anche nella pratica matematica. Finalmente, possiamo dare una definizione di *funzione continua* che forse sembrerà un po' più intuitiva di quella che di solito viene presentata durante i corsi di analisi (ma in realtà è del tutto equivalente!):

**Definizione**: sia $f \colon \mathbb R^2 \to \mathbb R^2$ una funzione dal piano in sé (va bene anche dalla retta in sé, o dalla retta al piano, o tutte le varianti che potete immaginarvi). Diciamo che $f$ è *continua* se dato un qualsiasi sottoinsieme $A \subseteq \mathbb R^2$, abbiamo che $x$ aderente ad $A$ implica che $f(x)$ è aderente all'insieme $f(A) = \{f(z) : z \in A\}$. Più sinteticamente:

$$
f(\overline{A}) \subseteq \overline{f(A)}.
$$

Ora, apprestiamoci a fare qualcosa che è squisitamente "matematico": l'*astrazione* e l'*assiomatizzazione*. In effetti, per quanto $\mathbb R, \mathbb R^2$ e cose simili siano tra gli esempi più comuni di "spazi" che potremmo avere in mente, il nostro scopo è un po' più generale, filosofico in un certo senso. Vogliamo capire cos'è l'*essenza* del concetto di spazio, vogliamo andare oltre i singoli esempi. E una proposta possibile ci viene rileggendo quanto abbiamo fatto finora. Sembra infatti che la nozione chiave adoperata sia quella di *aderenza*. Dunque... *se provassimo ad assiomatizzarla e renderla in un certo qual modo "arbitraria"?* Dunque, cosa potrebbe essere per noi uno "spazio"? Iniziamo da un insieme $X$ di "punti". Poi, dato un sottoinsieme $A \subseteq X$ qualsiasi, *diamo una nozione arbitraria di aderenza*, ossia gli associamo un altro sottoinsieme $\overline{A} \subseteq X$ che penseremo come "punti di $X$ aderenti ad $A$". Arrivati qui, avremo bisogno di imporre alcune proprietà 'ragionevoli':

- Se $x \in A$, vogliamo che sia aderente ad $A$. Ossia: $A \subseteq \overline{A}$.
- Abbiamo detto sopra che $\overline{A}$ può essere pensata come *chiusura* di $A$. Ci aspettiamo che prendere la chiusura della chiusura non aggiunga nulla: $\overline{\overline{A}}=\overline{A}$.
- Se $A, B \subseteq X$ sono due sottoinsiemi di $X$, vogliamo che essere aderenti all'unione $A \cup B$ sia la stessa cosa di essere aderenti ad $A$ oppure aderenti a $B$, ossia:  $\overline{A \cup B} = \overline{A} \cup \overline{B}$.
- C'è un sottoinsieme di $X$ un po' speciale, l'insieme vuoto $\emptyset$, per cui l'intuizione va sempre un po' a farsi benedire: chiederemo comunque che essere aderenti al vuoto sia una condizione... vuota: $\overline{\emptyset} = \emptyset$.

Queste richieste sono in linea con l'intuizione (l'esposizione precedente dovrebbe averla costruita almeno un poco) però lasciano una certa libertà di scelta. Dato un certo insieme di 'punti', possiamo *noi* decidere come si comportano dal punto di vista topologico! E dunque, arriviamo ad una definizione di grande successo storico (in verità, data qui in un modo leggermente diverso da come solitamente viene presentata, ma completamente equivalente):

**Definizione**: uno *spazio topologico* è il dato di un insieme $X$ e di una funzione $A \mapsto \overline{A}$ definita e a valori nell'insieme di tutti i sottoinsiemi di $X$, soggetta alle proprietà menzionate sopra. I punti di $\overline{A}$ si diranno "aderenti ad $A$", e $\overline{A}$ si dirà "chiusura di $A$".

Di seguito, faremo un'altra cosa tipica in matematica, ossia *abuseremo la notazione*, e scriveremo $X$ per indicare *lo spazio topologico che ha come insieme di "supporto" $X$*, di fatto confondendo due concetti diversi (quello di mero "insieme" e quello di "insieme con struttura di spazio topologico"). A questo punto, finalmente, possiamo dire cos'è una funzione continua tra spazi.

**Definizione**: siano $X$ e $Y$ spazi topologici. Una funzione $f \colon X \to Y$ si dice *continua* se preserva l'aderenza, ossia

$$
f(\overline{A})\subseteq \overline{f(A)}.
$$

per ogni sottoinsieme $A \subseteq X$.

Come esercizio: controllate che dato uno spazio topologico $X$, la funzione identità $1_X \colon X \to X$ è continua, e che date due funzioni continue $f \colon X \to Y$ e $g \colon Y \to Z$, la composizione $g\circ f \colon X \to Z$ è ancora continua.

Per concludere questa parte, giusto un paio di esempi "generali" ma istruttivi. Dato un insieme $X$, è sempre possibile renderlo uno spazio topologico in due modi diametralmente opposti:

- Nel primo caso, definiamo $\overline{A} = A$ per ogni sottoinsieme $A$. Come a dire: ogni insieme è chiuso, oppure i punti aderenti ad ogni insieme sono solo quelli che appartengono ad esso. Tale scelta produce una topologia su $X$ che si dice *topologia discreta*. In un certo senso, è quella che "distingue più di tutte". Ogni punto è davvero da pensarsi "isolato" con questa scelta.
- Nel secondo caso, definiamo $\overline{A} = X$ per ogni sottoinsieme $A$. Come a dire: ogni punto dello spazio è aderente a qualsiasi insieme. Tale scelta produce una topologia su $X$ che si dice *topologia indiscreta o banale*. In un certo senso, è quella che "distingue meno di tutte", e può essere pensata come un blob molto indistinto in cui dal punto di vista topologico ogni punto viene confuso a tutti gli altri.
- Sugli spazi $\mathbb R^n$ e pure sui loro sottoinsiemi, la nozione di aderenza che mettiamo è quella descritta nella prima parte dell'esposizione (bisognerebbe essere un po' più precisi qui, ma ci accontentiamo). Tale topologia è detta *topologia euclidea*.

Abbiamo una nozione di "spazio", ora, e possiamo finalmente cercare di capire un po' più precisamente cosa significa individuare una sua [*impalcatura*](https://fgenovese1987.github.io/blog/impalcatura-spazio/). Questo, però, farà sì che la nozione di spazio così come l'abbiamo data venga già messa (un po') in crisi!

<iframe width="560" height="315" src="https://www.youtube.com/embed/1Id2Kg1zwn0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
