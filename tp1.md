# tp1-groupe-1_DIOP
# Exercice 2:  Prise en main de l’interpréteur de commandes
## Manuel 
1. A l’aide du manuel, identifiez le rôle de la commande which
Which renvoie le chemin des fichiers (ou liens) qui seraient exécutés dans l’environnement courant.

 2. Quand on consulte une page du manuel, comment peut-on rechercher un terme (par exemple, chercher le terme option dans la page de manuel de which ? 
Pour rechercher un terme dans la page manuel (par exemple option) : on écrit /option.

3. Comment quitte-t-on le manuel ? 
Pour quitter le manuel on tape la lettre Q.

4. Chaque section du manuel a une première page, qui présente le contenu de la section. Afficher la première page de la section 6 ; de quoi parle cette section ?
La section 6 du man décrit les jeux man 6 intro.

## Navigation dans l’arborescence des fichiers 

1. allez dans le dossier /var/log 
cd /var/log
2. remontez dans le dossier parent (/var) en utilisant un chemin relatif 
cd ..
3. retournez dans le dossier personnel 
cd ~
4. revenez au dossier précédent (/var) sans utiliser de chemin
cd -
 5. essayez d’accéder au dossier /root ; que se passe-t-il ? 
On reçoit un message : Permission denied
Qui signifie qu’on a pas la permission pour accéder à ce dossier.

6. essayez la commande sudo cd /root ; que se passe-t-il ? Expliquez 
Avec sudo il nous est demandé de taper le mot de passe root contrairement à la question précédente.
Sudo donne certains droits nécessaires (administrateur) pour accéder à un dossier root.

7. à partir de votre dossier personnel, créez l’arborescence suivante :
mkdir Dossier1 : pour créer un dossier
cd Dossier1: naviguer dans le dossier
touch Fichier1 : pour créer le fichier
nano Fichier1: pour l’éditer

8. revenez dans votre dossier personnel ; à l’aide de la commande rm, essayez de supprimer Fichier1, puis Dossier1 ; que se passe-t-il ? 
Impossible de supprimer le Fichier1 directement dans le répertoire personnel car il est dans un autre dossier.
On peut pas supprimer un dossier avec la commande rm. 
9. quelle commande permet de supprimer un dossier ? 
Commande pour supprimer un dossier : rmdir.
10. que se passe-t-il quand on applique cette commande à Dossier2 ? 
Quand on essaie de supprimer Dossier2 on reçoit un message comme quoi le dossier n’est pas vide.
11. comment supprimer en une seule commande Dossier2 et son contenu ?
Pour supprimer un dossier et son contenu: rm -r

## Commandes importantes 
1. Quelle commande permet d’afficher l’heure ? 
C’est la commande date qui permet d’afficher l’heure. Elle affiche toutes les informations du jour.
A quoi sert la commande time ?
La commande time sert à determiner le temps d’éxecution de certaines commandes, on l’utilise dans des scripts.
2. Dans votre dossier personnel, tapez successivement les commandes ls puis la ; que peut-on en déduire sur les fichiers commençant par un point ? 
La commande ls affiche les fichiers présent dans le répertoire.
La commande la (ls -a) affiche tous les fichiers y compris ceux commençant par un point.

3. Où se situe le programme ls ? 
Le programme ls se situe dans /usr/bin/ls.
On le retrouve avec la commande ‘which ls’

4. Essayez la commande ll. Existe-t-il une entrée de manuel pour cette commande ? 
Il n’y a pas d’entrée pour cette commande car c’est un alias.
Utilisez les commandes alias ou alias pour en savoir plus sur la nature de cette commande. 
Cette commande liste les fichiers d’un répertoire avec leurs droits (c’est l’alias ls -alF)

5. Quelle commande permet d’afficher les fichiers contenus dans le dossier /bin ?
Pour afficher le contenu de /bin : ls /bin
6. Que fait la commande ls .. ? 
ls .. affiche notre dossier personnel

7. Quelle commande donne le chemin complet du dossier courant ?
La commande pwd.
8. Que fait la commande echo 'yo' > plop exécutée 2 fois ? 
Cette commande ajoute le mot ‘yo’ dans le fichier plop. 
Exécutée 2 fois permet de remplacer la ligne déjà existante.
9. Que fait la commande echo 'yo' >> plop exécutée 2 fois ? 
Cette commande ajoute le mot ‘yo’ dans le fichier plop. 
Lorsqu’on l'exécute une deuxième fois, elle ajoute un deuxième ‘yo’ dans le fichier.

10. A quoi sert la commande file ? Essayez la sur des fichiers de types différents. 
La commande (file) permet de connaître le type de l'objet passé en argument.

11. Créez un fichier toto qui contient la chaîne Hello Toto ! ; créer ensuite un lien titi vers ce fichier avec la commande ln toto titi. Modifiez à présent le contenu de toto et affichez le contenu de titi : qu’observe-t-on ? Supprimez le fichier toto ; quelle conséquence cela a-t-il sur titi ? 
Lorsqu'on crée un lien entre deux fichiers, quand on change le contenu de l'un l'autre change mais lorsque l'on supprime un fichier le lien est rompu et l'autre fichier devient simplement une copie de l'autre.

12. Créez à présent un lien symbolique tutu sur titi avec la commande ln -s titi tutu. Modifiez le contenu de titi ; quelle conséquence pour tutu ? Et inversement ? Supprimez le fichier titi ; quelle conséquence cela a-t-il sur tutu ? 
La commande (ln -s titi tutu) crée un lien symbolique, même effet que la question 11 mais dans ce cas lorsqu'on supprime titi , le fichier n'est plus accessible (broken symbolic link).

13. Affichez à l’écran le fichier /var/log/syslog. Quels raccourcis clavier permettent d’interrompre et reprendre le défilement à l’écran ? 
Les raccourcis clavier qui permettent d’interrompre (ctrl +s) et reprendre le défilement à l’écran (ctrl + Q).

14. Affichez les 5 premières lignes du fichier /var/log/syslog, puis les 15 dernières, puis seulement les lignes 10 à 20.
Les 5 premières lignes du fichier/var/log/syslog : head /var/log/syslog -n 5.
Les 15 dernières lignes: tail /var/log/syslog -n 15
Les lignes de 10 à 20: sed -n “10,20 p” /var/log/syslog 
 
 15. Que fait la commande dmesg | less ?
Cette commande affiche le kernel ring buffer avec moins d'informations.

16. Affichez à l’écran le fichier /etc/passwd ; que contient-il ? Quelle commande permet d’afficher la page de manuel de ce fichier ? 
/etc/passwd est un fichier texte qui contient la liste des comptes sur le système, ainsi que des informations utiles sur ces comptes, comme l'identification de l'utilisateur, du groupe, le répertoire personnel, le shell, ... Il doit y avoir, dans le fichier des mots de passe, une ligne par utilisateur, avec le format suivant : * account:passwd:UID:GID:GECOS:directory:shell

17. Affichez seulement la première colonne triée par ordre alphabétique inverse 
cat /etc/passwd|cut d: -f1 | sort -r

18. Quelle commande nous donne le nombre d’utilisateurs ayant un compte sur cette machine (pas seulement les utilisateurs connectés) ? 
cat /etc/passwd | awk -F: '{print $ 1}'
19. Combien de pages de manuel comportent le mot-clé conversion dans leur description ? 
man -k conservation | wc -l

20. A l’aide de la commande find, recherchez tous les fichiers se nommant passwd présents sur la machine. 
sudo find -name passwd |wc -l

21. Modifiez la commande précédente pour que la liste des fichiers trouvés soit enregistrée dans le fichier ~/list_passwd_files.txt et que les erreurs soient redirigées vers le fichier spécial /dev/null 
find -name passwd |wc -l 1> ~/list_passwd_files.txt 2> /dev/null

22. Dans votre dossier personnel, utilisez la commande grep pour chercher où est défini l’alias ll vu précédemment 
Il se situe dans le fichier .bashrc

23. Utilisez la commande locate pour trouver le fichier history.log. 
La commande locate history.log trouve les fichiers intitulés par le même nom. On le trouve dans le fichier var/log/apt

24. Créer un fichier dans votre dossier personnel puis utilisez locate pour le trouver. Apparaît-il ? Pourquoi ?
Non il n'apparait pas car locate se base sur une base de données qu'il faut synchroniser pour pouvoir voir le fichier qui vient d'être créé.

# Exercice 4. Personnalisation du shell
3.  Le fichier .bashrc est lu au démarrage du shell ; pour le recharger, il faudrait donc se déconnecter puis se reconnecter ; mais il existe un autre moyen : la commande source .bashrc. Testez-la, l’invite de commande devrait immédiatement passer en couleurs. 
Le fichier .baschrc doit être reload pour prendre en compte les changements c'est pour ça que les changements n'étaient pas pris en compte directement.

4.  Les couleurs par défauts (surtout celle du dossier courant) ne sont pas très visibles. Dans .bashrc, cherchez les lignes commençant par PS1= ; elles indiquent la mise en forme de l’invite de commande (selon que l’on est en couleurs ou non). 
On peut utiliser : [\e[88m] $HEURE \e[39m]- \e[92m] \u@\h\ \033[39m] : [\033[96m] $PWD
 

