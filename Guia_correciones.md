# Cómo corregir tu transcripción en GitHub

## Antes de empezar

Vas a corregir tus archivos **dentro del mismo Pull Request (PR) que ya subiste**, desde el navegador, sin instalar nada.

**La regla de oro:** nunca crees un PR nuevo. Cada vez que guardes, elige **"Commit directly to the `tu-rama` branch"**. Si eliges "Create a new branch", GitHub crea un PR repetido y tu corrección no llega al PR que se está revisando.

Necesitas:

- Tu cuenta de GitHub, la misma con la que subiste tus archivos.
- El Excel de errores, que tiene una fila por error. Filtra la columna Estudiante con tu usuario de GitHub.
- El video de YouTube de cada archivo, para escuchar cuando haga falta. El nombre del archivo es el código del video: `2rnU6oKHzXw.txt` es `youtube.com/watch?v=2rnU6oKHzXw`.

## Paso 1. Encuentra tu PR y tus errores

1. Entra a [github.com/Laboratorio-de-HD/CAR/pulls](https://github.com/Laboratorio-de-HD/CAR/pulls) con tu cuenta.
2. Haz clic en **Author** y elige tu usuario. Verás solo tus PRs.
3. Abre tu PR. Si tienes varios abiertos, la columna PR del Excel dice a cuál pertenece cada archivo.
4. Abre el Excel de errores, hoja **Errores**, y filtra la columna **Estudiante** con tu usuario. Cada fila es un error: el archivo, la línea (enlace a GitHub), el momento del video (enlace a YouTube) y qué hacer.

Si un PR tuyo dice **Closed** y el comentario dice que es repetido, no hagas nada con él. Trabaja solo en el PR que sigue abierto.

## Paso 2. Identifica tu rama

Debajo del título del PR hay una línea como esta:

> **tu-usuario** wants to merge 1 commit into `main` from `tu-usuario-patch-2`

El nombre que va después de **from** es tu rama (en el ejemplo, `tu-usuario-patch-2`). Anótalo o cópialo: lo vas a necesitar en el paso 5.

## Paso 3. Abre el archivo para editarlo

1. En tu PR, entra a la pestaña **Files changed**.
2. Busca el archivo que vas a corregir, por ejemplo `data/transcripciones/2rnU6oKHzXw.txt`.
3. A la derecha del nombre del archivo, haz clic en el menú **⋯** y elige **Edit file**.
4. Se abre el editor de GitHub con los números de línea a la izquierda. El enlace de la columna Línea del Excel te lleva directo a cada error.

Para encontrar un texto dentro del archivo, haz clic dentro del editor y usa **Ctrl + F** (Windows) o **Cmd + F** (Mac).

## Paso 4. Corrige

Corrige lo que indica cada fila del Excel y lo que encuentres del mismo tipo. Después marca la fila en la columna Estado: Corregido, No es error o Tengo una duda. Al editar:

- **Corrige dentro de la línea.** No muevas texto de una línea a otra: cada línea está amarrada a su tiempo en el video. Tampoco unas líneas en párrafos ni partas una línea en varias.
- **No cambies los tiempos `[mm:ss]`**, salvo que el error sea justamente de tiempos.
- **Cada línea empieza con su tiempo.** Sin líneas sueltas, sin títulos ni viñetas.
- **No vuelvas a pasar el archivo por un chatbot para corregirlo.** Así se originaron las marcas `[cite: N]` y algunos textos resumidos que ya no dicen lo que se dijo en el video. Corrige a mano.

La sección [Cómo corregir cada tipo de error](#cómo-corregir-cada-tipo-de-error), más abajo, tiene ejemplos de antes y después.

## Paso 5. Guarda en tu misma rama

1. Arriba a la derecha, haz clic en **Commit changes…**.
2. En **Commit message**, escribe qué corregiste. Ejemplo: `Corrige hablantes en 2rnU6oKHzXw`.
3. Revisa la opción que aparece marcada abajo. Debe ser:
   - ✅ **Commit directly to the `tu-rama` branch**
   - ❌ No: *Create a new branch for this commit and start a pull request*
4. Haz clic en **Commit changes**.
5. Repite los pasos 3 a 5 con cada archivo.

**Si tienes que cambiar mucho texto**, puedes editar el archivo en tu computadora y volver a subirlo a la misma rama:

1. En el editor de GitHub, selecciona todo (Ctrl/Cmd + A), copia y pega en un editor de **texto plano**: Bloc de notas en Windows, o VS Code. No uses Word ni Pages: agregan formato invisible.
2. Corrige y guarda con el **mismo nombre** (`2rnU6oKHzXw.txt`), en formato UTF-8.
3. Vuelve a la página del repositorio. En el selector de ramas (dice `main`), elige **tu rama**.
4. Entra a `data/transcripciones`, haz clic en **Add file → Upload files** y arrastra el archivo. Como se llama igual, reemplaza al anterior.
5. Al guardar, elige otra vez **Commit directly to the `tu-rama` branch**.

## Paso 6. Revisa el chequeo validar

Cada vez que guardas, GitHub vuelve a revisar el formato de tus archivos. Tarda uno o dos minutos.

1. Regresa a tu PR, pestaña **Conversation**, y baja hasta el final.
2. Busca el chequeo **validar**:
   - 🟡 círculo amarillo: todavía está revisando. Espera y recarga la página.
   - ✅ palomita verde: el formato está bien.
   - ❌ cruz roja: hay un error. Haz clic en **Details** y lee el mensaje: dice el archivo, la línea y el problema. Corrígelo como en los pasos 3 a 5.
3. En la pestaña **Commits** deben aparecer tus correcciones dentro de este mismo PR. Si no aparecen, ve a [Si algo sale mal](#si-algo-sale-mal).

La palomita verde solo confirma el formato. No sabe si una palabra está mal o si un nombre es el correcto: eso lo revisas tú escuchando el video.

## Paso 7. Avisa que terminaste

Cuando todas tus filas del Excel digan Corregido o No es error y **validar** esté en verde, escribe un comentario al final de tu PR, en la pestaña **Conversation**:

> Listo, corregí los errores señalados en los N archivos.

No cierres el PR ni lo fusiones tú: el profesor lo revisa y lo fusiona.

## Cómo corregir cada tipo de error

Cada fila del Excel ya dice qué hacer. Aquí tienes ejemplos de antes y después para los errores más comunes.

### Restos de IA: marcas [cite: N]

Borra todas las marcas. Busca `[cite` con Ctrl/Cmd + F hasta que no quede ninguna. Luego escucha un par de minutos del video: si el texto no coincide palabra por palabra, el chatbot lo reescribió y hay que volver a la transcripción de YouTube.

```text
Antes:   [44:46] >> Aurelio Collado: Seis preguntas[cite: 5]. Le voy a pedir...
Después: [44:46] >> Aurelio Collado: Seis preguntas. Le voy a pedir...
```

### Restos de IA: encabezados, viñetas o separadores en Markdown

Borra todo lo que no sea una línea de transcripción: títulos con `*` o `#`, listas de participantes, líneas `---` y frases como "Aquí tienes la transcripción corregida…". El archivo debe empezar directamente con la primera línea `[mm:ss]`.

```text
Antes:   * **Título del video:** México frente a tres imperialismos
         * **Participantes y roles:** ...
         [00:12] >> Alan Knight: Buenas tardes...
Después: [00:12] >> Alan Knight: Buenas tardes...
```

### Falta quién habla: sin >> Nombre:, sin dos puntos o un solo turno en todo el archivo

Después del nombre van siempre dos puntos: `>>Ana López Buenas tardes` está mal; `>> Ana López: Buenas tardes` está bien. Si en todo el archivo hay un solo `>>`, escucha el video: casi siempre hablan varias personas (presentador, moderador, público). Marca el inicio de cada turno con `>> Nombre:` justo después del tiempo. Las líneas que siguen dentro del mismo turno van sin nombre. El nombre real está en el título del video o en la presentación.

```text
Antes:   [00:23] Les voy a presentar con muchísimo gusto
         [00:25] a Susana Hernández Araico...
Después: [00:23] >> Nombre Apellido: Les voy a presentar con muchísimo gusto
         [00:25] a Susana Hernández Araico...
```

### Hablante principal sin nombre real

Cambia "Conferencista", "Presentador", "Ponente" o "Moderador/a" por el nombre real, en **todas** las líneas donde aparece. Usa Ctrl/Cmd + F para encontrarlas. "Participante 1", "Participante 2"… solo se acepta para personas del público que no dicen su nombre. Las instrucciones originales permitían "Moderador/a (nombre desconocido)"; ahora buscamos el nombre real en el video, su título o su descripción. Si de verdad no aparece, explícalo en la columna Observaciones del Excel.

```text
Antes:   [02:10] >> Conferencista: Muchas gracias por la invitación...
Después: [02:10] >> Nombre Apellido: Muchas gracias por la invitación...
```

### Nombre de hablante con título, paréntesis o barra

Escribe solo el nombre y apellido, igual en todo el archivo.

```text
Antes:   >> Profesor Jem Bendell:      >> Participante 4 (Carla Gaitán):
Después: >> Jem Bendell:               >> Carla Gaitán:
```

### Líneas sin tiempo [mm:ss]

Cada línea con texto empieza con su tiempo. Si una línea suelta es continuación de la anterior, únela a esa línea. Si es un título o nota, bórrala.

```text
Antes:   [11:17] Tenemos territorios del país donde el crimen organizado impera
         y no el Estado de derecho.
Después: [11:17] Tenemos territorios del país donde el crimen organizado impera y no el Estado de derecho.
```

### Dos tiempos en una línea (archivos o líneas pegadas)

Pon cada tiempo en su propia línea. Si se pegó el inicio de otro archivo o se repitió una parte, borra lo que sobra.

```text
Antes:   [00:33] ruano de la haza que es el experto en[00:01] [Música]
Después: [00:33] ruano de la haza que es el experto en
```

### Tiempos que retroceden

Los tiempos solo pueden subir. Un tiempo menor que el anterior casi siempre indica una parte pegada dos veces o fuera de orden. Busca la línea indicada, compara con el video y borra o reacomoda el bloque.

### Marcas sin resolver ([?], Nombre?, CONTINÚA EN)

Escucha ese punto del video y escribe lo que se dice o el nombre correcto. Borra las líneas "CONTINÚA EN".

```text
Antes:   [05:12] >> Moderadora?: Le damos la bienvenida a [?]
Después: [05:12] >> Nombre Apellido: Le damos la bienvenida a la autora Nombre Apellido
```

### Tiempos mayores que la duración del video

El último tiempo del archivo pasa la duración real del video. Abre el video y comprueba dos cosas: que la transcripción sea **de este video**, y que tres o cuatro líneas del principio, la mitad y el final suenen en su tiempo. Si no coinciden, toma los tiempos de la transcripción de YouTube (bajo el video: **⋯ → Mostrar transcripción**).

### Posible texto faltante al final o al inicio, y huecos de más de 3 minutos

Es una alerta, no siempre un error. Ve a ese punto del video: si se sigue hablando, falta texto y hay que agregarlo con sus tiempos; si es música, aplausos o créditos, no hay que hacer nada. Márcalo como "No es error" en el Excel.

### Líneas consecutivas repetidas

Borra la repetida y conserva la primera.

## Errores que no debes cometer

| No hagas esto | Por qué | Haz esto |
| --- | --- | --- |
| Elegir "Create a new branch" al guardar | Crea un PR nuevo y repetido; tu corrección no llega al PR revisado | Elegir **Commit directly to the `tu-rama` branch** |
| Subir otra vez los archivos con Upload files estando en `main` | También crea un PR nuevo | Cambiar primero el selector de ramas a **tu rama** |
| Cambiar el nombre del archivo | El nombre es el código del video; con otro nombre ya no se encuentra | Dejar `CODIGO.txt` tal cual |
| Editar en Word o Pages y guardar como .docx o .pages | Agregan formato invisible | Editor de GitHub, Bloc de notas, VS Code, o Google Docs descargado como .txt |
| Volver a pasar el texto por un chatbot | Agrega marcas `[cite]` y resume o reescribe lo que se dijo | Corregir a mano, escuchando |
| Mover texto entre líneas o retocar tiempos "a ojo" | Rompe la sincronización con el video | Corregir dentro de la línea |
| Cerrar o fusionar tu PR | Lo revisa y fusiona el profesor | Avisar con un comentario (paso 7) |

## Si algo sale mal

- **Guardaste en una rama nueva y se creó otro PR.** No subas nada más. Escribe en el PR nuevo: "Este PR es por error, mi PR original es #N". El profesor decide cuál se queda.
- **validar sigue en rojo después de corregir.** Abre **Details**, copia el mensaje y pégalo en un comentario de tu PR si no lo entiendes.
- **No aparece Edit file.** Revisa que entraste con tu cuenta y que el PR siga abierto. Si el PR está cerrado, no lo edites: pregunta al profesor en cuál trabajar.
- **Borraste algo por error.** Antes de guardar, recarga la página sin guardar y empieza de nuevo. Si ya guardaste, avisa en un comentario: cada guardado queda en el historial y se puede recuperar.
- **No sabes el nombre de un hablante.** Búscalo en el título y la descripción del video, o en la presentación al inicio. Si no aparece, escribe `>> Nombre?:` y explícalo en tu comentario del paso 7: esa marca hace que validar falle, así que el profesor lo resolverá contigo.
