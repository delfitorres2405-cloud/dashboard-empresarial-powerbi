# informe-empresarial-powerbi
Proyecto de Business Intelligence en Power BI con dashboards interactivos sobre clientes y finanzas, utilizando Power Query y DAX para el análisis de datos.

## Descripción General
Llevé a cabo la elaboración de estos dashboards interactivos que analizan las finanzas de una empresa en 2023 y el comportamiento de sus clientes entre 2020 y 2023.

El **dashboard financiero** tiene como objetivo evaluar la salud comercial del negocio a lo largo de 2023: cómo evolucionan las ventas y el margen mes a mes, qué tan rentable es el negocio en cada período, en qué meses aumentan las pérdidas y qué proporción de los ingresos se concentra en pocas órdenes (curva de Pareto), para identificar los puntos donde la rentabilidad se ve comprometida.

El **dashboard de clientes** tiene como objetivo entender quiénes son los clientes que aportan mayor valor al negocio y qué proporción representan, cómo compran, qué tan fieles son y qué clientes manifiestan ser un riesgo para el negocio (por cancelaciones o pérdidas).

En conjunto, ambos análisis buscan apoyar decisiones comerciales orientadas a la retención de clientes y la mejora de la rentabilidad.

## Fuente de Datos y Herramientas
- **Limpieza y transformación de datos:** Power Query
- **Herramienta de visualización:** Power BI
- **Fuente de datos:** Archivo .xlsb
- **Período cubierto:** 2020 - 2023 
- **Registros analizados:** 7122 ventas, 2521 clientes

## Proceso de limpieza y transformación de datos
Antes de detallar los KPIs elegidos para el dashboard, las visualizaciones presentadas y los insights clave, quiero comentar brevemente cómo fue el proceso de preparación de los datos para el posterior análisis.

Primero importé al software la fuente de datos que, como mencioné antes, es un archivo .xlsb con varias hojas, donde cada una representa las ventas de un año de la empresa.  
- Unificación: como tenía una hoja por año, unifiqué todas las tablas en una sola para poder trabajar con la información de forma conjunta.
- Filtrado: eliminé las columnas que tenían muchos datos faltantes o que no aportaban información relevante al análisis y eliminé filas vacías.
- Deduplicación: borré las filas duplicadas.
- Manejo de valores faltantes: convertí los datos faltantes de las columnas numéricas a 0.
- Estandarización de texto: estandaricé los nombres de los clientes, eliminando espacios de más y pasando todo el texto a mayúscula, para evitar que un mismo cliente quede registrado de formas distintas (antes de publicar el dashboard, anonimicé los nombres de los clientes reemplazándolos por códigos genéricos (Cliente_001, Cliente_002, etc.).
- Formateo de tipos de dato: revisé que el tipo de dato asignado automáticamente por Power BI a cada columna fuera el correcto, y en los casos en que no lo era, lo corregí. 

Todo este proceso lo realicé en **Power Query** antes de cargar los datos al modelo, por lo que se trata de un proceso **ETL (Extract, Transform, Load)**: primero extraje los datos del archivo original, luego los transformé aplicando los pasos mencionados, y recién al final los cargué al modelo de Power BI preparados para el análisis.

## Análisis de Ventas y Rentabilidad (2023)
<img width="1424" height="795" alt="image" src="https://github.com/user-attachments/assets/d455eef6-71d0-481b-a4a3-ce61ddfcbc22" />

### Objetivos del Análisis
- Identificar si el crecimiento en ventas viene acompañado de un margen sostenido.
- Detectar en qué meses aumenta el % de órdenes con pérdida para poder investigar qué lo causó.
- Ver si los meses con más órdenes también tienen mejor ticket promedio.
- Entender qué proporción de las ventas se concentra en rangos de margen bajo, medio o alto.
- Analizar qué porcentaje de las órdenes explica la mayor parte de los ingresos totales, fundamental para saber si el negocio depende de pocas ventas grandes o está bien distribuido.

### KPIs Principales 
| Indicador | Valor (2023) | Descripción |
|---|---|---|
| Ingresos Totales (USD) | $222.23 mil | Total facturado por ventas durante el año |
| Ganancia Total (USD) | $53.05 mil | Ganancia neta generada por el total de ventas |
| Margen de Ganancia | 23.87% | Porcentaje de ganancia sobre los ingresos totales |
| Cantidad de Ventas | 909 | Total de órdenes registradas en el período |
| Ticket Promedio (USD) | $244.48 | Monto promedio por orden de venta |
| % Órdenes con Pérdida | 2.31% | Proporción de órdenes que resultaron en pérdida |

### Visualizaciones Incluidas
- KPIs generales: ingresos totales, ganancia total, margen de ganancia, cantidad de ventas, ticket promedio y % de órdenes con pérdida.
- Evolución de Ventas y Margen: comparación mensual entre el total vendido y el margen obtenido a lo largo de 2023.
- % Órdenes con Pérdida por Mes: proporción de ventas que resultaron en pérdida, mes a mes.
- Cantidad de Órdenes y Ticket Promedio por Mes: relación entre volumen de ventas y el valor promedio de cada orden.
- Cantidad de Órdenes por Margen: distribución de las órdenes según su rango de rentabilidad (desde pérdida hasta más del 50% de margen).
- Concentración de Ingresos (Curva de Pareto): porcentaje acumulado de ingresos explicado por el porcentaje acumulado de órdenes.
- Filtro por mes: panel lateral que permite segmentar todo el dashboard por uno o varios meses del año.

### Insights Clave
- **Las ventas no muestran un crecimiento sostenido a lo largo del año**: fluctúan mes a mes sin seguir una tendencia clara, con picos en mayo, septiembre y octubre, y una caída marcada hacia noviembre y diciembre. **El margen evoluciona de forma independiente a las ventas**: no siempre acompaña a los meses de mayor volumen, **siendo septiembre el caso donde ambos coinciden con sus valores más altos del año**.
- **Abril fue el mes más crítico en rentabilidad**: el % de órdenes con pérdida llegó a casi 6%, más del doble que el resto de los meses (que se mantuvieron entre 1% y 3%), lo que lo convierte en el principal punto a investigar dentro del año.
- **Un mayor volumen de órdenes no garantiza un mejor ticket promedio**: enero concentró la mayor cantidad de órdenes del año pero el ticket promedio más bajo, mientras que en septiembre ocurrió lo contrario, con menos órdenes pero el ticket más alto.
- **La operación es mayormente rentable**, con margen concentrado en rangos medios-altos: el tramo de 20% a 30% de margen agrupa la mayor cantidad de órdenes, seguido de cerca por el de 10-20%+ y 50%+, y solo una porción menor de las ventas cae en pérdida.
- El negocio muestra una fuerte concentración de ingresos: **apenas el 36% de las órdenes (las de mayor valor) explican el 80% de los ingresos totales**, mientras que el 64% restante de las órdenes aporta solo el 20% del total facturado. Esto indica que una porción relativamente chica de ventas grandes sostiene la mayor parte de la facturación del negocio.
<img width="486" height="227" alt="image" src="https://github.com/user-attachments/assets/d3a0dad2-7d3e-4886-9e7f-3d552d9e3b02" />

## Análisis Comercial de Clientes (2020-2023)
<img width="1420" height="797" alt="image" src="https://github.com/user-attachments/assets/7cb09a27-c8e3-46ae-87bc-7baecd298faf" />

### Objetivos del Análisis
- Identificar qué clientes generan más valor (ganancias, cantidad de pedidos) y cuáles representan mayor riesgo (cancelaciones, pérdidas).
- Entender cómo se distribuyen los clientes según su categoría y frecuencia de compra.
- Medir la evolución de adquisición de nuevos clientes año a año.
- Detectar el método de pago dominante para optimizar procesos de cobro.
- Monitorear el churn rate como indicador de salud del negocio.

### KPIs Principales 
| Indicador | Valor (2020-2023) | Descripción |
|---|---|---|
| Recuento de Clientes | 2521 | Total de clientes en la base analizada |
| % Clientes Recurrentes | 45.5% | Clientes que realizaron más de una compra |
| Clientes Nuevos | 269 | Nuevos clientes captados en el último período registrado (2023) |
| Churn Rate | 76.41% | Porcentaje de clientes que dejaron de comprar (2023) |

### Visualizaciones Incluidas
- **Clientes nuevos por año** - evolución de la adquisición de clientes entre 2020 y 2023.
- **Métodos de pago más utilizados** - distribución de pagos (AUTHORIZE.NET, PayPal, Otros).
- **Cantidad de clientes por categoría** - segmentación en Esporádicos/Bajo Valor, VIP, Frecuentes Bajo Ticket, Alto Valor/Ocasionales.
- **Cantidad de clientes por cantidad de órdenes** - distribución de clientes según número de compras realizadas.
- **Clientes con mayor generación de ganancias** - top clientes por rentabilidad.
- **Clientes con mayor cantidad de pedidos** - top clientes por volumen de órdenes.
- **Clientes con mayor cancelación de órdenes** - clientes con más órdenes canceladas (riesgo operativo).
- **Clientes con mayor generación de pérdidas** - clientes que más impactan negativamente en la rentabilidad.

→ Cada visualización cuenta con **filtro interactivo por año (2020–2023)**, lo que permite explorar el comportamiento de un período específico sin necesidad de duplicar el análisis.

### Insights Clave
- **La ganancia está concentrada en un grupo reducido de clientes**: el top de mayor rentabilidad (Cliente_1214, Cliente_450, Cliente_785, entre otros) aporta una parte muy superior a la ganancia total en comparación con el resto de la base, lo que convierte a este grupo en prioridad de retención.
- **El riesgo operativo también se concentra en casos puntuales**: Cliente_18 representa más del 40% de las órdenes canceladas y Cliente_204 más del 40% de las pérdidas totales, lo que sugiere revisar individualmente a estos clientes. Cliente_18 aparece simultáneamente en el top de mayor cantidad de pedidos y en el top de mayor cancelación de órdenes: esto sugiere que no es solo un cliente de alto volumen, sino también **un caso puntual de riesgo operativo**.
- **La categoría Esporádicos/Bajo Valor representa la mayor parte de la base (casi el 44%)**, pero aporta poco a la rentabilidad. **La categoría VIP también representa una porción considerable de la base (31%) y es la categoría de mayor prioridad comercial**, ya que compran con frecuencia y generan un gran margen de ganancia (mayor a la media), lo cual se traduce en rentabilidad.
- **La captación de nuevos clientes cae de forma sostenida desde 2020**: ese año concentró el pico de adquisición (cerca de 1200 clientes nuevos), con la caída más pronunciada entre 2020 y 2021, y una tendencia descendente que se mantiene hasta 2023.
- **AUTHORIZE.NET es el método de pago ampliamente dominante**: concentra más del 60% de las transacciones, muy por encima de PayPal y otros métodos combinados.
- **El churn rate es alto y que crece año a año**: pasó de 71.25% (2020→2021) a 74.65% (2021→2022) y 76.41% (2022→2023), lo que indica que la pérdida de clientes se agrava con el tiempo en lugar de estabilizarse. La mayoría de los clientes en general hizo un solo pedido, lo que explica en parte el churn elevado. 

## Conclusión
Haber realizado este dashboard me permitió poner en práctica mis conocimientos en Power BI, interpretar las visualizaciones y sacar mis propias conclusiones, además de aprender a partir de los errores. También me hace valorar a la Inteligencia Artificial como herramienta de trabajo: me ayudó a entender mejor el funcionamiento del software, a identificar información en los gráficos que no había notado por mi cuenta, y a corregir errores en la elaboración de las métricas DAX.

## Autor

María Delfina Torres — delfitorres24.05@gmail.com / www.linkedin.com/in/maría-delfina-torres-479383242 / github.com/delfitorres2405-cloud
