# CAR

## Paso 1
Revisa las asignaciones en la [[base de datos]](https://docs.google.com/spreadsheets/d/1e0b7f0_LtSSDmdcdIjJPZApOSb8Y_ZTNUvvfDR2x9Nc/edit?gid=0#gid=0)
Usa el siguiente [[script](https://colab.research.google.com/drive/1R4xyRg5X-IR7lrCpb0Oes4W521fN74h5?usp=sharing)] y extrae las transcipciones con su timestamp. Obtendrás un archivo de texto .txt que usarás en el siguiente paso.

## Paso 2
Usa tu IA de confianza pero dale el siguiente PROMPT para pulir la transcripción:

Eres editor de transcripciones. Adjunto un archivo .txt con la transcripción automática de un video de YouTube. Cada línea empieza con un timestamp entre corchetes, en formato [mm:ss] o [h:mm:ss], seguido de un fragmento de texto sin puntuación fiable y sin indicar quién habla.

CONTEXTO

* Título del video: XXX
* Participantes y roles: [NOMBRE - rol, uno por línea. Si no conoces un nombre, escribe "Moderador/a (nombre desconocido)"]
* Idioma de la transcripción: Español

TU TAREA

1. Lee el archivo completo, de principio a fin, antes de comenzar la edición.

2. Elimina las líneas que solo dicen [Música], [Aplausos] o están vacías.

3. Une las líneas en párrafos coherentes de 1 a 3 oraciones. Cada párrafo conserva exactamente el timestamp de su PRIMERA línea. No calcules, ajustes, interpoles ni inventes timestamps: usa únicamente timestamps que aparezcan en el archivo original.

4. Corrige puntuación, mayúsculas, ortografía y errores de reconocimiento automático únicamente cuando la corrección sea inequívoca por el contexto. Escribe correctamente los nombres propios cuando estén identificados en la lista de participantes o cuando su identificación sea inequívoca en la transcripción.

5. Elimina repeticiones involuntarias, falsos arranques y errores mecánicos propios de la transcripción automática. Elimina muletillas solo cuando sean claramente prescindibles y no modifiquen el significado, el tono o el estilo del hablante. Conserva, en lo posible, el carácter oral de la intervención.

6. Identifica quién habla:

   * Quien da la bienvenida, presenta a los invitados o cede la palabra es probablemente el moderador.
   * Si alguien es descrito en tercera persona —por ejemplo, mediante una biografía, trayectoria o lista de premios—, esa persona NO es quien habla.
   * Un cambio de hablante es probable después de una pregunta, una presentación, una cesión explícita de la palabra, un "gracias, [nombre]" o expresiones equivalentes.
   * Usa el nombre real solo cuando exista evidencia suficiente en el texto o en la lista de participantes.
   * Si existe evidencia parcial pero no certeza, añade "?" al nombre: "Gabriel?".
   * Si no existe evidencia suficiente para identificarlo, usa "Participante 1", "Participante 2", etc., manteniendo el mismo número si esa persona vuelve a intervenir y puede identificarse como la misma.
   * Nunca inventes nombres ni atribuyas una intervención basándote únicamente en lo que parecería lógico.

7. Si una palabra, nombre, fecha, premio, cifra, título, institución u otro dato no se entiende o parece incorrecto, NO intentes corregirlo utilizando conocimiento externo. Conserva la forma de la transcripción y añade [?] inmediatamente después del fragmento dudoso.

8. No uses conocimiento externo para completar, corregir, reinterpretar o "mejorar" el contenido. Trabaja únicamente con la transcripción y el contexto proporcionado.

9. No resumas, no parafrasees, no omitas ideas, no añadas información y no traduzcas. Conserva el idioma original y la voz de cada hablante.

10. En caso de conflicto entre las reglas, prioriza siempre la fidelidad a la transcripción. Es preferible conservar un fragmento dudoso y marcarlo con [?] que introducir una corrección no demostrable.

FORMATO DE SALIDA

Texto plano, una línea por párrafo, sin JSON, sin viñetas, sin títulos y sin explicaciones antes ni después.

Cada línea empieza con el timestamp:
[mm:ss] texto

Pon el nombre del hablante SOLO en la primera línea de cada turno, utilizando el marcador ">>":
[mm:ss] >> Nombre: texto

Las líneas siguientes del mismo hablante llevan únicamente el timestamp y el texto:
[mm:ss] texto

Vuelve a escribir ">>" y el nombre únicamente cuando cambie quien habla:
[mm:ss] >> Otro hablante: texto

Mantén el formato original del timestamp. Si el archivo utiliza [h:mm:ss], conserva [h:mm:ss]. No conviertas los timestamps a otro formato.

Deja UNA LÍNEA EN BLANCO entre cada párrafo.

Entrega todo el resultado dentro de un único bloque de código para que pueda copiarse completo.

EJEMPLO DEL FORMATO

[00:22] >> Moderador/a: Buenas tardes, qué gusto que nos acompañen el día de hoy.
[00:44] Están aquí para escuchar sobre la novela más reciente de Valeria Luiselli.
[01:30] >> Valeria Luiselli: Muchas gracias. Es un gusto estar aquí.
[01:35] La novela nació de una pregunta que me hacía hace años.
[02:10] >> Participante 1: Quisiera preguntarte cómo comenzó el proyecto.
[02:18] >> Valeria Luiselli: Empezó durante un viaje que hice hace algunos años.

SI LA RESPUESTA ES MUY LARGA

Si no puedes completar la transcripción por límite de espacio:

* Termina siempre después de un párrafo completo.
* En una línea aparte escribe: CONTINÚA EN [timestamp]
* El timestamp debe ser exactamente el de la siguiente línea o párrafo pendiente del archivo original.
* Detente inmediatamente después de esa línea.
* Cuando yo escriba "continúa", retoma exactamente desde ese timestamp, manteniendo las mismas reglas, numeración de participantes e identificación de hablantes.
* No repitas ninguna parte ya entregada.


## Paso 3
Revisa de manera personal y meticulosa el documento que se generó.

Pega el resultado en un Google Doc y revísalo línea por línea:

Busca con Ctrl+F todos los [?] y todos los ? junto a nombres de hablante. Resuélvelos uno por uno: escucha ese momento del video y corrige, o deja el texto tal cual y quita la marca.

Revisa los cambios de hablante. Los puntos delicados son después de cada pregunta y cada "gracias, [nombre]". Si un cambio falta, todo lo siguiente queda atribuido a la persona equivocada.

Comprueba tres o cuatro timestamps al azar: abre el video en ese minuto y confirma que se dice lo que aparece en el texto.
Compara el último timestamp del documento con el final del video. Si faltan tramos de tiempo, el modelo se saltó partes.

Si trabajaste por partes, borra las líneas "CONTINÚA EN..." y verifica que no haya texto repetido en las uniones.

No cambies el formato del inicio de cada línea: [mm:ss] texto o [mm:ss] >> Nombre: texto.

## Paso 4
Descarga con Archivo → Descargar → Texto sin formato (.txt) y nómbralo con el ID del video: m3dt0KEggjs.txt

## Paso 5
Sube tu archivo final a tu repositorio de Github

