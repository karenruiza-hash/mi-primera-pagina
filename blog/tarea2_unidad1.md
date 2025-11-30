<h1>Reto 1</h1>
<img width="1919" height="469" alt="image" src="https://github.com/user-attachments/assets/735a71d9-6c32-40db-a722-56a4a466cf28" />

En el primer reto se solicita al usuario que ingrese el número de pasos que quiere que dé la tortuga.
La función `input()` obtiene la respuesta como texto; luego `int()` convierte ese texto en un número entero.
El valor resultante se guarda en la variable `pasos`.

Después, se muestra un mensaje indicando cuántos pasos dará la tortuga.
La función `str(pasos)` convierte nuevamente el número a texto para poder construir la frase final.

Finalmente, la expresión `"-" * pasos` crea una cadena que repite el guion tantas veces como número ingresó el usuario.
Por ejemplo, si el usuario escribe **5**, se generará:

```
-----
```

Luego se agrega el símbolo `>`, formando una flecha que avanza según el número ingresado.
El resultado final sería:

```
-----> 
```

<h1>Reto 2</h1>
<img width="1901" height="629" alt="image" src="https://github.com/user-attachments/assets/fab62eb8-2382-48d7-8325-f1adfa1b9c5f" />

Al igual que en el reto 1, se solicita al usuario que ingrese el número de pasos que dará la tortuga, en este caso, serán pasos hacia abajo, usando input(). La respuesta es recibida como texto y luego se convierte a un número entero con int().  Después se imprime la cantidad de pasos, agregando \n (saltos de línea), tantas veces como el número de pasos ingresado por el usuario, esto hace que se imprima |, uno debajo de otro. Finalmente, para simular la cabeza de la tortuga, ponemos la letra "v".
