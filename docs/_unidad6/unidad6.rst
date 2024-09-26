Unidad 6. Agentes autónomos
============================

Introducción
---------------

El término agente autónomo generalmente se refiere a una entidad que toma 
sus propias decisiones sobre cómo actuar en su entorno, sin ninguna influencia 
de un líder o plan global. Para nosotros, ``actuar`` significará movimiento.

Lo que harás en esta unidad se basa en el siguiente trabajo:

Steering Behaviors For Autonomous Characters by Craig Reynolds. GDC 1999 paper: 
Steering Behaviors For Autonomous Characters. 
Reynolds, C. W. (1999) Steering Behaviors For Autonomous Characters, in the 
proceedings of Game Developers Conference 1999 held in San Jose, California. 
Miller Freeman Game Group, San Francisco, California. Pages 763-782. El paper 
lo puedes descargar 
`aquí <https://github.com/juanferfranco/SimulacionInteractivos/blob/main/docs/_static/gdc99steer.pdf>`__.

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

.. note:: Alimento para el pensamiento

  ¿Cómo harías para simular que un agente ama, o tiene miedo?  

  ¿Qué motiva al agente?

Investigación
------------------------

Trayecto de actividades 
*****************************

* Lee el enunciado del reto de esta unidad. Observa cuáles son los conceptos 
  que debes investigar. De esta manera realizarás el siguiente paso con mayor 
  claridad.
* Realiza la lectura de la unidad 5 del texto guía: agentes autónomos.
* Analiza detenidamente los ejemplos. Ejecútalos y realiza 
  cambios que te permitan experimentar con el código.

Bitácora
**********

Reporta libremente en la bitácora los siguientes elementos:

* Conceptos fundamentales para el reto que identificaste en la lectura.
* Reflexión sobre los cambios que realizaste en los ejemplos y cómo 
  estos afectaron el comportamiento de los agentes autónomos.
* Código y enlaces a los ejemplos modificados.

Recursos 
*************

* `Capítulo 5 <https://natureofcode.com/autonomous-agents/>`__ del texto guía.
* `Videos <https://thecodingtrain.com/tracks/the-nature-of-code-2/noc/5-autonomous-agents/1-steering-agents>`__.


Reto
-------

Simulación interactiva
*****************************************

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

Bitácora 
*********

.. warning:: NO USES ChatGPT para hacer tu bitácora.

    Reflexiona tu mismo analizando los resultados obtenidos. NO uses 
    ChatGPT para hacer tu bitácora. Por favor, no copies y pegues. 
    Escribe tus propias ideas. 

* El enlace a la simulación interactiva.
* Código fuente con el resultado final.
* Explicación del concepto de la simulación.
* Explica cómo implementaste el flocking y cómo cambian los parámetros con el tiempo.
* Explica cómo se combinan los comportamientos de dirección (steering) en tu criatura.
* Un ENLACE a un video corto que muestre el resultado final de la simulación 
  y cómo interactúa el usuario con ella.
