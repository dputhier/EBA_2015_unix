Découverte rapide du Bureau MATE
===============================

Ce bureau est très similaire aux bureaux que vous avez pu rencontrer sous l'environnement Windows (XP, Seven,...) ou le système OSX sous Mac.

Vous disposez d'un bureau contenant une **barre des tâches** dans la partie supérieure et un **menu Application** dans la partie  supérieure gauche. Dans ce menu vous trouverez un certains nombre de sous menus vous permettant d'accéder à des applications (e.g Firefox, Chrome, Libreoffice,...).
     
.. hint::  Pour la suite nous aurons besoin de lancer un terminal (!). Pour lancer ce terminal, sélectionnez dans le menu : **Application > System tools > MATE terminal**.


L'arborescence sous Linux 
==========================

Fichiers et dossiers 
---------------------


 Au même titre que sous windows, les données sous unix sont contenues dans des **fichiers** qui eux même peuvent être contenus dans des **dossiers**. 

 Afin de faciliter l'apprentissage des chemins sous Unix, nous allons utiliser le navigateur de fichier dans un premier temps.


.. important::

   Lancez le navigateur de fichier en utilisant le menu "Places > Home folder".


Dossier racine 
----------------

 Sous windows, **la racine du disque** système est désignée par **C:\\**. Sous UNIX la racine est désignée par **"/"**. 



 Dans cette racine on trouve un certain nombre de répertoires: La liste de ces répertoire peut varier d'un système à l'autre (Ubuntu, Centos, OSX...).

 * /root Répertoire personnel (:fonticon:`fa fa-home  icon-2x`) de l'administrateur (appelé "root").
 * /home Répertoires des utilisateurs (:fonticon:`fa fa-home  icon-2x`). 
 * /bin Programmes système (binaries). 
 * /tmp Données temporaires. 
 * /boot Noyau, Bootmanager.
 * /dev Fichiers des périphériques (devices). 
 * /etc Fichiers de configuration. 
 * /lib Librairies partagées.
 * /mnt Répertoire de montage pour cdrom, floppy... (mount).
 * /opt Installations supplémentaires. 
 * /proc Informations sur le système et les processus en cours (process).
 * /sbin Programmes système pour le root. 
 * /usr Programmes des utilisateurs. 
 * /var Fichiers divers et certains fichiers de logs (variable)

.. important::  Sous Linux/UNIX on parle de répertoire **home** pour désigner le répertoire contenant les données d'un utilisateur connecté. La représentation symbolique de ce répertoire utilisateur est **~**.




Se déplacer dans l'arborescence
===============================

La commande cd
--------------

 La commande **cd (change working directory)** commande permet de changer de répertoire, de se **déplacer dans l'arborescence**.

.. hint:: On doit fournir un **chemin** ('path') à cette commande pour que celle-ci sache vers quel dossier on souhaite se déplacer (*cf* exemple ci-dessous). Ce chemin constitue l'unique **argument** de cette commande. Exemples:

   
.. code-block:: bash

   $ cd / # On se déplace à la racine
   $ cd /usr/ # On se déplace dans le répertoire usr présent à la racine
   $ cd /usr/local # On se déplace dans le répertoire usr qui contient un répertoire nommé local
   $ cd /usr/local/bin # On se déplace dans le répertoire usr qui contient un répertoire nommé local qui lui même contient un répertoire nommé bin.



La commande pwd
----------------

 La commande **pwd (print working directory)** permet de savoir dans quel repertoire nous sommes localisés à l'instant même où on fait appelle à cette commande (on parle de **répertoire courant**).


Tapez la commande suivante dans le terminal, elle permet de se déplacer à la racine du disque.


.. command-output:: pwd # On demande au système de nous indiquer le répertoire courant
   $ cd / # On se déplace à la racine
   $ pwd # Le répertoire courant a changé.
   :returncode: 1

.. program-output:: cd /
   pwd

.. note:: Tous les caractères se trouvant à droite du **caractère #** ne sont pas interprétés par le système. Il s'agit de **commentaires**.


Se déplacer dans son 'home' 
---------------------------

 Pour se déplacer dans son répertoire utilisateur ('home') il suffit de demander à aller dans le répertoire **~**.

.. code-block:: bash

   $ cd ~
   
.. note:: On peut aussi écrire directement 'cd' (sans l'argument '~'). En effet, quand la commande 'cd' est appelée sans argument elle change le répertoire courant à ~, par défaut. 


Créer des répertoires 
======================

La commande mkdir 
-----------------


 La commande **mkdir** peut être utilisée pour créer des répertoires. Cette commande prend comme argument le nom des répertoires que l'on souhaite créer. Par défaut, la commande refuse de créer un répertoire déja existant et renvoie un message d'erreur. Pour éviter ce message d'erreur, il faudra ajouter l'argument **-p**.
   
.. code-block:: bash

   $ cd ~
   $ mkdir chipseq_tuto
   $ mkdir chipseq_tuto # refuse de créer un dossier déjà existant
   $ mkdir -p chipseq_tuto # pas de message d'erreur (argument -p 
   $ cd chipseq_tuto
   $ mkdir raw_data
   $ mkdir trimmed
   $ mkdir fastqc
   $ mkdir bam            
   $ cd raw_data
   $ pwd
   $ cd 

.. todo:: finir "l'admonition" hint ci-dessous.

.. hint::  Si vous souhaiter visualiser ces répertoires avec un navigateur de fichier, Allez dans Menu > blabla >

 

Lister le contenu d'un répertoire 
===================================

Lister le contenu d'un répertoire 
----------------------------------

 Pour connaître la **liste** des éléments présents dans un répertoire, on utilisera la commande **ls**.

 La commande ls accepte de nombreux arguments. Sa forme générale est la suivante:

.. code-block:: C


 ls [-ABCFGHLOPRSTUW@abcdefghiklmnopqrstuwx1] [file/directory ...]

.. note:: Dans les manuels d'aide UNIX, les arguments entre crochets sont considérés comme facultatifs. Dans le cas de ls, l'ensemble des arguments sont facultatifs, indiquant que l'on peut simplement écrire simplement 'ls'. Dans ce cas, on obtient la liste des fichiers présents dans le répertoire courant.

 La liste ci-dessous donne un certain nombre d'arguments classiques de ls:

.. code-block:: C 

   -a liste tous ('all') les fichiers et dossiers (y compris les ceux qui sont cachés). 
   -l En plus de la liste des fichiers, donne une information exhaustive sur ceux-ci ('long'). 
   -t Trier les fichiers par date de modification ('time').
   -r Inverse l'odre de tri ('reverse'). 
   -R Lister de manière récursive (dossiers et sous-dossiers et sous-sous-dossiers...). 


.. code-block:: bash

   $ cd ~
   $ ls # tous les arguments sont facultatifs.
   $ ls -a # le dossier ~ contient de nombreux fichiers cachés.
   $ ls -l -a 
   $ ls -la # équivalent à ls -l -a
   $ ls -rtl # classique.
   $ ls chipseq_tuto # contient le dossier 'raw_data'.
   $ ls chipseq_tuto/raw_data # ne contient rien pour l'instant.
   $ ls / # les répertoires présents à la racine.

.. important:: On écrit rarement la totalité des chemins. Sous UNIX/Linux on utilise la **complétion**. On tapera le début du chemin puis on appuiera une à deux fois sur la touche tabulation afin que le système propose des solutions. Notez qu'il en est de même pour les noms de commandes.

.. code-block:: bash

   $ cd ~
   $ ls c # On appuie alors sur la touche tab (une à deux fois).
   $ ls chipseq_tuto/r # On ajoute r et on appuie sur la touche tab (une à deux fois).

Les opérateurs wilcard 
-----------------------

 Ils permettent de désigner un ensemble de fichiers ou dossiers. L'opérateur le plus fréquent est l'étoile (*).

 Deux exemples ci-dessous pour illustrer.

  
.. code-block:: bash 

   $ cd ~ $ ls chipseq_tuto/*a* # l'ensemble des fichiers et dossiers présents dans le dossier chipseq_tuto et dont le nom contient un 'a'. 
   $ ls chipseq_tuto/*m l'ensemble des fichiers et dossiers présents dans le dossier chipseq_tuto et finissant par un 'm'.
  
Chemins absolus et chemin relatifs 
===================================

 Il existe deux manière de désigner un chemin dans l'arborescence:

 * L'ecriture absolue: on désigne un fichier ou un répertoire en faisant référence à la racine de l'arborescence.     

 * L'ecriture relative: on désigne un fichier ou un répertoire en faisant **référence au répertoire courant**. 

Chemins absolus 
---------------

 Imaginons que l'on souhaite lister le contenu du répertoire chipseq_tuto. En écriture absolue, on écrira, dans notre cas :

.. code-block:: bash 

   $ cd ~
   $ ls /root/chipseq_tuto  


Chemins relatif 
---------------

 Si l'on souhaite faire référence au dossier chipseq_tuto en écriture relative, la commande dépendra alors du répertoire dans lequel on se trouve.


.. important:: En écriture relative, on pourra utiliser les éléments de langage suivant:

.. code-block:: C 

   ./ le répertoire courant
   .. Le répertoire supérieur de l'arborescence.
   ../.. Le répertoire se trouvant deux niveaux au dessus dans l'arborescence.
   ../../.. Le répertoire se trouvant trois niveaux au dessus dans l'arborescence.  
   ...  


.. code-block:: bash 

   $ cd ~
   $ ls chipseq_tuto # se dossier est visible depuis notre dossier courant. Son nom est suffisant
   $ ls ./chipseq_tuto # équivalent à 'ls chipseq_tuto'. On insiste en spécifiant que 'chipseq_tuto' se trouve dans le répertoire courant.
   $ cd / # on se déplace. Le dossier de réference change.
   $ ls chipseq_tuto # erreur. Ce dossier ne se trouve pas dans le dossier racine.
   $ ls root/chipseq_tuto # pas besoin d'utiliser le '/'. 
   $ cd ~/chipseq_tuto/raw_data # on se déplace à nouveau
   $ ls .. # que contient le répertoire supérieur
   $ ls ../.. # que contient le répertoire se trouvant deux niveaux au dessus ?     


Télécharger du contenu
=======================


La commande wget 
-----------------

 Nous souhaitons télécharger un fichier de reads présent à l'adresse: 

 ::
   
   http://denis.puthier.perso.luminy.univ-amu.fr/COURSES/CHIP-SEQ/PRACTICAL/data/siNT_ER_E2_r3_SRX176860_chr21_0.6_Noise.fastq.gz

 Nous allons pour se faire utiliser la commande **wget**. Cette commande téléchargera le fichier **siNT_ER_E2_r3_SRX176860_chr21_0.6_Noise.fastq.gz** dans **le dossier courant**. Il convient donc de se placer tout d'abord dans le dossier de destination.

.. code-block:: bash 

   $ cd ~/chipseq_tuto/raw_data
   $ wget http://denis.puthier.perso.luminy.univ-amu.fr/COURSES/CHIP-SEQ/PRACTICAL/data/siNT_ER_E2_r3_SRX176860_chr21_0.6_Noise.fastq.gz

Décompression 
==============

La commande gunzip 
------------------


 La commande **gunzip** permet de **décompresser** un fichier au **format *.gz**. Sa syntaxe générale est la suivante:

 ::

   gunzip [-cfhkLNqrtVv] [-S suffix] file [file [...]]

 Ici si nous souhaitons décompresser notre fichier nous pouvons donc écrire:

.. code-block:: bash

   $ cd ~/chipseq_tuto/raw_data
   $ gunzip *.gz # ou gunzip siNT_ER_E2_r3_SRX176860_chr21_0.6_Noise.fastq.gz


Analyser la qualité avec fastqc 
===============================

La commande fastqc
-------------------


 On peut utiliser la commande fastqc pour analyser la qualité des reads. Il faudra lui fournir un certain nombre d'arguments. La syntaxe générale est la suivante:

 :: 

   fastqc [-o output dir] [--(no)extract] [-f fastq|bam|sam] fq1 fq2 fq3 ...

 Ici nous souhaitons stocker le résultat de fastqc (un dossier contenant une page web) dans le dossier chipseq_tuto/fastqc/siNT_ER_E2_r3_SRX176860_chr21_0.6_Noise. Nous devons tout d'abord créer ce fichier puis lancer fastqc:


.. code-block:: bash 

   $ cd chipseq_tuto/fastqc
   $ mkdir chipseq_tuto/fastqc/siNT_ER_E2_r3_SRX176860_chr21_0.6_Noise
   $ fastqc -f fastq -o siNT_ER_E2_r3_SRX176860_chr21_0.6_Noise ../raw_data/siNT_ER_E2_r3_SRX176860_chr21_0.6_Noise.fastq 



 Pour visualiser le résultat on peut directement demander à firefox de l'ouvrir:

.. code-block:: bash

   $ firefox siNT_ER_E2_r3_SRX176860_chr21_0.6_Noise/.../...

.. todo:: finir ce qu'il y a au-dessus.


Rogner les reads 
=================

La commande sickle
---------------------

 Cette commande va nous permettre de trimmer les reads. Ici nous travaillons avec des données 'single-end' nous travaillerons donc avec 'sickle se' (voir 'sickle pe' pour le paired-end). Les arguments de sickle sont les suivants:

.. code-block:: bash

    $ sickle 
    
    Usage: sickle <command> [options]
    
    Command:
    pe  paired-end sequence trimming
    se  single-end sequence trimming
    
    --help, display this help and exit
    --version, output version information and exit



.. code-block:: bash

    $ sickle se 
    Usage: sickle se  -f <fastq sequence file>  -t <quality type> -o <trimmed fastq file> 
    Options: 
    -f, --fastq-file, Input fastq file (required)
    -t, --qual-type, Type of quality values (solexa (CASAVA < 1.3), illumina
    (CASAVA 1.3 to 1.7), sanger (which is CASAVA >= 1.8)) (required) 
    -o, --output-file, Output trimmed fastq file (required) 
    -q, --qual-threshold, Threshold for trimming based on average quality in a window. Default 20. 
    -l, --length-threshold, Threshold to keep a read based on length after trimming. Default 20. 
    -x, --no-fiveprime, Don't do five prime trimming. 
    -n, --discard-n, Discard sequences with any Ns in them. 
    --quiet, Don't print out any trimming information 
    --help, display this help and exit --version, output version information and exit