# HTML Semántico

- **`div` y `span`**: Estas etiquetas son genéricas y se utilizan para dividir el contenido. `span` agrupa contenido en línea, mientras que `div` agrupa contenido en bloque.

- **`aside`**: Se utiliza para contenido que está aparte o al lado del contenido principal.

- **`article`**: Representa un elemento independiente y autónomo con información propia. Si se extrae y se coloca en otro contexto, aún tiene sentido.

- **`header`**: No está limitado a un único `header` por página. Puede haber `header` dentro de `section`, `article` o `div`. Debe contener al menos un encabezado (`h1`...`h6`).

- **`section`**: Define secciones independientes genéricas de un documento. Pueden haber secciones dentro de otras secciones.

- **`main`**: Debe haber solo uno en todo el documento. Contiene el contenido principal que cambia en cada URL.

- **`a`**: Utilizado para enlaces. Puede abrir enlaces externos en una nueva pestaña (`target="_blank"`) y se recomienda agregar `rel="noreferrer"` por razones de seguridad.

- **`ol`**: Lista ordenada con opciones para cambiar la numeración y estilo.

- **`fieldset` y `legend`**: Utilizados para crear formularios con un marco y un título.

- **`datalist`**: Similar a `select`, pero para autocompletar campos de texto.

### Carga de imágenes en una página

Para cargar imágenes de manera eficiente, se puede usar el atributo `loading="lazy"`. Sin embargo, es importante evitar su uso en imágenes cerca del inicio de la página.

```html
<img loading="lazy" src="icon.png" title="Obito" alt="Sharingan">
```

### CSS


#### Font Family

Para aplicar una fuente importada a la página

```css
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
font-family: 'Poppins', sans-serif;
```
### Ejemplo de uso de RGBA en CSS para un fondo semitransparente

```css
/* Se define un color de fondo rojo con 50% de opacidad. */
background-color: rgba(255, 0, 0, 0.5); /* Rojo semitransparente */

/*
   Para un tono más oscuro de rojo, reducir el valor de rojo (el primer valor).
   Un tono rojo más claro, aumentar ese valor.
   La opacidad se ajusta para controlar la transparencia del color de fondo.
*/
background-color: rgba(150, 0, 0, 0.7); /* Rojo más oscuro y más transparente */
```

### Herencia en CSS

La herencia en CSS permite que los estilos de un elemento se apliquen a sus descendientes. Se pueden usar valores como `inherit`, `initial`, `unset`, y `revert` para controlar la herencia.

```css
.container {
  color: teal;
  font-size: 32px;
  border: 3px solid teal;   
}

.child {
  border: inherit;
  color: initial;
  font-size: initial;
}
```

### Pseudo Clases y Pseudo Elementos

Se utilizan para seleccionar estados especiales de elementos. Ejemplos incluyen `:hover`, `:active`, `:focus`, `:first-child`, y `:last-child`.

```css
li:first-child {
  color: purple;
}

li:last-child {
  color: orange;
}
```

## `Position: fixed;`

Este valor de la propiedad `position` ignora el `position: relative;`. El elemento se posiciona dentro de todo el viewport, es decir, dentro de la pantalla visible, y permanece fijo en las coordenadas que le indiquemos.

```css
section {
  position: relative;
}

.container {
  position: fixed;
  top: 0;
  right: 0;
}
```
## `Position: sticky;`

La propiedad `sticky` se refiere a algo pegajoso. Es similar a `position: fixed;`, pero `sticky` solo se mueve dentro del contenedor padre. Se recomienda que el contenedor padre tenga `position: relative;`.

```css
.container {
  position: sticky;
  top: 0;
  right: 0;
}
```

### Overflow y Text Overflow

- `overflow: visible`: Contenido no recortado, se dibuja fuera de la caja contenedora.
- `overflow: hidden`: Muestra solo lo que está dentro de la caja, recorta lo que está fuera.
- `overflow: scroll`: Agrega barras de desplazamiento vertical y horizontal.
- `text-overflow: ellipsis`: Muestra puntos suspensivos si el texto se desborda.

### Position y Z-Index

- `position: absolute`: Se posiciona con respecto al documento.
- `position: relative`: Crea un punto relativo para que los hijos lo utilicen como referencia.
- `position: fixed`: Se mueve con respecto al viewport.
- `position: sticky`: Se comporta como `fixed` pero dentro del contenedor padre.

`z-index` controla la superposición, donde un valor mayor tiene mayor prioridad.

# Especificidad en CSS

## Componentes de la especificidad

La especificidad se calcula utilizando cuatro componentes:

1. **Selectores de ID:** Cada ID en un selector tiene un valor de especificidad de 100.
2. **Selectores de clase, atributo y pseudo-clases:** Cada clase, atributo o pseudo-clase en un selector tiene un valor de especificidad de 10.
3. **Selectores de tipo y pseudo-elementos:** Cada tipo de elemento o pseudo-elemento en un selector tiene un valor de especificidad de 1.
4. **Selectores universales y combinadores:** Tienen un valor de especificidad de 0.

## Resolución de conflictos

Cuando dos reglas CSS entran en conflicto, la regla con la especificidad más alta se aplicará. Si dos reglas tienen la misma especificidad, se aplicará la regla que aparece más tarde en el archivo CSS.

## Ejemplos de especificidad

### Ejemplo 1:

```css
#id-selector {
  color: red;
}
```
### Ejemplo 2:
```css
.button {
  color: blue;
}
```

### Ejemplo 3:
```css
div {
  color: green;
}
```
