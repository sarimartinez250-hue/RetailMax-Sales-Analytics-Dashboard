RETAILMAX S.A. - ETAPA 1
===========================

Objetivo:
Construir un modelo de datos de ventas 2021-2025 en Power Query + Power Pivot,
limpiando fuentes heterogéneas y terminando con un dashboard interactivo.

Archivos:
- FactVentas_2021.csv: dos filas de cabecera / título y nombres en mayúsculas.
- FactVentas_2022.csv: nombres en español, codificación distinta, columna vacía y notas.
- FactVentas_2023.csv: delimitador ; y filas duplicadas.
- FactVentas_2024.xlsx: formato ancho con Sales_Jan...Sales_Dec; requiere despivotar.
- FactVentas_2025.csv: números como texto y valores nulos.
- DimTienda.csv
- DimProducto.csv
- DimCliente.csv
- DimFecha.csv
- DimEmpleado.csv
- FactObjetivos.csv
- FactDevoluciones.csv

Relaciones sugeridas:
DimFecha[Date] 1-* FactVentas[Date]
DimTienda[StoreID] 1-* FactVentas[StoreID]
DimProducto[ProductID] 1-* FactVentas[ProductID]
DimCliente[CustomerID] 1-* FactVentas[CustomerID]
DimTienda[StoreID] 1-* FactDevoluciones[StoreID]
DimProducto[ProductID] 1-* FactDevoluciones[ProductID]

Retos recomendados:
1. Crear una consulta parametrizada para importar todos los FactVentas_*.
2. Detectar automáticamente el año desde el nombre del archivo.
3. Estandarizar nombres de columnas y tipos.
4. Resolver las dos cabeceras de 2021.
5. Convertir nombres de columnas de 2022 al estándar.
6. Cambiar delimitador y eliminar duplicados en 2023.
7. Despivotar 2024.
8. Corregir tipos y nulos en 2025.
9. Crear columnas calculadas en Power Query:
   - GrossMargin = NetSales - (Quantity * UnitCost)
   - GrossMarginPct
   - Year
   - Month
   - ReturnValue
10. Crear el modelo estrella en Power Pivot.
11. Crear medidas DAX.
12. Usar Solver para optimizar una combinación de objetivos/promociones bajo restricciones.
13. Crear dashboard con botones para alternar entre:
   - Ventas
   - Margen
   - Devoluciones
   - Cumplimiento de objetivos

No se incluyen soluciones: la intención es que limpies y modeles los datos tú mismo.
