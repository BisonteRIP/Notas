
#### WHERE

La cláusula `WHERE` se utiliza en SQL para filtrar registros de una tabla según una condición específica. Solo se devuelven las filas que cumplen con la condición especificada. Es una parte fundamental de las consultas SQL, ya que permite obtener datos precisos y relevantes.

##### Sintaxis básica:
```sql
    SELECT columnas
    FROM tabla
    WHERE condición;
```
____

#### Condicionales

| TIPO | Operador | Descripcion | Ejemplo |
|------|----------|-------------|---------|
|Comparacion|`=,!=,<,>,>=,<=`|Operadores numericos estandar|col_name **!=** 4|
|Rango|`BETWEEN...AND...`|Dentro de un rango (inclusive)|col_name **BETWEEN** 1.5 **AND** 10.5|
|Rango|`NOT BETWEEN...AND...`|Todo lo que no esta en el rango (inclusive)|col_name **BETWEEN** 1 **AND** 10|
|Lista de valores| `IN (...)`|Coincide con cualquier valor en la lista|col_name  **IN** (1,2,3)|
|Lista de valores| `NOT IN (...)`|No coincide con ningun valor de la lista|col_name **NOT IN** (1,2,3)|
|Texto|`LIKE`| Coincide con un patrón (usando `%` para cualquier cadena y `_` para un carácter)| col_name **LIKE** 'A%'|
|Texto|`NOT LIKE`| No coincide con un patrón|col_name **NOT LIKE** 'A%'|
|Texto|`%`|Se utiliza en cualquier parte de una cadena para hacer coincidir una secuencia de cero o más caracteres (solo con `LIKE` o `NOT LIKE`)|col_name **LIKE** "%AT%" (matches "AT", "ATTIC", "CAT" or even "BATS")|
|Texto|`_`|Se utiliza en cualquier parte de una cadena para que coincida con un solo carácter (solo con `LIKE`  o `NOT LIKE`)|col_name **LIKE** "AN_" (matches "AND", but not "AN")|
|Logicos|`AND`|Ambas condiciones deben ser verdaderas|**WHERE** salario **>** 3000 **AND** edad **<** 40|
|Logicos|`OR`|Al menos una condición debe ser verdadera|**WHERE** salario **>** 3000 **OR** edad **<** 40|
|Logicos|`NOT`|Niega una condición|**WHERE** **NOT** salario > 3000|
|Nulos|`IS NULL`|Es nulo|**WHERE** telefono **IS NULL**|
|Nulos|`IS NOT NULL`|No es nulo| **WHERE** telefono **IS NOT NULL**|

