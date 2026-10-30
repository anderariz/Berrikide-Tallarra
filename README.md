# BerriKide · Gestión de tareas

Prototipo de una interfaz sencilla para sustituir las hojas de trabajo en papel. Pensado para tablet en horizontal, con botones grandes, instrucciones por pasos y una tarea activa por usuario.

[ Abrir la demo ](https://anderariz.github.io/Berrikide-Tallarra/)

## Usuarios de demostración

Los avatares del lateral permiten cambiar de perfil. Cada perfil muestra sus tareas y su actividad.

| Usuario | Función | Tareas de ejemplo |
| --- | --- | --- |
| Ane | Administración y compras | Comprar 80 barras de aluminio de 40 × 40 × 6000 mm, revisar facturas y confirmar pedidos. |
| Mikel | Taller | Corte de chapa, roscado M6 y recepción de material. |
| Gregorio | Gerencia | Aprobar ofertas, autorizar remesas de pagos y revisar prioridades. |

El selector simula usuarios: no hay contraseñas, autenticación ni permisos de servidor. Todos los datos de ejemplo están incluidos en el HTML.

## Recorrido de una tarea

1. Seleccionar una tarea del perfil.
2. Consultar el resumen, los pasos y los documentos asociados.
3. Pulsar **Empezar tarea**. El lateral desaparece y se muestra el paso actual.
4. Seguir las instrucciones y utilizar la acción principal: leer QR, confirmar una gestión o registrar cantidades.
5. Completar los movimientos requeridos y pulsar **Tarea terminada**.
6. Pasar a la siguiente tarea.

**Atrás** vuelve al detalle con el listado visible, pausa el tiempo y conserva el progreso. También se puede pausar una tarea o registrar una incidencia seleccionando su motivo, sin escribir texto libre. Al cambiar de usuario se pausa la intervención activa. La gestión simultánea de varias máquinas queda para una futura versión avanzada.

## Lotes, ubicaciones y cámara

- El QR de la hoja o pegatina del cestón identifica el **lote**.
- Los QR de máquinas y ubicaciones identifican **dónde** realizar o depositar el trabajo.
- **Leer QR** abre un visor con un cuadro para encuadrar la etiqueta.
- Si el navegador permite acceso a la cámara, se muestra su imagen; si no, se puede continuar la simulación.
- **Código OK** simula una lectura correcta y avanza.
- **Código NOK** cierra el visor, informa de la discrepancia y mantiene el paso.
- Cancelar no completa el paso. La cámara se detiene al cerrar el visor.

La imagen de cámara puede ser real, pero **no se decodifican ni validan QR reales**. El resultado se elige con los botones del mockup.

## Cantidades y cierre

Las cantidades se introducen con un teclado numérico táctil:

- Producción: piezas buenas y malas.
- Recepción: barras aceptadas y rechazadas.
- Compras: barras pedidas y pendientes; comprar y recibir son tareas distintas.
- Administración y gerencia: confirmación de pasos, sin cantidades de producción.

En esta demo, las dos cantidades deben sumar el objetivo del lote o pedido. Un lote de producción incompleto requiere registrar una incidencia y mantener la tarea abierta. El cierre de compra puede reflejar barras pendientes: no equivale a recibir el material.

## Instrucciones y documentos

Cada tarea incluye instrucciones de su paso actual y documentos que se abren dentro de la aplicación:

- Ficha de tarea.
- Croquis ilustrativo e instrucción de trabajo para producción.
- Solicitud de material para compras y recepción.
- Guías de revisión para administración y gerencia.

Son documentos de ejemplo integrados en el HTML. El croquis no contiene cotas ni parámetros de fabricación. Los planos, revisiones y procedimientos aprobados de la empresa deberán sustituir estos ejemplos antes de un uso operativo.

## Datos y alcance

- Un único archivo `index.html`, sin instalación ni compilación.
- Identidad visual de BerriKide y avatares compactos en el lateral.
- Registro de actividad por perfil y tiempo de intervención.
- Progreso, cantidades y actividad guardados en `localStorage` del navegador, si está disponible.
- Al recargar se conservan los datos guardados y las intervenciones activas quedan pausadas.
- No hay sincronización entre dispositivos, base de datos central ni integración con Businessmap.
- No se envían pedidos, correos, pagos ni autorizaciones reales.
- La conservación local no es una copia de seguridad: borrar los datos del navegador elimina el progreso.

Businessmap está previsto como centro de gestión en una fase posterior. La versión actual es únicamente un mockup funcional con datos de ejemplo.

## Uso y publicación

Abrir `index.html` permite probar la interfaz. Para probar la cámara, usar preferentemente la demo publicada mediante HTTPS y conceder permiso al navegador. Su disponibilidad depende del dispositivo y del navegador. El logo está integrado; las fuentes Exo y Nunito se solicitan a Google Fonts y tienen fuentes alternativas si no hay conexión.

Repositorio: [anderariz/Berrikide-Tallarra](https://github.com/anderariz/Berrikide-Tallarra).

Para actualizar:

1. Subir `index.html` a la raíz del repositorio, sustituyendo el existente.
2. Subir también `README.md` cuando cambien las funciones o las instrucciones.
3. Confirmar con **Commit changes**.
4. Comprobar en **Actions** que el despliegue de GitHub Pages termina correctamente.
5. Recargar la web para ver la versión publicada.

El README documenta la aplicación; cambiarlo por sí solo no modifica su interfaz. Subir un archivo no garantiza que ya esté publicado: si el despliegue aparece como **Queued**, sigue pendiente. Volver a subir el mismo contenido no resuelve una cola de publicación.

La configuración utilizada es GitHub Pages desde la rama `main` y la carpeta raíz `/(root)`.

## Evolución prevista

- Conexión con Businessmap.
- Usuarios autenticados y permisos reales.
- Lectura y validación automática de QR.
- Documentos reales por tarea y revisión.
- Almacenamiento compartido y trazabilidad centralizada.
- Nivel avanzado para supervisar procesos simultáneos.

