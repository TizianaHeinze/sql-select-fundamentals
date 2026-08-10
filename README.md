# sql-select-fundamentals
# sql-select-fundamentals

Práctica de consultas básicas SQL utilizando SELECT y alias sobre la tabla de ventas `sales` de TechStore.

## ¿Por qué es mala práctica usar SELECT * en producción?

Aunque `SELECT *` puede ser útil para explorar rápidamente una tabla durante el análisis, no es recomendable utilizarlo en producción.

Una de las razones es el **rendimiento**, ya que `SELECT *` recupera todas las columnas de la tabla, incluso aquellas que no son necesarias. Esto puede aumentar el procesamiento y la cantidad de datos transferidos.

También afecta la **mantenibilidad**. Si en el futuro se agregan nuevas columnas a la tabla, una consulta con `SELECT *` comenzará a devolverlas automáticamente, lo que podría afectar reportes o procesos que dependan de esa consulta.

Además, puede generar problemas de **seguridad**, porque podría devolver columnas con información que un usuario no necesita visualizar.

Por estas razones, es preferible seleccionar únicamente las columnas necesarias.

## ¿Por qué son importantes los alias para un stakeholder no técnico?

Los alias permiten presentar los resultados de una consulta con nombres más claros y cercanos al lenguaje del negocio, sin modificar el nombre original de las columnas en la base de datos.

Por ejemplo:

```sql
SELECT total_amount AS monto_total
FROM sales;
