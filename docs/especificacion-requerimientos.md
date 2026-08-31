# Especificación de Requerimientos

## 1. Descripción del sistema

## 2. Integrantes

- Nombre:
- Nombre:
- Nombre:
- Nombre:
- Nombre:

## 3. Requerimientos Funcionales

### RF-01 - Registro de tutoría

#### Resumen

Permite a un profesor registrar una nueva tutoría académica en la plataforma, indicando la información necesaria para que los estudiantes puedan encontrarla posteriormente.

#### Entradas

| Entrada | Tipo de dato | Descripción |
|---|---|---|
| codigoProfesor | String | Código identificador del profesor que ofrece la tutoría |
| tema | String | Tema o asignatura de la tutoría |
| fecha | Date | Fecha programada para la tutoría |
| horaInicio | Time | Hora de inicio de la tutoría |
| cantidadMaxima | Integer | Cantidad máxima de estudiantes que podrán asistir |

#### Reglas o condiciones

- La fecha de la tutoría no puede ser anterior a la fecha actual.
- La cantidad máxima de participantes debe estar entre 1 y 10 estudiantes.

#### Salidas

| Salida | Tipo de dato | Descripción |
|---|---|---|
| idTutoria | String | Identificador único asignado a la tutoría creada |
| mensajeConfirmacion | String | Mensaje que informa al profesor que la tutoría fue creada correctamente |

#### Resultado esperado

La tutoría queda registrada en el sistema con un identificador único asignado automáticamente y se encuentra disponible para ser consultada por los estudiantes.


### RF-02 - Consulta de tutorías disponibles

#### Resumen
Permite a los estudiantes buscar y consultar las tutorías académicas que se encuentran disponibles para una fecha específica, con la opción de filtrar por asignatura o tema de interés.

#### Entradas

| Entrada | Tipo de dato | Descripción |
|---|---|---|
| fecha | Date | Fecha que se desea consultar para buscar tutorías |
| asignatura | String | Asignatura de interés (opcional) |
| tema | String | Tema específico de interés (opcional) |

#### Reglas o condiciones

- La fecha es un parámetro obligatorio para la búsqueda.
- La asignatura y el tema son parámetros opcionales.
- El sistema debe buscar tutorías que coincidan con la fecha proporcionada.
- Si se proporciona asignatura o tema, debe filtrar adicionalmente por estos criterios.

#### Salidas

| Salida | Tipo de dato | Descripción |
|---|---|---|
| listaTutorias | Array | Lista de tutorías encontradas con sus detalles |
| mensajeInformacion | String | Mensaje informativo si no se encuentran tutorías |

Para cada tutoría en la lista se muestra:
- idTutoria: String
- tema: String
- profesorResponsable: String
- fecha: Date
- hora: Time
- cuposDisponibles: Integer

#### Resultado esperado
El sistema muestra al estudiante todas las tutorías disponibles que coinciden con los criterios de búsqueda, incluyendo el identificador, tema, profesor, fecha, hora y cupos disponibles. Si no se encuentran tutorías, se muestra un mensaje informativo indicando que no hay resultados.


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


### RF-04 - Cancelacion de inscripcion

#### Resumen

Permite a un estudiante inscrito cancelar su participacion en una tutoria, lo que elimina su inscripcion del sistema y libera un cupo para que este disponible para otros estudiantes.

#### Entradas

| Entrada | Tipo de dato | Descripcion |
|---|---|---|
| codigoEstudiante | String | Codigo estudiantil del estudiante que desea cancelar su inscripcion |
| idTutoria | String | Identificador unico de la tutoria a la cual esta inscrito |

#### Reglas o condiciones

- Debe existir una inscripcion previa y activa del estudiante en la tutoria especificada.
- La tutoria aun no debe haber comenzado (la fecha y hora programadas de inicio de la tutoria deben ser posteriores a la fecha y hora actual).

#### Salidas

| Salida | Tipo de dato | Descripcion |
|---|---|---|
| mensajeConfirmacion | String | Mensaje de exito informando que la inscripcion fue cancelada correctamente |
| mensajeError | String | Mensaje que indica el motivo por el cual no se pudo realizar la cancelacion |

#### Resultado esperado

La inscripcion del estudiante es eliminada del sistema, el cupo en la tutoria se libera (incrementando la cantidad de cupos disponibles en 1) y se muestra un mensaje de confirmacion exitoso o de error indicando la causa del fallo.


## 4. Gestion de Versiones

### Ramas utilizadas

- main
- develop
- feature/rf01-registro-tutoria
- feature/rf02-consulta-tutorias
- feature/rf03-inscripcion-tutoria
- feature/rf04-cancelacion-inscripcion

### Proceso de integracion

El flujo de trabajo implementado siguio la metodologia GitFlow:

1. Se establecio la rama `main` como la linea base con la estructura inicial.
2. Se creo la rama `develop` a partir de `main` para centralizar el desarrollo.
3. Cada integrante desarrollo su requerimiento en una rama `feature/*` independiente originada desde `develop`.
4. Al finalizar cada requerimiento, se integraron los cambios de vuelta a `develop` mediante Pull Requests.
5. Finalmente, se integrara la rama `develop` de regreso a `main` para consolidar la version estable y final.

Esquema del flujo:
```text
main -> develop -> feature/* -> develop -> main
```

### Conflictos encontrados

- Se presento un conflicto de estructura debido a que inicialmente se creo el documento en la raiz con el nombre `docs` (como archivo plano) en lugar de una carpeta `docs/` con el archivo `especificacion-requerimientos.md`. Esto se resolvio creando el directorio correspondiente y reubicando el archivo en la rama `develop`.
- No se presentaron otros conflictos de fusion (merge) durante la integracion de las ramas de caracteristicas (features).