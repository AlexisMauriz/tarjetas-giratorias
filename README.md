A continuación, se presenta una explicación del código HTML proporcionado:

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Tarjetas Giratorias</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <div class="cards">
      <div class="flip-card">
        <div class="flip-card-inner">
          <div class="flip-card-front">
            <img
              src="assets/zyro-image.png"
              alt="Avatar"
              style="width: 300px; height: 300px"
            />
          </div>
          <div class="flip-card-back">
            <h1>Alexis Mauriz</h1>
            <p>Programador Junior</p>
            <p>Front End</p>
          </div>
        </div>
      </div>
      <!-- ... Se repite similar estructura para otras tarjetas ... -->
    </div>
  </body>
</html>
```

**Explicación del Código HTML:**

1. `<!DOCTYPE html>`: Esta declaración define el tipo de documento como HTML5.

2. `<html lang="es">`: El elemento `<html>` es la raíz de un documento HTML y define el idioma del documento como español ("es").

3. `<head>`: La sección `<head>` contiene información sobre el documento, como metadatos y enlaces a recursos externos.

   - `<meta charset="UTF-8" />`: Especifica la codificación de caracteres UTF-8 para admitir caracteres especiales en el texto.

   - `<meta http-equiv="X-UA-Compatible" content="IE=edge" />`: Este metaetiqueta se utiliza para definir la compatibilidad con Internet Explorer y solicita que utilice el último motor de renderizado disponible.

   - `<meta name="viewport" content="width=device-width, initial-scale=1.0" />`: Esta metaetiqueta configura la escala inicial y el ancho de la ventana gráfica para dispositivos móviles.

   - `<title>Tarjetas Giratorias</title>`: Establece el título de la página que se mostrará en la barra de título del navegador.

   - `<link rel="stylesheet" href="style.css" />`: Enlaza el archivo de hoja de estilo externo llamado "style.css" para aplicar estilos al documento.

4. `<body>`: La etiqueta `<body>` contiene el contenido visible de la página web.

   - `<div class="cards">`: Un contenedor `<div>` con la clase "cards" que alberga las tarjetas giratorias.

   - `<div class="flip-card">`: Cada tarjeta giratoria se define dentro de un contenedor con la clase "flip-card".

     - `<div class="flip-card-inner">`: Dentro de cada tarjeta giratoria, hay un contenedor con la clase "flip-card-inner" que permite la rotación de la tarjeta.

       - `<div class="flip-card-front">`: La parte frontal de la tarjeta con la clase "flip-card-front". Contiene una imagen de avatar.

       - `<div class="flip-card-back">`: La parte posterior de la tarjeta con la clase "flip-card-back". Contiene información sobre una persona, como nombre y detalles de perfil.

         - `<h1>Alexis Mauriz</h1>`: Un encabezado que muestra el nombre.

         - `<p>Programador Junior</p>`: Un párrafo que muestra el título o cargo.

         - `<p>Front End</p>`: Un párrafo que muestra detalles adicionales.

El código HTML proporcionado crea una estructura de tarjetas giratorias que pueden usarse para mostrar información sobre personas, como sus nombres, títulos y detalles adicionales. Estas tarjetas tienen una parte frontal visible inicialmente y pueden girar para mostrar información adicional en la parte posterior. Se utiliza CSS para aplicar estilos y dar efecto de giro a las tarjetas.
A continuación, se presenta una explicación del código CSS proporcionado:

```css
body {
  font-family: Arial, Helvetica, sans-serif;
  padding: 0;
  margin: 0;
  background-color: #005c97; /* Fallback para navegadores antiguos */
  background: -webkit-linear-gradient(
    to right,
    #363795,
    #005c97
  ); /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(
    to right,
    #363795,
    #005c97
  ); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}

.cards {
  display: flex;
}

.flip-card {
  background-color: transparent;
  width: 300px;
  height: 300px;
  border: 1px solid #f1f1f1;
  perspective: 1000px;
  cursor: pointer;
}

.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.8s;
  transform-style: preserve-3d;
}

.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

.flip-card-front,
.flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}

.flip-card-front {
  background-color: #bbb;
  color: black;
}

.flip-card-back {
  background-color: #0f9b0f;
  color: white;
  transform: rotateY(180deg);
}
```

**Explicación del Código CSS:**

1. `body`: Establece estilos para el elemento `<body>` de la página.

   - `font-family: Arial, Helvetica, sans-serif;`: Define la fuente de texto que se utilizará en el contenido de la página.

   - `padding: 0; margin: 0;`: Elimina los márgenes y el relleno predeterminados del elemento `<body>` para asegurarse de que no haya espacio adicional alrededor de la página.

   - `background-color`: Establece el color de fondo de la página en un degradado azul (#005c97) en navegadores modernos y un color sólido azul (#005c97) como respaldo para navegadores antiguos.

2. `.cards`: Define estilos para elementos con la clase "cards".

   - `display: flex;`: Configura el diseño de los elementos con la clase "cards" como un contenedor flexible, lo que permite que los elementos secundarios se distribuyan horizontalmente en una fila.

3. `.flip-card`: Establece estilos para elementos con la clase "flip-card", que representan tarjetas giratorias.

   - `background-color: transparent;`: Establece el fondo de las tarjetas como transparente.

   - `width: 300px; height: 300px;`: Define el ancho y la altura de cada tarjeta en 300 píxeles cuadrados.

   - `border: 1px solid #f1f1f1;`: Agrega un borde de 1 píxel sólido y gris claro alrededor de cada tarjeta.

   - `perspective: 1000px;`: Establece la perspectiva de las tarjetas, que se usa en combinación con transformaciones 3D.

   - `cursor: pointer;`: Cambia el cursor a una mano cuando el mouse pasa sobre las tarjetas, indicando que son interactivas.

4. `.flip-card-inner`: Define estilos para el contenido interno de las tarjetas giratorias.

   - `position: relative;`: Establece la posición como relativa para que los elementos internos puedan posicionarse en relación con este contenedor.

   - `width: 100%; height: 100%;`: Ocupa todo el espacio disponible dentro de la tarjeta.

   - `text-align: center;`: Centra el contenido horizontalmente.

   - `transition: transform 0.8s;`: Aplica una transición suave de 0.8 segundos cuando se realiza una transformación (rotación) en la tarjeta.

   - `transform-style: preserve-3d;`: Conserva el efecto 3D al realizar una rotación.

5. `.flip-card:hover .flip-card-inner`: Cuando el mouse pasa sobre una tarjeta, se aplica una rotación de 180 grados a `.flip-card-inner`, lo que hace que la tarjeta gire y revele su parte posterior.

6. `.flip-card-front, .flip-card-back`: Define estilos para las partes frontal y posterior de las tarjetas.

   - `position: absolute;`: Coloca las partes frontal y posterior en una posición absoluta dentro de `.flip-card-inner`.

   - `width: 100%; height: 100%;`: Ocupa todo el espacio disponible dentro de la tarjeta.

   - `-webkit-backface-visibility: hidden;` y `backface-visibility: hidden;`: Oculta la parte trasera de las tarjetas cuando se giran, evitando que el contenido de la parte trasera se muestre en la parte frontal.

7. `.flip-card-front`: Define estilos específicos para la parte frontal de las tarjetas.

   - `background-color: #bbb;`: Establece un fondo gris claro para la parte frontal.

   - `color: black;`: Establece el color del texto en negro.

8. `.flip-card-back`: Define estilos específicos para la parte posterior de las tarjetas.

   - `background-color: #0f9b0f;`: Establece un fondo verde oscuro para la parte posterior.

   - `color: white;`: Establece el color del texto en blanco.

   - `transform: rotateY(180deg);`: Inicialmente, la parte posterior de la tarjeta está girada 180 grados para que no sea visible hasta que se realice la rotación.

En resumen, este código CSS establece estilos para crear tarjetas giratorias con una parte frontal y una parte posterior, con efectos de transición suave al pasar el mouse sobre ellas. El diseño general utiliza colores y bordes para resaltar las tarjetas y hacer que sean interactivas y atractivas para los usuarios.
