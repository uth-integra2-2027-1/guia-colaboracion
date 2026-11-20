# GitHub paso a paso (desde cero)

Versión web con ilustraciones: **https://integra2.sistemasprado.mx/github/** · Reglas de trabajo en equipo: [README](README.md)

GitHub está en inglés: los botones aparecen en **negritas** tal como se ven, con su traducción entre paréntesis. Lo que va en `este formato` es lo que escribes.

## Contenido

1. [Prepara tu cuenta de GitHub](#1-perfil)
2. [Crear un issue (una tarea)](#2-issue)
3. [Crear el tablero del equipo (una sola vez)](#3-tablero)
4. [Agregar y mover tarjetas](#4-tarjetas)
5. [Abrir un Pull Request (PR)](#5-pr)
6. [Revisar el PR de un compañero](#6-revision)
7. [Hacer el merge](#7-merge)
8. [Comprobar que cumpliste](#8-verificar)

<a id="1-perfil"></a>

## 1. 🪪 Prepara tu cuenta de GitHub

**Quién:** Cada alumno · **Cuándo:** Antes de registrarte en tu portal (a más tardar el 17 de enero)

**Para qué:** El docente debe reconocerte siempre en GitHub: tu foto, tu nombre completo y tu grupo aparecen junto a cada commit, PR y revisión. Integra2 no deja registrar una cuenta que no cumpla.

1. *¿Ya tienes cuenta?* Si tu cuenta tiene un apodo, la usas para otras cosas o no puedes poner tu foto y nombre real, *crea una nueva* sólo para la escuela. Si no tienes, también créala.
2. Para crearla entra a `https://github.com/signup`, escribe tu *correo institucional* (`a25310000@uthermosillo.edu.mx`), una contraseña y un **username** (usuario) sencillo, por ejemplo `juan-perez-uth`. Confirma el código que llega a tu correo.
3. Ya dentro, haz clic en tu *foto redonda* (arriba a la derecha) y luego en **Settings** (configuración).
4. Estás en **Public profile** (perfil público). En **Profile picture** haz clic en **Edit → Upload a photo** y sube una *foto de tu cara*: de frente, con buena luz y sin lentes oscuros ni filtros. Ajusta el recuadro y pulsa **Set new profile picture**.
5. En **Name** escribe tu nombre *exactamente como en la lista del grupo*: apellido paterno, apellido materno y nombres. Ejemplo: `PEREZ LOPEZ JUAN CARLOS`. Puede ser en mayúsculas o minúsculas, con o sin acentos.
6. En **Bio** escribe tu grupo así: `UTH · Integradora II · Grupo 5-1` (cambia `5-1` por tu grupo).
7. Baja hasta el final y pulsa el botón verde **Update profile** (actualizar perfil).
8. Comprueba: abre `https://github.com/tu-usuario` en otra pestaña. Debes ver tu foto, tu nombre completo y tu grupo.
9. Ahora sí, en tu portal de Integra2 → **Mis datos** escribe tu usuario y pulsa **Guardar**. Si algo falta, el portal te dice exactamente qué corregir.

> ⚠️ Integra2 revisa tu perfil cada 2 horas. Si cambias tu foto por un dibujo o quitas tu nombre, aparecerá como «perfil incompleto» en el panel del docente.

<a id="2-issue"></a>

## 2. 📌 Crear un issue (una tarea)

**Quién:** El coordinador crea las de todos; cualquiera puede crear issues de sus propias tareas · **Cuándo:** Al iniciar cada unidad

**Para qué:** Un issue es una tarea con responsable y fecha. Así todos saben qué hace cada quien y queda prueba de quién cumplió.

1. Abre el repositorio del equipo en GitHub (`https://github.com/uth-integra2-2027-1/tu-repo`).
2. Arriba, debajo del nombre del repositorio, haz clic en la pestaña **Issues**.
3. Pulsa el botón verde **New issue** (nuevo issue).
4. En **Title** (título) escribe la tarea en pocas palabras y empezando con un verbo: `Crear modelo Lectura en mod_qr`.
5. En la descripción (**Add a description**) explica: qué se entrega, cómo se sabe que está terminado y la fecha límite. Ejemplo: `Entregable: modelo con folio, fecha y tiempo de registro. Terminado: migración aplicada y prueba que pasa. Fecha: 21 de enero.`
6. A la derecha, en **Assignees** (responsables), haz clic en el engrane y elige al compañero responsable.
7. En **Labels** (etiquetas) puedes elegir una, por ejemplo `enhancement` (mejora) o `documentation` (documentación). Es opcional.
8. En **Projects** elige el tablero del equipo para que la tarjeta aparezca ahí (ver «Crear el tablero»).
9. Pulsa **Submit new issue** (crear). GitHub le pone un número, por ejemplo `#12`. Ese número se usa en el nombre de la rama y en el PR.

> ⚠️ Una buena tarea se termina en 1 a 3 días. Si es más grande, divídela en varios issues.

<a id="3-tablero"></a>

## 3. 🗂️ Crear el tablero del equipo (una sola vez)

**Quién:** El coordinador de la Unidad 1 · **Cuándo:** Primera semana (11 al 17 de enero)

**Para qué:** El tablero muestra todas las tareas como tarjetas en columnas: lo que falta, lo que se está haciendo, lo que espera revisión y lo terminado.

1. En el repositorio haz clic en la pestaña **Projects** y luego en **Link a project → New project** (si no aparece, entra a la organización `uth-integra2-2027-1` → **Projects → New project**).
2. Elige la plantilla **Board** (tablero) y escribe el nombre del proyecto: `Tablero equipo 51-E1`. Pulsa **Create project**.
3. El tablero trae tres columnas: **Todo**, **In Progress** y **Done**. Haz clic en los tres puntos (**…**) de cada columna → **Edit details** y ponles: `Por hacer`, `En proceso` y `Hecho`.
4. Agrega una cuarta columna: al final pulsa **+** (**New column**) y llámala `En revisión`. Arrástrala entre «En proceso» y «Hecho».
5. Arriba a la derecha, en los tres puntos del proyecto → **Settings → Manage access**, agrega a tus compañeros con permiso **Write** para que puedan mover tarjetas.
6. Vuelve al repositorio → **Projects → Link a project** y elige el tablero, para que quede conectado al repositorio.

> ⚠️ Se crea una sola vez y sirve para las 4 unidades. Cada unidad sólo se agregan tarjetas nuevas.

<a id="4-tarjetas"></a>

## 4. 🃏 Agregar y mover tarjetas

**Quién:** Cada alumno mueve las suyas; el coordinador revisa el tablero en cada sesión · **Cuándo:** Todos los días que trabajes

**Para qué:** Mover tu tarjeta avisa al equipo en qué vas sin tener que preguntar.

1. Para agregar una tarea al tablero: en la columna **Por hacer** pulsa **+ Add item**, escribe `#` y elige el issue de la lista (por ejemplo `#12`). Pulsa Enter.
2. Cuando empieces a trabajar, *arrastra tu tarjeta* a **En proceso** y crea tu rama `12-registro-qr`.
3. Cuando abras el Pull Request, muévela a **En revisión**.
4. Cuando el integrador haga el merge, muévela a **Hecho**. Si en el PR escribiste `Closes #12`, el issue se cierra solo.
5. Si te atoras, escribe un comentario en el issue explicando qué te detiene. Así el coordinador puede ayudarte o reasignarlo a tiempo.

> ⚠️ Una tarjeta 48 h sin moverse se marca «en riesgo»; a las 72 h se puede reasignar a otro integrante.

<a id="5-pr"></a>

## 5. 📤 Abrir un Pull Request (PR)

**Quién:** El autor del cambio · **Cuándo:** Cuando tu tarea funciona en tu computadora

**Para qué:** El PR pide permiso para unir tu rama a main. Tus compañeros ven qué cambiaste y lo aprueban.

1. Sube tus últimos cambios: `git add .`, `git commit -m "Agrega modelo Lectura #12"` y `git push`.
2. Abre el repositorio en GitHub. Aparece un aviso amarillo con el botón **Compare & pull request**; púlsalo. (Si no aparece: pestaña **Pull requests → New pull request**, en **compare** elige tu rama.)
3. Revisa que diga **base: main ← compare: 12-registro-qr**.
4. El título ya viene escrito; ajústalo para que diga qué hace el cambio.
5. En la descripción llena la plantilla: `Closes #12`, qué cambiaste, cómo probarlo y una captura.
6. A la derecha, en **Reviewers** (revisores), elige a uno o dos compañeros.
7. Pulsa **Create pull request**. Mueve tu tarjeta a **En revisión** y avisa al equipo.

> ⚠️ Si te piden cambios, corrige en la misma rama y haz `git push`: el PR se actualiza solo, no abras otro.

<a id="6-revision"></a>

## 6. 🔎 Revisar el PR de un compañero

**Quién:** Cualquier integrante distinto al autor (el QA revisa al menos 2) · **Cuándo:** En menos de 48 h desde que te lo piden

**Para qué:** Revisar evita que entren errores a main y es obligatorio: cada unidad debes revisar al menos un PR.

1. Entra a la pestaña **Pull requests** y abre el PR de tu compañero.
2. Lee la descripción: qué cambió y cómo probarlo.
3. Haz clic en la pestaña **Files changed** (archivos cambiados). En verde está lo agregado y en rojo lo borrado.
4. Si algo no se entiende o está mal, pasa el cursor sobre la línea, pulsa el **+** azul y escribe un comentario amable y concreto: `¿Qué pasa si el folio no existe? Sugiero mostrar un mensaje.`
5. Si es un cambio importante, pruébalo: en tu computadora `git fetch` y `git switch 12-registro-qr`, luego `python manage.py test`.
6. Arriba a la derecha pulsa **Review changes** (revisar cambios). Escribe un resumen y elige: **Approve** (aprobar) si está bien, **Request changes** (pedir cambios) si debe corregirse o **Comment** (comentar) si sólo opinas.
7. Pulsa **Submit review** (enviar revisión).

> ⚠️ No apruebes sin leer. Tu nombre queda registrado como quien aprobó.

<a id="7-merge"></a>

## 7. 🔀 Hacer el merge

**Quién:** El integrador de la unidad (si no lo hace en 48 h desde la aprobación, cualquier otro integrante) · **Cuándo:** Cuando el PR tiene al menos una aprobación

**Para qué:** El merge une la rama aprobada a main. Desde ese momento el cambio está en la versión oficial y se publica en Render.

1. Abre el PR. Abajo debe decir **Changes approved** (cambios aprobados) con el nombre de un compañero, y **This branch has no conflicts with the base branch** (sin conflictos).
2. Si dice **This branch has conflicts**, pulsa **Resolve conflicts**, y con el autor elige qué líneas quedan. Nunca borres el trabajo de otro.
3. Pulsa el botón verde **Merge pull request** (o la flecha → **Squash and merge**) y luego **Confirm merge**.
4. Pulsa **Delete branch** para borrar la rama ya unida.
5. Abre Render y espera a que el despliegue diga **Deploy live**. Abre la app y revisa que funcione.
6. Avisa al equipo para que todos hagan `git switch main` y `git pull`.

> ⚠️ Fusionar el PR de otro sin ser el integrador antes de 48 h desde la aprobación resta puntos a quien lo hace.

<a id="8-verificar"></a>

## 8. ✅ Comprobar que cumpliste

**Quién:** Cada alumno · **Cuándo:** Al menos dos veces por semana

**Para qué:** Saber a tiempo si te falta algo, antes del cierre.

1. Abre tu portal de Integra2 (el enlace que te llegó por correo).
2. En la unidad en curso revisa **Colaboración y mi rol**: tu rol de la unidad y ✅ o ❌ en PR propio, revisión, push directo y tarea del rol.
3. Revisa **Mi constancia en GitHub**: los días en verde son días con commit válido.
4. En GitHub, pestaña **Pull requests**, escribe en el buscador `is:pr author:tu-usuario` para ver tus PR y `is:pr reviewed-by:tu-usuario` para ver los que revisaste.
5. Si algo sale ❌ y crees que es un error, avisa al docente con el enlace del PR o del issue.

> ⚠️ El portal se actualiza cada 2 horas: un cambio de hace minutos puede no aparecer todavía.

---
*Generado desde Integra2 (`python manage.py exportar_guia`).*
