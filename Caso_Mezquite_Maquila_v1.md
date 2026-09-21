# Mezquite Maquila

**Caso IPADE · P 26 C 01/A (borrador) · Simulador EXSIM v6, perfil de un día**

Versión 1.0 del borrador. Redactado para revisión de Arturo Orozco.
Los apartados marcados como **[PENDIENTE]** son decisiones de diseño que aún no se han confirmado.

---

## Nota para el instructor

Este perfil está diseñado para una ronda de un solo día: **tres cuatrimestres de decisión**, que
equivalen a un año fiscal. Sustituye la manufactura completa del caso original por un esquema de maquila,
conservando la estructura de costos y el comportamiento del mercado.

Las tres equivalencias que sostienen la comparabilidad con el caso original:

| Dimensión | Caso original | Mezquite Maquila |
|---|---|---|
| Ciclos jugados | 6 cuatrimestres | 3 cuatrimestres |
| Mercado | 5 zonas × 2 segmentos | 3 zonas × 2 segmentos |
| Costo unitario objetivo | 31.61 | 31.60 con el maquilador intermedio |

Cada cuatrimestre del perfil nuevo acumula la demanda de dos cuatrimestres del original, así que el
volumen del año y la trayectoria de fases del mercado son las mismas. El motor comercial es idéntico: los
mismos cinco factores, los mismos exponentes, la misma memoria de cuota.

---

## 1. La empresa

Mezquite, S.A. fabricó electrodomésticos durante veintidós años. En 2025 el consejo aprobó la venta de las
plantas de Centro y Oeste al grupo industrial que las operaba bajo contrato, y el negocio se reorganizó
alrededor de lo que la empresa hacía mejor: la marca Electroclean, la red de distribuidores y el diseño
del producto.

Hoy Mezquite no fabrica. Compra el Electroclean terminado a maquiladores, lo empaca y lo etiqueta en su
propia línea, y lo distribuye a sus tres mercados. La planta de empaque de Centro es lo único que quedó de
la operación anterior: dos líneas de encintado y una de empaque, que siguen en el balance con su
depreciación.

El reto del año es el mismo que tenía la empresa cuando fabricaba: ganar cuota sin destruir el margen,
con la diferencia de que ahora el costo unitario ya no depende de cómo se cargue la planta sino de a quién
se le compre y con cuánta anticipación.

## 2. El producto

El Electroclean es un electrodoméstico de limpieza doméstica. Se vende en dos segmentos del mismo
mercado: **Alto**, que paga por desempeño y funcionalidades, y **Bajo**, que paga por eficiencia y
conveniencia.

El producto se puede mejorar. Cada mejora es una inversión que se hace una vez y queda para siempre, y
sube la calificación del producto en una o varias de cinco dimensiones: sostenibilidad, conveniencia,
rendimiento, funcionalidades extra y eficiencia.

Lo que hay que entender de las mejoras: **cada segmento tiene un nivel deseado en cada dimensión, y el
crédito se topa ahí.** Invertir por encima de lo que el segmento pide no da ni un punto. Y lo que un
segmento desea cambia conforme el mercado madura.

### Catálogo de mejoras

| Mejora | Costo | Sostenib. | Conven. | Rendim. | Func. extra | Eficien. |
|---|---|---|---|---|---|---|
| Material inoxidable | 15,000 | 1 | 1 | | | 1 |
| Materiales reciclables | 30,000 | 2 | | | | |
| Consumo eléctrico reducido | 30,000 | 1 | | | | 1 |
| Más ligero y más compacto | 30,000 | 1 | 1 | | | 1 |
| Resistencia a impactos | 30,000 | 1 | 1 | | | 1 |
| Reducción de ruidos | 45,000 | | 2 | | | |
| Mayor capacidad de batería | 45,000 | 1 | 1 | 1 | | |
| Autolimpieza | 45,000 | 1 | 1 | 1 | | |
| Ajustes de velocidad | 45,000 | | | 1 | 2 | |
| Controles digitales | 45,000 | | 2 | 2 | 2 | |
| Asistencia por voz | 45,000 | | 3 | | 3 | |
| Automatización y programabilidad | 45,000 | | 3 | | 4 | |
| Accesorios multifuncionales | 100,000 | | 3 | 3 | 4 | |
| Tecnología de mapeo | 100,000 | 1 | 2 | 3 | 2 | |

El máximo alcanzable por dimensión, comprando todo el catálogo, es 9, 20, 11, 17 y 4 respectivamente.
La inversión en mejoras se amortiza en tres cuatrimestres.

### Lo que cada segmento desea, por fase del mercado

Valor deseado y, entre paréntesis, la importancia que el segmento le da a esa dimensión.

| Fase | Segmento | Sostenib. | Conven. | Rendim. | Func. extra | Eficien. |
|---|---|---|---|---|---|---|
| Crecimiento | Alto | 0.40 (0.3) | 0.50 (0.6) | 0.70 (0.8) | 0.60 (0.7) | 0.40 (0.3) |
| Crecimiento | Bajo | 0.40 (0.2) | 0.60 (0.8) | 0.35 (0.4) | 0.40 (0.6) | 0.75 (0.9) |
| Madurez | Alto | 0.60 (0.8) | 0.70 (0.5) | 0.80 (0.9) | 0.80 (0.9) | 0.50 (0.3) |
| Madurez | Bajo | 0.50 (0.5) | 0.70 (0.8) | 0.40 (0.4) | 0.40 (0.7) | 0.85 (0.9) |
| Hipermadurez | Alto | 0.80 (0.8) | 0.80 (0.5) | 0.80 (0.9) | 0.90 (0.9) | 0.70 (0.3) |
| Hipermadurez | Bajo | 0.60 (0.5) | 0.80 (0.8) | 0.50 (0.4) | 0.50 (0.7) | 0.90 (0.9) |

## 3. El mercado

Tres zonas, dos segmentos en cada una. Seis mercados en total y cinco competidores en todos.

| Zona | Distribuidores | Población Alto | Población Bajo |
|---|---|---|---|
| Centro | 10 | 35,200 | 74,800 |
| Oeste | 10 | 24,000 | 51,000 |
| Norte | 8 | 19,600 | 50,400 |

La demanda de cada mercado la fija el año, no las empresas. **Nadie agranda el pastel.** Lo que se
reparte cada cuatrimestre es:

| Cuatrimestre | Centro Alto | Centro Bajo | Oeste Alto | Oeste Bajo | Norte Alto | Norte Bajo |
|---|---|---|---|---|---|---|
| 1 | 27,819 | 68,076 | 16,835 | 42,088 | 21,228 | 38,796 |
| 2 | 30,015 | 92,970 | 20,495 | 63,684 | 18,300 | 46,116 |
| 3 | 29,124 | 82,764 | 28,354 | 81,222 | 16,857 | 49,809 |

Cada cifra es la demanda total del mercado, a repartir entre los cinco competidores según su cuota.
Incluye el factor de escala de 1.394 que compensa la salida de las zonas Este y Sur, de modo que el
volumen del año sea el mismo que en el caso original.

El mercado madura solo, por acumulación de unidades vendidas sobre la población. Al arrancar el año,
Centro y Oeste están en crecimiento y Norte también; para el tercer cuatrimestre varios mercados habrán
pasado a madurez o hipermadurez. La fase importa porque cambia tres cosas: lo que el segmento desea del
producto, la rapidez con que se olvida la publicidad y cuánta inercia tiene la cuota del periodo anterior.

### Qué decide la cuota de mercado

Cinco factores, calificados de 0 a 100, que se combinan multiplicativamente. El peso de cada uno es
distinto y esa diferencia es el corazón del caso.

| Factor | Qué lo mueve | Peso en Alto | Peso en Bajo |
|---|---|---|---|
| Precio | El precio propio contra el promedio de los activos | 0.226 | 0.376 |
| Presupuesto | Si el precio cabe en el bolsillo del segmento | 1.796 | 1.324 |
| Promoción | Vendedores contra distribuidores de la zona | 0.024 | 0.030 |
| Publicidad | Conocimiento de marca acumulado | 0.856 | 0.797 |
| Producto | Mejoras contra lo que el segmento desea | 1.365 | 0.603 |

Dos consecuencias que conviene no descubrir tarde. El factor Presupuesto pesa entre cinco y ocho veces
más que el factor Precio, así que lo que importa no es ser el más barato sino no rebasar el techo del
segmento. Y el factor Promoción pesa casi nada: contratar vendedores es la decisión comercial que menos
mueve el mercado.

El mercado además **recuerda**. La cuota de un cuatrimestre es una mezcla de la cuota real del anterior y
del atractivo actual. El peso de la memoria va de 0.25 en crecimiento a 0.55 en madurez para el segmento
Alto. Quien pierde cuota por un desabasto la arrastra al cuatrimestre siguiente aunque corrija el precio.

**[PENDIENTE]** El techo de precio por zona y segmento va en el cuadernillo del participante o se entrega
solo como rango. Ver la sección 8.

## 4. Los maquiladores

Mezquite no fabrica. Compra el Electroclean terminado a uno o varios de tres maquiladores.

| Maquilador | Precio por unidad | Entrega | Lote mínimo | Falla de entrega |
|---|---|---|---|---|
| Tecnomex, Querétaro | 30.00 | 1 quincena | 500 | 0% |
| Industrias Bajío | 28.40 | 2 quincenas | 1,000 | 10% |
| Shenzhen Hanbo | 24.90 | 4 quincenas | 5,000 | 20% |

La falla de entrega significa que ese porcentaje del pedido puede no llegar en el cuatrimestre. Es un
riesgo por pedido, no un descuento garantizado.

A eso se suma el empaque propio, que Mezquite sí hace:

| Concepto | Costo |
|---|---|
| Material de empaque y etiqueta | 2.40 por unidad |
| Mano de obra de la línea de empaque | 0.80 por unidad |
| Depreciación de las tres líneas | 38,000 por cuatrimestre |
| Cuota fija del contrato de maquila | 279,000 por cuatrimestre |
| Capacidad de la línea de empaque | 5,500 unidades por quincena |

El costo unitario queda así, según el maquilador elegido:

| Maquilador | Maquila | Empaque | **Costo por unidad** | Contra el caso original |
|---|---|---|---|---|
| Tecnomex | 30.00 | 3.20 | **33.20** | +5.0% |
| Industrias Bajío | 28.40 | 3.20 | **31.60** | igual |
| Shenzhen Hanbo | 24.90 | 3.20 | **28.10** | −11.1% |

El maquilador intermedio reproduce exactamente el costo unitario del caso original, 31.61. Esto es
deliberado: un equipo que juegue en neutral obtiene la economía del caso original, y las otras dos
opciones son desviaciones medibles con un riesgo asociado.

La cuota fija del contrato de maquila es lo que sustituye a los costos fijos de planta del caso original.
Sin ella el perfil nuevo resultaría 29% más rentable que el original solo por no cargar depreciación ni
energía de fábrica, y la comparación dejaría de ser válida. Con ella, la utilidad del año coincide.

La capacidad de la línea de empaque, 5,500 unidades por quincena, sustituye al cuello de botella de las
cinco secciones del caso original. Es una sola restricción en lugar de cinco, pero funciona igual:
**produce el mínimo entre lo que se pidió, lo que llegó y lo que la línea puede empacar.**

## 5. Distribución y almacenes

Las tres zonas se surten desde donde llegue la maquila. Centro es el punto de entrada de Tecnomex y del
Bajío; Shenzhen Hanbo entra por Oeste.

| Concepto | Dato |
|---|---|
| Capacidad de un módulo de almacén | 100 unidades |
| Renta por módulo y cuatrimestre | 800 |
| Envío Centro a Oeste | 16.80 por unidad, llega en 2 quincenas |
| Envío Centro a Norte | 18.96 por unidad, llega en 2 quincenas |
| Envío Oeste a Norte | 21.60 por unidad, llega en 2 quincenas |
| Sobrecosto por envío urgente | 60% del precio, llega en 1 quincena |

Lo que no cabe en el almacén al cierre del cuatrimestre se desecha. No se guarda para el siguiente.

## 6. Comercial

Cuatro decisiones por cuatrimestre, y solo cuatro.

**Precio de venta por zona.** Un precio por zona, aplicable a los dos segmentos. Poner precio cero
significa no participar en esa zona.

**Condiciones de pago por zona.** Cuatro planes, que cambian el ingreso y el momento del cobro:

| Plan | Descuento | Cobro |
|---|---|---|
| A | 13.0% | inmediato |
| B | 7.5% | 2 quincenas |
| C | 2.5% | 4 quincenas |
| D | 0.0% | 8 quincenas |

El plan no afecta el atractivo del producto ante el cliente. Afecta cuánto se ingresa y cuándo entra el
dinero a la caja.

**Vendedores por zona.** Cada vendedor cuesta 750 por cuatrimestre. La calificación de Promoción satura
rápido: al igualar el número de distribuidores de la zona ya se llevan 63 de los 100 puntos posibles.

**Campañas de publicidad.** Dos medios y un enfoque.

| Medio | Costo por spot | Alcance |
|---|---|---|
| Televisión | 3,000 | las tres zonas a la vez |
| Radio | 300 | solo la zona contratada |

El enfoque es un número de 0 a 100 que reparte la campaña entre mensaje genérico y mensaje de marca. La
televisión pesa más en el segmento Alto y la radio en el Bajo.

El conocimiento de marca es un acervo con fuga. Cada cuatrimestre se pierde una fracción y se rellena con
lo que se compró: 40% de fuga en crecimiento, 25% en madurez y 15% en hipermadurez. Dejar de anunciar un
cuatrimestre no borra la marca, pero la erosiona.

## 7. Finanzas

| Concepto | Dato |
|---|---|
| Efectivo inicial | 850,000 |
| Línea de crédito | 11% anual, tope del 50% de los activos fijos |
| Depósitos a plazo | 4% anual |
| Factoraje de cuentas por cobrar | 8.5%, hasta el 60% de la cartera |
| Impuesto sobre la utilidad | 50% |
| Gastos fijos de administración | 117,600 por cuatrimestre |

El indicador con el que se evalúa al equipo es el **ROE**, el rendimiento sobre el capital contable.

**[PENDIENTE]** Los gastos fijos de administración de 117,600 son el valor observado en el caso original.
Aparecen aquí como dato dado. Si se decide hacerlos explícitos como decisión, hay que rehacer la
equivalencia de márgenes.

## 8. Los roles

Siete posiciones. El equipo decide quién ocupa cada una y todas tienen decisiones reales que tomar.

| Rol | Qué decide | Con quién negocia dentro del equipo |
|---|---|---|
| **CEO** | Estrategia de zonas y segmentos, desempate de conflictos, meta de ROE | Con todos |
| **CMO** | Precio por zona, campañas de TV y radio, enfoque | Con el CFO por el presupuesto y con el COO por el volumen |
| **COO de Maquila** | Qué maquilador, cuánto y en qué quincena; carga de la línea de empaque | Con el CLO por dónde entra y con el Controller por el costo |
| **CLO** | Módulos de almacén por zona, envíos entre zonas, urgencias | Con el COO por el inventario y con el CMO por el surtido |
| **CFO** | Línea de crédito, depósitos, factoraje, dividendos | Con todos, es la restricción |
| **CPO y Sostenibilidad** | Mejoras de producto y su secuencia; huella de CO2 del transporte | Con el CMO por el segmento objetivo |
| **Controller y Compras** | Condiciones de pago por zona, material de empaque, control de costo unitario | Con el CFO por el cobro y con el COO por la maquila |

La tensión que hace funcionar el caso: el CMO quiere precio bajo y mucha publicidad, el COO quiere
comprarle al maquilador más barato, el CLO quiere almacenes llenos y el CFO no tiene con qué pagar las
tres cosas. Y el Controller es el único que ve que el maquilador barato tarda cuatro quincenas.

## 9. La agenda del día

**[PENDIENTE]** Sujeta a la logística del aula.

| Bloque | Duración | Contenido |
|---|---|---|
| Introducción | 45 min | El caso, el mercado y los roles |
| Cuatrimestre 1 | 60 min | Decisión y resultados |
| Debrief 1 | 30 min | Qué movió la cuota |
| Cuatrimestre 2 | 45 min | Decisión y resultados |
| Cuatrimestre 3 | 45 min | Decisión y resultados |
| Debrief final | 60 min | ROE, decisiones determinantes, comparación con el caso completo |

## 10. Qué se conserva y qué se pierde

Para la discusión con Arturo, con honestidad sobre los recortes.

**Se conserva.** El motor comercial completo, con los cinco factores, sus pesos y la memoria del mercado.
La estructura de costos, con el maquilador intermedio reproduciendo el costo unitario original al
centavo. La restricción de capacidad, ahora en la línea de empaque. El desabasto y su castigo en la cuota
del cuatrimestre siguiente. La tensión entre las siete funciones.

**Se pierde.** El balanceo de líneas entre cinco secciones con cuatro tipos de máquina, que es la lección
de teoría de restricciones del caso original. La decisión de invertir en capacidad, porque ya no hay
máquinas que comprar salvo la línea de empaque. La gestión de personal, que en el original mueve la
productividad vía el FPR. Y la explosión de materiales con ocho insumos y tres proveedores, reducida a un
precio por unidad terminada.

**Se transforma.** La decisión de producción se vuelve una decisión de abastecimiento: en lugar de
balancear secciones, el equipo elige entre precio, plazo y riesgo de entrega. Es una lección distinta,
más de cadena de suministro que de operaciones, y hay que decidir si eso es lo que se quiere enseñar en
un día.

---

## Anexo. Parámetros para el instructor

No se entregan a los participantes.

| Parámetro | Valor |
|---|---|
| Elasticidad del precio, kappa | 0.20 en Alto, 0.15 en Bajo |
| Coeficiente del factor Presupuesto | 0.7005 con exponente 15 |
| Escalas de publicidad, TV | 30.15 en Alto, 13.61 en Bajo |
| Escalas de publicidad, radio | 7.30 en Alto, 9.02 en Bajo |
| Beta del factor Producto | 0.078 |
| Ruido multiplicativo del índice | desviación 0.05, base 10 |
| Lealtad por fase, Alto | 0.25 / 0.50 / 0.55 / 0.40 |
| Lealtad por fase, Bajo | 0.25 / 0.40 / 0.30 / 0.20 |
| Umbrales de fase, Alto | 10 / 55 / 60 |
| Umbrales de fase, Bajo | 10 / 40 / 50 |

Las escalas de publicidad y el beta del producto son parámetros estimados, no configurados en la
plataforma. El error medido del emulador sobre el caso original es de 1.24 puntos de cuota.
