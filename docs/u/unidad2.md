# Unidad 2

Antes de seguir deberías tener:

1. Uso básico de ordenadores, y uso pasivo de la Web (navegar y ver contenido).
1. Entorno básico de trabajo, leer [#Software Recomendado](/?id=software-recomendado).
1. Conocimiento básico de HTML y CSS. [_Repasar Uniodad 1_](/u/unidad1.md).

## Primer página web

Si bien en la [primer clase](/clases/clase1.md#clase-1) algo se vió, muy por arriba de la estructura básica y cómo una página debía llamar a los elementos que la componen, durante la [segunda clase](/clases/clase2.md#clase-2) se desarrolló con mayor profundidad lo que sería nuestro primer desarrollo web estático.

Se repasaron los conceptos de elementos `HTML` que ya habíamos visto; si aún no se sabe cuándo usar `<b>` o `<strong>`, recomiendo repasar el [Unidad 1](/u/unidad1.md#unidad-1). Y se ampliarán como veremos a continuación los conceptos con `CSS`.

?>A raíz de comprender mejor los ejemplos prácticos, el código que se practica en clase estará expuesto en una carpeta [`/www/` en GitHub](https://github.com/SidVal/dev.web/tree/master/www), y el comportamiento pueden verlo en [Fiddle](https://jsfiddle.net/Waldo/o31j84e1/) o bien en [Thimble](https://thimble.mozilla.org/es/user/walddo/1685329/); lee más sobre [Editores en Línea para practicar](https://github.com/SidVal/dev.web/wiki/Herramientas#editores-en-linea).

## CSS Introducción

Si bien en la documentación de clase hay mucho teórico, pueden ir completando los conocimientos con una lectura del sitio web de desarrolladores de Mozilla y su [introducción a CSS en español](https://developer.mozilla.org/es/docs/Learn/CSS/Introduction_to_CSS).

### Modelo de Cajas

En la documentación de clase se indica que todos los elementos HTML se interpretan por los navegadores web como cajas; así una página web es un grupo de cajas ordenadas siguiendo ciertas reglas. Entonces, cualquier elemento contenido en un documento web tiene la estructura de una _caja rectangular_ dentro del formato del documento, el tamaño y las capas que serán retocadas usando las propiedades CSS. Las propiedades importantes son: `margin`, `border`, `padding`, `width`, y `height`.

_Gráficamente_

![Propiedades del modelo de caja](https://mdn.mozillademos.org/files/13647/box-model-standard-small.png)

#### `width` y `height`

Las propiedades `width` y `height` establecen el **ancho** y **alto** de la caja de contenido, que es el área donde se muestra el contenido de la caja — este contenido comprende tanto el texto incluido en la caja como otras cajas representadas por elementos anidados.

Para un manejo más refinado del tamaño de la caja, se usan propiedades adicionales como: `min-width`, `max-width`, `min-height`, y `max-height`.

#### `padding`

El `padding` hace referencia al margen interior de la caja CSS — entre el límite exterior de la caja del contenido y el límite interior del borde. El tamaño de esta capa puede configurarse en sus cuatro lados a la vez con la propiedad abreviada `padding`, o cada lado por separado con las propiedades: `padding-top`, `padding-right`, `padding-bottom` y `padding-left`.

#### `border`

El borde de una caja CSS descansa entre el límite exterior del padding y el límite interior del margen. Por defecto tiene un tamaño de `0` — es decir, invisible — pero podemos cambiar su grosor, estilo y color para hacerlo visible. La propiedad abreviada de `border` permite establecer los cuatro lados a la vez, por ejemplo: `border: 1px solid black`. Pero también se puede dividir en varias propiedades extendidas para su uso en necesidades concretas de estilo:

* `border-top`, `border-right`, `border-bottom` y `border-left`: establecen el grosor, estilo y color de cada lado del borde.
* `border-width`, `border-style`, `border-color`: establecen únicamente el grosor, el estilo y el color por separado, pero para los cuatro lados del borde al mismo tiempo.
* Podemos también establecer cada propiedad por separado para cada lado individualmente, usando `border-top-width`, `border-top-style`, `border-top-color`, y así...

#### `margin`

El margen envuelve la caja CSS, y sostiene a otras cajas del diseño. Se comporta como `padding`; la propiedad abreviada es `margin` y las propiedades individuales son `margin-top`, `margin-right`, `margin-bottom`, y `margin-left`.

### Reglas para ordenar las cajas

Dijimos que una página web es un grupo de cajas ordenadas siguiendo ciertas reglas. Éstas reglas son establecidas por los estilos. Estilos que pueden ser definidos por los navegadores web (estilos por defecto), o bien los programadores de las páginas web. La combinación de las distintas reglas se llama modelo, o sistema de disposición. Y todas las reglas aplicadas juntas, es lo que llamamos _modelo de caja_.

El _Modelo de Caja Tradicional_ es el único modelo que se considera estándar, pero hay otros modelos que están en etapas experimentales.

#### Regla CSS

Hay cinco (5) términos básicos que debemos dominar para cuando nos referimos a Hoja de Estilos (CSS):

* Regla

Cada estilo es una regla, y la regla en sí misma está compuesta por una parte de _selectores_, el símbolo de apertura `{`, la _declaración_, y el símbolo de cierre `}`.

* Selector

Indica el elemento (o los elementos) HTML a los que se aplica la regla CSS.

* Declaración

Indica los estilos que se aplican a los elementos. Está compuesta por una o más _propiedades_ CSS.

* Propiedad

Indica la característica que se modifica en el elemento seleccionado por el _selector_. Por ejemplo, el tamaño de letra, el color, etcétera.

* Valor

Indica el nuevo valor de la característica seleccionada.

_Gráficamente_

![Regla CSS](../assets/img/regla-css.jpg)

### Archivo CSS

Un archivo CSS puede contener un número ilimitado de reglas CSS. Cada regla puede aplicar a la cantidad de selectores que se desee.

## Formas de insertar estilos

Hay básicamente tres formas:

1. Estilos en línea
1. Estilos embebidos
1. Estilos de archivos externos

### Estilos en línea

Cuando se trabaja con estilos en línea se puede cambiar el estilo de determinado elemento HTML. Si por ejemplo queremos que en un párrafo, la letra tenga de tamaño _20px_ (por decir un número cualquiera), podemos ir a ese párrafo, al elemento `<p>` y modificarlo de la siguiente manera:

`<p style="font-size:20px;">Esto sería un ejemplo de texto con tamaño de 20px</p>`

Ésta línea de estilo está "insertada" en el elemento HTML, modificando así su valor de estilo predeterminado que trae la página (y en caso de no traer, el navegador web interpreta que debería tener un tamaño "x").

?>[Practica tú mismo en este editor en línea](https://jsfiddle.net/Waldo/6oxxu5p0/). Dale con confianza, la mejor forma de entender CSS es practicando y viendo cómo queda el resultado a medida que practicas.

### Estilos embebidos

¿Qué ocurriría si tenemos mil párrafos y queremos que cada uno tenga letra de _20px_? ¿Te imaginas editando cada elemento `<p>` del código HTML para insertar a cada línea un estilo que modifique el tamaño de la letra al tamaño que necesitemos?

Para evitar ésta situación, se puede insertar estilos de forma embebida dentro del documento HTML, en la parte del `<head>` (fuera del `<body>`), así:

```html
<head>
<style>
    p {font-size:20px;}
    </style>
</head>
<body>
<p>Esto sería un ejemplo de texto que irá en 20px porque todos los elementos "p" tienen ahora ese tamaño.</p>
</body>
```

### Estilos de archivos externos

Si bien tener los estilos embebidos es la mejor forma de tener estilos en cada página, porque podemos personalizar y gestionar cada estilo directamente desde la página en sí, sin tener que insertar a cada elemento HTML el estilo, ¿qué pasaría si tendríamos 100 páginas HTML donde replicar todos los estilos?.

Para evitar tener que copiar y pegar en cada página los _estilos embebidos_, se usan los estilos de archivos externos. Es decir, tendremos todo el estilo en un archivo propiamente de "estilo", con extensión `.css` que podrá ser linkeado (o enlazado o mejor dicho, insertado) en cualquier página HTML que lo llame a través del elemento [`<link>`](https://www.w3schools.com/tags/tag_link.asp).

> Tener en cuenta que:
> * en HTML5 el elemento `<link>` no requiere cierre, pero si usamos XHTML sí necesita ser cerrado.
> * el elemento `<link>` solo contiene atributos, no debe contener texto de ningún tipo.
> * `rel` es atributo obligatorio.
> * debe ir en la sección `<head>` del documento HTML, pero puede haber muchos elementos `<link>` en dicha sección.

Entonces para insertar estilos de archivos externos debemos poner en la sección `<head>` la siguiente línea:
`<link rel="stylesheet" href="../css/estilos.css">`

En la unidad 1 vimos el elemento `<link>` cuando hablamos de las etiquetas html del "HEAD", que serviría para insertar nuestra página llamada "estilos.css" a nuestra primer página web. _Repasar unidad sobre el [link](/u/unidad1.md#link)_.

## Referencias

Comenzaremos con tres formas para referenciar elementos HTML desde reglas CSS:

* Referencia por palabra clave del elemento
* Referencia por el atributo id
* Referencia por el atributo class

### Referencia por palabra clave

Al utilizar la referencia por palabra clave del elemento HTML, cambiamos todos los elementos afectados en la página HTML, por ejemplo el que veníamos usando: `p {font-size:20px;}`. Lo que hará ésta referencia es que todos los elementos de párrafo (`<p>`) en un documento HTML pasen a tener tamaño 20px.

### Referencia por el atributo id

Como vimos en la unidad 1, el [atributo id](/u/unidad1.md/#id) debe ser utilizado para "identificar" cierto elemento HTML, y dicha identidad debe ser única dentro del documento. En CSS, para la regla a un ID, se identifica con un _hash_ (símbolo _#_).

```css
#principal {
  font-size: 30px;
  color: green;
  font-style: italic;
  text-decoration-color: red;
  text-decoration-line: underline;
  text-decoration-style: double;
}
```

`<p id="principal">Texto principal</p>`

?>[Hazlo tú mismo aquí](https://jsfiddle.net/Waldo/6oxxu5p0/2/).

### Referencia por el atributo class

También vimos el [atributo class](/u/unidad1.md#class) en la unidad 1, que servía para dar estilo ciertos elementos HTML que no eran únicos, y que se comportaban de forma similar (hablando de estilos). Por ejemplo, si tendríamos párrafos con texto secundario, podemos definir un class _secundario_ y darle ciertos estilos:

```css
.secundario {
  font-size: 15px;
  color: gray;
}
```

Un párrafo secundario de ejemplo:

```html
<p class="secundario">
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras dapibus est convallis erat ultricies commodo. Cras elementum volutpat eros id luctus. Nullam et turpis at nisl condimentum ultrices. Sed et ex tincidunt, dictum eros convallis, dictum elit. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas ut feugiat massa, vitae auctor velit. Aenean vel purus in velit egestas porta id nec elit. Cras eu diam vehicula metus volutpat elementum quis placerat libero. In hac habitasse platea dictumst. Etiam aliquet lorem pulvinar felis pharetra, vitae lobortis magna feugiat. Nam aliquet tortor a metus feugiat, in scelerisque libero congue. Sed at ante dictum, vestibulum ipsum sit amet, dictum felis. Aliquam nisi lacus, vehicula eget risus sit amet, eleifend viverra ipsum. Mauris id sodales lacus, eget faucibus nisi.</p>
```

?>[Hazlo tú mismo aquí](https://jsfiddle.net/Waldo/6oxxu5p0/3/).

También se podría crear el estilo solo para elementos `<p>`, y no para otros elementos que tengan la clase "secundario" (siguiendo nuestro ejemplo práctico).

Si al estilo lo cambiamos así:

```css
p.secundario {
  font-size: 15px;
  color: gray;
}
```

Aplicará a aquellos párrafos que tengan el `<p class="secundario">` pero si hay un `<div>` que tiene la misma clase, no tendrá el estilo.

?>[Hazlo tú mismo ahora](https://jsfiddle.net/Waldo/6oxxu5p0/4/).

## Nuevos métodos de referencia

* Selector Universal
* Referencia de cualquier atributo
* Referencia con pseudo clases
* Referencia con pseudo elementos

### Selector Universal

En la documentación del curso se menciona al selector universal únicamente cuando hablamos de la [_referencia a cualquier atributo_](#referencia-a-cualquier-atributo). Considero que debe ser tomado en cuenta como otro método de referencia, ya que se brinda estilos a través del selector universal, y debe ser tenido en cuenta para aprender CSS3.

El selector universal `*` es el mejor _comidín_. Permite seleccionar todos los elementos en una página. Como rara vez es útil aplicar un estilo a cada elemento de una página, a menudo se utiliza en combinación con otros selectores (consulte Combinators a continuación).

Ejemplo de selector universal:

```css
* {
  padding: 5px;
  border: 1px solid black;
  background: rgba(255,0,0,0.25)
}
```

!>Tenga cuidado al usar el selector universal. Como se aplica a todos los elementos, su uso en grandes páginas web puede tener un impacto perceptible en el rendimiento: las páginas web se muestran más despacio de lo esperado. No hay muchas instancias en las que use este selector universal.

### Referencia a cualquier atributo

!>Más conocidos como ["Selectores de Atributos"](https://www.w3schools.com/css/css_attribute_selectors.asp).

Los selectores de atributos son un tipo especial de selector que unirá elementos en función de sus atributos y valores de atributo. Su sintaxis genérica consta de corchetes `[ ]` que contienen un nombre de atributo seguido de una condición opcional para coincidir con el valor del atributo.

Los selectores de atributos se pueden dividir en dos categorías según la forma en que coincidan con los valores de los atributos:

* Selectores de atributos de presencia y valor
* Selectores de atributos de valor de subcadena

#### Selector de atributos de presencia y valor

Éstos selectores de atributos tratarán de hacer coincidir el valor exacto del atributo (o bien cualquier atributo mencionado):

* `[name]`: este selector actuará sobre todos los elementos que tengan el atributo `name` sin importar si tiene o no valor.
* `[name=val1]`: este selector actuará sobre todos los elementos que tengan el atributo `name` con el valor `val1`.
* `[name~=val2]`: este selector actuará sobre todos los elementos que tengan el atributo `name` pero únicamente sobre los que tengan el valor `val2` separado por un espacio.

?> [Ver ejemplo práctico](https://jsfiddle.net/Waldo/6oxxu5p0/8/)

!> Para uso más avanzado, si se quiere usar el atributo `data`, existen los "[data attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes)" que pueden ser manipulados con _JavaScript_.

#### Selector de atributo de valor de subcadena

Los selectores de atributos en esta clase también se conocen como "selectores similares a RegExp", ya que ofrecen una coincidencia flexible de forma similar a la expresión regular (pero, para que quede claro, estos selectores no son verdaderas expresiones regulares):

* `[attr|=val]`: este selector actuará sobre todos los elementos con el atributo `attr` donde el valor es exactamente `val` o comienza con `val-` (cuidado, el guión aquí no es un error, esto es para manejar los códigos de idioma).
* `[attr^=val]`: este selector actuará sobre todos los elementos con el atributo `attr` donde el valor comienza con `val`.
* `[attr$=val]`: este selector actuará sobre todos los elementos con el atributo `attr` donde el valor termina con `val`.
* `[attr*=val]`: este selector actuará sobre todos los elementos con el atributo `attr` donde el valor contiene la palabra `val` (es distinto a `[attr~=val]` donde el selector no trata los espacios como valores sino como parte del valor del atributo).

##### Prácticas de Selectores de Atributos

Haremos un ejemplo con listas, para entender mejor cómo trabajan todos los _selectores de atributos_ que hemos desarrollado hasta aquí.

<script async src="//jsfiddle.net/Waldo/n5qcos5z/embed/html,css,result/"></script>

### Referencia con pseudo clases

En la documentación de clase (aún no se ha dado en profundidad en alguna clase práctica) está muy compleja la explicación sobre pseudo-clases, así que en mi caso he realizado un resúmen siguiendo las explicaciones del [W3School.com sobre pseudo-classes](https://www.w3schools.com/css/css_pseudo_classes.asp).

```css
selector:pseudo-class {
    property:value;
}
```

<div align="right">_Nota: falta completar ésto con más detalles_</div>

### Referencia con pseudo elementos

No se explican los pseudo elementos en la documentación de clase, por lo que recomiendo leer [CSS Pseudo-elements](https://www.w3schools.com/css/css_pseudo_elements.asp).

```css
selector::pseudo-element {
    property:value;
}
```

<div align="right">_Nota: falta completar ésto con más detalles_</div>

## Nuevos selectores

* Selector `>`
* Selector `+`
* Selector `~`

<div align="right">_Nota: falta completar ésto con más detalles_</div>