# VIM Cheatsheet 

---

## Déplacement

- **h**      : Gauche.
- **l**      : Droite.
- **j**      : Bas.
- **k**      : Haut.
- **$**      : Fin de ligne.
- **0**      : Début de ligne.
- **w**      : Début du prochain mot.
- **b**      : Début du mot.
- **e**      : Fin du mot.
- **%**      : Saute au {[()]} correspondant.
- **fY**     : Prochaine occurence de 'Y' sur la ligne.
- **gg**     : Début du fichier.
- **G**      : Fin du fichier.
- **XG**     : Début de la Xieme ligne.
- **H**      : Haut de l'écran.
- **M**      : Milieu de l'écran.
- **L**      : Bas de l'écran.
- **CTRL+f** : Avance d'un écran.
- **CTRL+b** : Recule d'un écran.

Fonctionne avec un quantificateur :

- **[nombre] [déplacement]**

Exemples : 

- **3w**      : Début du 3eme prochain mot.
- **3j**      : Début 3eme ligne en dessous.
- **5e**      : Fin du 5ème prochain mot.
- **f+SPACE** : Prochain espace sur la ligne.

## Mode Insertion 

- **i** : Sous le curseur.
- **I** : Début de ligne.
- **a** : Après le curseur.
- **A** : Fin de ligne.
- **o** : Nouvelle ligne au dessous.
- **O** : Nouvelle ligne au dessus.
- **s** : Remplace le caractère sous le curseur.
- **S** : Remplace la ligne entière.

## Suppression

- **x**  : Supprime le caractère sous le curseur.
- **d [déplacement]**
- **d [nombre] [déplacement]**

Exemples :

- **d$**  : Supprime du curseur jusqu'a la fin de la ligne.
- **dG**  : Supprime du curseur jusqu'a la fin du fichier.
- **d5w** : Supprime les 5 prochains mots.

## Sélection de texte 

Pour sélectionner du texte il faut rentrer en mode **Visual**

- **v**      : Mode Visual.
- **CTRL+v** : Mode Visual bloc.
- **V**      : Sélectionne toute la ligne courante. 

On peut ensuite sélectionner du texte avec les commandes de déplacement.

## Copier / Couper / Coller

Une fois le texte selectionné on peux effectuer des opérations :

- **dd** : Coupe la ligne courante et la place dans le registre de vim.
- **y**  : Copie le texte selectionné ou la ligne courante si aucune sélection.
- **p**  : Colle le contenue du registre.
- **d**  : Coupe le texte sélectionné.

## Remplacement 

- **rX** : Pour remplacer le caractère sour le curseur par X.
- **R**  : Pour remplacer plus d'un caractère.  
- **xp** : Change le caractère sous le curseur avec le suivant.
- **Xp** : Change le caractère sous le curseur avec le précèdent.

L'opérateur de remplacement fonctionne comme celui de déplacement :

- **c [nombre] déplacement**

Exemples :

- **c2e** : Supprime du curseur jusqu'a la fin du deuxieme mot et passe en mode Insertion.	
- **c$**  : Supprime du curseur jusqu'a la fin de la ligne mot et passe en mode Insertion.	

## Recherche

- **/texte** : A la suite du curseur.
- **?texte** : Qui précède le curseur.
- **n** : occurence suivante.
- **N** : occurence précedente.
- **:set ic**   : Pour ignorer la case.
- **:set noic** : Pour ne plus ignorer la case.

## Substitution

- **:s/ancien/nouveau**        : Change uniquement la première occurence sur la ligne.
- **:s/ancien/nouveau/g**      : Change toute les occurences sur la ligne.
- **:X,Ys/ancien/nouveau/g**   : Change toutes les occurences sur plage de ligne [X-Y].
- **:%s/ancien/nouveau/g**     : Change toute les occurences dans le fichier.
- **:%s/ancien/nouveau/gc**    : Change toute les occurences dans le fichier avec demande de confirmation.

## Execution de commande 

- **:!cmd** : Exécute une commande externe.

## Sauvegarde de sélection

Une fois du texte sélectionné avec le mode VISUEL :

- **:w FILENAME** : Enregistre la sélection dans le fichier FILENAME.

## Insertion 

L'insertion se fait toujours sur la ligne en dessous du curseur.

- **:r FILENAME** : Insère le contenue du fichier FILENAME.
- **:r !cmd**     : Insère STDOUT de cmd.

## Annulation 

- **u**      : Annuler l'action précédente.
- **U**      : Annuler tous les changements sur la ligne.
- **CTRL-R** : Annuler l'annulation.

## Sauvergarder & Quitter Vim

- **:q** : Quitter si le fichier n'a pas été modifié.
- **:qa** : **q** pour tous les fichiers.
- **:q!** : Quitter sans sauvegarder.
- **:qa!** : **q!** pour tous les fichiers. 
- **:w** : Sauvegarder.
- **:wa** : **w** pour tous les fichiers.
- **:x** : Quitter en sauvegardant.
- **:xa** : **x** pour tous les fichiers.
- **:wFILENAME**  : Enregistre sous.

## Gestion des buffers

**vim file1 file2 file3** : Ouvrir plusieurs fichier en même temps.

- **:bn** : Buffer suivant.
- **:bp** : Buffer précédant.
- **:bd** : Ferme le buffer courant.
- **:tabe file** : Ouvre un file dans un nouveau buffer.

## Multiscreen

- **CTRL+w v** : Split écran horizontalement avec le fichier courant.
- **CTRL+w s** : Split écran verticalement avec le fichier courant.
- **CTRL+w l** : Fenetre droite.
- **CTRL+w h** : Fentre gauche.
- **CTRL+w j** : Fenetre bas.
- **CTRL+w k** : Fenetre haut.
- **CTRL+w**   : Fenetre suivante.

---

# Mapping

- **CTRL+j** : Insère une ligne vide après la ligne du curseur.
- **CTRL+k** : Insère une ligne vide avant la ligne du curseur.
- **CTRL+h** : Supprime une ligne vide après la ligne du curseur.
- **CTRL+l** : Supprime une ligne vide après la ligne du curseur.
- **ALT+j** : Déplace la ligne courante ou le bloc sur la ligne du dessous.
- **ALT+k** : Déplace la ligne courante ou le bloc sur la ligne du dessus.
- **ve** : Ouvre ~/.vimrc.
- **vr** : Reload ~/.vimrc.
- **CTRL+p** : Lance FZF.
- **CTRL+m** : Lance MarkdownPreview.
- **SPACE+a** : Ajoute le caractère a sous le curseur.

## Leader key

**Leader = ','**

- **Leader+n** : Buffer suivant.
- **Leader+p** : Buffer précédant.
- **Leader+d** : Ferme le buffer courant.
- **Leader+[0-9]** : Se déplace au buffer [0-9] (Note : 0=10).
- **Leader+y** : Copie la ligne courante sans le retour a la ligne.

---

# Plugin

## Gestion des plugins

- **:PlugInstall** : Installe tous les plugins présent dans .vimrc.
- **:PlugClean** : Supprime les plugins installés plus présent dans .vimrc.

## lightline 

Affiche des couleurs pour les différents mode de vim et informations sur le fichier.

## ligthline-bufferline

Affiche les différents buffers ouvert en haut de l'écran.

## nerdtree

- **:NERDTree** : Affiche l'arborescence de fichier du répertoire courant.

## vim-gitgutter

Montre les lignes modifiées par rapport au dernier commit.   

## markdown-preview

- **:MarkdownPreview** : Affiche le fichier dans un navigateur web.

## vim-cursorline

Met la ligne du curseur en surbrillance.

## fzf

- **:FZF** : Lance une recherche de fichier intéractif.

Exemples :

- **'toto**  : Tous les fichiers qui s'appellent "toto".
- **toto**   : Tous les noms de fichiers qui contiennent "toto".
- **^toto**  : Tous les noms de fichiers qui commencent par "toto".
- **toto$**  : Tous les noms de fichiers qui terminent par "toto".
- **!toto**  : Tous les noms de fichiers qui ne contiennent pas "toto".
- **!^toto** : Tous les noms de fichiers qui ne comment pas par "toto".
- **!toto$** : Tous les noms de fichiers qui ne terminent pas par "toto".

FZF permet aussi de faire de la recherche a l'intérieur de fichiers.   
Voir [README.md](https://github.com/junegunn/fzf) pour plus d'information.

## comments

- **CTRL+c** : Met en commentaire la ligne courante ou le bloc.
- **CTRL+x** : Enlève le commentaire de la ligne courante ou du bloc.

## vim-fugitive

Wrapper pour les commandes git, permet entre autre d'afficher la branche courante. Voir [README.md](https://github.com/tpope/vim-fugitive) pour plus d'information.

## vim-multiple-cursor

- **CTRL+n** : Lance des curseurs sur chaque ligne sélectionnée avec le mode Visual bloc.

## vim-go

Wrapper pour les commandes go et détection erreurs de syntaxe. 
Voir [README.md](https://github.com/fatih/vim-go) pour plus d'information.