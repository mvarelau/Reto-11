# Reto-11
## Punto 1
Desarrolle un programa que permita realizar la suma/resta de matrices. El programa debe validar las condiciones necesarias para ejecutar la operación.\
Se hace un recorrido por las filas y posteriormente cada elmento de las matrices, y los elementos en la misma posicion se suman y se añaden a una lista, y posteriormente esas lista se agregar a una lista que será la matriz final.
```python
def Suma(A,B):
  Matriz = []
  if len(A) != len(B) or len(A[0]) != len(B[0]):
    print("Las matrices no tienen la dimenciones requeridas para hacer la suma")
  else:
    for i in range(len(A)):
      fila = []
      for j in range(len(A[0])):
        suma_elemento = A[i][j] + B[i][j]
        fila.append(suma_elemento)
      Matriz.append(fila)

    return Matriz

def resta(A,B)
  Matriz = []
  if len(A) != len(B) or len(A[0]) != len(B[0]):
    print("Las matrices no tienen la dimenciones requeridas para hacer la resta")
  else:
    for i in range(len(A)):
      fila = []
      for j in range(len(A[0])):
        suma_elemento = A[i][j] - B[i][j]
        fila.append(suma_elemento)
      Matriz.append(fila)

    return Matriz



A=[[0,1],[2,3]]
B=[[4,5],[6,7]]
print(str(Suma(A,B)))
print(resta(A,B))
    
```
## Punto 2
Desarrolle un programa que permita realizar el producto de matrices. El programa debe validar las condiciones necesarias para ejecutar la operación. \
Fue un poco complica pensar en como manejaria la indexación de los elementos ya que la muktiplicación no se hace de manera lenial , pero despues descubrí que era usando iteraciones tanto por las filas como por las columnas, e ir ubicando los elementos en una fila.
```python




def cantidad_columnas(Matriz): #Evalua cantidad de comunas
  for i in Matriz:
    columnas=len(i)
    return columnas

def multiplicacion(A,B): 
  col_B= cantidad_columnas(B)
  col_A=cantidad_columnas(A)
  Matriz=[]
  if len(A)!= len(B[0]) or len(A[0])!= len(B):
    print("Las matrices no tienen la dimenciones requeridas para hacer la multiplicación")
  else:
    for i in range(len(A)):
      fila = []
      for j in range(col_B):
          valor = sum(A[i][k] * B[k][j] for k in range(col_A))
          fila.append(valor)
      Matriz.append(fila)
    return Matriz  

A=[[0,1],[2,3]]
B=[[4,5],[6,7]]
print(str(multiplicacion(A,B)))
```
## Punto 3
Desarrolle un programa que permita obtener la matriz transpuesta de una matriz ingresada. El programa debe validar las condiciones necesarias para ejecutar la operación.\
Hice una función para poder saber la cantidad de columnas de las matrices, y posteriormente en sun siclo while que va iterando en las posicones de la columna empecé aagregar los elementos a una matriz nueva en la posición requerida.
```python
def cantidad_columnas(Matriz):
  for i in Matriz:
    columnas=len(i)
    return columnas

def matriz_transpuesta(Matriz):
  columnas=cantidad_columnas(Matriz)
  num_columna=0
  while num_columna <= columnas-1:
    Columna=[]
    Matriz_t=[]
    for fila in Matriz:
      Columna.append(fila[num_columna])
    Matriz_t.append(Columna)
    num_columna+=1
    return Matriz_t

if __name__ =="__main__":
  A=[[2,4,6],[3,6,8],[8,1,2],[1,2,3]]
  transpuesta=matriz_transpuesta(A)
  print(transpuesta)

```
## Punto 4
Desarrollar un programa que sume los elementos de una columna dada de una matriz.
```python
def suma_columna(Matriz):
  num_columna=int(input("Ingrese la columna que dessea sumar: "))
  Columna=[]
  for fila in Matriz:
    Columna.append(fila[num_columna])
    sum=0
    for num in Columna:
      sum+=num
  print(f"La suma de los elementos de la fila en posisción {num_columna} es: {sum}")

if __name__ =="__main__":
  A = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
  suma_columna(A)
```

## Punto 5
Desarrollar un programa que sume los elementos de una fila dada de una matriz.
```python
def suma_fila(Matriz):
  num_fila=int(input("Ingrese la fila que desea sumar: "))
  Fila=Matriz[num_fila]
  sum=0
  for x in Fila:
    sum+=x
  print(f"La suma de los elementos de la fila en posisción {num_fila} es: {sum}")

if __name__ =="__main__":
  A = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
  suma_fila(A)
```






