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
