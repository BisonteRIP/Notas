## SELECT y FROM
___

#### SELECT

La cláusula `SELECT` se utiliza para especificar las columnas que deseas recuperar de una tabla o conjunto de datos. Puedes seleccionar una o varias columnas, o incluso usar `*` para seleccionar todas las columnas.

##### Sintaxis Basica:
``` sql
    SELECT columna1, columna2, ...
    FROM nombre_tabla;
```

##### Ejemplos:
- **Selecioncar una columna:**
```sql
    SELECT nombre
    FROM empleados;
```
Esto devuelve todos los valores de la columna `nombre` de la tabla `empleados`.
- **Selecioncar varias columnas:**
```sql
    SELECT nombre, salario
    FROM empleados;
```
Esto devuelve los valores de las columnas `nombre` y `salario` de la tabla `empleados`.
- **Selecioncar todas las columnas:**
```sql
    SELECT *
    FROM empleados;
```
Esto devuelve todas las columnas de la tabla `empleados`.
________

#### FROM
La cláusula `FROM` se utiliza para especificar la tabla o tablas de las cuales deseas recuperar los datos. Es obligatoria cuando usas `SELECT`, ya que indica de dónde provienen los datos.
##### Sintaxis Basica:
``` sql
    SELECT columnas
    FROM nombre_tabla;
```
##### Ejemplos:
- **Selecioncar datos de una tabla:**
```sql
    SELECT nombre, edad
    FROM clientes;
```
Esto devuelve las columnas `nombre` y `edad` de la tabla `clientes`.
- **Seleccionar datos de varias tablas (usando uniones):**
```sql
    SELECT empleados.nombre, departamentos.nombre
    FROM empleados
    JOIN departamentos ON empleados.departamento_id = departamentos.id;
```
Esto devuelve los nombres de los empleados y los nombres de sus departamentos, combinando datos de dos tablas (`empleados` y `departamentos`).