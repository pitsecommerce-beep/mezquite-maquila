# Banco de pruebas Mezquite

Herramienta de una sola página para correr el motor comercial y el costeo del caso Mezquite en dos
perfiles y comprobar si los resultados son comparables.

Proyecto Mezquite, S.A. (P 24 C 02/B) · IPADE Business School e IESE Business School
Profesor responsable: Arturo Orozco · Coordinación: Francisco Javier Tallabs Utrilla

## Qué hace

Corre el mismo motor comercial con dos configuraciones:

| | Caso original | Mezquite Maquila |
|---|---|---|
| Ciclos | 6 cuatrimestres | 3 cuatrimestres |
| Mercado | 5 zonas × 2 segmentos | 3 zonas × 2 segmentos |
| Operación | manufactura de 5 secciones | maquila más empaque propio |
| Costo por unidad | 12.17 material + 19.44 conversión | 28.40 maquila + 3.20 empaque |

Corriendo los dos con las decisiones reales de los cinco equipos, el agregado del mercado queda así:

| Concepto | Original | Maquila | Diferencia |
|---|---|---|---|
| Ingreso del año | 57,753,322 | 57,638,754 | −0.2% |
| Costo por unidad | 31.61 | 31.60 | 0.0% |
| Utilidad del mercado | 6,257,189 | 6,233,560 | −0.4% |
| Retorno sobre el capital | 83.4% | 83.1% | −0.4% |
| Unidades del año | 683,122 | 728,313 | +6.6% |
| Precio medio por unidad | 84.54 | 79.14 | −6.4% |

Las dos últimas filas se compensan y no se pueden igualar a la vez: al renunciar a Oriente, que era la
zona de precio más alto, el precio medio baja 6.4% y hacen falta 6.6% más unidades para el mismo ingreso.
La calibración prioriza el ingreso, la utilidad y el costo unitario.

El resultado de un equipo en particular no es comparable entre perfiles, porque sus decisiones históricas
se tomaron para un mercado de cinco zonas. La fila de dispersión del retorno mide ese efecto.

Y grafica los trece modelos que corren por dentro, numerados y agrupados según la cadena del motor
comercial: entradas del motor (demanda y fase), las cinco calificaciones, el índice Total, el índice
Final, la cuota, el nivel de servicio y el resultado. Cada gráfica trae leyenda, ejes etiquetados y
tooltip al pasar el cursor, con el detalle del equipo, el cuatrimestre y el parámetro que la gobierna.

## Publicar en GitHub Pages

1. Crea un repositorio y sube estos archivos tal cual.
2. En `Settings > Pages`, en `Source`, elige **GitHub Actions**.
3. El flujo `.github/workflows/deploy.yml` publica en cada `push` a `main`.

No hay que compilar nada. `index.html` es autocontenido: no carga ninguna librería externa, así que
funciona también abriéndolo desde el disco.

## Cómo usarlo

**Elegir el perfil.** Los dos botones de arriba a la derecha cambian todo: parámetros, número de ciclos,
zonas y estructura de costos.

**Cargar parámetros por omisión.** Los botones `Cargar los del original` y `Cargar los de maquila`
rellenan la estructura de costos sin tocar las decisiones, para comparar una sola cosa a la vez.

**Editar decisiones.** Cada ciclo arranca con las decisiones reales de los cinco equipos de la partida
IPADE MEDEX MEX C 2026. Cambiar cualquier celda recalcula al instante.

**Plantillas.** `Descargar plantilla` guarda un JSON con los parámetros y las decisiones completas.
Se edita fuera y se vuelve a cargar con `Cargar plantilla`.

**Comparar.** El botón de comparación corre los dos perfiles con sus decisiones por omisión y pone los
resultados del año lado a lado.

## De dónde salen los parámetros

Están medidos contra los reportes oficiales del simulador real, partida IPADE MEDEX MEX C 2026,
cuatrimestres 7 a 12, cinco empresas. El error del motor comercial es de **1.24 puntos porcentuales de
cuota** sobre 230 observaciones.

La tabla de trazabilidad al final de la página marca qué parámetros están configurados en la plataforma
y cuáles son estimaciones estadísticas. La distinción importa: un parámetro estimado tiene error residual
y no se puede presentar como identidad.

Tres advertencias que conviene tener presentes al leer los resultados:

- El estado de resultados está incompleto. Las partidas de distribución y los costos fijos están
  calibradas contra el reporte oficial, no calculadas desde las decisiones. El renglón de gastos de
  administración de 117,600 no corresponde a ningún parámetro capturado de la plataforma.
- El ruido multiplicativo del índice está en cero para que la réplica sea determinista. El simulador real
  inyecta una perturbación con desviación de 0.05.
- El retorno que muestra la tabla se calcula sobre el capital contable que esté en los parámetros. No es
  el ROE que reporta el simulador oficial.

## Estructura

```
index.html                  la herramienta completa
caso/                       borrador del caso IPADE del perfil nuevo
.github/workflows/deploy.yml  publicación en Pages
```

## Licencia

Material docente de IPADE Business School. Uso interno del proyecto.
