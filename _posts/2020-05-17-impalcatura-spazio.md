---
layout: post
title: L'impalcatura di uno spazio topologico (italiano)
excerpt: "Vediamo la definizione dell'insieme simpliciale singolare associato ad uno spazio topologico (post in italiano)"
tags: [topology, italiano]
mathjax: true
comments: true
category: blog
---

Teniamo sempre massimamente presente la nostra intuizione. Fare topologia significa certamente indagare il concetto di spazio in generale, ma anche poi lavorare materialmente su alcuni 'spazi' particolarmente interessanti: circonferenze, sfere, tori (altrimenti detti "ciambelle col buco"), eccetera. Cosa potrebbe essere l'"impalcatura" di uno spazio come questi? Giusto per fare un esempio: per quanto concerne le superfici, un approccio che storicamente ha avuto successo è quello delle "triangolazioni". Si prende una superficie e si disegnano su di essa punti, linee (anche curve) e "triangolini". Sembra un'idea interessante: uno spazio viene decomposto in "componenti" distinte per dimensione:

- in dimensione $0$, i punti
- in dimensione $1$, linee tra i punti (anche "curve")
- in dimensione $2$, "triangoli" (i cui lati sono le "linee curve" di cui sopra)
- in dimensioni superiori? Avremo "triangoli $n$-dimensionali". Per $n=3$ saranno dei tetraedri, per $n>3$ l'intuizione visiva viene un po' a mancare ma con l'immaginazione possiamo aiutarci. Si tratterà di entità che chiameremo *$n$-simplessi*.

Ora, prendiamo un qualsiasi spazio topologico $X$. Seguiamo l'idea delineata sopra per costruire una sua impalcatura piuttosto generale. Il primo passo è capire cosa sono "punti", "linee", "triangoli" e in generale "$n$-simplessi" in $X$. Per farlo, introduciamo per prima cosa modelli geometrici molto familiari di punti, linee, triangoli, $n$-simplessi. Definiamo:

$$
|\Delta^n| = \{(x_0,\ldots,x_n) \in [0,1]^{n+1} : \sum_{i=0}^nx_i=1\},
$$

il cosiddetto *$n$-simplesso geometrico*. La definizione scritta così può spaventare, ma basta svolgerla per $n=0,1,2$ per capire che è in realtà molto naturale:

- Se $n=0$, si tratta di un singolo punto!
- Se $n=1$, si tratta del segmento che collega i punti $e_0=(1,0)$ e $e_1=(0,1)$ nel piano.
- Se $n=2$, si tratta del triangolo con vertici i punti $e_0=(1,0,0), e_1=(0,1,0), e_2=(0,0,1)$ nello spazio tridimensionale.

Per $n>2$, avremo effettivi $n$-simplessi "geometrici". Se la definizione sopra rimane nonostante tutto ostica da digerire, potete sostituirla con dei disegnini (numerate i vertici!) e andrà bene lo stesso.

Con tali modelli fra le mani e la nozione di continuità, abbiamo finalmente modo di capire in modo preciso cosa sono "punti in $X$", "linee in $X$", "triangoli in $X$" e via dicendo:

- un "punto" sarà una funzione continua $x \colon \lvert \Delta^0 \rvert \to X$. Questo significa davvero scegliere un elemento $x \in X$!
- una "linea" sarà una funzione continua $\gamma \colon \lvert \Delta^1 \rvert \to X$. Questo significa prendere un cammino continuo tra due punti di $X$!
- un "triangolo" sarà una funzione continua $\alpha \colon \lvert \Delta^2 \rvert \to X$. Questo significa proprio prendere una qualche "forma triangolare continua" in $X$, magari un po' bruttina a vedersi
- in generale, un "$n$-simplesso" sarà una funzione continua $\beta \colon \lvert \Delta^n \rvert \to X$.

La storia non finisce qui. Una proprietà cruciale dei simplessi è che hanno delle *facce* che sono a loro volta simplessi di dimensione inferiore. Ad esempio, $\lvert \Delta^1 \rvert$ ha due facce di dimensione $0$ che sono letteralmente il punto iniziale e il punto finale del segmento. Facendo un piccolo sforzo di formalizzazione, possiamo certamente vedere queste due "facce" come funzioni continue:

$$
\begin{align*}
\delta^0 \colon |\Delta^0| & \to |\Delta^1|, \\
\delta^1 \colon |\Delta^0| & \to |\Delta^1|.
\end{align*}
$$

Anche se può sembrare strano, con $\delta^0$ denotiamo il vertice *finale*, e con $\delta^1$ denotiamo il vertice *iniziale*, per il motivo che sarà più chiaro ora che generalizziamo. Infatti, volendo considerare le facce del triangolo $\lvert \Delta^2 \rvert$, denoteremo per esempio

$$
\delta^0 \colon |\Delta^1| \to |\Delta^2|
$$

la faccia *opposta al vertice che ha l'etichetta $0$*. Si tratta di un lato del triangolo! Naturalmente avremo anche $\delta^1$ e $\delta^2$ in questo caso. Più in generale, avremo facce

$$
\delta^i \colon |\Delta^{n-1}| \to |\Delta^n|
$$

per $i=0,\ldots,n$.

Manca ancora un ingrediente: è opportuno "complicarsi un po' la vita" e considerare simplessi "degeneri". Per esempio, possiamo vedere un punto come una "linea degenere", una linea come un "triangolo degenere" e così via. Più formalmente, avremo ad esempio una funzione continua

$$
\sigma^0 \colon |\Delta^1| \to |\Delta^0|
$$

che prende il segmento e lo collassa nel punto. In dimensioni superiori? Avremo ad esempio $\sigma^0 \colon \lvert \Delta^2 \rvert \to \lvert \Delta^1 \rvert$ che collassa i vertici $0$ e $1$, e $\sigma^1 \colon \lvert \Delta^2 \rvert \to \lvert \Delta^1 \rvert$ che collassa i vertici $1$ e $2$ (con un disegno sarà tutto più chiaro). In generale avremo

$$
\sigma^i \colon |\Delta^{n+1}| \to |\Delta^n|
$$

per $i=0,\ldots,n$, e l'idea è che $\sigma^i$ collassa fra loro i vertici $i$ e $i+1$. Queste mappe $\sigma^i$ e $\delta^i$ non sono slegate fra loro, ma soddisfano opportune relazioni (che però sono noiose da ricordare e da scrivere, per quanto completamente "naturali").

Finalmente, possiamo usare tutto quel che abbiamo osservato per finalizzare la nostra "impalcatura dello spazio $X$". Iniziamo con esempi in "dimensione bassa":

- Dato un punto $x \colon \lvert \Delta^0 \rvert \to X$, possiamo associarvi un "cammino degenere" $s_0 x \colon \lvert \Delta^1 \rvert \to X$, che si ottiene dalla composizione $\lvert \Delta^1 \rvert \xrightarrow{\sigma^0} \lvert \Delta^0 \rvert \xrightarrow{x} X$.
- Dato un cammino $\gamma \colon \lvert \Delta^1 \rvert \to X$, possiamo associarvi gli estremi finale e iniziale componendo con le facce $\delta^i \colon \lvert \Delta^0 \rvert \to \lvert \Delta^1 \rvert$. Avremo dunque dei punti $d_0 \gamma, d_1 \gamma \colon \lvert \Delta^0 \rvert \to X$. 
- Osserviamo per inciso che il cammino degenere $s_0 x$ ha come estremi iniziale e finale lo stesso punto $x$: $d_0s_0 x = x$ e $d_1 s_0 x=x$.
- In generale, dato un $n$-simplesso $\alpha \colon \lvert \Delta^n \rvert \to X$, avremo $(n-1)$-simplessi $d^i\alpha$ ottenuti componendo con le mappe $\delta^i$. Le possiamo vedere come "facce di $\alpha$". Avremo poi $(n+1)$-simplessi "degeneri" $s_i \alpha$, ottenuti componendo con $\sigma^i$. Si possono vedere come "degenerazioni di $\alpha$". Facendo qualche disegno l'intuizione sarà chiara!

Abbiamo tutto per definire finalmente questa impalcatura di $X$, come detto piuttosto generale. Un po' di notazione, ora:

$$
\operatorname{Sing}_n(X) = \{\text{funzioni continue $|\Delta^n| \to X$}\}.
$$

Gli elementi dell'insieme $\operatorname{Sing}_n(X)$ sono anche chiamati *$n$-simplessi (singolari) di $X$*. Dalla discussione precedente deduciamo l'esistenza di funzioni:

$$
\begin{align*}
d_i \colon \operatorname{Sing}_n(X) &\to \operatorname{Sing}_{n-1}(X), \\
s_i \colon \operatorname{Sing}_n(X) &\to \operatorname{Sing}_{n+1}(X),
\end{align*}
$$

per $i=0,\ldots,n$. Chiameremo $d_i$ *operatori di faccia* e $s_i$ *operatori di degenerazione*. Essi soddisfano alcune identità dette *identità simpliciali*, che non riporterò qui (ma con qualche disegno diventano del tutto chiare).

La collezione dei $\operatorname{Sing}_n(X)$ insieme con gli operatori di faccia e degenerazione è un ente matematico che si chiama *insieme simpliciale*, lo denoteremo con $\operatorname{Sing}(X)$. Più in astratto:

**Definizione**: un *insieme simpliciale* $S$ è il dato di insiemi $S_0, S_1,\ldots$ insieme con funzioni

$$
\begin{align*}
d_i \colon S_n &\to S_{n-1}, \\
s_i \colon S_n &\to S_{n+1},
\end{align*}
$$

soggette alle identità simpliciali.

Gli insiemi simpliciali saranno i veri protagonisti di questo corso, e già ora sorge spontanea una domanda:

*È possibile ricostruire $X$ in qualche modo a partire da questa sua "impalcatura simpliciale" $\operatorname{Sing}(X)$?* 

Nel caso la risposta fosse affermativa, la nozione di spazio a cui siamo approdati con la definizione di spazio topologico potrebbe essere messa in crisi: potremmo chiederci se potrebbe valer la pena *confondere il concetto di spazio con quello di "sua impalcatura"*, ossia chiederci:

*Per caso, la nozione di insieme simpliciale è in grado di catturare l'essenza del concetto di spazio?*
