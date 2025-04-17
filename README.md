Análisis sobre Dashboard: Gatito - Gestión de Stock

1. Propósito del Dashboard:
El propósito principal de este dashboard es controlar y optimizar la gestión de inventario de productos en la empresa "Gatito". Permite monitorear los movimientos de entrada y salida de stock, identificar productos en riesgo de agotarse, y apoyar la toma de decisiones sobre reposición, compras y planificación operativa.

2. Funcionalidades:
El dashboard cuenta con funcionalidades interactivas que permiten:
  * Visualizar la cantidad actual en stock por producto o categoría.
  * Analizar los movimientos de entrada y salida de productos en el tiempo.
  * Identificar productos con stock en cero o en nivel crítico.
  * Filtrar información por fechas, productos y tipos de movimiento.
  * Consultar el historial de operaciones para cada producto.

3. Métricas y KPIs usados
Algunas de las métricas clave del dashboard incluyen:
  Métrica / KPI	                  Descripción
  Cantidad en Stock	              Diferencia entre el total de entradas y salidas de cada producto.
  Total de Entradas y Salidas	    Suma acumulada por tipo de movimiento.
  Stock Crítico	                  Productos que actualmente tienen cantidad igual o menor a cero.
  Movimientos Recientes	          Visualización temporal de entradas/salidas para observar tendencias.
  Productos más Movidos	          Identificación de los artículos con mayor rotación o volumen.
 
4. Cómo se usa:
  1. Abre el archivo .pbix en Power BI Desktop.
  2. Utiliza los segmentadores de fecha, producto o tipo de movimiento para explorar el inventario.
  3. Observa las tarjetas de KPI para monitorear los niveles globales de stock.
  4. Revisa los gráficos para analizar el flujo de productos y detectar tendencias.
  5. Usa la visual de tabla para consultar detalles específicos de productos y movimientos.

5. Qué datos utiliza:
El modelo de datos está basado en al menos una tabla principal que contiene:
  * Nombre del producto
  * Fecha del movimiento
  * Tipo de movimiento (Entrada o Salida)
  * Cantidad
  * Categoría o clasificación del producto (si aplica)
  * Opcionalmente, se puede conectar con otras tablas como proveedores, almacenes o precios.

6. Cómo mantenerlo actualizado:
Para asegurar que el dashboard refleje datos actuales:
  1. Actualiza el archivo de datos fuente (Excel, CSV o base de datos) con nuevos movimientos.
  2. En Power BI Desktop, ve a Inicio > Actualizar para recargar los datos.
  3. Si el dashboard está publicado en Power BI Service, configura una actualización programada desde el portal web.
  4. Asegúrate de que el modelo esté limpio y las relaciones bien definidas para evitar errores en cálculos.

7. Decisiones estratégicas sugeridas:
  1. Reordenar productos de alta rotación:
      * Identificar los productos con mayor frecuencia de salida.
      * Aplicar reglas automáticas de reposición (“reorder point”).
  2. Reducir inventario de productos con baja rotación:
      * Detectar productos con stock alto y baja salida en los últimos meses.
      * Evaluar promociones o descuentos para estimular su salida.
  3. Ajustar compras a la demanda estacional:
      * Usar gráficos de salidas mensuales para identificar picos de demanda.
      * Planificar abastecimiento en función del historial de movimiento.
  4. Monitorear rotura de stock (stockout):
      * Crear una alerta o tarjeta de “productos con stock en cero”.
      * Visualizar en mapa o lista los puntos críticos.
  5. Analizar tendencias por categoría o proveedor:
      * Agrupar productos por categoría o proveedor para ver rentabilidad.
      * Evaluar si ciertas categorías están sobreabastecidas o mal gestionadas.

8. Métricas recomendadas
   Indicador                    Fórmula DAX sugerida                                                    Propósito
   Stock Total                  SUM('Stock'[Cantidad_Actual])                                           Total actual disponible
   Stock por Producto           SUM('Stock'[Cantidad_Actual])filtrado por producto                      Nivel individual de inventario
   Rotación Mensual             SUM('Movimientos'[Cantidad]) por mes                                    Detectar productos más vendidos
   Última Fecha de Movimiento   MAX('Movimientos'[Fecha])                                               Medir actividad reciente por                                                                                                               producto
   Productos Inactivos          COUNTROWS(FILTER('Productos', [Última Fecha Movimiento] < TODAY()-90))   Productos sin movimiento reciente
   Porcentaje de Stock Crítico  DIVIDE(COUNTROWS(FILTER('Stock', 'Stock'[Cantidad_Actual] = 0)), COUNTROWS('Stock'))  Riesgo de rotura de                                                                                                                         stock
9. Visualizaciones recomendadas:
   * Mapa de calor de salidas por día/semana.
   * Tabla de productos con stock bajo.
   * Tarjetas de KPI: Stock Total, Stock Crítico, % Inactivos.
   * Gráfico de área: Stock disponible vs salidas acumuladas.
   * Segmentadores por fecha, categoría y proveedor.

10. Automatizaciones sugeridas:
    * Crear una alerta visual cuando el stock de un producto sea menor al mínimo definido.
    * Usar medidas con IF + SWITCH para clasificar productos: “Alta rotación”, “Riesgo bajo”, “Crítico”.
    
11. Valor a generar para Gatito:
    * Tomar decisiones basadas en datos (Data-Driven).
    * Aumentar eficiencia en compras y almacenamiento.
    * Reducir pérdidas por sobrestock o caducidad.
    * Incrementar ventas con disponibilidad correcta.
