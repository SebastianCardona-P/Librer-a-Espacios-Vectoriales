# Librería-Espacios-Vectoriales
---
por medio de un archivo en python se pretende mostrar una librería de operaciones dentro de un espacio vectorial complejo
Hecho por ***Sebastián Cardona Parra.***
---
***Para la ejecución de estos archivos debe instalar en su pc la librería numpy, pues en este proyecto se hace uso de ella*** 

El fin de esta libreria es estudiar un poco acerca de los espacios vectoriales y sus operaciones, además de implementarlos en un lenguaje de programación.

Dicha librería contiene 18 funciones los cuales son:
1. suma vectores:
  ``` python
  def sumvec(a, b):
      c=[]
      if len(a) == len(b):
          for i in range(len(a)):
             c.append(a[i]+b[i])
      else:
          c ="Error. vectores con tamaño diferente"
      return c
  ```
2. inverso de un vector:
  ``` python
  def invec(v):
    resp = []
    for k in range(len(v)):
        resp.append(-1*v[k])
    return resp
  ```
 (y otras funciones que por similitud no se mostrará en este lugar el código)
 
3. multiplicación escalar de un vector:

4. suma de matrices:

5. inverso de una matriz:

6. multiplicación por un escalar de una matriz:

7. traspuesta de una matriz:

8. conjugada de una matriz:

9. conjugada de una matrtiz:

10.producto matriz:
``` python
  fil_a = len(a) 
    col_a = len(a[0]) 
    fil_b = len(b) 
    col_b = len(b[0]) 
    if col_a == fil_b:
        matriz = []
        for k in range(col_b):
            fila = []
            for i in range(fil_a):
                suma = 0
                for j in range(col_a):
                    suma += a[k][j]*b[j][i]
                fila.append(suma)
            matriz.append(fila)
    else: 
        matriz = "Error, Tamaños erroneos"
    return matriz
  ```
11. acción de una matriz sobre un vector:
Básicamente es la multiplicación de una matriz por un vector

12. producto intenrno de vectores:

13. norma de un vector:

14. distancia de dos vectores:

15. valores y vectores propios de una matriz:

16. matriz unitaria:
define si una matriz es unitaria, es decir, UU* = U*U = I donde U es una matriz, U* es la matriz adjunta e I matri identidad

17. matriz hermitiana:
dice si una matriz es hermitiana, es decir A = A* donde A es una matriz y A* es la matriz adjunta

18. producto tensor:
un nuevo espacio vectorial que nace de otros dos espacios, cuyo algoritmo es
  ``` python
  def tensor_product(a,b):
    m = len(a)
    n = len(b)
    m_1 = len(a[0])
    n_1 = len(b[0])
    fil = m*n
    col = m_1*n_1
    result = [[0 for j in range(col)] for k in range(fil)]
    for j in range(fil):
        for k in range(col):
            result[j][k] = (a[j//n][k//n_1])*(b[j%n][k%n_1])
    return result
  ```
  
Además de este archivo, abrá otro archivo de pruebas que me rectifica si las funciones de la libreria funcionan adecuadamente.
por cada función abra otra función respectiva de prueba, se pondrá un ejemplo de una funcion:
  ``` python
  import unittest
  import libvecspaces as lvs


  class TestLibVecSpaces(unittest.TestCase):
	  def test_sumvec(self):
		  v = [3j, 4+5j, 6-9j,5]
		  w = [6j, 10-10j, 4+9j, 70j]
		  sumam = [9j, 14-5j, 10, 5+70j]
		  sumac = lvs.sumvec(v,w)
		  self.assertEqual(sumac, sumam)
  if __name__ == "__main__":
	unittest.main()
  ```
