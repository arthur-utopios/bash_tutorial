# La ligne de commande Bash

![*Tux, the Linux penguin*](tux.png)

Ce tutoriel vous familiarise avec **bash**. Vous allez apprendre à:

- naviguer dans les répertoires
- manipuler des fichiers
- exécuter des programmes

Si vous n'avez aucune expérience avec un système de type Unix ou connaissez quelques commandes mais souhaitez en savoir plus, ce tutoriel est fait pour vous.

### Conditions préalables

_Ce tutoriel a été préparé pour Ubuntu Linux, mais il fonctionne sur MacOS, Cygwin et Git bash, étant donné que Python 3 est installé sur
votre système._

---

## Objectif

Dans ce tutoriel, vous chercherez un mot de 22 caractères :

![](solution.png)

Tous les personnages sont cachés dans les exercices ci-dessous.

## Les préparatifs

- clonez le référentiel `https://github.com/arthur-utopios/bash_tutorial.git`
- localiser le dossier `exercises/`
- ouvrir un terminal `bash`

![](preparations.png)

---

## 1. Répertoires et fichiers

### 1.1. Navigation dans les répertoires

Le **premier caractère** est caché dans un fichier quelque part dans `exercise_1`. Utilisez les commandes

```{.sourceCode .bash}
cd <directory_name>
```

(ne tapez pas les accolades, insérez simplement le nom du répertoire) et

```{.sourceCode .bash}
ls
```

pour passer d'un répertoire à l'autre. Parcourez les sous-répertoires
jusqu'à trouver `solution_1.1` et énumérer son contenu.
Si vous vous êtes trompé de répertoire, vous pouvez revenir en arrière d'un niveau en tapant :

```{.sourceCode .bash}
cd ..
```

ou retournez dans votre dossier personnel :

```{.sourceCode .bash}
cd
```

### 1.2. Afficher un fichier caché

Certains fichiers ne sont pas visibles immédiatement. Pour les voir, il faut taper la commande

```{.sourceCode .bash}
ls -a
```

Le **deuxième caractère**, est dans le même répertoire que le premier, mais dans un fichier caché.

### 1.3. Exécuter un programme

Utilisez `cd ..` pour revenir au répertoire `exercise_1/directoryB/`.
En listant son contenu, il devrait y avoir un **fichier de script shell** `program.sh`.
Pour trouver le**troisième personnage**, vous devez exécuter le programme.
Sur bash, cela se fait en tapant source et le nom du programme:

```{.sourceCode .bash}
source program.sh
```

### 1.4. Découvrez la taille d'un fichier

Allez dans le dossier `exercise_1/directoryC/`. Trouver **le quatrième caractère** , vous devez connaître la taille du fichier texte dans le répertoire. Cela se fait avec la commande

```{.sourceCode .bash}
ls -l
```

Dans le tableau produit par la commande, vous trouverez la taille du fichier en octets, le propriétaire du fichier, les autorisations pour le lire et le modifier, ainsi que la date/heure de la dernière modification.

Pour obtenir le quatrième caractère, recherchez la taille du fichier dans le[Tableau de ASCII imprimable personnages](https://en.wikipedia.org/wiki/ASCII#Printable_characters):

![](ASCII-Table-wide.svg)

_Table ASCII, domaine public_

<div class="admonition hint">

Lorsque vous saisissez des noms de répertoires ou de fichiers, appuyez sur `[TAB]` pour avoir l'auto-complétion. Unix essaie de deviner ce que vous tapez.

</div>

---

## 2. Modifier les fichiers texte

Veuillez utiliser `cd ..` pour arriver au dossier racine où se situe `exercise_2`.

### 2.1. Voir ce qu'il y a dans un fichier texte

Dans le répertoire `exercice_2/`, vous trouverez un fichier texte `solution_2.1.txt`.
Le **cinquième personnage** est à l'intérieur de ce fichier. Pour voir son contenu, utilisez la commande

```{.sourceCode .bash}
less <filename>
```

### 2.2. Modifier des fichiers texte

Pour obtenir le **caractère numéro six**, vous devrez créer un fichier texte dans `exercise_2`.
Sur Ubuntu, vous pouvez le faire en utilisant l'éditeur `nano`.
Pour ce faire taper la commande suivante.

```{.sourceCode .bash}
nano <filename>
```

**Pour quitter nano, tapez Ctrl-X**

Créez un fichier texte avec les caractères que vous avez trouvés jusqu'à présent.

Le **sixième caractère** est celui sur lequel vous devez appuyer pour enregistrer un fichier dans`nano`.

<div class="admonition hint">

Si vous souhaitez en savoir plus sur une commande particulière, tapez

```{.sourceCode .bash}
man <command>
```

Une page d'aide s'affiche que vous pouvez quitter en appuyant sur « q ».

</div>

---

## 3. Copiez et supprimez des fichiers

Veuillez vous rendre à l'exercice `exercise_3`.

### 3.1. Créez un répertoire et copiez-y un fichier.

Pour trouver les **caractères sept et huit**, vous devez créer un
sous-répertoire nommé `solution` dans `exercise_3/`et copiez les fichiers de `part1/` et `part2/` à l'intérieur de celui-ci.

Pour créer des répertoires, utilisez la commande :

```{.sourceCode .bash}
mkdir <directory name>
```

Pour copier, vous pouvez utiliser la commande

```{.sourceCode .bash}
cp <filename from> <filename to>
```

Taper `ls -l solution/*` pour voir le contenu du répertoire.

### 3.2. Suppression de fichiers

Dans le répertoire `data`, tous les fichiers avec u n`Y `doivent être supprimés.
Utilisez la commande :

```{.sourceCode .bash}
rm <filename>
```

De plus, il y a davantage de fichiers à supprimer dans le_données_annuaire.
Pour supprimer plusieurs fichiers à la fois, vous pouvez utiliser `*` comme caractère générique, c'est-à-dire que `rm ju* `supprimera `junk.txt, juniper.txt`et `june.docx`.

Pour obtenir les caractères **neuf et dix**, regardez les fichiers qui restent après la suppression de tout ce qui contient un `Y`.

<div class="admonition hint">

Pour supprimer un répertoire vide, vous pouvez utiliser

```{.sourceCode .bash}
rmdir <directory name>
```

La commande

```{.sourceCode .bash}
rm -r <directory name>
```

supprime un répertoire et tout ce qu'il contient.

</div>

<div class="admonition warning">

Sous Unix, il n'est pas possible de restaurer des fichiers !

Cela rend la suppression des fichiers avec le `*` symbole **très** dangereuses, parce que vous pouvez tout effacer avec une seule commande (par exemple si vous tapez le mauvais répertoire par accident).

</div>

---

## 4. Traiter les données texte

Veuillez vous rendre à l'exercice `exercise_4`.

### 4.1. comparer deux fichiers

Il existe deux versions différentes d'un devis, `ai.txt`, et `artificial_intelligence.txt`.
Pour découvrir en quoi ils diffèrent, Unix fournit la commande

```{.sourceCode .bash}
diff <filename1> <filename2>
```

Bien sûr, vous pouvez d'abord regarder le texte en utilisant `less` ou `nano`.
Le **11ème caractère** de la solution est le caractère unique dans lequel le deux fichiers diffèrent.

### 4.2. Trier un fichier texte

Unix dispose d'un petit programme pour trier les fichiers texte par ordre alphabétique. On l'utilise comme ceci.

```{.sourceCode .bash}
less <filename> | sort
```

Le symbole '|' s'appelle un pipe et est souvent utilisé pour connecter Unix programmes les uns aux autres.
Le **12ème caractère** de la solution est le premier caractère du dernier mot du fichier `elephant.txt` trié par ordre alphabétique.

<div class="admonition hint">

Pour stocker les lignes triées dans un nouveau fichier, vous pouvez ajouter un fichier de sortie, comme

```{.sourceCode .bash}
less <filename> | sort > result.txt
```

</div>

### 4.3. Trouver des mots dans un fichier texte

Pour rechercher des mots spécifiques dans un fichier texte, utilisez la commande

```{.sourceCode .bash}
grep <word> <filename>
```

Il affiche toutes les lignes du fichier qui contient le mot donné.
`grep` est très puissante et peut gérer les expressions régulières.

Pour trouver le **13ème caractère**, recherchez le mot **fire** dans le fichier `datascience.txt` et prendre le **premier** caractère de la sortie.

<div class="admonition hint">

Vous pouvez rechercher dans plusieurs fichiers à la fois en incluant un `*` dans le nom de fichier.

</div>

<div class="admonition warning">

Les deux derniers exercices risquent de ne pas fonctionner sur Git Bash.

</div>

---

## 5. Décompressez les fichiers

Veuillez vous rendre à l'exercice `exercise_5`.

### 5.1. décompression des archives

La décompression de fichiers compressés est une tâche très basique et importante. Sous Unix, vous rencontrez souvent des archives WinZip, des archives .tar et des .gz compressés des dossiers.
Pour décompresser les fichiers zip Win, utilisez

```{.sourceCode .bash}
unzip <filename>
```

pour les fichiers .tar et .tar.gz

```{.sourceCode .bash}
tar -xf <filename>
```

et pour les fichiers .gz,

```{.sourceCode .bash}
gunzip <filename>
```

Le **14ème et 15ème caractère** de la solution sont compressés dans des archives de l'exercice 5.

<div class="admonition hint">

Pour grouper un répertoire et tout ce qu'il contient, vous pouvez utiliser la commande

```{.sourceCode .bash}
tar -cf backup.tar <directory>
```

Pour le compresser, utilisez

```{.sourceCode .bash}
gzip backup.tar
```

</div>

---

## 6. Outils de ligne de commande

Merci d'aller dans le répertoire `exercise_6`.

### 6.1. Modification des droits d'accès aux fichiers

Chaque fichier sous Unix dispose d'autorisations distinctes pour lire 'r', écrire 'w', et exécuter 'x'. Les afficher avec :

```{.sourceCode .bash}
ls -l
```

Il existe un triplet d'autorisations pour le propriétaire du fichier, un triplet pour un groupe d'utilisateurs et un pour tous les autres. La commande `chmod` permet de modifier ces autorisations, par ex.

```{.sourceCode .bash}
chmod a+x <filename>
```

accorde à tous les utilisateurs la permission d'exécuter un fichier, tandis que chmod u-w interdit à l'utilisateur actuel (lui-même) d'écrire dans le fichier (et ainsi le protégeant d’une suppression accidentelle).

Pour afficher les **caractères 16+17** de la solution, rendre le fichier ` permissions.sh` exécutable. Puis exécutez-le avec :

```{.sourceCode .bash}
./permissions.sh
```

<div class="admonition hint">

Vous pouvez accorder des autorisations pour une arborescence de répertoires entière en utilisant

```{.sourceCode .bash}
chmod -R a+x <directory>
```

</div>

### 6.2. Combien d’espace disque me reste-t-il ?

Pour savoir combien d'espace disque il vous reste, vous pouvez utiliser la commande

```{.sourceCode .bash}
df
```

`df` répertorie toutes les partitions du disque dur, les CD-ROM, les clés USB et certains partitions logiques utilisées par Unix.
Tous les nombres sont donnés en kilo-octets (1000 octet ou un 1000000ème Go).

Pour obtenir le **18ème caractère**, consultez la version du `df` programme.
Découvrez comment procéder avec :

```{.sourceCode .bash}
df --help
```

La solution est le dernier caractère du prénom des premiers auteurs.

### 6.3. Définir une variable d'environnement

Pour installer certains programmes, il est nécessaire de définir ce qu'on appelle l'environnement variables.
Ceux-ci peuvent être définis à l'aide de la commande

```{.sourceCode .bash}
export <variable-name>=<value>
```

Vous pouvez voir toutes les variables par la commande

```{.sourceCode .bash}
env
```

Pour obtenir le **19ème caractère**, vous devez utiliser `export` pour affecter la valeur `SOLUTION` à la variable `GIVME`.

```{.sourceCode .bash}
echo $GIVEME
```

Découvrez le **la position du caractère** avec :

```{.sourceCode .bash}
echo $GIVEME | wc -c
```

<div class="admonition hint">

Par défaut, les modifications apportées aux variables d'environnement n'affectent que le terminal actuel.

Si vous souhaitez définir des variables d'environnement pour toutes les fenêtres de console, écrivez la commande d'export vers le fichier `.bashrc` dans votre répertoire personnel (c'est un
fichier caché).

</div>

### 6.4. Vérifiez si vous avez Internet

Le moyen le plus simple de vérifier à partir de la ligne de commande Unix si Internet fonctionne consiste à envoyer une requête à un serveur connu (par ex.[www.spiced-academy.com](http://www.spiced-academy.com)) à l'aide de la commande

```{.sourceCode .bash}
ping <web address>
```

La commande indique la durée des allers-retours d'un message vers le
serveur donné. Pour interrompre les messages, appuyez sur Ctrl+C. Vous pouvez utiliser le programme

```{.sourceCode .bash}
./check_ping
```

Le **20ème caractère** est le `ping` option qui définit le nombre maximum de demandes envoyées. Consultez la documentation avec :

```{.sourceCode .bash}
man ping
```

### 6.5. Gestion des processus

Pour voir quels programmes sont en cours d'exécution sur votre ordinateur, tapez

```{.sourceCode .bash}
top
```

Il vous affiche une liste de tous les programmes actuellement actifs.

- `MAJ + P`: permet de trier par le temps de CPU qu'il utilisent
- `MAJ + M` permet de trier par mémoire vive utilisée
- `Q` permet de quitter le programme

Les **deux derniers caractères** de la solution sont les deux premiers caractères du deuxième mot de la ligne contenant les étiquettes des colonnes.

<div class="admonition hint">

Si vous souhaitez vous débarrasser d'un des programmes que vous avez démarré (par exemple parce que il s'est écrasé), vous pouvez le faire en tapant

```{.sourceCode .bash}
kill -s 9 <pid>
```

</div>

Vous trouverez le numéro de pid dans la première colonne de la sortie _top_. Bien entendu, vous ne pouvez interrompre que vos propres programmes, et non ceux qui appartiennent à des tiers.
Bien entendu, vous ne pouvez interrompre que vos propres programmes, et non ceux de _root_, l'administrateur du système.

---

### Licence

**© 2010 Dr Kristian Rother**

Ce didacticiel est publié sous Creative Commons Attribution
Licence de partage à l'identique 4.0

Vous pouvez trouver les sources complètes sur[&lt;https://github.com/krother/bash_tutorial>](https://github.com/krother/bash_tutorial).

### Remerciements

Je remercie Janusz M. Bujnicki, Allegra Via, Pedro Fernandes et Joachim
Jacob pour son aide lors des tests et de la révision du matériel. Plus loin
merci au Service allemand d'échanges universitaires (DAAD) pour ses contributions financières
soutien.

### Contact

Dr Kristian Rother

[krother@academis.eu](krother@academis.eu)

[www.academis.eu](www.academis.eu)
