### JOIN
___

En SQL, `JOIN` es una cláusula utilizada para combinar filas de dos o más tablas en funcion de una condición relacionada enrte ellas. Esto permite consultar datos de múltiples tablas como si fueran una sola, lo que es especialmente útil cuando la información está normalizada y distribuida en varias tablas.

Existen varios tipos de `JOIN`, cada uno con un comportamiento distinto en cuanto a cómo combina las filas.

#### INNER JOIN

Devuelve solo las filas que tienen coincidencias en ambas tablas.

##### Sintaxis INNER JOIN
La sintaxis general de un `JOIN` en sql es la siguiente:
```SQL
    SELECT columnas
    FROM tabla1
    INNER JOIN tabla2
    ON tabla1.columna = tabla2.columna;
```
#### LEFT JOIN

Devuelve todas las filas de la tabla izquierda y las coincidencias de las tablas derecha. Si no hay coincidencias, se devuelve `NULL` para las columnas de la tabla derecha.

##### Sintaxis LEFT JOIN
```SQL
    SELECT columnas
    FROM tabla1
    LEFT JOIN tabla2
    ON tabla1.columna = tabla2.columna;
```
#### RIGHT JOIN

Devuelve todas las filas de la tabla derecha y las coincidencias de la tabla izquierda. Si no hay coincidencias, se devuelve valores `NULL` para las columnas de la tabla izquierda.

##### Sintaxis RIGHT JOIN

```SQL
    SELECT columnas
    FROM tabla1
    RIGHT JOIN tabla2
    ON tabla1.columna = tabla2.columna;
```
#### FULL JOIN

Devuelve todas las filas cuando hay una coincidencia en cualquiera de las tablas. si no hay coincidencias, se devuelven valores `NULL` para las columnas de la tabla que no tienen coincidencias.

##### Sintaxis FULL JOIN


```SQL
    SELECT columnas
    FROM tabla1
    FULL JOIN tabla2
    ON tabla1.columna = tabla2.columna;
```

#### CROSS JOIN

Devuelve el producto cartesiano de las dos tablas, es decir, todas las combinaciones posibles de filas entre las dos tablas.

##### Sintaxis CROSS JOIN

```SQL
    SELECT columnas
    FROM tabla1
    FULL JOIN tabla2
    /* Devuelve las coincidencias entre la tabla1 y la tabla2*/
```