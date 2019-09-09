
# L'utilisation de Git et de GitHub

Voici une rapide introduction pour vous aider à utiliser [Git](https://git-scm.com/) à partir d'un dépôt déjà présent sur [GitHub](https://github.com). Ce document est très loin d'être exhaustif et pour de plus amples explications sur les gestionnaires de version et sur git, nous vous invitons fortement à suivre ces liens : 
  - https://git-scm.com/book/fr/v1 
  - https://openclassrooms.com/courses/gerez-vos-codes-source-avec-git

Un gestionnaire de version ?

C'est un logiciel qui permet de maintenir l'ensemble des versions d'un ou de plusieurs fichiers. C'est à dire qu'il agit sur une arborescence de fichiers afin de conserver toutes les versions de ces fichiers. Il peut être utile pour votre propre travail si jamais vous voulez revenir à une version plus ancienne de votre document ou de votre code, mais il devient surtout rapidement indispensable lorsque vous devez travailler en groupe. En effet, si deux personnes travaillent simultanément sur un même fichier, le gestionnaire de version est capable d’assembler (de fusionner) leurs modifications et d’éviter que le travail d’une de ces personnes ne soit écrasé.

Il existe différents logiciels de gestion de versions (tels que SVN, CVS...) mais nous allons nous intéresser plus particulièrement à **Git**. Ce dernier se distingue par sa rapidité et sa gestion des branches qui permettent de développer en parallèle de nouvelles fonctionnalités.

## Terminologie

**Dépôt** : Un répertoire ou un espace de stockage où vos projets peuvent vivre. Il peut être local vers un répertoire sur votre ordinateur, ou ce peut être un espace de stockage sur GitHub ou un autre hébergeur en ligne. Vous pouvez conserver des fichiers de code, des fichiers texte, des images, à l’intérieur d’un dépôt.

**Commit** : C’est la commande qui donne à Git toute sa puissance. Quand vous “committez”, vous prenez un “instantané”, une “photo” de votre dépôt à ce stade, vous donnant un checkpoint que vous pouvez ensuite évaluer de nouveau ou restaurer votre projet à tout état précédent.

**Branche** : Comment plusieurs personnes travaillant sur un projet en même temps sans que Git ne s’embrouille ? Généralement, elles se “débranchent” du projet principal avec leurs propres versions pleines de modifications qu’elles ont chacune produites de leur côté. Après avoir fait ça, il est temps de “fusionner” cette branche là avec le “master”, le répertoire principal du projet. Nous n'allons pas rentrer dans les détails des branches dans cette introduction.

## Installation

Pour son installation sur vos ordinateurs portables, suivez ce lien : https://git-scm.com/book/fr/v1/D%C3%A9marrage-rapide-Installation-de-Git 

## Configuration

La première chose à faire après l'installation de Git est de renseigner votre nom et votre adresse e-mail. C'est une information importante car toutes les validations dans Git utilisent cette information. Pour cela, ouvrez un terminal et tapez :

```
git config --global user.name "votre_nom"
git config --global user.email mon@email.com
```

## Utilisation d'un dépôt GitHub

Sans entrer dans les détails sur la manière de fonctionner de Git, voici les principales étapes pour vous lancer. 

* Créer un nouveau dépôt dans GitHub

Nous vous avions demandé de vous créer un compte GitHub. Maintenant que cela est fait, vous allez créer un nouveau **répertoire** (espace de stockage) où vous pouvez accéder à votre projet, ses fichiers, et toutes les versions de ses fichiers que Git a sauvegardés. <br>
Pour cela, cliquez sur la croix à gauche de votre îcone utilisateur (en haut à droite des pages GitHub lorsque vous êtes connecté) pour créer un nouveau répertoire. Donnez à votre dépôt un nom court et mémorisable. Afin de pouvoir effectuer l'étape suivante (le clone), cochez "Initialize this repository with a README".

* Cloner un dépôt existant : **`git clone`**

Le dépôt créé sur GitHub va vous servir de sauvegarde et vous permettre d'échanger avec les autres étudiants de votre groupe lorsque vous aurez à avancer sur des projets. Mais le gros du travail va se faire sur votre ordinateur, en local. Une manière simple de créer votre espace de travail de telle sorte qu'il soit directement paramétré avec git et lié avec le dépôt GitHub est de "cloner" le dépôt GitHub que vous venez juste de créer. <br>
Ouvrez un terminal, allez dans le dossier de votre choix (par exemple `cd Documents/cours_Python` après avoir créé le dossier `cours_Python`) puis clonez le dépôt GitHub :

```git clone https://github.com/votre_pseudo/nom_repertoire```

L'outil principal pour déterminer quels fichiers sont dans quel état est la commande **`git status`**. Si vous lancez cette commande juste après un clonage, vous devriez voir ce qui suit :

```
$ git status
On branch master
nothing to commit, working directory clean
```

* Le commit : **`git add`** puis **`git commit`**

Un *commit* est le fait d'enregistrer dans un outil de gestion de versions une nouvelle version d'un ensemble de fichiers. Une des particularité de Git est que le commit reste en **local**.

Pour indiquer à Git qu'il doit "suivre" un nouveau ficher, il faut l'ajouter :

```git add mon_fichier```

Si vous lancez à nouveau la commande `git status`, vous pouvez constater que votre nouveau fichier est maintenant suivi et indexé :

```
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   mon_fichier
```

Pour valider vos modifications, il faut ensuite faire un commit des fichiers. Attention, tout fichier auquel on n'aura pas appliqué un "`git add`" après sa modification ne fera pas parti de la prochaine validation. Il faut donc bien penser à ajouter tous les fichiers dont on souhaite sauvegarder la version actuelle avant de faire un commit.


```git commit -m "Penser a commenter chaque commit pour s'y retrouver !"```

* Pousser son travail sur le dépôt distant GitHub : **`git push`**

Lorsque votre dépôt vous semble prêt à être partagé, il faut le pousser en amont vers le répertoire GitHub que vous avez créé plus haut :

```git push```

* Télécharger les nouveautés : **`git pull`**

Si vous avez ajouté d'autres utilisateurs de GitHub en tant que *collaborateurs* (cette option se trouve dans les paramètres de votre répertoire), ils auront alors le droit de pousser leur travail dans votre dépôt GitHub. Pour alors récupérer la dernière version des documents, il faut utiliser :

```git pull```

## Conclusion

Ce document avait pour but de vous lancer d'une manière la plus simple possible dans l'utilisation de Git et GitHub pour ce cours. S'il n'y a pas de conflits dans vos fichiers, tout devrait se passer aussi simplement. Sinon, n'hésitez pas à regarder les liens fournis en haut ou à chercher sur google.