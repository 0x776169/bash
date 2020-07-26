<h1> Hello World </h1>
<h2> Simple Hello World </h2>
<p> Afficher du texte </p>

```BASH
#!/bin/bash

echo "Hello World"
```
<hr>

<h1> Les différentes variables spéciales </h1>

```BASH
Nom	fonction

$*	contient tous les arguments passés à la fonction
$#	nombre d'arguments
$?	code de retour de la dernière opération
$0	nom du script
$n	contient l'argument n, n étant un nombre
$!	contient le PID de la dernière commande lancée
```

<hr>
<h1>Opérateurs de comparaison</h1>

```BASH
Caractères       Significations
──────────	 ──────────────
   -eq	         est égal à
   -ne	         n'est pas égal à
   -gt	         est plus grand que
   -ge	         est plus grand ou égal à
```

<h2> Autres : </h2>

```BASH
Caractères       Significations
──────────	 ──────────────

    = 		 initialisation d'une constante numérique2)
    == 		 est égal à
    != 		 une différence
    > 		 plus grand que
    >= 		 plus grand ou égal que
    < 		 plus petit que
    ⇐ 		 plus petit ou égal que
```

<hr>

<h1> Opérateurs de test sur les fichiers </h1>
<p> Peut servir pour différent script ^^ </p>

```BASH
Opérateurs       Significations
──────────	 ──────────────
-e fichier 	Renvoie 0 si le fichier existe.
-d fichier 	Renvoie 0 si le fichier existe et est un répertoire.
-f fichier 	Renvoie 0 si le fichier existe et est un fichier 'normal'.
-w fichier 	Renvoie 0 si le fichier existe et est en écriture.
-x fichier 	Renvoie 0 si le fichier existe et est exécutable.
f1 -nt f2 	Renvoie 0 si f1 est plus récent que f2.
f1 -ot f2 	Renvoie 0 si f1 est plus vieux que f2. 
```

<h2>Exemple : </h2>

```BASH
#!/bin/bash
 
echo -n "Nom du fichier :" && read fichier

if [ -e "$fichier" ]; 
     then
     echo "Le fichier existe"
     else
     echo "Le fichier n'existe pas ou alors il n'est pas dans le répertoire ainsi."
fi
```

<hr>

<h1> Conditions </h1>

<h2> Condition [IF] </h2>
<p> Les conditions sont écrites comme ça </p>

```BASH
#!/bin/bash

if (( kalm == 0xkalm ));
    then 
    echo "Kalm & les conditions de if."
 
```

<h2> Exemple IF </h2>

```BASH

#!/bin/bash

echo -n "Voulez-vous un gâteau ? [O/N]: " && read gateau

if (( gateau == "O" ));
    then
    echo -n "Tenez un gâteau."
    
elif (( gateau == "N" ));
    then
    echo "Bah vous en aurez pas !"
    exit 1
fi
```
<hr>

<h2> Condition [ELSE] </h2>
<p> En général, la condition else, est utilisée en cas d'erreur entrée dans le champ </p>

```BASH

if (( pseudo == kalm ));
        then
        echo "Bonjour $pseudo"
        else 
        echo "Pseudo incorrect"
fi 

```
<hr>

<h1> Variable </h1>

<h2> Variable [Bool] </h2>

**En bash, la [variable booléenne](https://fr.wikipedia.org/wiki/Bool%C3%A9en) est comme dans les autres langages mais nous n'avons pas besoin de préciser 
< bool > comme en c# par exemple, on pourrait mais on en a pas besoin**

Exemple : 


```BASH
#!/bin/bash

kalm=true

if [ "$kalm" = true ] ; 
    then
    echo "C'est vrai !"
fi
```

<hr>

<h1> Les boucles </h1>

<h2> Boucle [FOR] Répétitif </h2>
<p> Boucle qui se répète 5 fois, puis s'arrête. </p>
    
```BASH

#!/bin/bash

for KALM in 1 2 3 4 5 .. N
do
	echo "kalm"
	echo "le meilleur"
	echo "développeur"
done
```

<h2> Boucle [FOR] Infini </h2>

```BASH
#!/bin/bash

for (( ; ; ))
do
   echo "La boucle est infini, tu peux faire ctrl + c pour l'arrêter"
done
```

<hr>

<h1> Regroupement d'informations </h1>
<h2> Regrouper plusieurs commandes ou textes</h2>

```BASH
#!/bin/bash

info="je m'appelle 0xkalm"
age="j'ai 14 ans"



print_information() {
echo $info
echo $age
}

print_information
```

<hr>

<h1> Les options </h1>
<p> Exemple : ./programme.sh -s [file], en exécutant ça, il supprimera le fichier indiqué </p>

```BASH
#!/bin/bash

print_notfound() {
echo "Cette option n'existe pas."
}

print_help() {
echo "Usage: $0 -$OPTIONS"
}

while getopts "k:a:l:mox?:" OPTIONS; do 
   case ${OPTIONS} in
      k ) file=$OPTARG && rm -rf $file && reset && echo "$file a bien été supprimé" ;;
      a ) ;;
      l ) ;;
      m ) ;;
      o ) ;;
      x ) ;;
      ? ) clear && print_notfound; exit 0;;
   esac
done


if (( file == 'a-zA-Z0-9' ))
     then 
     echo "Suppression de $file"
     fi
```

<hr>

<h1> Les effets, les couleurs. </h1>
<p> 

Comme toute personne, tout le monde a voulu faire un script avec différentes couleurs pour différenciés quelque chose de spéciale dans le script ou bien autre chose ou bien pour faire joli.

<hr>

toute commande sous linux, il faut utiliser une syntaxe par défaut et y donner quelques paramètres. Pour les couleurs c’est le même principe.

```BASH

echo -e '\033[A;B;Cm toto \033[0m'

```

Dans la commande ci-dessus, nous pouvons constater qu’il y a 3 paramètres présents: A, B et C..

```
A = un effet affecté au texte affiché 
B = à la couleur du texte 
C : identifie la couleur du fond du texte affiché
```

Et enfin on termine avec 

```
\033[0m 

```
qui indique au terminal de revenir aux couleurs définies par défaut.

 </p>
<h2> Effets : </h2>

```BASH
Code	Effet
────    ─────
0	Normal
1	Gras
21	Non-gras
2	Sombre
22	Non-sombre
3	Italique
23	Non-italique
4	Souligné
24	Non-souligné
5	Clignotant
25	Non-clignotant
7	Inversé
27	Non-inversé
8	Invisible
28	Non-invisible
9	Barré
29	Non-barré
```

<h2> Couleurs </h2>

```BASH
Couleur texte  Couleur fond     Couleur	
─────────────  ──────────── ────────────── 
      30	     40	         Noir
      31	     41          Rouge
      32             42          Vert
      33             43		 Jaune
      34             44		 Bleu
      35             45		 Magenta
      36             46          Cyan
      37             47          Blanc
```

<h3>Exemple : </h3>

```BASH
 echo -e "\033[3;31;30m 0xkalm \033[1;34m est\033[9;33m passionné par l'infosec \033[0m"
 ```
