# El relevamiento, como una sola tabla

`relevamiento_plano.csv` es el conjunto de datos que usan las clases 1, 2 y 3: **45 filas y 12
columnas**. Es el relevamiento de hogares del taller T8001, ya limpio, con las columnas que ese
taller no tenía.

De dónde sale, exactamente: es la salida de la clase 3 del T8001. Se toman las 40 filas de
`relevamiento_completo.csv`, se descarta el duplicado exacto y se descartan las dos filas en
conflicto del `id` 41. Quedan los **37 hogares** con los que cierra ese taller. Después, ocho de
esos hogares reciben una segunda visita en junio, y eso lleva el archivo a 45 filas. Se construye
con un script local, que no forma parte del repositorio publicado.

Los notebooks lo fabrican en el momento, así que funcionan sin conexión y no leen esta copia. El
archivo está acá para poder mirarlo desde el repositorio y para citarlo por su dirección web.

## Por qué está así, y no mejor

Este archivo está limpio y sigue siendo un mal diseño. Esa es la tesis del taller. Cada defecto de
estructura está puesto a propósito, y cada uno se trabaja en una sección concreta:

| Dónde | Qué tiene | Clase y sección |
|---|---|---|
| `localidad` y `provincia` | El par `Ramallo` — `Buenos Aires` se repite en 20 filas: redundancia | 1 · 3.1 |
| `provincia` | Depende de `localidad`, no del hogar: dependencia transitiva | 3 · 4.4 |
| `encuestador_nombre` y `encuestador_telefono` | Dependen de `encuestador_legajo`: la segunda transitiva | 3 · 4.4 |
| `servicios` | Hasta cuatro servicios en una celda, separados por `;` | 3 · 4.2 |
| 8 hogares con dos filas | La clave no es `id_hogar`: es `id_hogar` más `fecha_visita` | 1 · 6.3 |
| `localidad` y `servicios` | Dependen de una parte de la clave: dependencia parcial | 3 · 4.3 |
| `ingreso`, hogares 3 y 9 | Vacío. Un nulo no es un cero | 1 · 5.4 |
| `cobertura_salud` y `satisfaccion` | Vacías en las mismas 10 filas, herencia del T8001 | 1 · 5.4 |

## Los números que importan

**45 visitas, 37 hogares, 3 localidades, 3 provincias, 4 encuestadores y 4 servicios.** Ese es el
arco del taller: la tabla plana de 45 filas y 12 columnas termina, en la clase 3, como seis tablas
en tercera forma normal.

Dos detalles útiles para las demostraciones:

- El hogar 1 tiene 3 personas en marzo y 4 en junio. Por eso `personas` pertenece a la visita y no
  al hogar, y por eso la clave tiene que ser compuesta.
- `Concepción` existe en más de una provincia argentina. Por eso el nombre de la localidad no sirve
  como clave, y hace falta una clave sustituta. Es el ejemplo de la clase 1, sección 6.2.

`encuestador_nombre` va entre comillas dobles porque contiene una coma, como pide el
[RFC 4180](https://datatracker.ietf.org/doc/html/rfc4180). Es la regla de la clase 1 del T8001.
