# 00 - El entorno de desarrollo integrado Arduino (IDE)

[img01]: ./../imatges/ard/ard_00_01.png "IDE Arduino"
[img02]: ./../imatges/ard/ard_00_02.png "Barra de herramientas"
[img03]: ./../imatges/ard/ard_00_03.png "Barra de menú"
[img04]: ./../imatges/ard/ard_00_04.png "Menú Archivo"
[img05]: ./../imatges/ard/ard_00_05.png "Menú Editar"
[img06]: ./../imatges/ard/ard_00_06.png "Menú Boceto"
[img07]: ./../imatges/ard/ard_00_07.png "Menú Herramientas"

Vamos a presentar el entorno de desarrollo integrado Arduino (IDE, nombre generado por su sigla en inglés). Es el software que nos permite programar las placas Arduino y hay que conocerlo para sacar todo el provecho de su potencia y características.

El entorno de desarrollo integrado Arduino (IDE) contiene:

1. barra de menú:
   - archivo
   - editar
   - boceto
   - herramientas
   - ayuda
2. barra de herramientas:
   - verificar
   - subir
   - debug
   - tipo placa
   - plotter serie
   - monitor serie
3. editor de texto
4. barra lateral izquierda:
   - sketchbook
   - gestor de placas
   - getor de bibliotecas
   - depurar
   - buscar

Se conecta a las placas Arduino para cargar programas y comunicarse con ellas.

![IDE Arduino][img01]

## Escribir bocetos (sketch)

Los programas escritos con el software Arduino (IDE) se llaman bocetos o "sketches". Estos bocetos se escriben en el editor de texto y se guardan con la extensión de archivo **.ino**. El editor tiene funciones para copiar/pegar y para buscar/sustituir texto.

El área de mensajes proporciona comentarios mientras se guarda y se exporta y también muestra errores. La consola muestra la salida de texto del software Arduino (IDE), incluyendo mensajes de error completos y otra información.

En el extremo inferior derecho de la ventana se muestra la placa configurada y el puerto serie.

Los botones de la barra de herramientas te permiten verificar y subir programas, crear, abrir y guardar bocetos y abrir el monitor serie.

### Los botones de la barra de herramientas

![Barra de herramientas][img02]

- **Verificar**. Comprueba el código por si hay errores antes de compilarlo.
- **Cargar**. Compila el código y lo sube a la placa configurada.
- **Debug**. Inicia el depurador.
- **Tipo de placa**. Selecciona el tipo de placa.
- **Plotter serie**. Abre el plotter serie.
- **Monitor serie**. Abre el monitor serie.

### Los menús

![Barra de menú][img03]

Se encuentran órdenes adicionales en los cinco menús: **Archivo, Editar, Boceto (Sketch), Herramientas, Ayuda**. Los menús son sensibles al contexto, lo que significa que solo hay disponibles los elementos relevantes para el trabajo que se está realizando actualmente.

### Archivo

![Menú Archivo][img04]

- **Nuevo.** Abre una nueva ventana del editor, con la estructura mínima de un boceto ya instalada.
- **Nuevo boceto en la nube.** Igual que el anterior pero en la nube.
- **Abrir.** Permite cargar un archivo de boceto navegando por las unidades y carpetas del ordenador.
- **Aberto recientemente.** Ofrece una lista breve de los bocetos más recientes, listos para abrirse.
- **Sketchbook.** Muestra los bocetos actuales dentro de la estructura del Sketchbook; al hacer clic en cualquier nombre se abrirá el boceto correspondiente en una nueva ventana del editor.
- **Ejemplos.** Cualquier ejemplo proporcionado por el software Arduino (IDE) o la biblioteca aparece en este elemento del menú. Todos los ejemplos se estructuran en un árbol que permite un fácil acceso por tema o biblioteca.
- **Cerrar.** Cierra la ventana del software Arduino desde la que se hace clic.
- **Guardar.** Guarda el boceto con el nombre actual. Si el archivo no se ha nombrado antes, se proporcionará un nombre en la ventana "Nombra y guarda...".
- **Guardar como...** Permite guardar el boceto actual con un nombre diferente.
- **Preferencias.** Abre la ventana Preferencias, donde se pueden personalizar algunos parámetros del IDE, como el idioma de la interfaz IDE.
- **Avanzado.** Abre la ventana Avanzado, donde se pueden ejecutar comandos avanzados.
- **Salir.** Cierra todas las ventanas IDE. Los mismos bocetos abiertos cuando se eligió _Salir_ se volverán a abrir automáticamente la próxima vez que inicies el IDE.

### Editar

![Menú Editar][img05]

- **Deshacer/Rehacer.** Retrocede uno o más pasos que has hecho mientras editas; cuando vuelves atrás, puedes avanzar con Rehacer.
- **Cortar.** Elimina el texto seleccionado del editor y lo coloca en el portapapeles.
- **Copiar.** Duplica el texto seleccionado en el editor y lo coloca en el portapapeles.
- **Copiar al foro (Markdown).** Copia el código de tu boceto al portapapeles en un formato adecuado para publicarlo en el foro, con color de sintaxis.
- **Pegar.** Pone el contenido del portapapeles en la posición del cursor, en el editor.
- **Seleccionar todo.** Selecciona y resalta todo el contenido del editor.
- **Ir a la línea...** Solicita y posiciona el cursor en la línea indicada.
- **Comentar o descomentar.** Pone o suprime el marcador de comentarios **//** al principio de cada línea seleccionada.
- **Aumentar/Disminuir sangría.** Añade o resta un espacio al principio de cada línea seleccionada, moviendo el texto un espacio a la derecha o eliminando un espacio al principio.
- **Autoformato.** Formatea el código para que sea más legible.
- **Reemplazar.** Busca y reemplaza texto en el sketch.
- **Incrementar/Reducir tamaño de fuente.** Hace más grande/pequeña la letra del sketch.
- **Buscar.** Abre la ventana _Buscar y reemplazar_ donde puedes especificar texto para buscar dentro del sketch actual según varias opciones.
- **Buscar siguiente.** Destaca la siguiente ocurrencia (si hay) de la cadena especificada como elemento de búsqueda en la ventana _Buscar_, en relación con la posición del cursor.

### Boceto

![Menú Boceto][img06]

- **Verificar/Compilar.** Comprueba tu boceto buscando errores al compilarlo; informará del uso de memoria para el código y las variables en el área de la consola.
- **Cargar.** Compila y carga el archivo binario a la placa configurada a través del puerto configurado.
- **Configura y cargar.** Configura la placa y carga el archivo binario a la placa configurada a través del puerto configurado.
- **Cargar usando el programador.** Graba el programa en la placa usando un programador externo, saltándose el bootloader.
- **Exportar binario compilado.** Guarda un archivo **.hex** que se puede conservar como archivo o enviarlo a la placa mediante otras herramientas.
- **Optimizar para depuración.** Optimiza el código para que sea más fácil de depurar.
- **Mostrar la carpeta del Sketch.** Abre la carpeta de bocetos actual.
- **Incluir biblioteca.** Añade una biblioteca a tu boceto insertando declaraciones _\#include_ al principio del código. Además, desde este elemento de menú puedes acceder al gestor de bibliotecas e importar bibliotecas nuevas desde archivos **.zip.**
- **Añadir fichero \...** Añade un archivo fuente al boceto (se copiará desde su ubicación actual). El archivo nuevo aparece en una nueva pestaña en la ventana de boceto. Los archivos se pueden borrar del boceto mediante el menú de pestañas accesible haciendo clic en el icono de triángulo pequeño que hay debajo del monitor de serie al costado derecho de la barra de herramientas.

### Herramientas

![Menú Herramientas][img07]

- **Auto Formato.** Esto formatea muy bien tu código: es decir, sangrarlo de manera que la apertura y el cierre de las llaves se alineen y que las declaraciones dentro de las llaves queden más recorridas.
- **Archivo de programa.** Archiva una copia del boceto actual en formato .**zip**. El archivo se coloca en el mismo directorio que el boceto.
- **Gestionar bibliotecas.** Abre el gestor de bibliotecas.
- **Monitor serie.** Abre la ventana del monitor serie e inicia el intercambio de datos con cualquier placa conectada al puerto seleccionado actualmente. Normalmente, se reinicia la placa, si la placa admite _Reinicio por apertura del puerto serie._
- **Plotter serie.** Aplicación que nos permite dibujar gráficas.
- **Firmware Updater.** Actualiza el firmware de la placa.
- **Cargar certificados raíz SSL.** Carga los certificados raíz SSL.
- **Placa:** Selecciona el tipo de placa que usas.
- **Puerto.** Este menú contiene todos los dispositivos en serie (reales o virtuales) de tu equipo. Se actualizará automáticamente cada vez que abras el menú de herramientas.
- **Reload Board Data.** Recarga los datos de la placa.
- **Obtener información de la placa.** Da información de la placa conectada.
- **Programador**. Para seleccionar un programador de placa cuando se programa una placa o un chip y no se utiliza la conexión serie USB integrada. Normalmente no necesitarás esto.
- **Grabar el Bootloader**. Los elementos de este menú te permiten grabar un cargador de arranque en el microcontrolador de una placa Arduino. Esto no es necesario para el uso normal de una placa Arduino o Genuino, pero es útil si adquieres un microcontrolador ATmega nuevo (que normalmente no incluye un cargador de arranque). Asegúrate de que has seleccionado la placa correcta en el menú Placa antes de grabar el cargador de arranque en la placa de destino. Esta orden también establece los fusibles adecuados.

### Ayuda

Aquí encontrarás fácil acceso a varios documentos que incluye el
software Arduino (IDE). Tienes acceso a Introducción, Referencia, una
guía del IDE y otros documentos localmente, sin conexión a Internet.
Los documentos son una copia local de los documentos en línea y pueden
enlazar a nuestro sitio web en línea.

**Buscar en la referencia.** Esta es la única función interactiva del
menú Ayuda: selecciona directamente la página pertinente a la copia local
de la referencia para la función o la orden que hay bajo el cursor.

## Ver también

- [Inicio](../README.md)
