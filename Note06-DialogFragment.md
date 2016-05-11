DialogFragment
==========================

Backstack behavior
-------
- Permite preguntarle al usuario sobre decisiones o información requerida para continuar con las tareas de la app.

- Se conforma de 3 partes:
	1. **Optional Title** Nombre de la característica a modificar o de la decisión que tiene que tomar.
	2. **Content Area** elementos UI (text fields, checkboxes, radio buttons) para que el usuario cambie las settings de la aplicación.
	3. **Action Buttons** Cancel and/or Ok buttons
		- Acciones negativas a la izquierda.
		- Acciones afirmativas a la derecha.
		- Acciones negativas te llevan al estado previo.
		- Acciones positivas cumplen con las metas.

- Para desplegar el dialog se usa el método ```show()``` el cual invoca el método ```commit()```. Por eso, el método ```show()``` debe ser el último en utilizarse en una transacción y NO se debe llamar el método ```commit()``` después de él.


Referencias
------------
- [#22 Android DialogFragment Part 1: Android Tutorial For Beginners [HD 1080p]](https://www.youtube.com/watch?v=xi3kMn82YcE&index=22&list=PLonJJ3BVjZW4lMlpHgL7UNQSGMERcDzHo)