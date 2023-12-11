# Resumen de Curso de CSS Grid

## ¿Qué es CSS Grid Layout?

Css grid es una especificación de CSS para realizar layouts más dinámicos. Anteriormente sólo se podía usar tablas para realizar lo que ahora podemos hacer con Grid de manera mucho más sencilla. Nos permite dividir una página en áreas o regiones principales, por definir la relación en términos de tamaño, posición y capas construidas a partir de HTML.

![image](https://static.platzi.com/media/user_upload/image%28266%29-b7f95173-f330-4552-ad94-a04a8418afe8.jpg "image")

CSS Grid introdujo un sistema de grilla que es una cuadrícula con columnas (columns) y filas (rows), con ellas podemos ubicar elementos de manera más fácil.

Podemos crear, por ejemplo, un layout simple con el header, main y footer ya que cada bloque conforma un elemento de la grilla que se puede ubicar. Como los layouts pueden cambiar mucho, Grid nos ayuda a posicionar y reposicionar los elementos cuantas veces necesitemos.

## Conceptos basicos de CSS Grid

### Qué es contenedor

Es el elemento que se va a convertir en una grilla. Algo como una caja en la que vamos agregando elementos.

![image](https://static.platzi.com/media/articlases/Images/image%28268%29.png "image")

### Qué son items

Son los elementos que están dentro del contenedor. Estos elementos pueden ser de cualquier tipo como links, botones, imágenes, etc. Todos ellos se convertirán en grid items. Esto quieres decir que por defecto van a tener propiedades que los ayudan a trabajar muy bien con nuestro sistema de grilla.

![image](https://static.platzi.com/media/articlases/Images/image%28269%29.png "image")

### Qué son líneas

Son los elementos que limitan o dividen las filas o columnas de una grilla. Como vemos en el ejemplo, cuatro líneas dividen las tres columnas (columns), y se lee de izquierda a derecha. Tres líneas dividen las 2 filas (rows) y se enumeran de arriba hacia abajo.

![image](https://static.platzi.com/media/articlases/Images/image%28270%29.png "image")

### Qué es celda

Es la unidad mínima que nosotros podemos tener en una grilla. Está delimitada por 4 líneas y normalmente solo ocupa 1 fila y 1 columna.

![image](https://static.platzi.com/media/articlases/Images/image%28271%29.png "image")

### Qué es track

Es un grupo de celdas, que solo puede estar en una fila o en una misma columna.

![image](https://static.platzi.com/media/articlases/Images/image%28272%29.png "image")

### Qué es área

Es un grupo de celdas, estas pueden usar varias filas o varias columnas a la vez.

![image](https://static.platzi.com/media/articlases/Images/image%28273%29.png "image")

## Propiedades del contenedor

- **grid-template-columns**: indica cuantas columnas va a tener y de que ancho va a ser cada columna.
- **grid-template-rows**: indica cuantas filas va a tener y de que altura va a ser cada fila.

Ejemplo,para crear 3 columnas (cada uno de diferentes tamaño): **grid-template-columns: 100px 200px 300px;** Nota: Si en tu contenedor hay 4 o más items, **grid-template-columns** te creará automáticamente 1 nueva fila y comenzará a llenarla, y pondrá cada fila en 3 columnas Además, también podemos colocar ambos tipos de grid-template Ejemplo: **grid-template-columns: 100px 200px 300px; grid-template-rows: 150px 250px;**

Otra forma de colocar los tamaños de las filas y columnas, sería usar grid-auto Esta propiedad define el tamaño de cualquier fila o columna que se crea. Existe **grid-auto-rows**, **grid-auto-columns**, **grid-auto-flow**.

- **grid-auto-flow**: Modifica cómo se está llenando nuestra grilla.

Por defecto está el row, ya que cuando los elementos no caben en lo que hemos definido, lo que hace es crear mas filas nuevas.

- **grid-auto-flow: dense;** : Si hay un espacio vacío en la grilla, lo que va a hacer es poner los elementos allí, en vez de seguir poniéndolos en filas y columnas **grid-auto-flow: column;** :Crea nuevas columnas, en vez de nuevas filas.

## Propiedades de alineación

### align-content | justify-content

Especifica la alineación vertical (align-content) / horizontal (justify-content) de los elementos dentro de una flex-box o una cuadrícula.

```css
align-content: flex-start;
justify-content: flex-start;
```

#### Valores disponibles

- **flex-start**: Cada línea solo llenará el espacio que necesita. El conjunto de elementos se moverán hacia el inicio del eje vertical / horizontal del contenedor.

- **flex-end**: Cada línea solo llenará el espacio que necesita. El conjunto de elementos se moverán hacia el final del eje vertical / horizontal del contenedor.

- **center**:Cada línea solo llenará el espacio que necesita . El conjunto de elementos se moverán hacia el centro del eje vertical / horizontal del contenedor.

- **space-between**: Cada línea solo llenará el espacio que necesita. El espacio restante aparecerá entre las líneas.

- **space-around**: Cada línea solo llenará el espacio que necesita. El espacio restante se distribuirá equitativamente alrededor de las líneas.

- **space-evenly**:Cada línea solo llenará el espacio que necesita. El espacio restante se distribuirá equitativamente entre las líneas.

- **stretch**:Cada línea se estirará para llenar el espacio restante. Disponible únicamente para la alineación vertical.

### align-self | justify-self

Especifica la alineación vertical (align-self) / horizontal (justify-self) del contenido de un elemento independiente dentro una flex-box o una cuadrícula.

```css
align-self: center;
justify-self: center;
```

#### Valores disponibles

- **auto** - el objetivo utilizará el valor de la propiedad align-items.
- Admite todos los valores disponibles en las propiedades align-items & justify-items.

### place-content | place-items | place-self

Las 3 propiedades son un atajo que nos permite definir en una sola linea las propiedades align- y justify-.

```css
place-content: stretch space-between;
place-items: center start;
place-self: center start;
```

## Propiedades de ubicación

Para las columnas, las propiedades que nos van a ayudar son:

- **grid-column-start**: con esta propiedad nosotros vamos a decirle al elemento en que línea de columna debe comenzar.
- **grid-column-end**: con esta propiedad nosotros vamos a decirle al elemento hasta que línea de la columna va a llegar.
- **grid-column**: es una mezcla de grid-column-start y grid-column-end. Los valores que necesita son el valor inicial y el valor final, estos van separados de un “/” (diagonal).

Para las filas las propiedades son iguales, solo que vamos a trabajar en las filas:

- **grid-row-start**
- **grid-row-end**
- **grid-row**

Además de estas propiedades, tenemos:

- **grid-area**: con esta propiedad declaramos solo una vez donde va a comenzar tanto en columna como en fila y donde va a terminar tanto en columna como en fila.

![image](https://static.platzi.com/media/articlases/Images/image%28290%29.png "image")

## Funciones especiales

- **minmax**: ayuda a declarar el tamaño mínimo y máximo para el ancho y alto de una celda, sin depender del contenido que tengamos en ella.

- **repeat** : se usa cuando todas las columnas o filas tienen el mismo ancho y evitar repetir el tamaño de las columnas.

## Keywords especiales

- **fr** : Es una unidad de medida especial de css grid para darle ancho o alto a filas y columnas 1fr representa una fracción del total de columnas o filas.
- **min-content** : Ajusta el ancho de la celda lo mínimo posible sin romper su contenido.
- **max-content** : Ajusta el ancho de la celda lo máximo posible para mostrar su contenido.
- **auto-fill** : Agrega columnas “fantasma” que rellenan el espacio sobrante del contenedor.
- **auto-fit** : Ensancha las columnas para que ocupen todo el espacio del contenedor.
