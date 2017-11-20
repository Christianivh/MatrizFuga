Examen Semana 2 RMarkdown
================
Christian Vasquez
12/11/2018

Ejercicio 1:
============

Se pide crear un vector con los 10 primeros números naturales,y a continuación:

1.  Recuperar su sexto elemento
2.  Recuperar los elementos que hay entre el cuarto y el séptimo ambos inclusive.
3.  Recuperar los elementos entre el segundo y el noveno ambos inclusive de tres en tres.

``` r
x<-c(1:10)
```

Solución
--------

**Sexto elemento**

``` r
  x[6]
```

    ## [1] 6

**Elementos que hay entre el cuarto y el séptimo ambos inclusive**

``` r
  x[4:7]
```

    ## [1] 4 5 6 7

**Elementos entre el segundo y el noveno ambos inclusive de tres en tres**

``` r
  seq(x[2],x[9],3)
```

    ## [1] 2 5 8

Ejercicio 2:
============

Se pide crear una matriz 2\*3 cuyas filas son los seis primeros números impares consecutivos. A continuación, se pide:

1.  Anular el elemento (2,3).
2.  Transponer la matriz resultante.
3.  Añadir a la matriz resultante la matriz identidad de dimensión 3\*3 a su derecha.

Solución
--------

Agrego una función que ayude a la construcción de numero impares

``` r
  Num_Impares<- function(n)
        {
          return(seq(1,n*2,2))
        }
```

Creando matriz 2\*3 cuyas filas son los seis primeros números impares consecutivo

``` r
  x= matrix(Num_Impares(6),2,3)
  x
```

    ##      [,1] [,2] [,3]
    ## [1,]    1    5    9
    ## [2,]    3    7   11

**Anular el elemento (2,3)**

``` r
  x[2,3]<-NA
  x
```

    ##      [,1] [,2] [,3]
    ## [1,]    1    5    9
    ## [2,]    3    7   NA

**Transponer la matriz resultante**

``` r
  x<-t(x)
  x
```

    ##      [,1] [,2]
    ## [1,]    1    3
    ## [2,]    5    7
    ## [3,]    9   NA

**Añadir a la matriz resultante la matriz identidad de dimensión 3x3 a su derecha.**

``` r
  x<-cbind(x,diag(3))
  x
```

    ##      [,1] [,2] [,3] [,4] [,5]
    ## [1,]    1    3    1    0    0
    ## [2,]    5    7    0    1    0
    ## [3,]    9   NA    0    0    1

Ejercicio 3:
============

Considerar la secuencia de enteros del cero al seis. Calcular la secuencia que contenga sus cuadrados

Solución
--------

``` r
  r2<-c(0:6)
  r2^2
```

    ## [1]  0  1  4  9 16 25 36

Ejercicio 4:
============

Dadas las matrices:

      A=-c(-1,1)
      B=matrix(1:4,nrow=2)

¿Cómo se obtendría su producto matricial?

Solución
--------

``` r
  A=-c(-1,1)
  B=matrix(1:4,nrow=2)
```

Su producto matricial

``` r
  A%*%B
```

    ##      [,1] [,2]
    ## [1,]   -1   -1

Ejercicio 5:
============

Considerar la matriz `A=matrix(1:9,nrow=3)+diag(3)`. Se pide obtener su inversa.

Solución
--------

``` r
  A=matrix(1:9,nrow=3)+diag(3)
  solve(A)
```

    ##      [,1] [,2] [,3]
    ## [1,]   -6 -1.0    5
    ## [2,]   -2  0.5    1
    ## [3,]    3  0.0   -2

Ejercicio 6:
============

Dado el vector:

      x = 1:10

Cómo se puede obtener:

      ¿[1] 1 2 3 4 20 20 20 20 20 20 ?

Solución
--------

``` r
  x = 1:10
  replace(x,x[5:10],20)
```

    ##  [1]  1  2  3  4 20 20 20 20 20 20

Ejercicio 7:
============

Dados los siguientes datos sobre pesos y alturas:

      Personas={Pérez, González, Rodríguez,Alonso,López,Tello,Domínguez}
      Pesos={85,72,80,95,85,72,84}
      Alturas={1.81,1.70,1.75,1.90,1.83,1.75,1.81}

Se pide construir un dataframe con estos datos

Solución
--------

``` r
  Personas=c('Pérez', 'González', 'Rodríguez','Alonso', 'López', 'Tello', 'Domínguez')
  Pesos=c(85,72,80,95,85,72,84)
  Alturas=c(1.81,1.70,1.75,1.90,1.83,1.75,1.81)
```

Para construir un dataframe se usa el comando as.data.frame

``` r
  mdataframe <- as.data.frame(cbind(Personas,Pesos, Alturas))
  mdataframe
```

    ##    Personas Pesos Alturas
    ## 1     Pérez    85    1.81
    ## 2  González    72     1.7
    ## 3 Rodríguez    80    1.75
    ## 4    Alonso    95     1.9
    ## 5     López    85    1.83
    ## 6     Tello    72    1.75
    ## 7 Domínguez    84    1.81

Ejercicio 8:
============

Dado el siguiente vector de datos: `1,3,5,8,2,1,3,5,3,5`

Se pide construir un factor a partir de los datos, de manera que sus niveles sean `a,b,c,d,e`

Solución
--------

``` r
  vector<-c(1,3,5,8,2,1,3,5,3,5)
  vector
```

    ##  [1] 1 3 5 8 2 1 3 5 3 5

Se obtiene su factor, y a su vez se le asigna sus equivalencias

``` r
  fvector = factor(vector,labels=c('a','b','c','d','e'))
  fvector
```

    ##  [1] a c d e b a c d c d
    ## Levels: a b c d e

Ejercicio 9:
============

Se quiere almacenar los siguientes datos en una estructura: `"Coche",35,TRUE,5.67,"Rojo"` Elige una estructura de datos adecuada para almacenarlos. Mostrar el tercer elemento de la estructura generada

Solución
--------

``` r
  vector1<- c("Coche",35,TRUE,5.67,"Rojo")
  vector1[3]
```

    ## [1] "TRUE"

Ejercicio 10:
=============

Considerar las siguientes matrices

      M1=matrix(-11:-14,2,2)
      M2=matrix(8:11,2,2)
      M3=matrix(20:23,2,2)

Obtener la matriz M:

          [,1] [,2] [,3] [,4] [,5] [,6]
        [1,]  -11  -13    8   10   20   22
        [2,]  -12  -14    9   11   21   23

A continuación realizar el determinante de la matriz formadas por las columnas 3 y 4 de la matriZ M

Solución
--------

Creamos las 3 matrices y las unimos, con cbind

``` r
  M1=matrix(-11:-14,2,2)
  M2=matrix(8:11,2,2)
  M3=matrix(20:23,2,2)
  M=cbind(M1,M2,M3)
  M
```

    ##      [,1] [,2] [,3] [,4] [,5] [,6]
    ## [1,]  -11  -13    8   10   20   22
    ## [2,]  -12  -14    9   11   21   23

Calculamos el determinante

``` r
  det(M[,3:4])
```

    ## [1] -2

Fin del examén
