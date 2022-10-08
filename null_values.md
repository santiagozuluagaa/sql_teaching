# Null Values


## Table for example

|id |name                 |sex         |
|---|---------------------|------------|
|1  | Carlos Ballesteros  |            |
|2  | Efraín Zapata       | M          |
|3  | Santiago Lopero     | M          |
|4  | Maria Urrutia       | F          |
|5  | Perrosky Lopez      |            |

```sql
DROP TABLE IF EXISTS estudiante;

CREATE TABLE  estudiante(
	id INT NOT NULL,
	nombre VARCHAR(30) NOT NULL,
	genero VARCHAR(5)
);

INSERT INTO 
    estudiante(id, nombre, genero)
VALUES
	(1, 'Carlos Ballesteros', NULL),
	(2, 'Efraín Zapata', 'M'),
	(3, 'Santiago Lopero', 'M'),
	(4, 'Maria Urrutia', 'F'),
	(5, 'Perrosky Lopez', NULL);
```

It is not possible to use operators like '=' or '<>'. 

## Querying Nulls

### NULL values

```sql
SELECT * FROM estudiante
WHERE genero IS NULL;
```

| id | nombre             | genero |
|---|---------------------|------------|
|  1 | Carlos Ballesteros | NULL   |
|  5 | Perrosky Lopez     | NULL   |

### Not NULL values

```sql
SELECT * FROM estudiante
WHERE genero IS NOT NULL;
```

| id | nombre          | genero |
|---|---------------------|------------|
|  2 | Efraín Zapata   | M      |
|  3 | Santiago Lopero | M      |
|  4 | Maria Urrutia   | F      |





