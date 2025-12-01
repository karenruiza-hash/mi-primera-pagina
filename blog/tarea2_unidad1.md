# Tarea 2 - Ejercicios Unidad 1

## Reto 1
Intenta recrear el movimiento de la tortuga únicamente con texto, usando funciones, print() y input() para pedir valores al usuario.

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

## Reto 2
Crea el rastro de una tortuga moviéndose hacia abajo usando únicamente print() e input().  
La salida esperada es similar a:

```python
pasos = int(input("¿Cuántos pasos dará la tortuga hacia abajo?"))
print("Creando tortuga simulada que da " + str(pasos) + " pasos")
print("|\n" * pasos + "∨")
```

Al igual que en el reto 1, se solicita al usuario ingresar el número de pasos que dará la tortuga hacia abajo.  
La respuesta es recibida como texto y luego se convierte a un número entero con `int()`.  
Después se imprime la cantidad de pasos, agregando `\n` (saltos de línea) tantas veces como el número de pasos ingresado, esto hace que se imprima `|` uno debajo de otro.  
Finalmente, para simular la cabeza de la tortuga, ponemos la letra `∨`.

## Reto 3
Ahora la tortuga no solo avanza: también gira.  
Observa cómo lo hace la versión gráfica: se dibuja una “L”.

```python
pasosD = int(input("¿Cuántos pasos dará la tortuga hacia la derecha?"))
pasosA = int(input("¿Cuántos pasos dará la tortuga hacia abajo?"))

print("Creando tortuga simulada que da " + str(pasosD) + str(pasosA) + " pasosD" + " pasosA")
print("-" * pasosD)
print((" " * pasosD + "|\n") * pasosA + (" " * pasosD + "V"))
```

Se solicita al usuario ingresar el número de pasos que dará la tortuga, tanto hacia la derecha como hacia abajo, usando dos `input()`.  
Las respuestas se reciben como texto, luego se convierten a números enteros usando `int()`.  
Se imprime una línea de guiones según los pasos a la derecha, luego las líneas hacia abajo usando `(|\n)` y finalmente la letra `V` para representar la cabeza de la tortuga.  
El resultado es un recorrido que simula cómo la tortuga avanza hacia la derecha y luego hacia abajo.

## Reto 4
Reescribe los retos anteriores creando funciones que representen los movimientos de la tortuga solo con texto.  
Usa las siguientes funciones como interfaz:

Por ejemplo, al ejecutar:

```python
adelante(5)
abajo(3)
```

Debería producir un patrón en forma de L como en la figura.

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

Con este programa, se recrea el recorrido de la tortuga en forma de escalón.  
Se fijan valores para los pasos hacia la derecha y hacia abajo, luego se crean dos funciones:  
- `derecha(n)`: imprime una línea de guiones seguida del símbolo `>`  
- `abajo(n)`: imprime barras verticales y al final la letra `V`, representando el giro y avance de la tortuga hacia abajo.  

Al ejecutar `derecha(pasosD)` y `abajo(pasosA)`, se dibuja el recorrido en forma de L.

## Reto 5
Ajusta tus funciones para que la tortuga pueda bajar escalones.  
Cada escalón debe conservar la posición horizontal acumulada y dibujar correctamente tanto el tramo horizontal como el vertical.

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
  escalones += 1

derecha(pasosD)
abajo(pasosA)

derecha(pasosD)
abajo(pasosA)

derecha(pasosD)
abajo(pasosA)
```



Inicialmente se definen tres variables: pasosD: para el número de pasos que dará la tortuga hacia la derecha. pasosA: para el número de pasos que dará la tortuga hacia abajo. escalones: para el contador que indica en qué escalon se encuentra la tortuga. También se definen dos funciones, derecha(n), usa el valor de escalones para calcular cuántos espacios debe dejar a la izquierda (espaciosIzquierda), además imprime una línea de guiones, seguida del símbolo >, que marca el recorrido de la tortuga hacia la derecha, según el escalón actual. La función abajo(n) calcula los espacios a la izquierda según el escalón, imprime líneas con una barra vertical | y al final la letra v, marcando la posición de la tortuga, finalmente, aumenta el contador escalones en 1, lo que hace que el próximo bloque se dibuje más a la derecha. Al finalizar se llaman las funciones derecha(pasosD) y abajo(pasosA) tres veces seguidas para representar el número de escalones que se formarán en el recorrido de la tortuga.
