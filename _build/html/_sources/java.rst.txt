================
Rappels sur Java
================

Types primitifs
===============

Il existe 8 types primitifs :

=============== =========================== =========== =========== ================================================
Type            Description                 Default     Size        Example Literals
=============== =========================== =========== =========== ================================================
boolean         true or false               false       1 bit       true, false
byte            twos complement integer     0           8 bits      (none)
char            Unicode character           \u0000      16 bits     'a', '\u0041', '\101', '\\', '\'', '\n', 'ß'
short           twos complement integer     0           16 bits     (none)
int             twos complement integer     0           32 bits     -2, -1, 0, 1, 2
long            twos complement integer     0           64 bits     -2L, -1L, 0L, 1L, 2L
float           IEEE 754 floating point     0.0         32 bits     1.23e100f, -1.23e-100f, .3f, 3.14F
double          IEEE 754 floating point     0.0         64 bits     1.23456e300d, -1.23456e-300d, 1e1d
=============== =========================== =========== =========== ================================================

Classes
=======

Déclarer une classe
-------------------

.. code-block:: java

    class Voiture {
        //On déclare les atributs de la classe ici :
        int roue = 4;
        float vitesse;
        Couleur carrosserie;
      
        //Je déclare une méthode qui s'appelle "arreter"
        void arreter() {
            int vitesse = 0;            // variable locale
            //Pour s'arrêter, je passe la vitesse à 0 
            //On donne à l'attribut ``this.vitesse`` la valeur de la variable 
            //locale ``vitesse``
            this.vitesse = vitesse;
        }
    }
    
Attributs de classe
-------------------

Mot clé pour faire référence aux attributs de classe : ``this``

Héritage
--------

``abstract`` : classe qui ne peut être instanciée
"""""""""""""""""""""""""""""""""""""""""""""""""

.. code-block:: java

    // Dans le fichier vehicule.java
    // Classe qui ne peut être instanciée
    abstract class Vehicule {
        int nombre_de_roues;
        float vitesse;
    }
    
``extends`` : créer une classe fille
""""""""""""""""""""""""""""""""""""

.. code-block:: java

    // Dans le fichier voiture.java
    // Une Voiture est un Vehicule
    class Voiture extends Vehicule { }
    
Autres mots clés
""""""""""""""""

.. code-block:: java

    public final class R {
        ...
        public static final class layout {
            public static final int activity_main=0x7f030000;
        }
    }

* ``final`` : classe à partir de laquelle on ne peut pas créer de classe dérivée
* ``static`` : dans le cas d'une classe interne, signifie que la classe n'est pas liée à une instanciation de la classe qui l'encapsule. Pour accéder à ``layout``, on ne doit pas nécessairement créer un objet de type ``R``. On peut y accéder par ``R.layout``

    
Niveaux d'accessibilité des attributs et méthodes
-------------------------------------------------

* ``public``, pour qu'un attribut ou une méthode soit accessible à tous.
* ``protected``, pour que les éléments ne soient accessibles qu'aux classes filles.
* ``private``, pour que les éléments ne soient accessibles à personne si ce n'est la classe elle-même.

Les interfaces
--------------

.. code-block:: java

    //Interface des objets qui peuvent voler
    interface PeutVoler {
      void décoller();
    }

    class Avion extends Vehicule implements PeutVoler {
      //Implémenter toutes les méthodes de PeutVoler et les méthodes abstraites de Vehicule
    }
    
Compilation
===========

La compilation transforme le code source en **bytecode**. Dans le cas d'Android, ce bytecode sera interprété par la **machine virtuelle Dalvik** lors de l'éxécution du programme.

Plateformes Java
================

Il existe deux plateformes en Java :

* Le **JRE (Java Runtime Environment)**, qui contient la JVM (Java Virtual Machine, rappelez-vous, j'ai expliqué le concept de machine virtuelle dans le premier chapitre), les bibliothèques de base du langage ainsi que tous les composants nécessaires au lancement d'applications ou d'applets Java. En gros, c'est l'ensemble d'outils qui vous permettra d’**exécuter des applications Java**.

* Le **JDK (Java Development Kit)**, qui contient le JRE (afin d’exécuter les applications Java), mais aussi un ensemble d'outils pour **compiler et déboguer** votre code.

SDK
===

Le **SDK Android** est donc un ensemble d'outils que met à disposition Google afin de vous permettre de développer des applications pour Android.