Scrollable Tabs
==========================

Swipe Tabs
-------
- Se despliegan del mismo tamaño, toman el ancho de la pestaña más ancha.

- Si no hay suficiente espacio para que se vean todas, las etiquetas se vuelven scroleables.

- Es mejor utilizarlas cuando se van a desplegar 3 o menos pestañas.

Scroll Tabs
-------
- Pueden contener un mayor número de pestañas.

- Pasos para generarlas:
	1. Crear las clases y layouts de los Fragments.
	2. Crear el ViewPager.
		- Es un layout manager en el que cada hijo es una página separada.
		- Es una implementación de PageAdapter para cambiar entre páginas.
		- Puede usar **FragmentStatePagerAdapter** o **FragmentPagerAdapter**.
		- Debe ser el root layout (al final de cuentas es un container).
	3. Implementar el Adapter apropiado.
		- ```getItem()``` Regresa el Fragmento en la posición dada.
		- ```getCount()``` Regresa el npumero total de páginas o Fragments.
	4. Agregar un título dentro del ViewPager.

Diferencias entre **FragmentStatePagerAdapter** y **FragmentPagerAdapter**
-------
- **FragmentPagerAdapter:**
	- Se usa para una cantidad pequeña y determinada de páginas
	- Cada Fragment se mantiene como un objeto asociado a la Activity, su UI es destruida conforme el usuario cambia de fragmento.

- **FragmentStatePagerAdapter**
	- Se usa cuando se tiene una gran cantidad de páginas.
	- El Fragment entero puede ser destruido sólo manteniendo su ```onSaveInstanceState()``` retenido.

Referencias
------------
- [#27 Android Scrollable Tabs Part 1:Android Tutorial For Beginners [HD 1080p]](https://www.youtube.com/watch?v=JJeeZHFgLfc&index=27&list=PLonJJ3BVjZW4lMlpHgL7UNQSGMERcDzHo)