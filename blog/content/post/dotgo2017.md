---
title: "dotGo 2017"
description: "La dotGo 2017 au théatre de Paris"
date: 2018-02-13T10:15:02+01:00
draft: true
tags : [
    "conference",
    "dotGo",
    "go",
]
categories : [
    "conferences",
]
---
{{< load-photoswipe >}}

La dotGo 2017 s'est une fois de plus déroulée au [théâtre de Paris](https://goo.gl/maps/3c4xym8SrJ92) le lundi 06 novembre 2017.

## Arrivée
Les trottoirs se remplissent, il est 9h30, la foule est divisée alphabétiquement de chaque côté de l'entrée du théâtre.
 
On aperçoit rapidement quelques speakers qui entrent se préparer. On discute avec les connaissances, collègues et amis et nous voilà aux portes du théâtre.
On récupère son badge, dépose ses affaires au vestiaire et première étape incontournable : les goodies.

Cette année aussi nous sommes gâtés, t-shirts homme et femme, stickers, tatouage et autres goodies des sponsors.
C'est les poches bien remplies et l'estomac vide que nous nous dirigeons vers le second arrêt incontournable : le petit déjeuner.
Quelques viennoiseries, jus de fruits frais et café plus tard nous voilà parés pour pour matinée de choc qui s'annonce.

La disposition des stands des [sponsors](https://www.dotgo.eu/#partners) a été revue cette année, on en profite pour continuer la chasse aux goodies 
et voir quelle est l'utilisation de Go chez Sixt l'un des sponsors majeurs de l'évènement.

## Début des conférences
La cloche retentit, il est l'heure de se trouver une place pour la première série de présentation.
Le maître de cérémonie cette année est un guest néanmoins pas inconnu du public, j'ai nommé [Blake Mizerany](https://twitter.com/bmizerany).

Vous trouverez ci-dessous les résumés et liens vers les vidéos et slides des différents speakers.
Certains sujets donnerons surement suite à des articles plus approfondis.

#### Sameer Ajmani : Simulating a real world system in go
[Sammer Ajmani](https://twitter.com/Sajma) est le manager de l'équipe Go chez Google.

Il nous a présenté une simulation en Go d'une opération du quotidien qu'est la préparation de café en boutique.
Comment optimiser le nombre de cafés préparés en fonction du personnel, des opérations à effectuer et des machines à disposition.

Go est un langage qui excelle dans le parallélisme et la concurrence, Sameer nous en présente les possibilités dans un cas d'application concret.
Channel, verrous, go routine, conditions de courses, tout est illustrés de manière ludique dans cette présentation.   

Sa [fiche dotGo est disponible ici](https://www.dotconferences.com/2017/11/sameer-ajmani-simulating-a-real-world-system-in-go)
 
{{< speakerdeck 7374acb4c326492fbf326cea56381f3d >}}

et le code source de son talk est disponible sur [son github](https://github.com/Sajmani/dotgo)
forkez si vous souhaitez tester par vous-même d'autres techniques pour préparer plus de café à la minute.

#### John Cinnamond : Go lift

Le talk de [John Cinnamond](https://twitter.com/jcinnamond) était attendu avec impatience par les connaisseurs.
Mêlant intelligemment technique et humour (troll ?), John nous présente ici ses idées pour traiter de manière moins intrusive
les erreurs dans vos programmes en Go. On termine sa présentation pour se rendre compte qu'il a réussi à nous instiller
des concepts de programmation fonctionnelle à l'insu de notre plein gré, magnifique, bravo John.   
 
Ses [slides et vidéo sont disponibles ici](https://www.dotconferences.com/2017/11/john-cinnamond-go-lift).

{{< speakerdeck 0f474ade72814bd9be851b03b854e04c >}}


#### Mat Ryer : The art of testing

[Mat Ryer](https://twitter.com/matryer) travaille pour [machinebox.io](https://machinebox.io),
habitué aux lightning talks et auteur de [Go Programming Blueprints](http://amzn.eu/c5kIMmM)
il nous a fait le plaisir de remplacer [Jessie Frazelle](https://twitter.com/matryer/status/927801298610741248) au pied levé
pour nous parler d'un sujet qu'il connait bien : le testing.

`Le plus difficile n'est pas d'écrire du code mais de le maintenir - Mat Ryer dotGo 2017`

Pourquoi fait-on des tests ?

* pour avoir du code maintenable
* pour dormir la nuit quand ce code est en production
* pour avoir confiance dans les changements fait à ce code
* pour comprendre les impacts de ces changements

Les tests même s'ils allongent les temps de développement sont un investissement à long terme.
Qui sait, avec l'avènement du machine learning, on n'écrira bientôt plus que les tests et les machines se chargeront du code !

Mat nous donne ici quelques bonnes pratiques pour les tests en général et particulièrement en Go.   
Vous trouverez tout le détail de sa [présentation ici](https://www.dotconferences.com/2017/11/mat-ryer-the-art-of-testing)

#### William Kennedy : Behavior of channels

Le logging est une une science difficile, choisir son niveau de log, quel détail de log, où logger ?
Il est aussi très facile de détériorer les performances d'un programme en ayant trop de log à traiter
ou encore si le logger en peut écrire les logs sur le support choisi.
Dans son live coding William Kennedy aka Bill, formateur Go de son état, nous montre comment se servir des outils du langage
pour créer un logger non bloquant avec les mécanisme de Go, à savoir goroutine et channel.   
Sa [vidéo est disponible ici](https://www.dotconferences.com/2017/11/william-kennedy-behavior-of-channels)

#### Sam Boyer : The functional design of dep

Sam Boyer est le core committer de l'outil de gestion de dépendances de Go : **[dep](https://github.com/golang/dep)**.
Go n'est pas un langage fonctionnel même s'il en présente certaines caractéristiques. 
Sam introduit ici la [mémoïsation](https://fr.wikipedia.org/wiki/M%C3%A9mo%C3%AFsation) d'un programme. 
Une pratique qui permet de mémoriser certaines sortie de fonctions pures pour ne pas avoir à les recalculer.
Il nous explique comment ce concept est appliqué à dep pour résoudre les dépendances d'un programme.   
[Slides et vidéo sont disponibles ici](https://www.dotconferences.com/2017/11/sam-boyer-the-functional-design-of-dep)

#### Jaana B. Dogan : Go work stealing scheduler

JBD ou [Rakyll](https://twitter.com/rakyll) travaille chez Google et nous présente ici le fonctionnement du scheduler de Go.
Go traite la concurrence avec une abstraction qui lui est propre : les goroutines.
Les goroutines sont exécutées par des threads de l'OS cible. 
Le travaille réalisé par le scheduler Go est identique à celui de l'OS : définir quel programme doit s'exécuter à un instant T. 
Jaana nous en présente ici les principes et stratégies.   
[Slides et vidéo sont disponibles ici](https://www.dotconferences.com/2017/11/jaana-b-dogan-go-work-stealing-scheduler)   

{{< speakerdeck 98640ef7bffd408e861f050cb1cc81e2 >}}   

#### Cindy Sridharan : Unmasking netpoll.go

Vous ouvrez une socket TCP en Go et `ListenAndServe` mais que ce passe-t-il ensuite dans les couches basses de votre programme.
Cindy Sridharan rentre dans les couches les plus basses du langage aux frontière du noyau 
pour nous expliquer comment les couches de communications font leur travail et leur lien avec le scheduler du langage.    
[Slides et vidéo sont disponibles ici](https://www.dotconferences.com/2017/11/cindy-sridharan-unmasking-netpoll-go)

{{< speakerdeck 3e50f5a7d39b4316850fd7bcb372e220 >}}

#### Liz Rice : Debuggers from scratch

Le live coding le plus bluffant restera surement celui de Liz Rice. Avec un peu de préparation elle nous emmène
dans un périple de 20 minutes ayant pour objectif d'implémenter un debugger de Go rudimentaire, certes, mais fonctionnel !
Très instructif sur les possibilités du package `ptrace` de Go.   
[Slides et vidéo sont disponibles ici](https://www.dotconferences.com/2017/11/liz-rice-debuggers-from-scratch)

{{< speakerdeck bc8d14557a084ccfa5a6987ca72f2743 >}}

#### Francesc Campoy Flores : Machine learning and Go

Francesc a récemment quitté Google pour source{d}, entreprise travaillant sur le machine learning appliqué au code source.
Fort de sa passion pour le Go, Francesc nous montre ici les possibilité du langage en machine learning et calcul matriciel.  
[Slides et vidéo sont disponibles ici](https://www.dotconferences.com/2017/11/francesc-campoy-flores-machine-learning-and-go)

{{< speakerdeck 9f60ca6a63244109a0b4eb10dd1896f1 >}}

#### Brian Ketelsen : Is go moving to enterprise ?

Brian Ketelsen est aussi un formateur Go depuis plusieurs années. Il organise la Gophercon
et plus récemment il a choisi de poursuivre sa carrière chez Microsoft. Il conclut ici cette dotGo 2017 mais
vous ne trouverez pas la vidéo de son talk sur le site de la dotGo mais celle de la Gophercon UK s'en approche.
En substance Brian jette un pavé dans la marre et demande à Go et aux Gophers de s'ouvrir au monde de l'entreprise et à Microsoft.
Pour Brian une adoption massive de Go passe par des frameworks de qualité pour accélérer le développement d'application Go.
Parce que la standard library n'est pas l'unique réponse, 
il annonce également la création de [go-commons](https://github.com/go-commons/commons) sur la philosophie de Apache-commons et
[learn-golang.com](https://learn-golang.com)
Quelques mois après ces annonces, force est de constater que le mouvement n'a pas vraiment pris.   
[Vidéo de son talk à la Gophercon UK disponible ici](https://www.youtube.com/watch?v=mxlJqrVSalY)

## Lightning talks

En plus de ses formats classiques, la dotGo fait la part belle aux lightning talks,
ces présentations éclair pour les speakers en devenir ou pour les sujets d'introduction à un outil, une méthodologie ou autre.

#### Daniel Martí : Reducing Go Programs   

[Slides et vidéo sont disponibles ici](https://www.dotconferences.com/2017/11/daniel-marti-reducing-go-programs)

#### Jaime Silvela : Handling slow requests in your go web server   

[Slides et vidéo sont disponibles ici](https://www.dotconferences.com/2017/11/jaime-silvela-handling-slow-requests-in-your-go-web-server)

#### Fabio Rapposelli : Managing package licenses in go   

[Slides et vidéo sont disponibles ici](https://www.dotconferences.com/2017/11/fabio-rapposelli-managing-package-licenses-in-go)

#### Pascal Costanza : Go, C++ or Java for dna sequencing pipelines   

[Slides et vidéo sont disponibles ici](https://www.dotconferences.com/2017/11/pascal-costanza-go-c-plus-plus-java-for-dna-sequencing-pipelines)

#### Massimiliano Pippi :  Embedding Python in Go   

[La vidéo GothamGo est disponible ici](https://www.youtube.com/watch?v=egSvw7xYw9s)

#### Ron Evans : Gobot    

[Vidéo FOSDEM disponible ici](https://www.youtube.com/watch?v=qza7-CRCVVU)

#### Laurent Lévêque : Exposing Go code to android and python   

[Slides et vidéo sont disponibles ici](https://www.dotconferences.com/2017/11/laurent-leveque-exposing-go-code-to-android-and-python)

#### Diana Ortega : Go and data can they be friend ?   

[Slides et vidéo sont disponibles ici]()

#### Mickaël Rémond : Go for real time streaming architectures   

[Slides et vidéo sont disponibles ici](https://www.dotconferences.com/2017/11/mickael-remond-go-for-real-time-streaming-architectures)

#### Marcel van Lohuizen : Rethinking errors in go   

[Slides et vidéo sont disponibles ici](https://www.dotconferences.com/2017/11/marcel-van-lohuizen-rethinking-errors-in-go)


## Le mot de la fin

Pari tenu pour cette édition 2017 de la dotGo. Un cadre inhabituel et agréable, un lineup de qualité ainsi qu'un savant équilibre entre talk et lighting
pour garder l'auditoire en haleine. La dotGo reste un évènement européen mais on sent plus que jamais une communauté française qui s'organise,
des visages connus émerge de la foule, les meetups s'organisent, les speakers du cru montent sur scène.
Vivement l'édition 2019, car oui pour alléger le calendrier de l'équipe dot, il n'y aura
pas de dotGo en 2018, mais le rendez-vous est pris le [25 mars 2019](https://2019.dotgo.eu).

## Les photos

C'est avec plaisir que nous vous partageons nos photos de l'événement.

{{< gallery dir="/img/post/171106_gallery_dotgo" caption="L'album dotGo 2017" caption-position="none" />}}

## Liens

- [L'interview de Jaana B. Dogan à la dotGo 2017](https://frenchgo.fr/2017/11/interview-jbd-dotgo-2017)
- [L'interview de Francesc à la dotGo 2017](https://frenchgo.fr/2017/11/interview-francesc-dotgo-2017)
- [Les vidéos et slides officiels des présentations de la dotGo 2017](https://www.dotconferences.com/conference/dotgo)
- [Le live blogging en anglais de sourcegraph lors de la conférence](https://about.sourcegraph.com/go)
