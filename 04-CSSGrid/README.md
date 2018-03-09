### Trascripción del guión:

Guion CSS Grid

---- PRESENTACION ----

Hola! Hoy voy a hablaros de CSS! Pero no de css cualquiera sino del que mola.
En concreto veremos CSS Grid, una forma increíble de crear layout en un navegador web de forma nativa.
Además usaremos las CSS Custom Properties, que dicho así quizás no os suene de nada pero se trata ni mas ni menos que de variables nativas en CSS.
Todo esto lo veremos levantando un mini-entorno de desarrollo basado en npm y usando ParcelJS como bundelizador y servidor web. Si no lo conoces todavía te recomiendo el vídeo anterior de este mismo canal en el que Miguel Angel Durán nos muestra en detalle cómo funciona. Pero antes vamos a ver un poco de historia sobre la forma de crear layout en CSS:

---- SLIDES ----

0 => Posicionar elementos en una página y que se visualicen de forma consistente en todos los navegadores es vital en cualquier desarrollo. Hemos usado hacks de todo tipo: 

1 => Empezamos usando Tablas a finales de los 90, 
2 => Luego usamos Floats
3 => El patrón Position relative/absolute, etc..
4 => Hasta que no llegó Flexbox que sí que se trataba de una propiedad pensada específicamente para posicionar elementos hemos ido haciendo lo que hemos podido en función del soporte que han ido dando los navegadores.

5 => Y hablando de soporte, a día de hoy prácticamente todos los navegadores soportan CSS-Grid. El cual nos ofrece una solución completa no sólo para posicionar elementos sino para crear un layout de página completo.. lo que siempre hemos querido tener vaya! Pero.. A que llamamos grid?

6 => Cuando hablamos de crear un grid nos referimos exactamente a crear una parrilla de contenedores distribuidos en filas y columnas en los cuales vamos a poder posicionar elementos en su interior.
Con CSS-Grid podemos especificar si queremos crear filas, columnas o una combinación de ambas.

7 => Por ejemplo: Si a un contenedor con 12 elementos en su interior, le añadimos la propiedad: grid-template-columns definimos de forma explícita el número de columnas que queremos que tenga nuestro grid. Por cada valor que añadimos a grid-template-columns nos creará una columna con el ancho especificado. Los elementos que sobren formarán filas de manera implícita siguiendo el flujo natural de la página de izquierda a derecha en nuestro caso.

8 => Si además también definimos de forma explícita las filas mediante la propiedad grid-template-rows, se crearán las que especifiquemos con los parámetros de altura indicados y de nuevo, el resto de elementos que puedan quedar fuera de esa declaración se irán posicionando a continuación de forma implícita siguiendo el flujo natural de la página.

9 => Ahora que ya hemos visto de que se trata a nivel conceptual vamos a ver todo esto con código! Recordad que podéis clonaros el repositorio que contiene este ejemplo y todos los que vamos haciendo en el canal.

---- SCREENCAST ----

=> A modo de repaso, os muestro la estructura de carpetas del proyecto:

- Tenemos un index.html que tiene un div con la clase grid-container y 12 elementos dentro todos con la clase grid-item. Además, en la cabecera cargamos un archivo javascript que si lo abrimos vemos que lo único que hace es importar los estilos css y enviar a consola un mensaje.

=> Para crear un contenedor CSS-Grid utilizaremos la propiedad display Grid. Al aplicarla, todos los elementos hijos contenidos dentro pasan a ser grid-elements, exactamente igual que sucede con Flexbox. Aunque si os fijáis, de momento no cambia nada ya que el resto de propiedades que definen las filas y las columnas todavía no están definidas.

=> Como comentábamos anteriormente en las slides, añadiendo la propiedad grid-template-columns definimos de forma explícita el número de columnas y el ancho que queremos que tenga cada una. Para ver mejor cómo se aplican estos cambios vamos a añadir a cada uno de los grid-items un poco de estilado como por ejemplo, un color de fondo, un outline, algo de padding y el texto alineado al centro.

=> Si os fijáis, para añadir los valores de background-color y outline, he utilizado la función var() pasándole un atributo. Esta función lo que hace es evaluar el contenido de esta CSS Custom Property y aplicarla a la propiedad. Como véis aquí arriba tenemos un import/settings que contiene la declaración de esas custom properties. 

No me voy a extender mucho más en explicarlas ya que dan para otro vídeo pero como os comentaba al principio, quedaros con la idea de que se tratan de variables CSS nativas.

=> Volviendo a nuestro ejemplo, vemos que gracias al estilado de los grid-items ahora vemos claramente cada uno de los contenedores que conforman nuestro grid. Hasta ahora hemos visto que añadiendo 4 valores en píxeles absolutos a la propiedad grid-template-columns las columnas se quedan fijas en anchura. Como esto no se ajusta demasiado a un ejemplo práctico real, vamos a ver como haríamos que alguna de ellas ocupase todo el espacio disponible. Para ello sólo hay que añadir el valor auto. Otra característica interesante es el valor grid-gap, que como su nombre indica, nos añade un espaciado entre cada uno de ellos.

=> Hablando de ejemplos prácticos reales, lo más probable es que utilicemos valores relativos en nuestro grid. Para ello podemos usar porcentajes, pero si lo hacemos es posible que provoquemos efectos indeseados ya que los paddings y espaciados también computan en el ancho total como podéis ver. De modo que para evitarlo os recomiendo utilizar la unidad fraction con su acrónimo fr. Esta unidad hace referencia a cómo han de repartirse el espacio disponible entre todos los grid-items. De modo que si indicamos que una columna tenga el dobre de fractions ocupará el doble de dicho espacio disponible como podemos ver en el inspector. Por último, tened en cuenta que si aplicamos las unidades fr a una única propiedad como por ejemplo grid-templare rows, no tendrá efecto alguno. Siempre es relativa a sus hermanos adyacentes, de modo que si queremos que la segunda fila sea el doble que la primera hemos de indicar los 2 valores a grid-template-rows.

=> Finalmente, antes de acabar esta introducción a CSS-Grid os mostraré una característica llamada span. Se trata de indicarle a un grid-item concreto que ha de extenderse y ocupar tantas filas o columnas como le indiquemos. Vamos a ver un ejemplo:

=> Si queremos que el grid-item que contiene el número 6 ocupe el espacio del 7 le podemos aplicar la propiedad grid-column: span 2. De esta forma ocupará el espacio de 2 columnas en lugar de quedarse en la suya propia. El último elemento con el valor 12 pasará a posicionarse en una nueva fila. Por último comentaros que span también podemos aplicarlo a la propiedad grid-row.


---- CIERRE ----

=> Con esto que hemos visto de CSS Grid ya podemos ver que combina potencia y facilidad de uso a partes iguales. Además, la mayoría de navegadores ya lo soportan de forma nativa o usando vendor prefixes en el caso de Internet Explorer. A si que, que os ha parecido? Creeis que ya es hora de usarlo en proyectos reales? Alguno de vosotros ya lo tiene aplicado en producción? Dejadnos vuestros comentarios y ya sabéis, si os ha gustado dadle al like, suscribiros al canal si todavía no lo habéis hecho y ayudadnos a difundirlo por twitter!
