Practica: Metodos Iterativos (Jacobi y Gauss-Seidel) en Java


-1. Descripcion del Proyecto
El proyecto implementa una arquitectura modular de tres componentes en Java para resolver sistemas de ecuaciones lineales mediante los metodos iterativos de Jacobi y Gauss-Seidel.
Sistema de Ecuaciones
El sistema de ecuaciones lineales evaluado corresponde a:

  5x +  y +  z = 7
  
   x + 2y + 5z = 8
   
   x + 4y + z = 6

Parametros de inicio:
* Vector de aproximacion inicial: X^(0) = [0, 0, 0]^T
* Tolerancia de error: epsilon = 0.0001


-2. Estructura Modular del Codigo
El codigo fuente esta organizado dentro del paquete "ecuaciones_lineales" respetando la separacion de responsabilidades:

1. Modulo 1 ("Defmatrix"): Clase encargada de almacenar y proveer la matriz de coeficientes A, el vector independiente b, el vector de aproximacion inicial X^(0) y la tolerancia de error.
2. Modulo 2 ("MetodosIterativos"): Clase que contiene la logica de calculo para los metodos de Jacobi (empleando vector auxiliar) y Gauss-Seidel (con actualizacion inmediata de variables).
3. Modulo 3 (Clases Principales de Ejecucion):
   * "ecuaciones_lineales.jacobi.MainJacob": Ejecuta el algoritmo de Jacobi e imprime la solucion aproximada y el numero de iteraciones.
   * "ecuaciones_lineales.gauss_seidel.MainGaussSeidel": Ejecuta el algoritmo de Gauss-Seidel e imprime la solucion aproximada y el numero de iteraciones.


-3. Instrucciones de Compilacion y Ejecucion

Pasos de Compilacion y Ejecucion via Terminal

1. Posicionarse en la carpeta raiz del proyecto (donde se ubica el directorio "ecuaciones_lineales").

2. Compilar los modulos del proyecto:
   javac ecuaciones_lineales/Defmatrix.java ecuaciones_lineales/MetodosIterativos.java ecuaciones_lineales/jacobi/MainJacobi.java ecuaciones_lineales/gauss_seidel/MainGaussSeidel.java

3. Ejecutar el Método de Jacobi:
   java ecuaciones_lineales.jacobi.MainJacobi

4. Ejecutar el Método de Gauss-Seidel:
   java ecuaciones_lineales.gauss_seidel.MainGaussSeidel

---

## 4. Comparativa Tecnica Breve
* Método de Jacobi: Utiliza los valores de la iteración previa para calcular simultáneamente todas las componentes del nuevo vector, requiriendo un número mayor de iteraciones para cumplir con la tolerancia establecida.
* Método de Gauss-Seidel: Emplea de manera inmediata las variables recién calculadas dentro de la misma iteración, reduciendo de forma significativa el número de iteraciones requeridas para converger.
