<h1> Variable [Bool] </h1>

**En** __bash__, **la __[variable booléenne](https://fr.wikipedia.org/wiki/Bool%C3%A9en)__ est comme dans les autres langages mais nous n'avons pas besoin de préciser 
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

<h1> Condition [IF] </h1>
<p> Les conditions sont écrites comme ça </p>

```BASH
#!/bin/bash

if (( kalm == 0xkalm ));
    then 
    echo "Kalm & les conditions de if."
 
```

<h1> Exemple IF </h1>

```BASH

#!/bin/bash

echo -n "Voulez-vous faire un gâteau ? [O/N]: " && read gateau

if (( gateau == "O" ));
    then
    echo -n "Tenez un gâteau."
    
elif (( gateau == "N" ));
    then
    echo "Bah vous en aurez pas !"
    exit 1
fi
```
