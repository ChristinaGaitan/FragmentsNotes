Inter-Fragment Communication
==========================

- NO es recomendable mantener referencia de un Fragment con otro.

- Es mejor crear una Interface que contenga el método que funcionará como un event carrier.

- La Activity implementa la Interface.

- Se usa un método callback en la Activity para disparar los cambios en el segundo Fragment.



Referencias
------------
- [#8 Fragment Tutorial Android: Inter-Fragment Communication Part 1 [HD 1080p]](https://www.youtube.com/watch?v=VyyGP_d0Ia8&index=8&list=PLonJJ3BVjZW4lMlpHgL7UNQSGMERcDzHo&nohtml5=False)