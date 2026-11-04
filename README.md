# METALGEST 1.0

**Sistema de gestión de compras y proveedores — Metalmecanicosfr**

Prototipo web de una sola página para el plan de mejoramiento de la práctica tecnológica. Funciona con HTML, CSS y JavaScript, sin compilación ni instalación de dependencias.

## Funciones incluidas

- Panel con indicadores de proveedores, cotizaciones, órdenes, gastos y vencimientos.
- Proveedores: alta, búsqueda, edición y eliminación controlada.
- Materiales: catálogo, códigos, categorías, unidades y dimensiones.
- Obras: registro de proyectos y asociación a documentos.
- Cotizaciones: registro por proveedor, con múltiples materiales, cantidades, precios, descuentos, transporte, IVA, fechas y plazo.
- Comparativo: selección de dos o más cotizaciones, total y plazo de entrega, con desglose de materiales.
- Órdenes de compra: consecutivos automáticos, edición, vista imprimible y guardado en PDF mediante el navegador.
- Seguimiento: estado de órdenes, vencimiento automático y registro de entregas parciales por material.
- Reportes: exportación por módulo a Excel XML `.xls` compatible con Excel/LibreOffice (no `.xlsx` nativo).
- Seguridad de datos: copia de seguridad JSON, importación, datos de prueba claramente identificados y limpieza total.

## Uso local

1. Descomprimir el ZIP.
2. Abrir `index.html` en Chrome, Edge o Firefox.
3. Entrar a **Reportes y respaldo** y pulsar **Cargar datos de demostración** para explorar sin utilizar información real.
4. Registrar proveedores y materiales antes de crear cotizaciones u órdenes.
5. En **Seguimiento**, solo las órdenes enviadas admiten recepción.
6. Descargar periódicamente el respaldo JSON (se conserva todo el registro, incluidas recepciones).

## Publicarlo en GitHub Pages

1. Crear un repositorio nuevo en GitHub, por ejemplo `metalgest`.
2. Subir `index.html`, `styles.css` y `app.js` a la raíz del repositorio; subir también este README.
3. Abrir el repositorio → **Settings** → **Pages**.
4. En **Build and deployment**, seleccionar **Deploy from a branch**, rama `main`, carpeta `/ (root)`. Guardar.
5. Acceder al enlace de GitHub Pages indicado en esa sección una vez finalizado el despliegue.

**No subir documentos reales de cotización, facturas ni respaldos JSON al repositorio público.** Para fines de demostración utilizar exclusivamente los datos de prueba incluidos.

## Limitaciones importantes

- GitHub Pages solo aloja la interfaz pública; **NO es una base de datos**.
- Los datos se guardan en `localStorage` del navegador y equipo donde se usa. No se sincronizan en otros navegadores, computadores o dispositivos.
- Borrar el almacenamiento del navegador, utilizar modo privado o cambiar de equipo puede hacer que se pierdan registros. Por ello se incluye respaldo/restauración JSON.
- No hay inicio de sesión, autorización por roles, cifrado de datos en servidor, auditoría ni almacenamiento de archivos adjuntos. Esta versión **no está preparada para operar con información comercial sensible en producción**.
- La comparación sirve de apoyo; solo tiene sentido comparar cotizaciones equivalentes en materiales, cantidades, especificaciones, IVA y fletes.
- El estado `Retrasada` se calcula por fecha de entrega. Los estados `Recibida` y `Parcialmente recibida` se calculan por cada material recibido.
- La descarga Excel es `.xls` XML (SpreadsheetML), no `.xlsx`. Si Excel advierte de formato, se puede abrir con LibreOffice Calc o importar el XML en Excel y guardar como `.xlsx`.
- No emite facturas electrónicas ni documentos tributarios.

## Futura versión empresarial

Para uso real compartido se recomienda base de datos PostgreSQL/Supabase, autenticación, roles, políticas de seguridad por fila, adjuntos privados, historial de cambios y exportación `.xlsx` del lado del cliente o servidor. **No guardar claves privadas de servicios en el frontend ni en GitHub.**

## Alcance académico

El aplicativo se entrega como prototipo implementado. Las capturas y pruebas con valores ficticios demuestran funcionalidades, **no** resultados operativos reales ni la implementación permanente en la empresa. El diagnóstico, el análisis y las conclusiones del informe deben validarse con la practicante y los datos de la empresa, respetando las instrucciones institucionales sobre uso de IA.
