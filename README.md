# Amano

Software de gestión comercial para negocios chicos. Se instala en la
computadora del negocio y los datos quedan ahí: no hay servidor, no hay cuenta,
no hay mensualidad.

**Estado: beta.** Funciona de punta a punta y está en período de prueba con
catálogos reales. Se puede usar; puede tener errores.

---

## Qué hace

| | |
|---|---|
| **Catálogo** | Artículos con costo, precio de venta, stock y códigos de barras. Búsqueda por cualquier parte del código o la descripción |
| **Mostrador** | Pantalla para atender parado: se escanea o se escribe, aparece el precio, se arma la venta y se cobra |
| **Listas de precio** | El precio de venta sale del costo y un margen, que puede ser distinto por rubro y por cliente. Al actualizar el costo, la venta se actualiza sola |
| **Importar listas** | Lee el Excel del proveedor, muestra qué sube y qué baja antes de aceptar, y guarda la historia de precios |
| **Stock** | Existencia por depósito, recuento de inventario, mínimos de reposición |
| **Ventas y compras** | Presupuesto, remito y factura interna. Anular no borra: registra el movimiento contrario |
| **Cuentas corrientes** | Lo que debe cada cliente y lo que se le debe a cada proveedor, con cobros y pagos parciales |
| **Caja** | Apertura, movimientos por medio de pago, arqueo y cierre |
| **Informes** | Cuánto se vendió, qué deja margen, cuánto hay en stock y quién debe |
| **Dólar** | Los artículos comprados en moneda extranjera se pasan a pesos con la cotización del día |

## Qué no hace

- **No emite comprobantes fiscales ni se conecta a ARCA.** Los comprobantes que
  imprime son internos y lo dicen. Es una decisión, no algo pendiente.
- **No funciona desde el celular ni por internet.** Es un programa de
  escritorio.
- **No guarda nada en la nube.** Los datos no salen de la máquina.
- **Está pensado para un puesto.** Dos computadoras contra la misma base es
  posible pero todavía no está probado.

---

## Requisitos

- Windows 10 o Windows 11, 64 bits.
- 300 MB de disco para el programa. La base de datos crece con el uso: un
  catálogo de 35.000 artículos con un año de movimiento ocupa unos 40 MB.
- No hace falta instalar nada más.

## Instalación

1. Descargar `Amano-setup.exe` de la sección **Releases**.
2. Doble clic. El asistente deja elegir en qué carpeta instalarlo.
3. **La primera vez Windows va a avisar** que no reconoce el programa: dice
   «Windows protegió tu PC». Hay que tocar **Más información** y después
   **Ejecutar de todas formas**. Pasa porque el instalador no está firmado
   digitalmente; aparece una sola vez por computadora.
4. Listo. Queda en el menú Inicio y abre con doble clic.

No pide clave de administrador y no instala nada en segundo plano.

## Primeros pasos

1. **Importar listas** — elegí el Excel de un proveedor y decile qué columna es
   cada cosa. Antes de aceptar, la pantalla muestra qué artículos suben, cuáles
   bajan y cuáles son nuevos.
2. **Catálogo** — revisá que los precios hayan entrado bien. La columna Venta
   sale sola del costo y el margen.
3. **Mostrador** — buscá un artículo y hacé una venta de prueba.
4. **Caja** — abrila al empezar el día y cerrala al terminar, contando el
   efectivo.
5. **Revisar catálogo** — muestra lo que está mal: artículos sin costo, con
   stock en negativo, por debajo del mínimo o que se venden perdiendo plata.

## Los datos y las copias de seguridad

Todo vive en un solo archivo:

```
C:\Users\<usuario>\AppData\Roaming\ar.amano.gestion\amano.db
```

El programa guarda **una copia por día** al abrirse, en la subcarpeta
`respaldos\`, y conserva las últimas veinte. Restaurar está en la pantalla
**Revisar catálogo**: cada copia muestra cuántos artículos tiene adentro, y
antes de restaurar guarda el estado actual, así que siempre se puede volver.

Para llevar los datos a otra computadora se copia ese archivo, con el programa
cerrado.

---

## Código

El código fuente no es público.

Los informes de errores y las sugerencias van en la sección **Issues**.
