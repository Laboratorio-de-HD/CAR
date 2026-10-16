# CAR

## Paso 1
Extra las transcipciones con su timestap y obtén un archivo .txt

## Paso 2
Usa el siguiente prompt para pulir la transcripción:

Eres editor de transcripciones. Adjunto un archivo .txt con la transcripción automática de un video de YouTube. Cada línea empieza con un timestamp entre corchetes, en formato [mm:ss] o [h:mm:ss], seguido de un fragmento de texto sin puntuación fiable y sin indicar quién habla.

CONTEXTO
- Título del video: 
- Participantes y roles: [NOMBRE - rol, uno por línea. Si no conoces un nombre, escribe "Moderador/a (nombre desconocido)"]
- Idioma de la transcripción: Español

TU TAREA
1. Lee el archivo completo, de principio a fin.
2. Elimina las líneas que solo dicen [Música], [Aplausos] o están vacías.
3. Une las líneas en párrafos de 1 a 3 oraciones. Cada párrafo conserva el timestamp de su PRIMERA línea. No calcules, ajustes ni inventes timestamps: usa únicamente los que aparecen en el archivo. Se riguroso en ello.
4. Corrige puntuación, mayúsculas y errores evidentes de reconocimiento. Escribe correctamente los nombres propios según la lista de participantes. Quita muletillas y repeticiones involuntarias.
5. Identifica quién habla:
   - Quien da la bienvenida, presenta a los invitados o cede la palabra es el moderador.
   - Si alguien es descrito en tercera persona (biografía, premios), esa persona NO es quien habla.
   - Un cambio de hablante es probable tras una pregunta, un "gracias, [nombre]" o un "como decía [nombre]".
   - Usa el nombre real solo si hay evidencia en el texto. Si dudas, añade "?" al nombre (ejemplo: "Gabriel?"). Si no hay evidencia, usa "Participante". Nunca inventes nombres.
6. Si algo no se entiende, o un dato (fecha, premio, cifra, título) parece incorrecto, déjalo como está y márcalo con [?].
7. No resumas, no omitas ideas, no añadas información y no traduzcas. Conserva el idioma original.

FORMATO DE SALIDA
- Texto plano, una línea por párrafo, sin JSON, sin viñetas, sin títulos y sin explicaciones antes ni después.
- Cada línea empieza con el timestamp: [mm:ss] texto
- Pon el nombre del hablante SOLO en la primera línea de su turno, con el marcador ">>":
  [mm:ss] >> Nombre: texto
- Las líneas siguientes del mismo hablante llevan solo el timestamp y el texto.
- Vuelve a poner ">>" y el nombre únicamente cuando cambie quien habla.
- Entrega todo dentro de un único bloque de código, para poder copiarlo completo.

EJEMPLO DEL FORMATO
[00:22] >> Moderador/a: Buenas tardes, qué gusto que nos acompañen el día de hoy.
[00:44] Están aquí para escuchar sobre la novela más reciente de Valeria Luiselli.
[01:30] >> Valeria Luiselli: Muchas gracias. Es un gusto estar aquí.
[01:35] La novela nació de una pregunta que me hacía hace años.

SI LA RESPUESTA ES MUY LARGA
Si te quedas sin espacio, termina en una línea completa, escribe en una línea aparte "CONTINÚA EN [mm:ss]" con el timestamp de la siguiente línea que falta, y detente. Cuando yo escriba "continúa", sigue desde ese punto con el mismo formato y sin repetir lo anterior.

## Paso 3
Revisa de manera personal y meticulosa el documento que se generó y guárdalo con el nombre del video.
