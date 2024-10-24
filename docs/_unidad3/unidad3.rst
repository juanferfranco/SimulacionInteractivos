Unidad 3. Fuerzas
=======================================

Introducción 
-------------

En la unidad anterior experimentaste con algunos algoritmos para manipular 
la aceleración: constante, aleatorio, interactivo. En esta unidad 
usarás fuerzas para modificar la aceleración de un objeto.

Investigación 
---------------

Actividad 1
************

Comienza dando una lectura rápida a la 
`unidad 2 del libro <https://natureofcode.com/forces>`__. La idea es 
que veas de qué se trata. Observa los ejemplos y lee las partes 
que más te llamen la atención o aquello que requieras repasar.
  
Actividad 2
************

¿Recuerdas el marco motion 101 de la unidad anterior?

.. code-block:: javascript

    let mover;

    function setup() {
        createCanvas(640, 240);
        mover = new Mover();
    }

    function draw() {
        background(255);
        mover.show();
        mover.update();
        mover.checkEdges();
    }

    ...
    update() {
        this.velocity.add(this.acceleration);
        this.velocity.limit(this.topSpeed);
        this.position.add(this.velocity);
    }        
  
En la unidad anterior tu definías la aceleración mediante 
algún algoritmo. Ahora la vas a calcular. ¿Qué tiene 
que ver esto con las leyes de movimiento de Newton?

Actividad 3
************

Ahora supón que estás aplicando dos fuerzas a una criatura. Observa estos 
fragmentos de código:

.. code-block:: javascript

    mover.applyForce(wind);
    mover.applyForce(gravity);
    .
    .
    .
    applyForce(force) {
      this.acceleration = force;
    }

    .
    .
    .

    this.velocity.add(this.acceleration);

* ¿Qué problema le ves a esto? 
* ¿Por qué la fuerza debe ser acumulativa?

Actividad 4
************

En el siguiente código:

.. code-block:: javascript

    update() {
        this.velocity.add(this.acceleration);
        this.position.add(this.velocity);
        this.acceleration.mult(0);
    }

* ¿Por qué es necesario multiplicar la aceleración por 
  cero en cada frame? 
* ¿Por qué se multiplica por cero 
  justo al final de update()?
* ¿Cómo tener en cuenta la masa de la criatura?

Actividad 5
************

En el siguiente código:

.. code-block:: javascript

    applyForce(force) {
        force.div(mass);
        this.acceleration.add(force);
    }

* ¿force se está pasando por VALOR o por REFERENCIA?
* Cuando se `modela una fuerza <https://natureofcode.com/forces/#modeling-a-force>`__ 
  ¿Qué pasos hay que seguir para 
  poder incorporar dicha fuerza a la simulación?

Actividad 6
************

En el siguiente código:

.. code-block:: javascript

    let friction = this.velocity.copy();
    let friction = this.velocity;

* ¿Cuál es la diferencia entre las 
  dos líneas?
* ¿Qué podría salir mal con ``let friction = this.velocity;``
* De nuevo, toca repasar. ¿Cuál es la diferencia entre 
  copiar por VALOR y por REFERENCIA?
* En el fragmento de código cuándo es por VALOR y cuándo por REFERENCIA.

Reto
------

Seguimos explorando los conceptos usando criaturas. PERO considera esto. 
Las criaturas no tienen que ser personajes o animales. Pueden ser conceptos, 
ideas, objetos, etc. 

* Tus criaturas van a interactuar con elementos del ecosistema como COMIDA, 
  depredadores, plantas, etc.
* Simula fuerzas de ATRACCIÓN y REPULSIÓN entre tus criaturas y el mundo en el que viven.
* Vas a buscar ``3 tipos de fuerzas`` y las vas a ``MODELAR`` para 
  incorporarlas en la simulación, pero esas fuerzas deberán responder a una 
  ``NARRATIVA``, tu la defines, es tu ecosistema.

  .. warning:: TENEMOS UN NUEVO REQUISITO

      La narrativa. Tu la defines, no tiene que ser una historia, la narrativa 
      es la razón de ser de tu simulación. ¿Por qué tus criaturas se mueven 
      de esa manera? ¿Por qué interactúan con el mundo de esa manera?

* Incluye en tu simulación interacción de las criaturas con líquidos donde 
  experimenten fuerzas de resistencia.
* Incluye una extraña colonia de criaturas que se comporten según las ideas 
  de un n-Body problem.
* Debes adicionar interactividad a tu aplicación. Puede ser mediante teclado, 
  mouse, música, el micrófono, video, sensor o cualquier otro dispositivo 
  de entrada.

