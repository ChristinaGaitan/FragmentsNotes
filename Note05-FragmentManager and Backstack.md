FragmentManager and Backstack
==========================

Backstack behavior
-------
- Cuando el usuario va de una Activity a otra, Android NO destruye las Activities, simplemente las pone en un Stack desde el que pueden se accedidas cuando se presiona el botón de Back.

- Por default, los Fragments NO tienen noción del Back botón.

- Cuando el usuario presiona el botón de Back es llevado a la Activity anterior, Backstack NO considera cambios dentro de la misma Activity (Add/Remove/Replace de Fragments).

- Para agregar los cambios en los Fragments es necesario llamar el método ```addToBackStack``` antes de llamar el método ```commit``` de la transacción.

- Cuando varias operaciones son efectuadas en la misma transacción, al hacer uso del método ```addToBackStack``` todas las operaciones son guardadas como una sola entrada en el Stack.

- Cuando se remueve un Fragment sin invocar el método ```addToBackStack``` el Fragment es destruido y el usario ya no puede accederese a él.

- En cambio, cuando se remueve un Fragment y antes se invoca el método ```addToBackStack``` el Fragment es sólamente detenido y reasumed cuando el usuario vuelve a él, lo que hace a la aplicación más rápida.

Programmatic Backstack behavior
-------
- La operación del botón de Back puede ser simulada utilizando el método ```popBackStack```
	- ```popBackStack()``` Regresa a la Activity inmediatamente anterior.
	- Utilizando primero ```addToBackStack("A")``` y después ```popBackStack("A")``` Regresa a la Activity que tenga la tag "A" asociada.
	- Utilizando primero ```addToBackStack("A")``` y después ```popBackStack("A", POP_BACK_STACK_INCLUSIVE)``` Regresa a la Activity anterior a la que tenga la tag "A" asociada.

- Para observar cambios en la BackStack se usa el método ```onBackStackChangedListener```

- ```onBackStackChanged``` es llamado cada que el contenido de la StackBack es cambiado.

- ```getBackStackEntryCount``` regresa el número de entradas en el Back Stack.

- ```getBackStackEntryAt(int index)``` obtiene la entrada en el índice especificado.

- ```getBackStackEntry``` obtiene la entrada con el nombre especificado.

Referencias
------------
- [#18 Android FragmentManager and Backstack Part 1: Android Fragments Tutorial [HD 1080p]](https://www.youtube.com/watch?v=ZbKKxYUOH-c&index=18&list=PLonJJ3BVjZW4lMlpHgL7UNQSGMERcDzHo)