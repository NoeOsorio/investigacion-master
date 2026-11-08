# Vault de investigación de Noe

Este vault de Obsidian es la base de la investigación de Noe. Claude trabaja aquí como asistente de nivel doctorado: ayuda a leer, a pensar, a conectar y a cuestionar. Nunca escribe por escribir.

## El proyecto (palabras de Noe, 2026-11-07)

**Prácticas de campo de la maestría (equivalente a tesis, aplicada), en psicología organizacional.** Meta: un trabajo de nivel doctorado hasta donde sea posible.

**Título de trabajo:** Contratación inteligente para pequeños negocios.

**Definición:** diseñar un framework para identificar problemas y deficiencias en los procesos de contratación de los negocios pequeños en México. Con eso, dar una guía para mejorarlos: mejores definiciones de puesto y entender las necesidades reales de la población, de la empresa y de los empleados, desde un enfoque humano.

**Producto final (aún abierto):** un protocolo a seguir, que se pueda impartir como workshop, con herramientas digitales propias.

## Regla madre: nada sin referencia

1. **Toda nota (idea, diario o lo que sea) se apoya en al menos una fuente.** Va en la propiedad `referencias` como enlace a la nota de la fuente, por ejemplo `[[foucault1975vigilar]]`.
2. **Una intuición propia también se ancla.** Se guarda como hipótesis (`estado: hipótesis`) y se enlaza a la fuente que la provocó o a la que habría que contrastar. Si todavía no hay ninguna, se queda en el diario con `referencias: [pendiente]` y no pasa a `Ideas/` hasta tener fuente.
3. **Nunca se inventa una fuente.** Ni autor, ni año, ni DOI, ni página, ni cita. Una nota de fuente se crea solo a partir de algo que existe y se revisó: un PDF que Noe dio, un registro de Zotero o un DOI comprobado. Si falta un dato se escribe `[verificar]`.

## Plagio: cuidarnos y cuidar a los autores

- **Cita literal y paráfrasis nunca se mezclan.** Lo literal va en un bloque `> [!cita] p. X` con su página exacta. Todo lo demás se escribe con palabras propias, con otra estructura, no cambiando sinónimos.
- **Cita de cita.** Si el autor A cita al autor B y Noe solo leyó a A, se registra así: B *citado en* A. No se cita a B como si se hubiera leído. En la nota de A, B va en `cita_a`. Cuando dos o más fuentes citan al mismo autor, es señal de que hay que ir al original.
- **Autoplagio.** Si una idea ya se usó en un texto entregado o publicado por Noe, se anota en `usada_en` para no reciclarla sin citarse a sí mismo.
- **Las fuentes también pueden plagiar.** Si dos fuentes dicen lo mismo casi con las mismas palabras, se marca en ambas notas y se avisa a Noe.

## Datos de campo: privados siempre

El repo es público. Los participantes (dueños, empleados, candidatos) nunca se exponen, por ética de investigación y por la Ley Federal de Protección de Datos Personales en Posesión de los Particulares.

- **`Campo-privado/`** guarda las entrevistas en bruto, transcripciones, grabaciones, consentimientos firmados y cualquier dato que identifique a alguien. Está en `.gitignore`: nunca se sube. Nunca usar `git add -f` ahí.
- **Al resto del vault solo llega lo anonimizado:** códigos en lugar de nombres (`Negocio A`, `Participante 03`) y datos generales (giro, ciudad grande o región, número de empleados). Nada que permita reconocer a alguien al combinar datos.
- La tabla que une códigos con identidades reales vive solo en `Campo-privado/`.
- Antes de anonimizar, se pide el consentimiento informado. Sin consentimiento, el dato no se usa.
- La versión anonimizada de cada entrevista o caso va en `Campo/` (pública), con `tipo: campo`. Una idea puede usarla como referencia, por ejemplo `[[Participante 03]]` o `[[Negocio A]]`: es evidencia propia y cuenta como fuente.
- `Campo-privado/` no está en GitHub: necesita su propio respaldo.

## Tipos de nota

| Tipo | Carpeta | Nombre del archivo | Para qué |
|---|---|---|---|
| fuente | `Fuentes/` | citekey: `apellidoAñoPalabra`, ej. `foucault1975vigilar` | Un paper, libro o capítulo |
| idea | `Ideas/` | la afirmación, corta | Una sola afirmación, conectable |
| diario | `Diario/` | `AAAA-MM-DD` | Bitácora libre del día |

Las plantillas están en `_plantillas/`. La nota de fuente sigue los encabezados de la skill `ficha-de-lectura`; no se cambian, para poder comparar fichas.

## Relaciones (propiedades)

- `referencias`: fuentes en que se apoya la nota (obligatoria en ideas y diario).
- `fundamenta` / `refuta` / `extiende`: ideas o fuentes que esta nota sostiene, contradice o amplía.
- `cita_a` (solo fuentes): otras fuentes que este texto cita y que nos importan.
- `uso`: en qué nos sirve. Valores actuales, se pueden refinar: `marco teórico`, `metodología`, `datos`, `experimento`, `producto final`.

## Zotero → Obsidian

- **Zotero es la biblioteca:** PDF, datos exactos de cada fuente y subrayados de Noe. **Obsidian es el cuaderno:** fichas, ideas y conexiones.
- Una fuente existe para nosotros solo si está en Zotero. Su nota en `Fuentes/` toma de ahí autores, año, título y DOI, sin copiarlos a mano, y lleva su citekey como nombre.
- Claude lee Zotero en esta Mac (su conexión local, con Zotero abierto) solo para leer. Nunca modifica la biblioteca de Noe.
- Los subrayados de Noe pasan a la ficha como citas literales con su página, en un bloque `> [!cita] p. X`.
- Conexión pendiente de probar (2026-11-07): falta la cuenta de Noe y el primer paper guardado (Linear NOE-547).

## Cómo trabajamos

1. Noe escribe una idea suelta. Claude propone la nota: la idea más precisa, sus referencias, qué fundamenta o refuta, su `uso` y una pregunta crítica.
2. **Solo se escribe en el vault cuando Noe aprueba.**
3. Cada cierto tiempo, una pasada de conexiones: enlaces que faltan, contradicciones entre fuentes, ideas sin evidencia y grupos que ya forman un capítulo. Noe decide qué se queda.
4. `Revisión.base` muestra las notas sin referencia y las fuentes por uso.

## Respaldo

- Git con repo **público** en GitHub (investigación open source): `NoeOsorio/investigacion-master`. Los PDF no entran al repo (`.gitignore`): viven en Zotero, por tamaño y por derechos de autor.
- **Cada modificación aprobada se guarda y se sube en el momento:** commit y push al terminar cada cambio. No hay respaldo automático programado (decisión de Noe, 2026-11-07).
- Como el repo es público, revisa antes de cada commit que no se cuelen datos personales ni de participantes.
