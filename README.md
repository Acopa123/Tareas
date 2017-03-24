- **Investigar Viewport**

Viewport es un atributo de la etiqueta meta, que se usa para indicar un tamano de ancho para los dispositivos movil.

```
 <meta name="viewport" content="user-scalable=no, width=device-width, initial-scale=1">
 ```

La anchura y la altura de viewport se refieren a las dimensiones fijas del viewport inicial. Lo habitual es definir únicamente la anchura con el valor device-width, medida que hace referencia a la anchura de la pantalla del dispositivo.

Con initial-scale=1 le indicamos que no se haga zoom sobre el documento cuando entremos en él.

Con user-scalable=no, el usuario no podrá pellizcar en la imagen  para hacer zoom. Esto nos podrá facilitar tener siempre la escala a como nosotros hayamos definido en la etiqueta META viewport, lo que puede simplificarnos la vida a la hora de definir cómo se debe ver una web.

Algunos atributos de viewport son:

| Atributo     | Descripcion     |
| :------------- | :------------- |
| width       | ancho del viewport       |
| height       | alto del viewport       |
| initial-scale       | zoom inicial       |
| minimum-scale       | nivel minimo para hacer "zoom out"       |
| maximum-scale       | nivel maximo para hacer "zoom in"       |
| user-scale       | establece si el usuario puede hacer zoom       |

- **Semantica HTML5**

Una buena semantica de html5 deve de llevar las etiquetas que corresponden y que este bien estructurado.

Estructura basica de HTL5:

| TAG's     | Descripcion     |
| :------------- | :------------- |
| ``` <!DOCTYPE html> ```       |  Indica que el documento esta escrito en HTML5      |
| ``` <html></html> ```       |  Dentro de esta etiqueta colocaremos toda las etiquetas que componen una pagina web      |
| ``` <head></head> ```      |  Dentro de esta etiqueta se coloca el titulo de la pagina, al igual que las etiquetas metas y link     |
| ``` <body></body> ```       |  Dentro de esta etiqueta colocaremos el contenido que llevara la pagina web (estructura semantica)      |

Semantica de HTML5:

| TAG's     | Descripcion     |
| :------------- | :------------- |
| ``` <header></header> ```       |    Representa un grupo de artículos introductorios o de navegación. Está destinado a contener por lo general la cabecera de la sección      |
| ``` <nav></nav> ```       |     Representa una sección de una página que enlaza a otras páginas o a otras partes dentro de la página.      |
| ``` <main></main> ```       |     Representa la sección principal de una página.      |
| ``` <article></article> ```       |     Representa un componente de una página que consiste en una composición autónoma en un documento, página, aplicación, o sitio web con la intención de que pueda ser reutilizado y repetido.      |
| ``` <aside></aside> ```       |     Representa una sección de la página que abarca un contenido relacionado con el contenido que lo rodea, por lo que se le puede considerar un contenido independiente.      |
| ``` <section></section> ```       |     Se utiliza para representar una sección "general" dentro de un documento o aplicación, como un capítulo de un libro.      |
| ``` <footer></footer> ```       |    Representa el pie de una sección, con información acerca de la página/sección que poco tiene que ver con el contenido de la página, como el autor, el copyright o el año.      |

Semantica estructurado:

```
<!DOCTYPE html>
<html>
  <head>

  </head>
  <body>
    <header>
      <nav>

      </nav>
    </header>
    <main>
      <section>

      </section>
      <aside>

      </aside>
    </main>
    <footer>

    </footer>
  </body>
</html>
```
- **FlexBox**

El objetivo de FlexBox es crear un modelo de caja o contenedor optimizado para los distintos dispositivos que usan los usuarios de una web.

Para activar FlexBox declaramos dentro del container

```
display: flex;
```
Esto define un “contenedor flexible” y convierte de forma automática a sus “hijos” directos en “elementos flexibles”.

¿Desea filas o columnas?

```
flex-direction: row; /*Indica que la caja se acomode en filas*/
flex-direction: column; /*Indica que la caja se acomode en columnas*/
```

¿Desea que estos artículos estén
Principio del eje principal?

```
justify-content: flex-start; /*Indica que la caja esten al inicio del eje principal*/
justify-content: flex-end; /*Indica que la caja esten al final del eje principal*/
justify-content: center; /*Indica que la caja esten centradas*/
```
Para que la caja se alinie de forma vertical en pantallas moviles usamos el elemento:

```
flex-wrap: wrap;
/*or*/
flex-wrap: wrap-reverse;
```

- **Sass version Sass**

Se caracteriza, al igual que Stylus y coffeescript para el lenguaje de programación Javascript, en no hacer uso de llaves ni punto y coma final, en busca de la simplicidad y eliminación de ruido.

```
body
background: #000
font-size: 62.5%
```

Variables

Permite reutilizar valores que podemos manejar desde un solo sitio de forma sencilla y centralizada.

```
$brand: #F98355;
body
color:$brand
```
Mixins

Algunas cosas en CSS son un poco tediosas para escribir, especialmente con CSS3 y los prefijos de muchos proveedores que existen. Un mixin te permite crear grupos de declaraciones CSS que deseas reutilizar en todo tu sitio. Usted puede incluso pasar en valores para hacer su mixin más flexible. Un buen uso de un mixin es para prefijos de proveedores. Aquí hay un ejemplo para border-radius.

```
=border-radius($radius)
  -webkit-border-radius: $radius
  -moz-border-radius:    $radius
  -ms-border-radius:     $radius
  border-radius:         $radius

.box
  +border-radius(10px)
```
Extend/Inheritance

Esta es una de las características más útiles de Sass. El uso de @extend le permite compartir un conjunto de propiedades CSS de un selector a otro. Ayuda a mantener su Sass muy seco. En nuestro ejemplo vamos a crear una simple serie de mensajes para errores, advertencias y éxitos.

```
.message
  border: 1px solid #ccc
  padding: 10px
  color: #333


.success
  @extend .message
  border-color: green


.error
  @extend .message
  border-color: red


.warning
  @extend .message
  border-color: yellow
```
Nesting

Sass nos permitirá anidar sus selectores CSS de una manera que sigue la misma jerarquía visual de su HTML. Tenga en cuenta que las reglas demasiado anidadas resultarán en un CSS excesivamente calificado que podría resultar difícil de mantener y generalmente se considera mala práctica.

```
nav
  ul
    margin: 0
    padding: 0
    list-style: none

  li
    display: inline-block

  a
    display: block
    padding: 6px 12px
    text-decoration: none
```
