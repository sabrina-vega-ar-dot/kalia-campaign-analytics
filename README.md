# Análisis de campaña Kalia

Proyecto de Business Intelligence realizado con Power BI para analizar los resultados de una campaña de prueba de una gama de yogur alto en proteína. El caso y los datos son ficticios, según la consigna GELT.

## Problema comercial

Kalia se lanzó en marzo de 2026. La prioridad del primer año era conseguir que más compradores probaran el producto y observar oportunidades para incentivar una recompra. El informe resume el origen histórico de los compradores, las unidades por ticket, los sabores vendidos y las marcas proteicas que aparecen en su historial.

## Campaña

- Fechas: 4 de mayo al 14 de junio de 2026.
- Incentivo: €1,50 de cashback por yogur.
- Límite indicado: hasta 3 unidades por ticket y 1 uso por usuario.
- Meta de volumen: 3.000 unidades.

## Datos y herramientas

Los cuatro archivos CSV incluyen tickets de campaña, historial de yogur de los 12 meses anteriores, perfil de participantes y una referencia agregada del universo GELT. El análisis se trabajó con Power Query, modelo tabular de Power BI y medidas DAX.

## Resultados reproducidos desde los CSV

- 1.800 compradores, 2.061 tickets y 3.103 unidades registradas.
- Origen: 265 sin historial de yogur (14,72 %), 708 con historial no proteico (39,33 %) y 827 con historial proteico (45,94 %).
- 1.595 participantes no muestran compra previa de Kalia en el historial entregado. Kalia se lanzó en marzo de 2026, así que este dato no representa 12 meses completos de disponibilidad de la marca.
- Unidades por sabor: Fresa 1.057, Natural 1.045 y Mango 1.001.
- Marcas proteicas históricas: Protis 793, Fitlac 754, MDD 709 y Kalia 205. Los compradores pueden aparecer en varias marcas.

## Salvedad sobre el objetivo de unidades

El volumen bruto registrado es 3.103, equivalente al 103,4 % de la meta. Sin embargo, 209 personas tienen más de un ticket. Al contar solo el primer ticket cronológico por persona, el archivo suma 2.703 unidades (90,1 % de la meta). Hay que conciliar tickets y redenciones para saber qué volumen recibió cashback bajo la regla de un uso por usuario.

## Alcance del informe

El PBIX presenta el volumen, la evolución diaria, unidades por SKU, origen histórico, compradores previos de Kalia, carga por ticket y marcas históricas. El análisis demográfico, la visualización por enseña, la relación entre sabor y segmento de comprador, la recompra posterior y la confianza en el fabricante requieren datos o visuales adicionales.

## Validación

Los recuentos y porcentajes principales se recalcularon desde los CSV. Se revisó la definición de los visuales del PBIX y se confirmaron las correcciones del gráfico de origen y de las conclusiones de marcas/enseñas. El DAX no se ejecutó en el motor de Power BI Desktop durante esta revisión. La serie diaria todavía utiliza `Calendario[Día/Mes]` como texto; debe cambiarse a una fecha real para asegurar el orden cronológico.

## Archivos

- `docs/Requerimiento_Funcional_Kalia_v0.2.docx`: problema, alcance, metodología, KPI y limitaciones.
- `presentation/Presentacion_Resultados_Campana_Kalia_v0.3.pptx`: explicación ejecutiva del informe.
- `report/Informe de resultados de campaña.pbix`: archivo del informe, tras revisar las rutas de origen y los metadatos.
- `data/`: CSV ficticios autorizados y revisados para publicación, con una nota de procedencia.
