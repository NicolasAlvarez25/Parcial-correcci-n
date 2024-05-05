# Parcial-correcci-n
#### Necesidad: Se necesita realizar un sistema que permita guardar la `categoría_de_carros`, se necesita almacenar `4` atributos , los `autos` necesitan guardar `6` atributos, los `Autos_persona` necesitan guardar `4` atributos, y las `personas` necesita guardar `6` atributos.


#### Requerimientos funcionales:

1. RF 1: En la Categoria_de_carros se necesita guardar:
    #### `id`
    #### `Nombre_categoría`
    #### `Descripción`
    #### `Cantidad_de_puertas`

2. RF 2: En los autos se requiere almacenar:
    #### `id`
    #### `marca`
    #### `garantía`
    #### `cilindraje`
    #### `id_categorías_de_carros`
    #### `descripción`
    - Ref: Se necesita tener información guardada en categoría_de_carros.

3. RF 3: En persona se va a almacenar:
    #### `id`
    #### `nombre`
    #### `apellido`
    #### `telefono`
    #### `dirección`
    #### `documento`

4. RF 4: En Autos_persona se necesita almacenar:
    #### `id`
    #### `id_autos`
    #### `id_persona`
    #### `Descripción`
    
    - Ref: Se requiere tener información guardada en autos
    - Ref: Se necesita tener información guardada en personas

    #### Diseñar Base de Datos
`Categorias_de_carros`

| id | Nombre_categoría  | Descripción | Cantidad_de_puertas|
|----|-------------------|---------------|-------------|
| 1  | Deportivo   |Alto rendimiento      | 2        |
| 2  | Sedán   |Automóvil familiar         |4         |
| 3  | SUV   | Vehículo versátil      |4         |
 - Se detallan la categoría del vehículo, descripción y cantidad de puertas del vehículo.

`Autos`

| id | marca         | garantia | cilindraje | id_categorias_de_carros | descripción|
|----|---------------|----------|------------|-------------------------|------------|
| 1  | Ford          | 3 año    |5000        |  1                      | Marca de automóviles estadounidense      |
| 2  | Chevrolet     | 4 años   |1000        |  2                      | Marca de automóviles estadounidense      |
| 3  | Audi          | 6 años   |4000        |  3                      | Marca de automóviles de lujo alemana      |
- Nuevamente se especifica la marca, garantía, cilindraje, su respectiva id y descripción.

`Persona`       

| id | nombre        | apellido | telefono | dirección   | documento|
|----|---------------|----------|----------|-------------|----------|
| 1  |    Nicolás       | Álvarez   |3251258   | cll 12 norte| 102354  |
| 2  |    Edgar     | Álvarez  |3875691   | cr 5 # 20    | 102487  |
| 3  |    Cristian       | Vélez   |321589   | cll 7 30 sur| 123605  |
- Se captura la información de la persona, datos personales.

`Autos_persona`

| id | id_autos | id_persona | descripción |
|----|----------|------------|-------------|
| 1  |  1       |   1        |ideal         |
| 2  |  2       |   2        |ideal         |
| 3  |  3       |   3        |ideal         |
- Se requiere conocer el id de los autos, persona, y una breve descripción.

Ver ![imagen](out/dsa/dsa.png)


> Script de la base de datos
```sql
    DROP DATABASE IF EXISTS Parcial-correci-n;

    CREATE DATABASE Parcial-correci-n;

    USE Parcial-correci-n;

    CREATE table categorias_de_carros (
        id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
        Nombre_categoría VARCHAR1(150) NOT NULL UNIQUE,
        Descripción VARCHAR(150) NOT NULL,
        Cantidad_de_puertas VARCHAR(150) NOT NULL
        
    ); 

    CREATE table autos (
        id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
        marca VARCHAR(150) NOT NULL,
        garantia DATE NOT NULL,
        cilindraje INT NOT NULL,
        FOREIGN KEY (id_categorias_de_carros) REFERENCES categorias_de_carros(id),
        descripciónVARCHAR(150) NOT NULL
    ); 

    CREATE table persona (
        id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
        nombre VARCHAR1(150) NOT NULL UNIQUE,
        apellido VARCHAR(150) NOT NULL,
        telefono INT NOT NULL,
        dirección VARCHAR(150) NOT NULL,
        documento INT NOT NULL
    ); 

    CREATE table Autos_persona  (
        id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
        FOREIGN KEY (id_autos) REFERENCES autos(id),
        FOREIGN KEY (id_persona) REFERENCES persona(id),
        descripción VARCHAR(150) NOT NULL
        
    ); 
```



[ver](https://trello.com/b/1M8bZ7fM/mi-tablero-de-trello)

