# dashboard-empresarial-powerbi
Proyecto de Business Intelligence en Power BI con dashboards interactivos sobre clientes y finanzas, utilizando Power Query y DAX para el análisis de datos.

# Análisis Comercial de Clientes (2020–2023)

<img width="1420" height="797" alt="image" src="https://github.com/user-attachments/assets/7cb09a27-c8e3-46ae-87bc-7baecd298faf" />

## Descripción General

Llevé a cabo la elaboración de este dashboard interactivo que analiza el comportamiento de los clientes de una empresa entre 2020 y 2023. El objetivo de este es entender quiénes son los clientes que aportan mayor valor al negocio y qué proporción representan, cómo compran, qué tan fieles son y qué clientes manifiestan ser un riesgo para el negocio (por cancelaciones o pérdidas), para apoyar decisiones comerciales orientadas a retención y rentabilidad.

## Objetivo del Análisis

- Identificar qué clientes generan más valor (ganancias, cantidad de pedidos) y cuáles representan mayor riesgo (cancelaciones, pérdidas).
- Entender cómo se distribuyen los clientes según su categoría y frecuencia de compra.
- Medir la evolución de adquisición de nuevos clientes año a año.
- Detectar el método de pago dominante para optimizar procesos de cobro.
- Monitorear el churn rate como indicador de salud del negocio.

## Fuente de Datos y Herramientas

- **Herramienta de visualización:** Power BI
- **Fuente de datos:** Archivo .xlsb
- **Período cubierto:** 2020 – 2023 
- **Registros analizados:** 2521 clientes

## KPIs Principales

| Indicador | Valor (2020-2023) | Descripción |
|---|---|---|
| Recuento de Clientes | 2521 | Total de clientes en la base analizada |
| % Clientes Recurrentes | 45.5% | Clientes que realizaron más de una compra |
| Clientes Nuevos | 269 | Nuevos clientes captados en el último período registrado (2023) |
| Churn Rate | 76.41% | Porcentaje de clientes que dejaron de comprar (2023) |

## Visualizaciones Incluidas

- **Clientes nuevos por año** - evolución de la adquisición de clientes entre 2020 y 2023.
- **Métodos de pago más utilizados** - distribución de pagos (AUTHORIZE.NET, PayPal, Otros).
- **Cantidad de clientes por categoría** - segmentación en Esporádicos/Bajo Valor, VIP, Frecuentes Bajo Ticket, Alto Valor/Ocasionales.
- **Cantidad de clientes por cantidad de órdenes** - distribución de clientes según número de compras realizadas.
- **Clientes con mayor generación de ganancias** - top clientes por rentabilidad.
- **Clientes con mayor cantidad de pedidos** - top clientes por volumen de órdenes.
- **Clientes con mayor cancelación de órdenes** - clientes con más órdenes canceladas (riesgo operativo).
- **Clientes con mayor generación de pérdidas** - clientes que más impactan negativamente en la rentabilidad.

→ Cada visualización cuenta con **filtro interactivo por año (2020–2023)**, lo que permite explorar el comportamiento de un período específico sin necesidad de duplicar el análisis.

## Insights Clave

- El churn rate del último período (2022→2023) es del 76.41%, es decir que **de los clientes que compraron en 2022, más de 3 de cada 4 no volvieron a comprar en 2023**. Este indicador se calcula año contra año y muestra una tendencia creciente (71.25% en 2020→2021, 74.65% en 2021→2022, 76.41% en 2022→2023).
- **El año 2020 fue el año con mayor captación de clientes nuevos** (cerca de 1200), muy por encima de los años siguientes.
- **La adquisición de nuevos clientes cae sostenidamente desde 2020**, siendo de 2020 a 2021 el período de mayor caída.
- El año 2022 fue el año de mayor recurrencia de clientes.
- **La mayoría de los clientes hace un solo pedido**. El gráfico "Cantidad de Clientes por Cantidad de Órdenes" muestra que el grupo más numeroso compró solo 1 vez, lo que explica en parte tanto el churn alto como el peso de la categoría de clientes Esporádicos/Bajo Valor.
- La categoría Esporádicos/Bajo Valor representa la mayor parte de la base (casi el 44%), pero **aporta poco a la rentabilidad**. Para esta categoría, se tuvieron en cuenta aquellos clientes que hicieron menos de 2 pedidos y cuya ganancia total generada es menor a la ganancia media de todos los clientes.
- Si bien la categoría Esporádicos/Bajo Valor es la más numerosa (casi el 44%), la categoría VIP también representa una porción considerable de la base. **Esta es la categoría de mayor prioridad comercial**, ya que compran seguido y esa frecuencia se traduce en rentabilidad. Para esto, se tuvieron en cuenta aquellos clientes que hicieron más de 2 pedidos y cuya ganancia total generada es mayor a la ganancia media de todos los clientes.
- **La ganancia está concentrada en pocos clientes**. El top de "Clientes con Mayor Generación de Ganancias" (Cliente_1214, Cliente_450, Cliente_785, etc.) concentra una parte muy superior de la rentabilidad total en comparación con el resto de la base, lo que sugiere que retener a este grupo específico debería ser prioridad.
- Cliente_18 aparece simultáneamente en el top de mayor cantidad de pedidos y en el top de mayor cancelación de órdenes (representa más del 40% de las órdenes canceladas). Esto sugiere que no es solo un cliente de alto volumen, sino también **un caso puntual de riesgo operativo que merece revisión individual**, más allá de las métricas agregadas.
- **Un pequeño grupo de clientes concentra la mayor parte de las cancelaciones y pérdidas**: Cliente_18 representa más del 40% de órdenes canceladas y Cliente_204 representa más del 40% de las pérdidas.
- AUTHORIZE.NET concentra más del 60% de los pagos.

## Conclusión

Haber realizado este dashboard me permitió poner en práctica mis conocimientos en Power BI, interpretar las visualizaciones y sacar mis propias conclusiones, además de aprender a partir de los errores. También me hace valorar a la Inteligencia Artificial como herramienta de trabajo: me ayudó a entender mejor el funcionamiento del software, a identificar información en los gráficos que no había notado por mi cuenta, y a corregir errores en la elaboración de las métricas DAX.

## Autor

María Delfina Torres — delfitorres24.05@gmail.com / www.linkedin.com/in/maría-delfina-torres-479383242 / github.com/delfitorres2405-cloud
