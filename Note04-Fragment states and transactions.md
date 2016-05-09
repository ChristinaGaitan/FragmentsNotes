Fragment States y Transactions
==========================

States
-------
- Los Fragments pueden existir en 3 diferentes estados:
	1. Objeto Java
	2. Asociado con una Activity
	3. Asociado con una Activity y desplegado al usuario como UI.

Transactions
------------
- Nos permiten manejar varios Fragments al mismo tiempo.

- Los pasos para una Transaction son:
	1. Obtener el FragmentManager.
	2. Begin la Transaction.
	3. Add/Remove/Replace fragments.
	4. Commit la Transaction.

- **Add fragment**
    ```add(ID del layout, Fragment OBJECT, TAG para referenciar el Fragment)```
    1. Crear el objeto FragmentTransaction.
    2. Begin la Transaction.
    3. Add el Fragment.
    4. Commit la Transaction.
    5. Todos los lifecycle methods son ejecutados en el Fragment.

- **Remove fragment**
    ```remove(Fragment OBJECT)```
    1. Obtener el Fragment object usando el ID o TAG.
    2. Begin la FragmentTransaction.
    3. Remove el Fragment.
    4. Commit la Transaction.
    5. Todos los lifecycle methods son ejecutados en el Fragment.
    - Después de remover el Fragment éste ya no puede utilizarse porque es destruido, puede o no puede ser NULL.

- **Replace fragment**
    ```replace(Layout ID, Nev Fragment OBJECT)```
    - Remueve un Fragment y agrega otro.
    - Los destructive methods son llamados en el primer Fragment y los constructive methos en el segundo.
    1. Crear el nuevo Fragment Object.
    2. Especificar el Layout ID en dónde el antiguo Fragment está contenido y llamar el método replace.

- **attach method**
    - ```onAttach()``` es llamado dentro del Fragment para notificar que el Fragment ha sido asociado a la Activity.
    - ```transaction.attach()``` crea la UI, en este caso el método ```onAttach()``` no es invocado porque ya existe la asociación con la Activity.
    - Sirve para mostrar el Fragment al usuario.


- **detach method**
	- ```onDetach()``` es llamado dentro del Fragment para notificar que el Fragment ha sido desasociado de la Activity.
    - ```transaction.detach()``` destruye la UI, en este caso el método ```onDetach()``` no es invocado porque sólo se destruye la UI.
    - Sirve para esconder el Fragment del usuario.

Referencias
------------
- [#8 Fragment Tutorial Android: Inter-Fragment Communication Part 1 [HD 1080p]](https://www.youtube.com/watch?v=VyyGP_d0Ia8&index=8&list=PLonJJ3BVjZW4lMlpHgL7UNQSGMERcDzHo&nohtml5=False)