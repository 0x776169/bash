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

<h1> Les boucles </h1>

<h2> Boucle [FOR] Répétitif <h2>
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
