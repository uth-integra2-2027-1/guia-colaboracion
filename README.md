# Guía de trabajo en equipo · Proyecto Integrador II 2027-1

Universidad Tecnológica de Hermosillo · Docente: Bernardo Prado Díaz · del 11 de enero al 2 de marzo de 2027.

> Versión web, con tu rol de cada unidad: **https://integra2.sistemasprado.mx/colaboracion/** · Tu avance: tu portal de Integra2.

Todos contribuyen y todos revisan. **Integra2 lo verifica en GitHub y descuenta sólo a quien no cumple.**

## Contenido

1. [Las 5 reglas](#1-las-5-reglas)
2. [main, rama y merge](#2-main-rama-y-merge)
3. [Flujo de trabajo paso a paso](#3-flujo-de-trabajo-paso-a-paso)
4. [Roles](#4-roles)
5. [Qué resta Integra2](#5-qué-resta-integra2)
6. [Si alguien no cumple](#6-si-alguien-no-cumple-no-afecta-a-los-demás)
7. [Mínimos por unidad](#7-mínimos-por-unidad)
8. [Dónde constatarlo](#8-dónde-constatarlo)
9. [Configurar GitHub](#9-configurar-github)

## 1. Las 5 reglas

| # | Regla | Qué significa |
|---|---|---|
| 1 | **Nadie sube directo a main** | Cada quien trabaja en su propia rama y propone sus cambios con un Pull Request (PR). |
| 2 | **Otro integrante aprueba** | Un PR sólo cuenta si lo aprueba alguien distinto al autor antes del merge. |
| 3 | **Todos revisan** | Cada unidad revisas al menos 1 PR de un compañero, en máximo 48 h. |
| 4 | **Un rol por unidad** | Coordinador organiza, integrador cuida main, documentador sube evidencias e informe, QA prueba que todo funcione. Rota cada unidad. |
| 5 | **Descuento individual** | Si un compañero falla, el descuento es sólo suyo. |

## 2. main, rama y merge

Piensa en el informe del equipo en un documento compartido: si todos escriben a la vez sobre la versión final, se borran cosas y nadie sabe qué cambió. Git lo resuelve así:

```mermaid
gitGraph
  commit id: "main funciona"
  branch 12-registro-qr
  checkout 12-registro-qr
  commit id: "día 1"
  commit id: "día 2"
  commit id: "día 3"
  checkout main
  merge 12-registro-qr id: "PR aprobado + merge"
```

| | 🟢 **main** | 🔵 **Rama (branch)** | 🟣 **Merge (fusionar)** |
|---|---|---|---|
| **Qué es** | La rama principal: la **versión oficial** del proyecto. | Una **copia de trabajo** que sale de main para **una tarea**. | **Unir** a main los cambios de una rama ya **aprobada**. |
| **Para qué** | Es lo que se publica en Render y lo que evalúa Integra2. Debe funcionar siempre. | Trabajar, equivocarte y corregir sin afectar a main ni a tus compañeros. | Que el trabajo revisado llegue a la versión oficial. |
| **Quién** | Nadie trabaja directo en ella. | Cada integrante, una rama por tarea (`12-registro-qr`). | El integrador; si no está, cualquier otro integrante. Nunca el autor sin aprobación. |
| **Se parece a** | 📄 La versión final del informe que se entrega. | ✏️ Tu borrador de una sección. | 📎 Pegar tu borrador revisado en la versión final. |

**Otros términos**

- **Commit:** una foto de tus cambios con un mensaje que dice qué hiciste; con `git push` sube a GitHub.
- **Pull Request (PR):** la solicitud en GitHub para integrar tu rama a main; ahí se ven, comentan y aprueban los cambios.
- **Revisión:** un compañero elige *Approve* (aprobar), *Request changes* (pedir cambios) o *Comment* (comentar).
- **Issue:** una tarea registrada en GitHub con responsable y fecha.
- **Conflicto:** dos ramas cambiaron las mismas líneas; el integrador lo resuelve con el autor, sin borrar trabajo ajeno.

## 3. Flujo de trabajo paso a paso

1. **Toma tu tarea.** En GitHub → *Issues*, busca el issue que te asignó el coordinador (ejemplo `#12`).
2. **Crea tu rama desde main actualizado:**
   ```bash
   git switch main
   git pull
   git switch -c 12-registro-qr
   ```
3. **Trabaja y haz commits en días distintos** (push el mismo día):
   ```bash
   git add mod_qr/
   git commit -m "Agrega vista de escaneo con lector USB #12"
   git push -u origin 12-registro-qr
   ```
4. **Abre el Pull Request** (*Compare & pull request*), base `main`, con `Closes #12`, qué cambiaste y cómo probarlo. Elige un revisor.
5. **Un compañero revisa:** *Files changed* → *Review changes* → *Approve* o *Request changes*. Si piden cambios, corrige en la misma rama y haz `git push`.
6. **El integrador hace el merge** (*Merge pull request* o *Squash and merge*) y borra la rama. Si no está en 48 h, lo hace otro integrante.
7. **Todos actualizan:**
   ```bash
   git switch main
   git pull
   git branch -d 12-registro-qr
   ```

> ⛔ **Prohibido:** `git push` a main, fusionar sin aprobación o hacer *force-push*. Integra2 lo detecta aunque GitHub no lo bloquee.
>
> 💡 Tus commits en tu rama **sí cuentan** para tu constancia desde que haces push.

## 4. Roles

### ¿Fijos o rotativos? Rotan en cada unidad

El rol se asigna al **iniciar cada unidad** y dura toda la unidad:

- **U1:** del 11 ene al 17 ene
- **U2:** del 18 ene al 31 ene
- **U3:** del 1 feb al 21 feb
- **U4:** del 22 feb al 1 mar

Integra2 ordena a los integrantes activos por **matrícula** (de menor a mayor) y rota. Se rota por unidad porque:

- **Es justo:** con 4 integrantes, cada quien pasa exactamente una vez por cada rol.
- **Es didáctico:** todos aprenden a coordinar, integrar, documentar y probar.
- **Da tiempo:** una unidad (1 a 3 semanas) alcanza para cumplir el rol completo.
- **Coincide con la evaluación:** Integra2 califica cada rol al cierre de su unidad.

**Equipo de 4**

| Posición | U1 (desde 11 ene) | U2 (desde 18 ene) | U3 (desde 1 feb) | U4 (desde 22 feb) |
|---|---|---|---|---|
| 1 | Coordinador | Integrador | Documentador | Revisor de calidad (QA) |
| 2 | Integrador | Documentador | Revisor de calidad (QA) | Coordinador |
| 3 | Documentador | Revisor de calidad (QA) | Coordinador | Integrador |
| 4 | Revisor de calidad (QA) | Coordinador | Integrador | Documentador |

**Equipo de 3 (sin QA)**

| Posición | U1 (desde 11 ene) | U2 (desde 18 ene) | U3 (desde 1 feb) | U4 (desde 22 feb) |
|---|---|---|---|---|
| 1 | Coordinador | Integrador | Documentador | Coordinador |
| 2 | Integrador | Documentador | Coordinador | Integrador |
| 3 | Documentador | Coordinador | Integrador | Documentador |

Posición 1 = la matrícula más baja. Tu rol de cada unidad aparece en tu portal. El rol es **adicional** a tu módulo independiente (QR, Cámara, Impresión o Análisis): todos programan su módulo, abren sus PR y revisan PR de compañeros.

### 📋 Coordinador

*Organiza el trabajo para que nadie se quede sin tarea.*

**¿Qué es?** Es quien planea y da seguimiento. No hace el trabajo de los demás: convierte los pasos de la unidad en tareas concretas, las reparte de forma pareja, vigila los tiempos y avisa a tiempo cuando algo se atrasa. Es el enlace del equipo con el docente.

**🚀 Al iniciar la unidad**

- Primer día de la unidad: abre la unidad en Integra2 (Reglas y Entregas) y la lee con el equipo: pasos, evidencias, entregables y fecha de cierre.
- Divide el trabajo en tareas pequeñas (de 1 a 3 días). Ejemplo: «Modelo Lectura en mod_qr», «Foto de la visita con tarjeta U2», «Sección de metodología del informe».
- Crea un issue por tarea en GitHub → Issues → New issue, con título claro, descripción de qué se entrega, criterio de «terminado» y fecha límite.
- Asigna cada issue en Assignees: al menos uno por integrante (incluido él). Reparte parejo: nadie con el triple de trabajo.
- Acomoda los issues en el tablero de GitHub Projects con las columnas Por hacer, En proceso, En revisión y Hecho.

**🔁 Durante la unidad**

- Al inicio de cada sesión de clase revisa el tablero con el equipo (5 minutos): qué hizo cada quien, qué sigue y qué lo detiene.
- Mueve o pide mover las tarjetas del tablero según avanzan los issues y los PR.
- Aplica la regla 48/72 h: a las 48 h sin avance comenta el issue y lo etiqueta «en riesgo»; a las 72 h lo reasigna a otro integrante y deja escrito por qué.
- Cuida que cada quien trabaje en su propio módulo y que los PR pendientes tengan revisor.
- Si alguien no responde o no aporta, avisa al docente con los issues como prueba (no espera al cierre).

**🏁 Antes del cierre**

- Dos días antes de la zona roja revisa en el portal qué evidencias, entregables y verificaciones de la app faltan, y crea issues para lo que falte.
- Verifica que todo lo de la unidad esté en main antes de la zona roja.
- Cierra los issues terminados y comenta los que no se cumplieron con el nombre del responsable: es la prueba para el docente y para el ajuste individual.

**📦 Lo que entrega (se ve en GitHub)**

- Issues de la unidad con responsable y fecha (al menos uno por integrante).
- Tablero de GitHub Projects actualizado.
- Comentarios de seguimiento en los issues atrasados o reasignados.

**🗓️ Ejemplo de su semana**

- Lunes (sesión): lee la unidad con el equipo y crea 6 issues: 2 para él, 1 para cada compañero y 1 compartido.
- Martes (sesión): revisa el tablero; Ana ya abrió su PR y Luis no ha empezado: le comenta su issue.
- Jueves: el issue de Luis cumple 48 h sin avance; lo etiqueta «en riesgo».
- Viernes: lo reasigna a Carla, deja el comentario y avisa al docente.

**🚫 Lo que NO le toca**

- Hacer el trabajo de los demás para «salvar» al equipo sin dejar registro.
- Quedarse sin tarea propia: también programa su módulo y abre sus PR.

> ✅ **Lo que revisa Integra2:** Al menos un issue creado por ti dentro de la unidad y asignado a cada integrante (incluido tú). Si no se cumple: **−5** sólo a quien tiene el rol.
>
> 💡 Un buen issue se puede terminar en 1 a 3 días. Si es más grande, divídelo.

### 🔀 Integrador

*Cuida que main siempre funcione.*

**¿Qué es?** Es el guardián de la rama main. Decide cuándo un PR aprobado está listo para entrar, hace el merge, resuelve los conflictos junto con el autor y comprueba que la app siga funcionando en Render después de cada cambio.

**🚀 Al iniciar la unidad**

- Comprueba que main esté sana: la app abre en Render, /integra2/estado.json responde y las pruebas pasan (python manage.py test).
- Confirma que main esté protegida (sin force-push y con PR obligatorio) y que el merge borre la rama automáticamente.
- Recuerda al equipo el flujo: rama por tarea, PR hacia main y revisión de otro integrante.

**🔁 Durante la unidad**

- Revisa los PR abiertos al menos una vez cada día de trabajo. Un PR aprobado no espera más de 48 h para el merge.
- Antes del merge confirma: tiene aprobación de alguien distinto al autor, la descripción dice qué cambió y cómo probarlo, y GitHub no marca conflictos.
- Si el cambio es grande, descarga la rama (git switch nombre-rama), corre las pruebas y abre la app en local.
- Hace el merge con «Merge pull request» o «Squash and merge» y borra la rama.
- Si hay conflictos, se sienta con el autor y los resuelven juntos; nunca borra trabajo ajeno para que «compile».
- Después de cada merge abre Render y espera el «Deploy live». Si el despliegue falla, avisa al autor y se corrige con otro PR (no con push directo).

**🏁 Antes del cierre**

- Antes de la zona roja confirma que todos los PR de la unidad estén fusionados o cerrados con un comentario.
- Verifica que /integra2/estado.json muestre el último commit de main y que la app conecte con TiDB.
- Avisa al equipo si queda algún PR sin aprobar a tiempo.

**📦 Lo que entrega (se ve en GitHub)**

- Merges de PR aprobados en la pestaña Pull requests (aparece como quien los fusionó).
- main funcionando y desplegada en Render.
- Comentarios en los PR con conflictos o con despliegue fallido.

**🗓️ Ejemplo de su semana**

- Martes: Ana abre el PR #14 y Beto lo aprueba; el integrador lo prueba, lo fusiona y revisa el Deploy live.
- Miércoles: el PR #15 de Luis choca con el #14; resuelven juntos el conflicto en 15 minutos.
- Viernes: un despliegue falla por una dependencia; avisa a Carla, que lo corrige con el PR #17.

**🚫 Lo que NO le toca**

- Fusionar su propio PR sin aprobación de otro integrante.
- Arreglar main con push directo: todo, incluso una corrección, va por PR.

> ✅ **Lo que revisa Integra2:** Fusionaste (merge) al menos un PR de un compañero dentro de la unidad. Si no se cumple: **−5** sólo a quien tiene el rol.
>
> 💡 Si no estás, cualquier otro integrante puede hacer el merge. Sólo a ti se te descuenta el rol.

### 📝 Documentador

*Deja constancia de lo que hace el equipo.*

**¿Qué es?** Es el responsable de que el trabajo se vea y se pueda comprobar: README, fotografías y capturas de evidencia, y el armado del informe. No redacta solo: junta lo que escribe cada integrante, le da formato y revisa que cumpla lo que pide Integra2.

**🚀 Al iniciar la unidad**

- Crea en el README la sección «## Unidad N» con la lista de evidencias que pide Integra2 (nombre exacto de cada archivo).
- Imprime la tarjeta de evidencia de la unidad con la impresora del equipo (Portal → Imprimir tarjeta de evidencia).
- Con el coordinador reparte quién redacta cada sección del informe y crea el archivo de trabajo en docs/uN/.

**🔁 Durante la unidad**

- Toma o recibe las fotos originales del celular (sin WhatsApp ni edición, para conservar la fecha EXIF), con la tarjeta visible.
- Las renombra con el nombre exacto (por ejemplo foto_visita.jpg), las sube a evidencias/uN/ por PR y las inserta en la sección de la unidad del README.
- Toma las capturas de pantalla pedidas (TiDB, Render, admin, tablero) sin mostrar contraseñas.
- Revisa en el portal que cada evidencia aparezca con ✅; si sale 🟡 o ❌, lee el motivo y la corrige.
- Va integrando al informe lo que cada integrante redacta, con formato uniforme y referencias APA 7, conforme avanza (no todo al final).

**🏁 Antes del cierre**

- Exporta el informe a PDF con el nombre exacto (docs/uN/informe_uN.pdf) y comprueba el tamaño mínimo.
- Revisa que los demás entregables de la unidad (diagramas, instrumento, CSV) estén en su carpeta con el nombre correcto.
- Hace una revisión final del README: todas las imágenes se ven y no hay evidencias repetidas.

**📦 Lo que entrega (se ve en GitHub)**

- Sección «## Unidad N» del README con todas las evidencias insertadas.
- Fotos y capturas en evidencias/uN/ con el nombre exacto.
- Informe en PDF y entregables en docs/uN/.

**🗓️ Ejemplo de su semana**

- Lunes: crea la sección «## Unidad 2» del README e imprime la tarjeta U2.
- Miércoles: en la visita toma foto_visita.jpg con la tarjeta y la sube ese mismo día por PR.
- Jueves: el portal marca captura_er.png con resolución baja; la vuelve a exportar en mejor calidad.
- Sábado: integra al informe las secciones de sus compañeros y genera el PDF.

**🚫 Lo que NO le toca**

- Escribir todo el informe solo: cada integrante redacta su parte.
- Subir fotos reenviadas por WhatsApp o editadas (pierden la fecha EXIF).

> ✅ **Lo que revisa Integra2:** Commits válidos tuyos en README.md, evidencias/uN/ o docs/uN/ en al menos 2 días distintos de la unidad. Si no se cumple: **−5** sólo a quien tiene el rol.
>
> 💡 Sube evidencias en cuanto existan: una foto tomada el último día puede quedar fuera por la fecha.

### 🔍 Revisor de calidad (QA) · sólo equipos de 4

*Encuentra los errores antes que el usuario.*

**¿Qué es?** QA viene de Quality Assurance (aseguramiento de la calidad). Es quien comprueba que lo que se entrega funciona: prueba la app como lo haría un usuario, corre las pruebas automáticas, prueba los dispositivos reales y revisa los PR con lupa antes de que entren a main. Sólo existe en equipos de 4.

**🚀 Al iniciar la unidad**

- Escribe en un issue la lista de casos de prueba de la unidad: qué debe pasar al escanear un QR, tomar una foto, imprimir una etiqueta o capturar una encuesta, y qué pasa con datos incorrectos.
- Prueba la versión actual en Render con esa lista y crea un issue por cada error que encuentre.

**🔁 Durante la unidad**

- Revisa al menos 2 PR de compañeros: descarga la rama (git switch nombre-rama), corre python manage.py test y prueba el cambio en la app.
- En la revisión deja comentarios concretos en las líneas con problema y elige Approve o Request changes; no aprueba sin probar.
- Prueba los dispositivos reales (lector QR, cámara e impresora) con la app publicada en Render, no sólo en local.
- Reporta cada error como issue con: pasos para reproducirlo, qué esperaba, qué pasó y una captura.
- Vuelve a probar cuando el autor dice que ya lo corrigió y cierra el issue si funciona.

**🏁 Antes del cierre**

- Hace una prueba completa de la app en Render con la lista de casos antes de la zona roja.
- Confirma que los errores reportados estén corregidos o, si no dio tiempo, documentados en el issue.
- Avisa al integrador si algo de main está roto antes del cierre.

**📦 Lo que entrega (se ve en GitHub)**

- Revisiones (Approve o Request changes) con comentarios en al menos 2 PR.
- Issues de errores con pasos, resultado esperado y captura.
- Lista de casos de prueba de la unidad.

**🗓️ Ejemplo de su semana**

- Lunes: escribe 8 casos de prueba del módulo QR y de la cámara.
- Martes: revisa el PR #14 de Ana; al escanear un folio inexistente la app marca error 500; pide cambios.
- Miércoles: Ana lo corrige; vuelve a probar y aprueba.
- Viernes: prueba la impresora con la app en Render y reporta que la etiqueta sale cortada (issue #19).

**🚫 Lo que NO le toca**

- Aprobar un PR sin probarlo sólo para cumplir.
- Corregir él mismo los errores de otros módulos: los reporta y el dueño los corrige.

> ✅ **Lo que revisa Integra2:** Revisaste al menos 2 PR distintos de compañeros (aprobar o pedir cambios). Si no se cumple: **−5** sólo a quien tiene el rol.
>
> 💡 Un buen reporte dice: qué hiciste, qué esperabas, qué pasó y una captura.

## 5. Qué resta Integra2

Por alumno y por unidad, de la parte técnica (0–100). Tope total de penalizaciones: 40 puntos.

| Situación | Resta |
|---|---|
| No tienes ningún Pull Request tuyo fusionado a main en la unidad con la aprobación de otro integrante (o del docente). | −10 |
| No revisaste (aprobar, pedir cambios o comentar) ningún Pull Request de un compañero en la unidad. | −5 |
| Por cada commit tuyo que llegó a main sin Pull Request (desde la Unidad 2); máximo 10 puntos. | −2 |
| No cumpliste la tarea verificable de tu rol de la unidad (coordinador, integrador, documentador o QA). | −5 |

- Un PR **cuenta para su autor** si se fusionó a main dentro de la unidad y antes lo aprobó otro integrante o el docente (@BernardoPD).
- Una **revisión cuenta** si es *Approve*, *Request changes* o *Comment* en un PR de un compañero, dentro de la unidad.
- Un **commit directo** es uno tuyo que llegó a main sin PR. En la Unidad 1 sólo se avisa; desde la Unidad 2 resta.
- Si GitHub no responde al evaluar, **no se descuenta nada** por colaboración.

## 6. Si alguien no cumple, no afecta a los demás

- ✅ **Aprobar no depende de una persona:** cualquier compañero aprueba; si nadie responde en 48 h, pide la revisión al docente (@BernardoPD).
- ✅ **El merge tampoco:** si el integrador falta, otro integrante fusiona; sólo el integrador pierde su rol.
- ✅ **Tu módulo es tuyo:** los puntos del módulo y la constancia son individuales.
- ⚠️ **Regla 48/72 h:** a las 48 h sin avance el coordinador marca el issue «en riesgo»; a las 72 h se reasigna y el crédito es de quien lo entregó.
- ⚠️ **Partes de equipo** (evidencias, entregables, app): si alguien no aportó, avisen al docente con los issues como prueba; puede aplicar un ajuste individual.
- ℹ️ **Coevaluación:** el docente puede pedirla en las sesiones de evaluación.

## 7. Mínimos por unidad

| Unidad | Trabajo | Días con commit válido | PR propios aprobados | PR revisados | Push directo a main |
|---|---|---|---|---|---|
| U1 | 11 ene – 17 ene | 3 (1 por semana obligatoria) | 1 | 1 | sólo aviso |
| U2 | 18 ene – 31 ene | 5 (1 por semana obligatoria) | 1 | 1 | resta |
| U3 | 1 feb – 21 feb | 7 (1 por semana obligatoria) | 1 | 1 | resta |
| U4 | 22 feb – 1 mar | 3 (1 por semana obligatoria) | 1 | 1 | resta |

🏁 **¿Terminan antes?** Los mínimos de PR, revisión y rol se cumplen en cuanto los alcanzan. La constancia sí pide un día con commit válido en cada semana obligatoria.

## 8. Dónde constatarlo

| Quién | Dónde | Qué ve |
|---|---|---|
| Alumno | Portal de Integra2 → *Colaboración y mi rol* | Su rol, el de sus compañeros y ✅/❌ de cada regla (cada 2 h). |
| Alumno | Correo de resultados | Cada descuento con su motivo. |
| Equipo | GitHub → *Pull requests* (`is:pr is:merged`) e *Issues* | Quién abrió, aprobó y fusionó; tareas y responsables. |
| Equipo | GitHub → *Insights → Contributors* | Commits por persona. |
| Docente | Panel docente → equipo → unidad | PR, commits directos, issues, rol y descuentos de cada integrante. |

## 9. Configurar GitHub

- **Settings → General → Pull Requests:** *Allow merge commits* o *Allow squash merging* y *Automatically delete head branches*.
- **Settings → Rules → Rulesets** para `main`: *Restrict deletions*, *Block force pushes*, *Require a pull request before merging* con 1 aprobación.
- Edita `.github/CODEOWNERS` con el usuario de cada dueño de módulo.

**Plantilla de descripción del PR**

```markdown
Closes #12

## Qué cambié
- Vista de escaneo con lector USB en mod_qr

## Cómo probarlo
1. python manage.py test mod_qr
2. Abrir /qr/escanear/ y leer una etiqueta

## Evidencia
(captura o enlace a Render)
```

---
*Generado desde las reglas de Integra2 (`python manage.py exportar_guia`). Si hay diferencia, manda lo que dice Integra2.*
