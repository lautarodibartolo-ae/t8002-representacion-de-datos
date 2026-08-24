# La tabla del trabajo final

`capacitaciones.csv` es la tabla del trabajo final: **28 filas y 9 columnas**. Registra
inscripciones a cursos de capacitación de un municipio. Es un dato inventado, y está limpio: no hay
nada que corregir, solo hay que rediseñarlo.

Es otro dominio a propósito. Tiene la misma clase de problemas que el relevamiento de las clases 1
a 3, así que el método se traslada, pero las respuestas no se pueden copiar. Se construye con un
script local, que no forma parte del repositorio publicado.

## El otro archivo de la carpeta

`prestamos.csv` es el caso del notebook de esta clase: **10 filas y 7 columnas**, diez préstamos de
una biblioteca. No es la tabla del trabajo final. Está acá porque el notebook resuelve las cinco
piezas sobre él, para mostrar qué forma tiene una entrega terminada. Tiene la clave compuesta
`socio_id` más `isbn`, dependencias parciales de las dos mitades y la transitiva
`editorial` → `editorial_ciudad`, y **no tiene columna multivalor**: su primera forma normal sale
gratis, y eso el notebook lo avisa.

## Qué contiene

**5 cursos, 8 alumnos, 3 sedes, 4 materiales y 28 inscripciones.** Un alumno se inscribe en varios
cursos y un curso tiene varios alumnos, así que la clave de una fila es el par
`curso_codigo` más `dni_alumno`.

## Los problemas que tiene que encontrar el estudiante

Esta lista es para el docente. **No está en la consigna.**

| Qué | Dónde |
|---|---|
| Redundancia: el nombre del curso y su sede se repiten en cada inscripción | `curso_nombre`, `sede` |
| Redundancia: el nombre del alumno se repite en cada inscripción | `alumno_nombre` |
| Dependencia parcial de la primera mitad de la clave | `curso_codigo` → `curso_nombre`, `sede`, `materiales` |
| Dependencia parcial de la segunda mitad de la clave | `dni_alumno` → `alumno_nombre` |
| Dependencia transitiva | `sede` → `sede_direccion` |
| Columna multivalor | `materiales`, con hasta tres valores separados por `;` |
| Nulos con significado | `nota` vacía en cuatro filas: el alumno no terminó la cursada |

El diseño esperado en tercera forma normal tiene **seis tablas**: `sede`, `curso`, `alumno`,
`inscripcion`, `material` y `curso_material`. Es la misma cantidad que el relevamiento de las
clases 1 a 3, y no es casualidad: la consigna es el mismo ejercicio sobre otro caso.

Un estudiante puede llegar a cinco tablas si deja los materiales como una tabla sola, sin la tabla
que conecta, y a siete si además separa el tipo de material. Las dos variantes se aceptan si están
justificadas. Lo que se evalúa es la justificación, no la cantidad de tablas.

Un detalle para la devolución: al rearmar la columna `materiales` desde las dos tablas, el orden
que reconstruye las 28 filas exactas es `cuadernillo, manual, planillas, pendrive`. Con el orden de
aparición en los datos, DAT-201 vuelve como `manual;pendrive;planillas` en lugar de
`manual;planillas;pendrive`. No es un error del diseño: el orden dentro de la celda no era un dato,
y conviene aceptarlo así si el estudiante lo nota.
