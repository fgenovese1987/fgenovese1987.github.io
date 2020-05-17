---
layout: post
title: L'impalcatura di uno spazio topologico (Italiano)
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
|\Delta^n| = \{(x_0,\ldots,x_n) \in \mathbb R^{n+1} : \sum_{i=0}^nx_i=1\},
$$

il cosiddetto *$n$-simplesso geometrico*. La definizione scritta così può spaventare, ma basta svolgerla per $n=0,1,2$ per capire che è in realtà molto naturale:

- Se $n=0$, si tratta di un singolo punto!
- Se $n=1$, si tratta del segmento che collega i punti $e_0=(1,0)$ e $e_1=(0,1)$ nel piano.
- Se $n=2$, si tratta del triangolo con vertici i punti $e_0=(1,0,0), e_1=(0,1,0), e_2=(0,0,1)$ nello spazio tridimensionale.

Per $n>2$, avremo effettivi $n$-simplessi "geometrici". Se la definizione sopra rimane nonostante tutto ostica da digerire, potete sostituirla con dei disegnini (numerate i vertici!) e andrà bene lo stesso.

Con tali modelli fra le mani e la nozione di continuità, abbiamo finalmente modo di capire in modo preciso cosa sono "punti in $X$", "linee in $X$", "triangoli in $X$" e via dicendo:

- un "punto" sarà una funzione continua $x \colon |\Delta^0| \to X$. Questo significa davvero scegliere un elemento $x \in X$!
- una "linea" sarà una funzione continua $\gamma \colon |\Delta^1| \to X$. Questo significa prendere un cammino continuo tra due punti di $X$!
- un "triangolo" sarà una funzione continua $\alpha \colon |\Delta^2| \to X$. Questo significa proprio prendere una qualche "forma triangolare continua" in $X$, magari un po' bruttina a vedersi
- in generale, un "$n$-simplesso" sarà una funzione continua $\beta \colon |\Delta^n| \to X$.
