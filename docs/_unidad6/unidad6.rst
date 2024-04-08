Unidad 6. Agentes autónomos
============================

Introducción
---------------

El término agente autónomo generalmente se refiere a una entidad que toma 
sus propias decisiones sobre cómo actuar en su entorno sin ninguna influencia 
de un líder o plan global. Para nosotros, ``actuar`` significará movimiento.

Lo que harás esta unidad se basa en el siguiente trabajo:

Steering Behaviors For Autonomous Characters by Craig Reynolds. GDC 1999 paper: 
Steering Behaviors For Autonomous Characters. 
Reynolds, C. W. (1999) Steering Behaviors For Autonomous Characters, in the 
proceedings of Game Developers Conference 1999 held in San Jose, California. 
Miller Freeman Game Group, San Francisco, California. Pages 763-782. El paper 
lo puedes descargar 
`aquí <https://github.com/juanferfranco/BookCodeSimCourse/files/11272755/gdc99steer.pdf>`__.

Reynolds describe el movimiento de los vehículos idealizados (agentes autónomos 
idealizados) como una serie de tres capas. En la simulación solo implementarás dos 
de las capas (selección y dirección).

1. Selección: un vehículo tiene un objetivo (u objetivos) y puede seleccionar 
   una acción (o una combinación de acciones) basada en ese objetivo. 
   El vehículo echa un vistazo a su entorno y calcula una acción basada en un 
   deseo: ``Veo a un zombi marchando hacia mí. Como no quiero que me coman el 
   cerebro, voy a huir del zombi``. El objetivo es mantener el cerebro y la 
   acción es huir.

   Ejemplos de objetivos: buscar un objetivo, evitar un obstáculo, seguir un camino.

2. Dirección (steering): una vez que se ha seleccionado una acción, el vehículo 
   tiene que calcular su siguiente movimiento. Para nosotros, el próximo paso será una 
   fuerza; más específicamente, una fuerza de dirección.

   Ejemplos: buscar, huir, seguir un camino, seguir un campo de flujo, reunirse con 
   los vecinos.

.. note:: RETO DE DISEÑO 

  ¿Cómo harías para simular que un agente ama, o tiene miedo?  

  ¿Qué motiva al vehículo?

Requisitos de la aplicación interactiva
--------------------------------------------

#. Crea una simulación de flocking donde todos los parámetros 
   (peso de separación, peso de cohesión, peso de alineación, fuerza máxima, 
   velocidad máxima) cambian con el tiempo. Los parámetros podrían ser controlados por  
   ruido Perlin o por la interacción del usuario mediante sliders o cualquier 
   otra idea que quieras explorar.
#. Diseña una criatura con tantos comportamientos de dirección (steering) como 
   sea razonable. Piensa en maneras de variar los pesos de estos comportamientos 
   para que se puedan combinar en tiempo real. ¿Cómo se establecen los 
   pesos iniciales? ¿Qué reglas determinan cómo cambian los pesos con el tiempo?
#. Debes adicionar interactividad a tu aplicación. Puede ser mediante teclado, 
   mouse, música, el micrófono, video, sensor o cualquier otro dispositivo 
   de entrada.
#. Debes desarrollar tu aplicación bajo control de versión. Usa el directorio 
   correspondiente de cada unidad.


Trayecto de actividades
------------------------

* Realiza la lectura de la unidad 5 del texto guía: agentes autónomos.
* Analiza detenidamente cada uno de los ejemplos. Ejecútalos y realiza 
  cambios que te permitan experimentar con el código.
* Realiza el reto.


Recursos 
----------------------

* `Capítulo 5 <https://natureofcode.com/autonomous-agents/>`__ del texto guía.
* `Videos 38 al 44 <https://youtube.com/playlist?list=PLRqwX-V7Uu6ZV4yEcW3uDwOgGXKUUsPOM>`__ 
  del curso the nature of code 2. 

..
  Evaluación
  -----------

  Durante varias semanas has construido un prototipo para incluir 
  en un tu portafolio. En la unidad anterior añadiste efectos. En esta 
  unidad utilizarás otras facilidades del motor para enriquecer tu 
  simulación interactiva.

  ¿Te animas a escribir esta vez el README.md en inglés? La idea es que 
  tu portafolio pueda ser disfrutado por una audiencia global.

  Características de la simulación
  **********************************

  Para cada característica que te propongo puedes leer la sección 
  del texto guía correspondiente para buscar inspiración:

  * Añade a tus criaturas OJOS. Si, ojos. El motor te ofrece Raycasts para esto.
  * Utiliza las colisiones del sistema de partículas para armar "el desorden" 
    en tu simulación.
  * Añade físicas de viento a algunas de las partículas de la simulación o añade 
    un nuevo sistema de partículas que incorpore esto.
  * Modifica una criatura o añade una planta que tenga FixedJoints.
  * Modifica o crea una nueva criatura que tenga SpringJoints.
  * Y que tal una planta o criatura que incluya HingeJoint Ropes.
  * Por último explora la facilidad que te brinda el motor para 
    definir Physics Materials. Incluye algunos en la simulación.

  .. note:: Para las personas más curiosas

      En los recursos te voy a dejar otras facilidades del motor 
      que podrían enriquecer aún más tu simulación.


  Recursos 
  ----------------------

  * Esta unidad no tiene videos del relacionados con el libro original. La 
    idea es usar las facilidades que brinda el motor, los componentes 
    de física que Unity provee. Tendrás algunos ejemplos muy interesantes 
    `aquí <https://natureofcodeunity.com/chapterfive.html>`__.
  * `Unity Scripting Tutorial: Physics.SphereCast <https://youtu.be/Nplcqwq_oJU?si=7mlE8iDm9QsvyRRv>`__.
  * `Getting Started With Cloth Physics <https://youtu.be/Nc_ZMgEFj-A?si=oJV5585D2oHA49vJ>`__.
  * `Unity Physics Joint Tutorial: Fixed Joint <https://youtu.be/GB8BdFjX8vM?si=Xazv_4qzT90zJsTp>`__.
  * `Unity Physics Joint Tutorial: Spring Joint <https://youtu.be/3EkJfRbYFos?si=lkIcl9KAW-4Ow3cK>`__.
  * `Unity Physics Joint Tutorial: Hinge Joint <https://youtu.be/Fltt-j655MI?si=IKbdU-DwQVSxqTzA>`__.