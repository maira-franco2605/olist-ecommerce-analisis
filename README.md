# Análisis de e-commerce brasileño (Olist) con Python

Trabajo práctico de Análisis de Datos con IA. Se cargan, revisan, unen y analizan las 8 tablas del dataset público de Olist (pedidos, ítems, pagos, clientes, productos, vendedores, reseñas y geolocalización) para responder 10 preguntas de negocio y construir 5 visualizaciones.

## Stack
Python · pandas · numpy · matplotlib · seaborn · Google Colab · Google Drive

## Proceso
1. **Ingesta:** carga de los CSV desde Google Drive.
2. **Calidad de datos:** revisión de dimensiones y valores nulos por tabla; detección de pagos con valor cero.
3. **Modelado:** uniones entre tablas por sus claves, con dos tablas de trabajo: una a nivel de ítem y otra a nivel de pedido.
4. **Análisis:** agregaciones por estado, ciudad, usuario, producto y mes.
5. **Visualización:** 5 gráficos con su justificación.

## Decisiones técnicas
- Los pagos se agregan por pedido antes de unirlos, porque un pedido puede tener varios métodos de pago y se duplicarían filas.
- Se usa `customer_unique_id` (la persona) en lugar de `customer_id`, que cambia en cada pedido.
- Se agrupa por ciudad y estado juntos, porque existen ciudades homónimas en distintos estados.
- El ticket por ciudad se filtra a un mínimo de 10 pedidos, para evitar promedios distorsionados por un solo pedido.
- Se usa escala logarítmica en el gráfico de usuarios vs. ventas por estado, porque São Paulo es mucho más grande que el resto.

## Hallazgos principales
- São Paulo, Rio de Janeiro y Minas Gerais suman el 62,6% de los ingresos.
- El ticket promedio por pedido es de 160,99 BRL.
- Cerca del 97% de los usuarios compró una sola vez.
- La tarjeta de crédito es el método de pago principal en los 27 estados (cerca del 76% de los pedidos).
- Los pedidos llegan en promedio 10,9 días antes de la fecha estimada, y solo el 8,1% llega tarde.
- Con retrasos de más de 7 días, entre el 69% y el 79% de las reseñas son de 1 o 2 estrellas; con entregas a tiempo o antes, cerca del 10%.

## Cómo reproducirlo
1. Descargá el dataset "Brazilian E-Commerce Public Dataset by Olist" desde Kaggle (no se incluye acá por su tamaño).
2. Subí los CSV a una carpeta de tu Google Drive.
3. Abrí el notebook en Google Colab y cambiá la ruta `/content/drive/MyDrive/TP FINAL/` por la de tu carpeta.
4. Ejecutá todas las celdas.

## Próximos pasos
- Cargar las tablas en una base de datos (PostgreSQL o BigQuery) y replicar las consultas en SQL.
- Convertir la limpieza y las uniones en funciones o scripts reutilizables.

## Autoría
MAIRA FRANCO. Trabajo práctico.
