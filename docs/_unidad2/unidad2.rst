Unidad 2. Vectores
=======================================

Introducción 
-------------

En la programación creativa, los vectores son una herramienta fundamental para representar 
y manipular información en dos o tres dimensiones. Los vectores son utilizados para 
representar posiciones, velocidades, aceleraciones, fuerzas, direcciones, entre otros.

Investigación 
---------------

En tu bitácora de aprendizaje, investiga sobre el uso de vectores en la programación creativa. Te 
propondré que reportes en tu bitácora algunas actividades y experimentos tomados de  
`este <https://nature-of-code-2nd-edition.netlify.app/vectors/>`__ recurso. 

Para cada actividad reporta en tu bitácora la respuesta a las preguntas planteadas. 
En el caso de los experimentos reporta qué pregunta estás investigando con el 
experimento, qué resultados esperas obtener, qué resultados obtuviste y qué aprendiste. Además, 
añade el código y un enlace al editor de p5.js con el resultado.


Actividad 1
*****************

Analiza `este <https://natureofcode.com/vectors/#example-12-bouncing-ball-with-vectors>`__  
ejercicio:

* ¿Cómo funciona la suma dos vectores?
* ¿Por qué esta línea ``position = position + velocity;`` no funciona?

Experimento 1
*****************

Realiza el `este <https://natureofcode.com/vectors/#exercise-11>`__ ejercicio.
   
* ¿Que tuviste que hacer para hacer la conversión propuesta?

Experimento 2
**************

Dale una mirada a este código

.. code-block:: javascript

    let position;

    function setup() {
        createCanvas(400, 400);
        posicion = createVector(6,9);
        playingVector(posicion);
        noLoop();
    }

    function playingVector(v){
        v.x = 20;
        v.y = 30;
    }

    function draw() {
        background(220);
        console.log("Only once");
    }

Para este experimento puedes usar las funciones console.log() y print() para imprimir 
mensajes en la consola del navegador. También puedes usar el método toString() de la clase 
p5.Vector para imprimir el vector en la consola.

* ¿Qué resultado esperas obtener?
* ¿Qué resultado obtuviste?
* Recuerdas los conceptos de paso por valor y paso por referencia en programación? ¿Qué 
  tipo de paso se está realizando en este código?
* ¿Qué aprendiste?

Actividad 2
**************

Dale una mirada a la clase p5.Vector `aquí <https://p5js.org/reference/p5/p5.Vector/>`__. 

* ¿Para qué sirve el método ``mag()``? Nota que hay otro método llamado ``magSq()``. 
  ¿Cuál es la diferencia entre ambos? ¿Cuál es más eficiente?
* ¿Para qué sirve el método ``normalize()``?
* Te encuentras con un periodista en la calle y te pregunta ¿Para qué el método ``dot()``? 
  ¿Qué le responderías en un frase?
* El método ``dot()`` tiene una versión estática y una de instancia. ¿Cuál es la diferencia 
  entre ambas?
* Ahora el mismo periodista curioso de antes te pregunta si le puedes dar una intuición 
  geométrica acerca del producto cruz. Entonces te pregunta ¿Cuál es la interpretación 
  geométrica del producto cruz de dos vectores? Tu respuesta debe incluir qué pasa 
  con la orientación y la magnitud del vector resultante.
* ¿Para que te puede servir el método ``dist()``?
* ¿Para qué sirven los métodos ``normalize()`` y ``limit()``?

Actividad 3
*************

Vas a tomar como inspiración este ejemplo de la referencia de p5.js:

.. code-block:: javascript

    function setup() {
        createCanvas(100, 100);    
    }
    
    function draw() {
        background(200);

        let v0 = createVector(50, 50);
        let v1 = createVector(30, 0);
        let v2 = createVector(0, 30);
        let v3 = p5.Vector.lerp(v1, v2, 0.5);
        drawArrow(v0, v1, 'red');
        drawArrow(v0, v2, 'blue');
        drawArrow(v0, v3, 'purple');
    }

    function drawArrow(base, vec, myColor) {
        push();
        stroke(myColor);
        strokeWeight(3);
        fill(myColor);
        translate(base.x, base.y);
        line(0, 0, vec.x, vec.y);
        rotate(vec.heading());
        let arrowSize = 7;
        translate(vec.mag() - arrowSize, 0);
        triangle(0, arrowSize / 2, 0, -arrowSize / 2, arrowSize, 0);
        pop();
    }

Vas a modificarlo para generar este resultado:

.. image:: ../_static/vectorLerp.gif
    :alt: lerp and color lerp animation
    :scale: 50 %

* Analiza entonce cómo funciona el método ``lerp()``. Nota que además de la interpolación 
  lineal de vectores, también puedes hacer interpolación lineal de colores con el método 
  ``lerpColor()``.
* Dedica un tiempo a estudiar cómo se dibuja una flecha en el método ``drawArrow()``. No 

Actividad 4
*************

Modifica de nuevo el programa, pero esta vez cambia la base de las flechas y la 
escala de los vectores usando el mouse.

Actividad 5
*************

Ahora vas a leer y analizar con mucho detenimiento la sección 
`Motion with vectors <https://natureofcode.com/vectors/#motion-with-vectors>`__.
El autor propone un marco de movimiento llamado motion 101.

* ¿En qué consiste motion 101?

Experimento 3
***************

Realiza un experimento para basado en el `ejemplo 1.7 <https://natureofcode.com/vectors/#example-17-motion-101-velocity>`__.


Experimento 4
***************

En el libro proponen una regla (que eventualmente se rompe cuando conviene :)): 

The goal for programming motion is to come up with an algorithm for calculating 
acceleration and then let the trickle-down effect work its magic.

Para investigador el significado de esta frase te propone que construyas un experimento 
donde analices cómo se comporta un objeto en movimiento con:

* Aceleración constante.
* Aceleración aleatoria.
* Aceleración hacia el mouse.

Reto
------

Nuestro reto de programación creativa se llamará ``Mundos aleatorios y criaturas Vectoriales``.

Objetivo
*********

Diseñar un pequeño mundo interactivo donde convivan al menos 3 criaturas distintas, 
cada una con su propio comportamiento y personalidad, utilizando únicamente conceptos de vectores 
y aleatoriedad.

Requisitos
***********

1. Apariencia y Personalidad:

  * Diseña 3 criaturas con apariencias diferentes.
  * Dale a cada criatura una personalidad que se refleje en su comportamiento, utilizando variaciones 
    en la velocidad, dirección y tipo de movimiento.

2. Comportamiento y Movimiento:

  * Controla el movimiento de las criaturas exclusivamente manipulando la ACELERACIÓN a través de vectores.
  * Usa el marco motion 101. RECUERDA que ChatGPT no sabe esto, así que debes explicarle qué es.
  * Implementa una caminata aleatoria con Lévy flight para al menos una de las criaturas, utilizando los conceptos 
    del capítulo de aleatoriedad.

3. Interactividad. Agrega interactividad a tu mundo, utilizando una o más de las siguientes opciones: 
   
  * Teclado/mouse: el usuario puede cambiar la dirección de una o más criaturas, crear obstáculos, o afectar la velocidad.
  * Audio/Música: las criaturas responden a la intensidad del sonido (por ejemplo, más ruido puede aumentar la velocidad 
    o hacer que cambien de dirección).

Bitácora
**********

* Documenta cómo resolviste cada uno de los tres requisitos: apariencia y personalidad, comportamiento y movimiento, 
  e interactividad.
* Explica cómo utilizaste vectores y aleatoriedad en tu diseño.
* Describe cómo implementaste el marco motion 101 en tu diseño.
* Enlace al proyecto en el editor de p5.js.
* Archivo scketch.js con el código fuente de tu proyecto (en la carpeta unidad 2).
* Enlace a un video o Gif que muestre tu proyecto en acción.

