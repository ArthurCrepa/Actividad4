#ACTIVIDAD4
---
---

En el presente repositorio se ha agregado el código fuente de "cannon" 
recuperado de: http://www.grantjenks.com/docs/freegames/cannon.html . En el código original, debemos de disparar un proyectil rojo hacia los círculos azules que aparecerán a la derecha de la pantalla, dirigiéndose hacia la izquierda de forma aleatoria, nuestro objetivo es destruir la mayor cantidad de estos antes de que lleguen a la pared izquierda. Podemos direccionar el proyectil con nuestro cursor según su posición en el tablero.

Se nos ha pedido realizar lo siguiente:

1)La velocidad del movimiento para el proyectil y los balones sea más rápida
-
2)Hacer que el juego nunca termine, de manera que los balones al salir de la ventana se re posicionen.
-

Explicaciones
***


*Primer Caso:* Para modificar la velocidad del proyectil, siendo determinado por *speed.x* y *speed.y*,este ha sido dividido entre 15 (previamente era 25) logrando un aumento de velocidad drástico, así mismo afectamos la gravedad de la pelota en *speed.y -= 0.35*, modificamos el valor de 0.35 a 0.7, donde se observa que la "gravedad" es más fuerte. Para los círculos azules se incrementó la frecuencia en que estos aparecen en el tablero *randrange(40) -> randrange(30)*, en *target.x -= 0.5* se elevó a 2.0,logrando modificar su velocidad hacia la izquierda (disminuye su posición sobre el eje x).

*Segundo Caso:*la función move() se encarga de mover los balones y la bola. Cada vez que un balón sale de la ventana (verificado por la función inside()), su posición en el eje X se restablece a 200, colocándolo de nuevo en el borde derecho de la pantalla, asegurando que siga moviéndose indefinidamente. La función tap() responde a los clics en la pantalla, iniciando el movimiento de la bola si está fuera de la ventana. Finalmente, draw() dibuja los balones y la bola, y ontimer(move, 50) mantiene la actualización continua del movimiento en el juego.
