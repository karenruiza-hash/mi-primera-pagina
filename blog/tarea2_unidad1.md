<h1>Tarea 2 - Ejercicios Unidad 1</h1>

<h2>Reto 1</h2>

```python
pasos = int(input("¿Cuántos pasos dará la tortuga?"))
print("Creando tortuga simulada que da.. " + str(pasos) +" pasos")
print("-" * pasos + ">")
```
En el primer reto se solicita al usuario que ingrese el número de pasos que quiere que dé la tortuga.
La función `input()` obtiene la respuesta como texto; luego `int()` convierte ese texto en un número entero.
El valor resultante se guarda en la variable `pasos`.

Después, se muestra un mensaje indicando cuántos pasos dará la tortuga.
La función `str(pasos)` convierte nuevamente el número a texto para poder construir la frase final.

Finalmente, la expresión `"-" * pasos` crea una cadena que repite el guion tantas veces como número ingresó el usuario.
Por ejemplo, si el usuario escribe **5**, se generará:

Luego se agrega el símbolo `>`, formando una flecha que avanza según el número ingresado.
El resultado final sería:

<h2>Reto 2</h2>

```python
pasos = int(input("¿Cuántos pasos dará la tortuga hacia abajo?"))
print("Creando tortuga simulada que da " + str(pasos) + " pasos")
print("|\n" * pasos + "∨")
```

Al igual que en el reto 1, se solicita al usuario que ingrese el número de pasos que dará la tortuga, en este caso, serán pasos hacia abajo, usando `input()`. La respuesta es recibida como texto y luego se convierte a un número entero con int().  Después se imprime la cantidad de pasos, agregando `\n` (saltos de línea), tantas veces como el número de pasos ingresado por el usuario, esto hace que se imprima |, uno debajo de otro. Finalmente, para simular la cabeza de la tortuga, ponemos la letra "v".

<h2>Reto 3</h2>

```python
pasosD = int(input("¿Cuántos pasos dará la tortuga hacia la derecha?"))
pasosA = int(input("¿Cuántos pasos dará la tortuga hacia abajo?"))

print("Creando tortuga simulada que da " + str(pasosD) + str(pasosA) + " pasosD" + " pasosA")
print("-" * pasosD)
print((" " * pasosD + "|\n") * pasosA + (" " * pasosD + "V"))
```

Se solicita al usuario ingresar el número de pasos que dará la tortuga, tanto hacia la derecha, como hacia abajo, usando dos `inpunt()`. Las respuestas se reciben como texto, luego son convertidas a números enteros usando `int()`. Se imprime una cadena de guiones que depende del número ingresado por el usuario para pasos a la derecha, luego se imprimen las líneas hacia abajo, usando `(|\n)` para los saltos de línea, finalmente se imprime la letra "v" para representar la cabeza de la tortuga. Entonces, al ejecutar el código, se forma un recorrido que simula cómo la tortuga avanza hacia la derecha, y luego hacia abajo. 

<h2>Reto 4</h2>

```python
pasosD = 5
pasosA = 5

def derecha(n):
  print("-" * n + ">")
def abajo(n):
  print((" " * pasosD + "|\n") * n + (" " * pasosD + "V"))

derecha(pasosD)
abajo(pasosA)
```

Con este programa, se recrea el recorrido de la tortuga en forma de escalón, fijamos valores para los pasos hacia la derecha y para los pasos hacia abajo, estos valores se almacenan en las variables pasosD y pasosA, luego crea dos funciones, `derecha(n)`, que imprime una línea de guiones seguida del símbolo `>`, que muestra que la tortuga avanzó hacia la derecha, y `abajo(n)` que imprime barras verticales y al final la letra `v`, representando el giro y el avance de la tortuga hacia abajo. 

Al ejecutarse `derecha(pasosD)` y `abajos(pasosA)`, el resultado es un dibujo que muestra el recorrido de la tortuga, inicialmente a la derecha, y luego hacia abajo.

<h2>Reto 5 </h2>

```python
pasosD = 5
pasosA = 5
escalones = 0

def derecha(n):
  global escalones
  espaciosIzquierda = " " * pasosD * escalones
  print(espaciosIzquierda + "-" * n + ">")
def abajo(n):
  global escalones
  espaciosIzquierda = " " * pasosD * escalones
  print((espaciosIzquierda + (" " * pasosD + "|\n")) * n + (espaciosIzquierda + " " * pasosD + "V"))
  escalones = escalones + 1

derecha(pasosD)
abajo(pasosA)

derecha(pasosD)
abajo(pasosA)

derecha(pasosD)
abajo(pasosA)
```
Inicialmente se definen tres variables:
`pasosD`: para el número de pasos que dará la tortuga hacia la derecha. 
`pasosA`: para el número de pasos que dará la tortuga hacia abajo.
`escalones`: para el contador que indica en qué escalon se encuentra la tortuga.
También se definen dos funciones, `derecha(n)`, usa el valor de escalones para calcular cuántos espacios debe dejar a la izquierda `(espaciosIzquierda)`, además imprime una línea de guiones, seguida del símbolo `>`, que marca el recorrido de la tortuga hacia la derecha, según el escalón actual. La función `abajo(n)` calcula los espacios a la izquierda según el escalón, imprime líneas con una barra vertical `|` y al final la letra `v`, marcando la posición de la tortuga, finalmente, aumenta el contador `escalones` en 1, lo que hace que el próximo bloque se dibuje más a la derecha. 
Al finalizar se llaman las funciones `derecha(pasosD)` y `abajo(pasosA)` tres veces seguidas para representar el número de escalones que se formarán en el recorrido de la tortuga. 
