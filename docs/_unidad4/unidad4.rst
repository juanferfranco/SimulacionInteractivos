Unidad 4. Oscilaciones
=======================================

Requisitos de la aplicación interactiva
--------------------------------------------

Vas a continuar enriqueciendo el proyecto del ecosistema. A medida que avances con esta simulación 
las historias de tu ecosistema de criaturas se harán más ricas. No olvides que tu aplicación interactiva 
en Ingeniería en Diseño de Entretenimiento Digital se queda corta si deja de contar una historia, si no 
hay narrativa.

Crea una simulación interactiva de un ecosistema donde diferentes especies interactúan 
y se comportan utilizando estos conceptos: 

#. Movimiento angular
#. Apuntar en la dirección del movimiento.
#. Movimiento armónico simple.
#. Waves
#. Fuerzas de resorte
#. Péndulos
#. Debes adicionar interactividad a tu aplicación. Puede ser mediante teclado, 
   mouse, música, el micrófono, video, sensor o cualquier otro dispositivo 
   de entrada.
#. Debes desarrollar tu aplicación bajo control de versión. Usa el directorio 
   correspondiente de cada unidad.

.. warning:: MUY IMPORTANTE

    * No olvides verificar que tu simulación incluya de alguna manera cada uno de los aspectos anteriores.
    * Lo que leerás en seguida NO LO TIENES QUE IMPLEMENTAR, son solo ideas para que te inspires.

Te voy a dar IDEAS para que te inspires (puedes preguntarte también a ChatGPT):

* Un ecosistema virtual con diferentes especies, como presas, 
  depredadores y plantas. Cada especie estará representada por objetos que se comporten como 
  péndulos y fuerzas de resortes.
* Puedes implementar reglas y comportamientos para que las especies 
  interactúen entre sí. Por ejemplo, los depredadores pueden ``apuntar`` a las presas y las 
  presas pueden evadir a los depredadores. Además, las especies pueden interactuar con las 
  plantas para obtener energía y nutrición.
* Las especies se pueden mover en patrones de movimiento armónico simple. 
  Por ejemplo, las presas pueden oscilar mientras se desplazan en línea recta, y los 
  depredadores pueden realizar movimientos oscilatorios mientras persiguen a sus presas.
* Simulaciones ondas en el ecosistema. Por ejemplo, puedes agregar un lago o un cuerpo de agua 
  donde las ondas se propaguen y afecten el comportamiento de las especies que interactúan con el agua.
* Las interacciones entre las especies se pueden basar en fuerzas de resortes 
  simuladas. Por ejemplo, los depredadores experimentarán una fuerza de resorte al acercarse a 
  las presas, y las especies pueden experimentar fuerzas de repulsión o atracción 
  entre sí.
* Las especies pueden tener movimientos angulares que afecten su comportamiento. 
  Por ejemplo, algunas especies pueden girar para enfrentar la dirección de movimiento o 
  apuntar hacia sus objetivos.
* Los usuarios podrán interactuar con el ecosistema y modificar 
  parámetros como la cantidad de especies, las constantes elásticas de los resortes, 
  la frecuencia y amplitud de las oscilaciones, entre otros.
* Puedes personalizar tu ecosistema eligiendo diferentes tipos de especies con comportamientos 
  específicos. Por ejemplo, agrega especies herbívoras, carnívoras y omnívoras con distintos 
  tamaños y velocidades.
* Establece la densidad y distribución de las especies en el entorno para influir en la 
  competencia y la disponibilidad de recursos.
* Implementa un sistema de alimentación donde las especies depredadoras deben cazar y atrapar 
  a las presas para obtener alimento y mantener su energía.
* Agrega comportamientos de reproducción para que las especies puedan aumentar su población 
  y mantener un equilibrio en tu ecosistema.
* Ajusta la frecuencia y amplitud de las oscilaciones de las especies, lo que afecta su 
  velocidad y comportamiento general.
* Experimenta con oscilaciones de diferentes patrones, como oscilaciones amortiguadas o 
  forzadas, para simular especies con comportamientos únicos.
* Agrega eventos que generen ondas en el entorno, como terremotos, movimientos de masas de agua 
  o ráfagas de viento, para afectar el comportamiento de las especies y su ubicación en el ecosistema.
* Ajusta la intensidad y frecuencia de las ondas para ver cómo afectan a las especies y 
  cómo se propagan por todo tu ecosistema.
* Incorpora objetos o trampas con fuerzas de resorte que interactúen con las especies, como 
  redes de pesca o campos magnéticos, para afectar su movimiento y comportamiento.
* Experimenta con resortes de diferentes constantes elásticas para simular diferentes 
  niveles de rigidez en el entorno y observa cómo afectan la movilidad de las especies.
* Ajusta el ángulo de dirección de movimiento de las especies para que apunten hacia 
  fuentes de alimento o eviten áreas peligrosas.
* Implementa comportamientos de orientación, donde las especies busquen seguir una 
  dirección específica, como la posición del sol o una fuente de calor.

Trayecto de actividades
------------------------

* Realiza la lectura de la unidad 3 del texto guía: oscilaciones.
* Ve haciendo experimentos pequeños con cada concepto que encuentras. Reporta y analiza 
  esos experimentos en tu bitácora. En el texto guía encontrarás experimentos que puedes 
  personalizar y modificar para explorara diferentes posibilidades. Captura en la bitácora 
  imágenes de esos experimentos.
* Te propongo este experimento. Ejecuta y compara los siguientes códigos. Explica qué está 
  pasando:

  Código 1:

  .. code-block:: javascript

    // The Nature of Code
    // Daniel Shiffman
    // http://natureofcode.com

    let angle = 0;

    function setup() {
      createCanvas(640, 240);
    }

    function draw() {
      background(255);

      fill(127);
      stroke(0);
      rectMode(CENTER);
      translate(width / 2, height / 2);

      line(-50, 0, 50, 0);
      stroke(0);
      strokeWeight(2);
      fill(127);
      circle(50, 0, 16);
      circle(-50, 0, 16);
      angle += 0.1;
      rotate(angle);
    }

  Código 2:

  .. code-block:: javascript

    // The Nature of Code
    // Daniel Shiffman
    // http://natureofcode.com

    let angle = 0;

    function setup() {
      createCanvas(640, 240);
    }

    function draw() {
      background(255);

      fill(127);
      stroke(0);
      rectMode(CENTER);
      translate(width / 2, height / 2);
      rotate(angle);
      line(-50, 0, 50, 0);
      stroke(0);
      strokeWeight(2);
      fill(127);
      circle(50, 0, 16);
      circle(-50, 0, 16);
      angle += 0.1;
    }

* Te preguntarás ¿Cómo hago entonces para controlar de manera independiente 
  la rotación de cada elementos de la simulación? Analiza con detenimiento 
  este código:

  .. code-block:: javascript

      function draw() {
        background(255);

        attractor.display();

        for (let i = 0; i < movers.length; i++) {
          let force = attractor.attract(movers[i]);
          movers[i].applyForce(force);

          movers[i].update();
          movers[i].show();
        }
      }

  En cada Mover:

  .. code-block:: javascript

      update() {
        this.velocity.add(this.acceleration);
        this.position.add(this.velocity);
        this.angleAcceleration = this.acceleration.x / 10.0;
        this.angleVelocity += this.angleAcceleration;
        this.angleVelocity = constrain(this.angleVelocity, -0.1, 0.1);
        this.angle += this.angleVelocity;
        this.acceleration.mult(0);
      }

  Y el truco está en el método que pinta cada Mover:

  .. code-block:: javascript

      show() {
        strokeWeight(2);
        stroke(0);
        fill(127, 127);
        rectMode(CENTER);
        push();
        translate(this.position.x, this.position.y);
        rotate(this.angle);
        circle(0, 0, this.radius * 2);
        line(0, 0, this.radius, 0);
        pop();
      }

  Nota la pareja ``push()`` y ``pop()``. ¿Qué hacen y por qué 
  son importantes?


Recursos 
----------------------

* `Capítulo 3 <https://natureofcode.com/oscillation/>`__ del texto guía.
* `Videos 23 al 31 <https://youtube.com/playlist?list=PLRqwX-V7Uu6ZV4yEcW3uDwOgGXKUUsPOM>`__ 
  del curso the nature of code 2.
