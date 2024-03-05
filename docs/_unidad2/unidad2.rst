Unidad 2. Vectores
=======================================

Requisitos de la aplicación interactiva
--------------------------------------------

Vas a imaginarte una población de CRIATURAS COMPUTACIONALES en un ecosistema digital, 
interactuando unos con otros de acuerdo con varias reglas.

* Vas a diseñar al menos 3 criaturas que tengan:

  * Apariencia diferente.
  * Desarrolla un conjunto de reglas para simular el comportamiento de cada criatura. 
    Por ejemplo: una mosca nerviosa, un pez nadando, un conejo saltando, una 
    serpiente deslizándose, etc.
  * Controla el movimiento de la criatura ÚNICAMENTE manipulando la ACELERACIÓN.
  * Dale personalidad a la criatura a través de su comportamiento.
  * Asegúrate que al menos una criatura, usando vectores, implemente una caminata aleatoria 
    y un vuelo de `Lévy <https://natureofcode.com/random/>`__ (mediante una distribución 
    personalizada de números aleatorios). Por ejemplo, el siguiente código muestra un random walker 
    con una probabilidad del 1% de realizar un paso enorme. Mira el capítulo anterior para 
    repasar.

.. code-block::javascript

    let r = random(1);
    if (r < 0.01) {
      xstep = random(-100, 100);
      ystep = random(-100, 100);
    A 1% chance of taking a large step

    } else {
      xstep = random(-1, 1);
      ystep = random(-1, 1);
    }

* Debes adicionar interactividad a tu aplicación. Puede ser mediante teclado, 
  mouse, música, el micrófono, video, sensor o cualquier otro dispositivo 
  de entrada.
* Debes desarrollar tu aplicación bajo control de versión. Usa el directorio 
  correspondiente de cada unidad.

Trayecto de actividades
------------------------

* Realiza la lectura de la unidad 1 del texto guía.
* Experimenta con los conceptos y el código. Documenta las conclusiones que 
  vas descubriendo.
* Trabaja en tu aplicación interactiva.

Recursos 
----------------------

* `Capítulo 1 <https://natureofcode.com/vectors/>`__ del texto guía.
* `Videos 10 al 16 <https://youtube.com/playlist?list=PLRqwX-V7Uu6ZV4yEcW3uDwOgGXKUUsPOM>`__ 
  del curso the nature of code 2.


