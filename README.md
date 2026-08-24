# T8002 — Representación de datos

Taller de nivelación de 12 horas de cursada repartidas en cuatro clases. El material de cada clase
es un apunte en PDF y un notebook de Google Colab que lo acompaña. El botón abre el notebook en
Colab, sin instalar nada.

| Clase | Modalidad | Notebook |
|---|---|---|
| 1 — Bases de datos, DBMS y claves | Asincrónica | [![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/lautarodibartolo-ae/t8002-representacion-de-datos/blob/main/clase-1-bases-y-claves/01_bases_y_claves.ipynb) |
| 2 — Fases de diseño e integridad referencial | Sincrónica | [![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/lautarodibartolo-ae/t8002-representacion-de-datos/blob/main/clase-2-diseno-e-integridad/02_diseno_e_integridad.ipynb) |
| 3 — Dependencias funcionales y normalización | Sincrónica | [![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/lautarodibartolo-ae/t8002-representacion-de-datos/blob/main/clase-3-dependencias-y-normalizacion/03_dependencias_y_normalizacion.ipynb) |
| 4 — Trabajo final | Asincrónica | [![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/lautarodibartolo-ae/t8002-representacion-de-datos/blob/main/clase-4-trabajo-final/04_trabajo_final.ipynb) |

## De qué se trata

Representación de datos es un taller de nivelación de la Especialización en Inteligencia de Datos
para la Gestión Estratégica. Es una introducción a los conceptos de bases de datos: qué es una base
de datos, en qué se diferencia del almacenamiento de archivos y qué hace un sistema de gestión de
bases de datos (DBMS). Y cómo se diseña la estructura de un conjunto de datos, para que se lo pueda
consultar y auditar.

El taller es el paso siguiente al T8001. Allí el conjunto de datos quedó limpio en una sola tabla.
Acá se pregunta si esa tabla plana es la estructura correcta, y la respuesta es que casi nunca lo
es.

El alcance es conceptual, y es una decisión deliberada. **No se escribe SQL ni se implementa
ninguna base de datos.** El taller nombra el vocabulario, muestra los problemas y explica los
criterios de diseño. La idea es que los conceptos ya suenen conocidos al llegar a la asignatura
Modelado de datos, que es donde se implementan. El eje es el criterio de diseño y no la
herramienta.

Las clases 1 y 4 son asincrónicas y cada estudiante las recorre a su ritmo. Las clases 2 y 3 son
encuentros virtuales sincrónicos teórico-prácticos, y el docente recorre el notebook en vivo,
ejecutando cada celda.

Los notebooks son **demostraciones para ejecutar y mirar**. No traen actividades ni ejercicios: cada
celda muestra un concepto del apunte sobre datos concretos, y el resultado se lee justo abajo. Las
herramientas son `pandas`, la misma del T8001, y la biblioteca estándar. Un `merge` de `pandas`
muestra qué hace un cruce de dos tablas, y una comparación de columnas muestra qué revisa una clave
foránea. Donde el concepto se podía mostrar con lo que ya se sabe, no se agregó una herramienta
nueva.

Las tres primeras clases usan un mismo conjunto de datos: el relevamiento de hogares del taller
T8001, que llega como una sola tabla plana con redundancia y sale como un diseño de seis tablas. El
trabajo final es breve y usa otra tabla plana y chica.

## Contenidos

- **Clase 1** — Diferencia entre una base de datos y el almacenamiento de archivos. Redundancia y
  anomalías. Funciones de un DBMS: consulta, integridad, concurrencia, seguridad y recuperación.
  Relación, tupla, atributo y dominio. Claves, incluida la clave compuesta. Metadatos.
- **Clase 2** — Fases de diseño de una base de datos. Diseño conceptual: entidades, vínculos y
  cardinalidad. Traducción del modelo conceptual a un conjunto de tablas. Qué se decide al crear una
  base de datos. Integridad de entidad, de dominio y referencial.
- **Clase 3** — Dependencias funcionales. Primera, segunda y tercera forma normal. Cuándo
  desnormalizar, y qué se paga.
- **Clase 4** — Un trabajo final breve: reconocer las entidades de una tabla plana y chica, escribir
  sus dependencias funcionales, llevarla a tercera forma normal y justificar el diseño. No hace
  falta programar.

La única entrega del taller es el trabajo final, que es opcional y recomendado. Las clases 1 a 3 no
tienen entrega.

## Licencia

Este material se publica bajo [CC BY 4.0](LICENSE): se puede usar, copiar y adaptar libremente,
con atribución.
