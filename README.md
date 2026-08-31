# TALLER

# Markdown + GitFlow: Documentación y Gestión de Requerimientos

---

## Objetivo del taller

Aplicar un flujo básico de trabajo basado en GitFlow para gestionar cambios sobre un documento compartido, utilizando Markdown como formato para documentar requerimientos funcionales.

Durante el taller se trabajarán los siguientes conceptos:

- Creación y edición de archivos Markdown (`.md`).
- Organización de información mediante títulos, listas y tablas.
- Control de versiones.
- Uso de las ramas `main`, `develop` y `feature/*`.
- Trabajo colaborativo sobre un mismo repositorio.
- Integración de cambios mediante Pull Requests.
- Especificación básica de requerimientos funcionales.

> La especificación de requerimientos utilizada en este taller corresponde a conceptos trabajados previamente en Ingeniería de Software I. El propósito principal del ejercicio es utilizar estos artefactos para practicar Markdown, control de versiones y GitFlow.

---

# 1. Antes de comenzar: ¿qué es un archivo Markdown?

Markdown es un formato de texto que permite organizar y dar estructura a un documento utilizando una sintaxis sencilla.

Los archivos Markdown utilizan la extensión:

`nombre-archivo.md`

GitHub interpreta automáticamente esta sintaxis y muestra el contenido de manera organizada.

Durante este taller utilizaremos Markdown para construir el documento de especificación de requerimientos del sistema.

---

## 1.1. Títulos y subtítulos

Los títulos se crean utilizando el símbolo `#`.

```md
# Título principal

## Título de segundo nivel

### Título de tercer nivel

#### Título de cuarto nivel
```

El número de símbolos `#` representa el nivel del título.

---

## 1.2. Texto en negrita

Para resaltar una palabra o frase:

```md
**Texto en negrita**
```

Resultado:

**Texto en negrita**

---

## 1.3. Listas

Para crear una lista:

```md
- Elemento 1
- Elemento 2
- Elemento 3
```

También se pueden crear listas numeradas:

```md
1. Primer paso
2. Segundo paso
3. Tercer paso
```

---

## 1.4. Tablas

Las tablas serán uno de los elementos más importantes de este taller.

Ejemplo:

```md
| Campo | Tipo de dato | Descripción |
|---|---|---|
| nombre | String | Nombre de la persona |
| edad | Integer | Edad de la persona |
```

GitHub mostrará la información de forma tabular:

| Campo | Tipo de dato | Descripción |
|---|---|---|
| nombre | String | Nombre de la persona |
| edad | Integer | Edad de la persona |

---

## 1.5. Código o términos técnicos

Para resaltar nombres de archivos, ramas, comandos o elementos técnicos se pueden utilizar comillas invertidas:

```md
`develop`
```

Por ejemplo:

La rama `develop` contiene el trabajo que está siendo integrado por el equipo.

---

## 1.6. Enlaces

Para agregar un enlace:

```md
[Texto que se mostrará](https://ejemplo.com)
```

---

# 2. Organización del trabajo

El taller se realizará en grupos de **4 o 5 estudiantes**.

Cada grupo trabajará en un único repositorio.

Todos los integrantes deberán participar en el proceso de control de versiones.

El equipo deberá utilizar obligatoriamente las siguientes ramas:

```text
main
develop
feature/*
```

No se permite desarrollar directamente sobre `main`.

Cada requerimiento deberá trabajarse en una rama `feature/*` independiente.

---

# 3. Roles dentro del equipo

El sistema contiene **cuatro requerimientos funcionales principales**.

Cada requerimiento será responsabilidad de un integrante.

### Si el grupo tiene 4 integrantes

Cada integrante será responsable de un requerimiento.

Uno de los integrantes tendrá adicionalmente el rol de **responsable de integración**.

### Si el grupo tiene 5 integrantes

- 4 integrantes serán responsables de un requerimiento cada uno.
- 1 integrante será el responsable principal de integración.

El responsable de integración deberá:

- Verificar que las ramas se hayan creado correctamente.
- Revisar los Pull Requests.
- Coordinar la integración de las ramas `feature/*` hacia `develop`.
- Verificar la consistencia del documento completo.
- Gestionar la integración final de `develop` hacia `main`.
- Apoyar la resolución de conflictos si estos aparecen.

> El responsable de integración no debe modificar directamente en `main` el trabajo realizado por sus compañeros.

---

# 4. Sistema a analizar

## Plataforma de Tutorías Académicas

La Universidad desea implementar una plataforma que facilite la organización de las tutorías académicas ofrecidas por sus profesores.

Actualmente, gran parte de estas tutorías se coordinan de manera informal entre profesores y estudiantes, por lo que se desea contar con un sistema que permita administrar la información de forma centralizada.

Cuando un profesor desea ofrecer una tutoría, deberá poder registrar la información necesaria para que posteriormente los estudiantes puedan encontrarla. Para hacerlo deberá indicar su código de profesor, el tema de la tutoría, la fecha, la hora de inicio y la cantidad máxima de estudiantes que podrá atender. No se permitirá programar una tutoría para una fecha anterior a la fecha actual y la cantidad máxima de participantes deberá estar entre 1 y 10 estudiantes. Cuando el registro sea exitoso, el sistema asignará un identificador único a la tutoría e informará al profesor que esta fue creada correctamente.

Los estudiantes podrán consultar las tutorías que se encuentran disponibles. Para realizar la búsqueda deberán indicar la fecha que desean consultar y, de manera opcional, podrán indicar una asignatura o tema de interés. Por cada tutoría encontrada, el sistema deberá mostrar su identificador, el tema, el profesor responsable, la fecha, la hora y la cantidad de cupos que todavía se encuentran disponibles. En caso de no encontrar tutorías que correspondan con la búsqueda, el estudiante deberá recibir un mensaje informándolo.

Cuando un estudiante encuentre una tutoría de su interés podrá solicitar su inscripción utilizando su código estudiantil y el identificador de la tutoría. Para completar la inscripción, el estudiante deberá encontrarse activo en la Universidad, la tutoría deberá existir, deberá tener al menos un cupo disponible y el estudiante no podrá encontrarse previamente inscrito en ella. Cuando la inscripción sea exitosa, el sistema deberá registrarla, actualizar la cantidad de cupos disponibles y mostrar un mensaje de confirmación. Si alguna de las condiciones necesarias no se cumple, la inscripción no deberá realizarse y el sistema deberá informar la situación.

Finalmente, un estudiante que ya se encuentre inscrito podrá cancelar su participación utilizando su código estudiantil y el identificador de la tutoría. La cancelación solamente podrá realizarse si existe una inscripción previa y si la tutoría aún no ha comenzado. Cuando la cancelación sea realizada correctamente, el sistema deberá eliminar la inscripción, liberar nuevamente el cupo correspondiente e informar al estudiante que la operación fue exitosa. Si no es posible realizarla, deberá mostrarse un mensaje indicando el motivo.

---

# 5. Actividad de análisis

A partir del enunciado anterior, el equipo deberá identificar los **cuatro requerimientos funcionales principales**.

Cada requerimiento deberá identificarse utilizando la siguiente nomenclatura:

```text
RF-01
RF-02
RF-03
RF-04
```

El equipo deberá asignar un requerimiento a cada integrante antes de comenzar el desarrollo.

Para cada requerimiento se deberá identificar:

1. Nombre del requerimiento.
2. Resumen.
3. Entradas.
4. Tipo de dato de cada entrada.
5. Reglas o condiciones necesarias.
6. Salidas.
7. Tipo de dato de cada salida.
8. Resultado esperado.

---

## ¿Cómo distinguir estos elementos?

### Entradas

Son los datos que el sistema necesita recibir para ejecutar la funcionalidad.

Pregúntense:

> ¿Qué información necesita recibir el sistema para realizar esta acción?

---

### Reglas o condiciones

Son restricciones o condiciones que deben cumplirse durante la ejecución del requerimiento.

Pregúntense:

> ¿Qué debe cumplirse para que esta funcionalidad pueda ejecutarse correctamente?

---

### Salidas

Son los datos o información que el sistema devuelve o presenta como consecuencia de la operación.

Pregúntense:

> ¿Qué información recibe el usuario como respuesta?

---

### Resultado esperado

Representa el efecto que debe producirse en el sistema una vez ejecutada correctamente la funcionalidad.

Pregúntense:

> ¿Qué cambió en el sistema después de realizar la operación?

---

# 6. PASO 0 – Crear la línea base antes de aplicar GitFlow

Antes de crear `develop` o cualquier rama `feature/*`, el equipo deberá preparar una **línea base inicial del proyecto**.

La rama `main` no debe encontrarse vacía al iniciar el trabajo.

El equipo deberá:

1. Crear el repositorio.
2. Verificar que exista la rama `main`.
3. Crear la carpeta:

```text
docs/
```

4. Dentro de esta carpeta crear:

```text
docs/especificacion-requerimientos.md
```

5. Agregar únicamente la estructura base indicada a continuación.

---

## Estructura inicial obligatoria

```md
# Especificación de Requerimientos

## 1. Descripción del sistema

## 2. Integrantes

- Nombre:
- Nombre:
- Nombre:
- Nombre:
- Nombre:

## 3. Requerimientos Funcionales

### RF-01 - [Nombre del requerimiento]

#### Resumen

#### Entradas

| Entrada | Tipo de dato | Descripción |
|---|---|---|

#### Reglas o condiciones

#### Salidas

| Salida | Tipo de dato | Descripción |
|---|---|---|

#### Resultado esperado


### RF-02 - [Nombre del requerimiento]

#### Resumen

#### Entradas

| Entrada | Tipo de dato | Descripción |
|---|---|---|

#### Reglas o condiciones

#### Salidas

| Salida | Tipo de dato | Descripción |
|---|---|---|

#### Resultado esperado


### RF-03 - [Nombre del requerimiento]

#### Resumen

#### Entradas

| Entrada | Tipo de dato | Descripción |
|---|---|---|

#### Reglas o condiciones

#### Salidas

| Salida | Tipo de dato | Descripción |
|---|---|---|

#### Resultado esperado


### RF-04 - [Nombre del requerimiento]

#### Resumen

#### Entradas

| Entrada | Tipo de dato | Descripción |
|---|---|---|

#### Reglas o condiciones

#### Salidas

| Salida | Tipo de dato | Descripción |
|---|---|---|

#### Resultado esperado


## 4. Gestión de Versiones

### Ramas utilizadas

### Proceso de integración

### Conflictos encontrados
```

---

Una vez creada esta estructura, realizar un commit en `main`.

Commit sugerido:

```text
docs(setup): crea estructura base de especificacion
```

> En este momento todavía NO deben desarrollar los requerimientos.

La rama `main` contiene solamente la estructura inicial acordada por el equipo.

---

# 7. Implementación de GitFlow

El flujo que utilizaremos durante el taller será:

```text
                  feature/rf01
                 /
main → develop ─ feature/rf02
                 \
                  feature/rf03
                   \
                    feature/rf04
```

Posteriormente:

```text
feature/* → develop → main
```

---

# 8. PASO 1 – Crear la rama `develop`

Una vez que la estructura base se encuentre en `main`, el grupo deberá crear:

```text
develop
```

La rama `develop` debe crearse **a partir de `main`**.

En adelante, esta será la rama utilizada para integrar el trabajo que está realizando el equipo.

---

# 9. PASO 2 – Crear las ramas `feature/*`

Cada integrante deberá crear su propia rama desde `develop`.

Ejemplo:

```text
feature/rf01-registro-tutoria
feature/rf02-consulta-tutorias
feature/rf03-inscripcion-tutoria
feature/rf04-cancelacion-inscripcion
```

Los nombres anteriores son únicamente un ejemplo.

El equipo deberá identificar primero los requerimientos encontrados en el enunciado y establecer nombres adecuados para sus ramas.

> Todas las ramas `feature/*` deben crearse desde `develop`, NO desde `main`.

---

# 10. PASO 3 – Trabajo individual

Cada integrante deberá trabajar **únicamente en la sección correspondiente al requerimiento que le fue asignado** dentro del archivo:

```text
docs/especificacion-requerimientos.md
```

Por ejemplo, la persona responsable de `RF-02` deberá completar:

```md
### RF-02 - [Nombre del requerimiento]

#### Resumen

...

#### Entradas

...

#### Reglas o condiciones

...

#### Salidas

...

#### Resultado esperado

...
```

No deberá desarrollar los demás requerimientos.

---

# 11. Estructura esperada para cada requerimiento

Todos los requerimientos deben conservar la misma estructura.

## RF-XX – Nombre del requerimiento

### Resumen

Explicar brevemente qué debe permitir realizar el sistema.

El resumen debe describir la funcionalidad de manera clara y concisa.

### Entradas

Identificar la información que necesita recibir el sistema.

Utilizar la siguiente tabla:

```md
| Entrada | Tipo de dato | Descripción |
|---|---|---|
| datoEjemplo | String | Descripción del dato |
```

### Reglas o condiciones

Identificar las condiciones que deben cumplirse para ejecutar correctamente el requerimiento.

Utilizar una lista:

```md
- Condición 1.
- Condición 2.
- Condición 3.
```

### Salidas

Identificar la información que devuelve o presenta el sistema.

```md
| Salida | Tipo de dato | Descripción |
|---|---|---|
| resultado | String | Descripción de la salida |
```

### Resultado esperado

Describir qué debe ocurrir en el sistema después de ejecutar exitosamente el requerimiento.

---

# 12. PASO 4 – Realizar commits

Cada estudiante deberá realizar al menos un commit significativo desde su rama `feature/*`.

Los mensajes deben indicar claramente cuál fue el cambio realizado.

Formato recomendado:

```text
tipo(area): descripcion del cambio
```

Ejemplos:

```text
docs(rf01): agrega especificacion del requerimiento
docs(rf02): documenta entradas y salidas
docs(rf03): agrega reglas de inscripcion
fix(rf04): corrige tipos de datos
```

Evitar mensajes como:

```text
cambios
actualizacion
archivo
commit 1
trabajo
```

El mensaje del commit debe permitir entender qué modificación se realizó.

---

# 13. PASO 5 – Integrar cada `feature` en `develop`

Cuando un estudiante considere terminado su requerimiento deberá crear un Pull Request:

```text
feature/rfXX → develop
```

Antes de realizar el merge, el responsable de integración deberá revisar:

- Que el requerimiento asignado esté completo.
- Que tenga nombre y resumen.
- Que se hayan identificado las entradas.
- Que las entradas incluyan tipos de datos.
- Que se hayan identificado las reglas o condiciones.
- Que se hayan identificado las salidas.
- Que las salidas incluyan tipos de datos.
- Que exista un resultado esperado.
- Que la estructura Markdown sea correcta.
- Que el estudiante no haya modificado accidentalmente otro requerimiento.

Una vez revisado, podrá integrarse a `develop`.

---

# 14. PASO 6 – Revisar el documento integrado

Cuando todas las ramas `feature/*` hayan sido integradas, el equipo deberá revisar el archivo completo desde `develop`.

El documento deberá contener:

```text
RF-01 ✓
RF-02 ✓
RF-03 ✓
RF-04 ✓
```

Todos deben conservar una estructura consistente.

El equipo deberá revisar especialmente:

- Coherencia entre los requerimientos.
- Nombres utilizados.
- Formato de las tablas.
- Tipos de datos.
- Reglas identificadas.
- Ortografía y redacción.
- Uso adecuado de Markdown.
- Información duplicada o contradictoria.

---

# 15. Gestión de posibles conflictos

Durante la integración puede ocurrir que Git detecte modificaciones realizadas por varias personas sobre una misma parte del archivo.

Esto se conoce como un **conflicto de merge**.

Si ocurre un conflicto:

1. No eliminar automáticamente los cambios de los compañeros.
2. Identificar qué modificaciones provienen de cada rama.
3. Revisar cuál información debe conservarse.
4. Construir la versión final del contenido.
5. Guardar la solución.
6. Registrar el cambio.
7. Continuar con el proceso de integración.

En la sección:

```md
### Conflictos encontrados
```

el equipo deberá indicar si tuvo conflictos.

Si no existieron:

```md
No se presentaron conflictos durante la integración.
```

Si existieron, describir brevemente:

- Qué archivos o secciones entraron en conflicto.
- Qué ramas estaban involucradas.
- Cómo decidió el equipo resolverlo.

---

# 16. PASO 7 – Documentar el uso de GitFlow

En la sección:

```md
## 4. Gestión de Versiones
```

el equipo deberá documentar el proceso realizado.

### Ramas utilizadas

Listar las ramas creadas.

Ejemplo:

```md
- main
- develop
- feature/rf01-...
- feature/rf02-...
- feature/rf03-...
- feature/rf04-...
```

### Proceso de integración

Explicar brevemente el flujo seguido por el grupo.

Por ejemplo:

```text
main
   ↓
develop
   ↓
feature/*
   ↓
develop
   ↓
main
```

No es necesario realizar una explicación extensa.

### Conflictos encontrados

Indicar si durante la integración se presentaron conflictos y cómo fueron resueltos.

---

# 17. PASO 8 – Integración final

Cuando todos los requerimientos se encuentren integrados y revisados en `develop`, el responsable de integración deberá crear el Pull Request final:

```text
develop → main
```

Antes de aprobarlo, todo el equipo deberá verificar el documento.

Una vez aprobado:

```text
feature/rf01 ─┐
feature/rf02 ─┤
feature/rf03 ─┼──→ develop ───→ main
feature/rf04 ─┘
```

La versión encontrada en `main` representará la versión final y estable del entregable del taller.

---

# 18. Resultado esperado del repositorio

Al finalizar, el repositorio deberá contener como mínimo:

```text
repositorio/
│
├── README.md
│
└── docs/
    └── especificacion-requerimientos.md
```

Además, en el historial del repositorio deberán poder identificarse:

- La rama `main`.
- La rama `develop`.
- Las cuatro ramas `feature/*`.
- Los commits realizados por los integrantes.
- Los Pull Requests desde `feature/*` hacia `develop`.
- El Pull Request final desde `develop` hacia `main`.

---

# 19. Entregable

Cada grupo deberá entregar el enlace de su repositorio.

Se verificará:

| Aspecto | Evidencia esperada |
|---|---|
| Markdown | Documento organizado mediante títulos, listas y tablas |
| Análisis | Cuatro requerimientos identificados a partir del enunciado |
| Especificación | Resumen, entradas, tipos de datos, reglas, salidas y resultado |
| GitFlow | Uso de `main`, `develop` y `feature/*` |
| Trabajo individual | Commits y rama correspondiente a cada requerimiento |
| Integración | Pull Requests desde las features hacia `develop` |
| Versión final | Integración de `develop` hacia `main` |
| Trabajo colaborativo | Participación identificable de los integrantes |

---

# 20. Reflexión final

Responder en grupo:

1. ¿Qué diferencia encontraron entre trabajar directamente en `main` y trabajar mediante ramas `feature/*`?
2. ¿Cuál consideran que es el propósito de la rama `develop`?
3. ¿Qué ventaja tiene que cada funcionalidad o cambio tenga su propia rama?
4. ¿Qué podría ocurrir en un proyecto si todos los integrantes modificaran directamente la versión estable?
5. ¿Cómo ayuda Markdown a mantener organizada la documentación dentro de un repositorio?
6. ¿Qué responsabilidad tiene la persona encargada de integrar los cambios del equipo?

---

## Recuerden

Una rama `feature/*` representa un cambio o trabajo específico.

`develop` permite reunir y revisar el trabajo que se encuentra en construcción.

`main` representa la versión estable que el equipo ha decidido consolidar.

El objetivo no es solamente lograr que todos los archivos estén en el repositorio, sino comprender **cómo se puede controlar e integrar el trabajo realizado por varias personas sobre un mismo producto**.