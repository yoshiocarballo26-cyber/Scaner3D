# Scaner3D — YC Editor 3D

Editor 3D en el navegador para crear, editar, revisar y preparar modelos 3D, sin instalar nada.

## Funciones actuales

- **STL guía**: carga un STL como referencia semitransparente y no editable.
- **Importar modelos editables**: STL, OBJ, GLTF/GLB.
- **Primitivas**: cubo, esfera, cilindro, cono, toro y plano.
- **Biblioteca de modelos**: plantillas rápidas y modelos guardados localmente.
- **Selección y transformación**: mover, rotar, escalar, duplicar y eliminar.
- **Alineación entre piezas**: alineación por eje y modos de centro/extremos.
- **Imán de superficie**: detecta una superficie real de otra pieza y acerca la pieza seleccionada para hacer contacto. Puede activarse al soltar o ejecutarse manualmente.
- **Materiales**: color, rugosidad, metalicidad, opacidad y sombreado.
- **Edición de malla**: subdividir, extruir, esculpir, soldar vértices, invertir caras, suavizar y simplificar.
- **Corte de malla**: corte por plano y caja de corte.
- **Agujero de drenado**: crea un cilindro de corte para preparar un orificio de drenaje y después aplicarlo mediante resta booleana.
- **Vista de rayos-X / sección**: permite inspeccionar visualmente el interior de una pieza mediante transparencia y plano de sección, sin modificar la geometría.
- **Diagnóstico de malla**: analiza geometría válida, triángulos degenerados, vértices repetidos, cierre de la malla, volumen y dimensiones. El diagnóstico no modifica la pieza.
- **Operaciones booleanas**: unión, resta e intersección.
- **Medición**: distancias y ángulos, con lectura en mm y cm.
- **Deshacer / Rehacer**: `Ctrl+Z` / `Ctrl+Y`.
- **Exportación**: STL, OBJ, GLTF/GLB.
- **Autoguardado local**: guarda periódicamente y después de acciones importantes, con recuperación de sesión.
- **Funcionamiento en navegador**: la aplicación está diseñada para trabajar localmente en el navegador.

## Tutorial rápido

### 1. Crear o importar una pieza

Puedes comenzar desde **Crear** para añadir una primitiva o importar un modelo desde **Importar**.

Formatos editables admitidos:

- STL
- OBJ
- GLTF/GLB

Para trabajar sobre una pieza de referencia, carga el STL como **STL guía**.

### 2. Seleccionar y mover

Toca una pieza para seleccionarla.

Usa el gizmo para:

- mover,
- rotar,
- escalar.

También puedes usar el panel de objeto para introducir dimensiones y transformaciones con mayor precisión.

### 3. Alinear dos piezas

Selecciona la pieza que quieres mover y utiliza **Alinear**.

Elige la pieza objetivo y el eje correspondiente.

Esta función realiza una alineación geométrica basada en la caja de cada pieza. Para buscar contacto real entre superficies utiliza **Imán de superficie**.

### 4. Usar el imán de superficie

1. Selecciona la pieza que quieres mover.
2. Activa **Imán de superficie al soltar** si quieres que se ejecute automáticamente al terminar un movimiento.
3. Ajusta la distancia máxima, inicialmente **3 mm**, si es necesario.
4. Mueve la pieza cerca de otra pieza.
5. Al soltar, el editor busca una superficie de la otra pieza y acerca el punto detectado hasta hacer contacto.

También puedes pulsar **Imán de superficie ahora** para ejecutarlo manualmente.

Si no encuentra una superficie dentro de la distancia configurada, la pieza no se mueve.

### 5. Inspeccionar el interior con rayos-X

1. Selecciona una pieza.
2. Ve a **Malla / corte**.
3. Activa **Vista de rayos-X**.
4. Ajusta el eje y la posición del plano de sección.
5. Observa el interior de la pieza sin aplicar el corte.

La vista de rayos-X es una herramienta de inspección: activar la vista no modifica la geometría.

### 6. Preparar un agujero de drenado

Para una pieza hueca:

1. Selecciona la pieza.
2. Utiliza **Agujero de drenado**.
3. Aparecerá un cilindro que funciona como herramienta de corte.
4. Mueve y rota el cilindro para atravesar la pared en el lugar deseado.
5. Aplica la operación de **Restar de la pieza**.
6. Comprueba el resultado con **Rayos-X**.

El agujero de drenado utiliza el sistema de resta booleana; por eso la pieza debe estar en condiciones adecuadas para una operación booleana.

### 7. Diagnosticar una malla

1. Selecciona la pieza.
2. Abre **Diagnóstico de malla**.
3. Pulsa **Analizar pieza seleccionada**.
4. Revisa:

   - cantidad de triángulos,
   - geometría válida,
   - triángulos degenerados,
   - vértices repetidos,
   - malla cerrada,
   - volumen,
   - dimensiones.

Si aparece **✓ MALLA LISTA**, las comprobaciones actuales no encontraron problemas en esos criterios.

Si aparece **⚠ REVISAR**, utiliza las herramientas de reparación de malla antes de continuar.

> El diagnóstico actual es una revisión geométrica. No sustituye todavía un análisis completo de imprimibilidad, como espesor mínimo de pared, soportes o tolerancias.

### 8. Reparar una malla

Si el diagnóstico encuentra problemas, utiliza las herramientas de **Reparar y optimizar**, según el problema detectado.

Después vuelve a ejecutar el diagnóstico para comprobar el resultado.

### 9. Medir

Activa **Medir** y selecciona los puntos de la pieza.

Puedes medir:

- distancia,
- diferencia en X, Y y Z,
- ángulo.

Las distancias se muestran en mm y cm.

### 10. Cortar y usar booleanas

Las herramientas de malla permiten realizar cortes y operaciones booleanas:

- unión,
- resta,
- intersección.

Las operaciones booleanas requieren geometría adecuada; si una operación falla, primero revisa y repara la malla.

### 11. Exportar

Cuando termines, utiliza **Exportar** y elige:

- STL
- OBJ
- GLTF/GLB

Antes de exportar una pieza destinada a impresión 3D, conviene ejecutar el diagnóstico de malla y revisar el modelo con rayos-X.

## Flujo recomendado para impresión 3D

Un flujo de trabajo recomendado dentro de las funciones actuales es:

**Crear/importar → editar → alinear o usar imán de superficie → ahuecar → agujero de drenado → rayos-X → diagnóstico de malla → reparar si es necesario → medir → exportar.**

## Privacidad

Esta app corre **100% en tu navegador**. Los modelos y diseños se procesan localmente en el navegador. El autoguardado y la biblioteca de modelos utilizan el almacenamiento local del navegador.

Algunas funciones, como el motor de operaciones booleanas y la carga de determinadas fuentes/recursos externos, pueden requerir conexión a Internet.

## Licencia

Todos los derechos reservados © 2026 Yoshio Carballo. Ver [LICENSE](./LICENSE).
