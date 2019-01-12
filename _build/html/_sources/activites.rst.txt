=========
Activités
=========

https://openclassrooms.com/fr/courses/2023346-creez-des-applications-pour-android/2023968-votre-premiere-application

* briques de base qui composent une application
* remplissent la fenêtre en entier
* infos que l'état d'une activité : ``context``
* quand une activité est lancée, elle va en haut d'une **pile d'activités** (LIFO)
* l'activité que voit l'utilisateur est celle qui se trouve au-dessus de la pile

.. list-table::
   :widths: 25 25 50
   :header-rows: 1

   * - État
     - Visibilité
     - Description
     
   * - Active («**active**» ou «**running**»)
     - L'activité est visible en totalité.
     - Elle est sur le dessus de la pile, c'est ce que l'utilisateur consulte en  ce moment même et il peut l'utiliser dans son intégralité.
     
       C'est cette application qui a le focus, c'est-à-dire que l'utilisateur agit directement sur l'application.
       
   * - Suspendue («**paused**»)
     - L'activité est partiellement visible à l'écran.
     - C'est le cas quand vous recevez un SMS et qu'une fenêtre semi-transparente se pose devant votre activité pour afficher le contenu du message et vous permettre d'y répondre par exemple. Ce n'est pas sur cette activité qu'agit l'utilisateur.
       
       L'application n'a plus le focus, c'est l'application au-dessus qui l'a. Pour que notre application récupère le focus, l'utilisateur devra se débarrasser de l'application partiellement au-dessus pour que l'utilisateur puisse à nouveau interagir avec notre activité. Si le système a besoin de mémoire, il peut très bien tuer l'application.
     
   * - Arrêtée («**stopped**»)
     - L'activité est tout simplement invisible pour l'utilisateur, car une autre activité prend toute la place sur l'écran.
     - L'application n'a évidemment plus le focus, et puisque l'utilisateur ne peut pas la voir, il ne peut pas agir dessus.
       
       Le système retient son état pour pouvoir reprendre, mais il peut arriver que le système tue votre application pour libérer de la mémoire système.

