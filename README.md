# Scaner3D — Editor 3D sobre STL guía

Editor 3D en el navegador para cargar un modelo STL como **referencia** y diseñar tu propia pieza encima, sin instalar nada.

Pensado originalmente para generar en malla/red de filamento sobre un STL guía, para montarlo sobre una base y obtener un efecto tipo holograma — pero sirve para cualquier diseño que necesite una referencia 3D de fondo.

## Funciones

- **STL guía**: cárgalo como referencia semi-transparente (no editable).
- **Importar modelo editable**: STL, OBJ, GLTF/GLB.
- **Primitivas**: cubo, esfera, cilindro, cono, toro, plano.
- **Biblioteca de modelos**: plantillas rápidas (pilar, corona, anillo) + tus propios modelos guardados en el navegador.
- **Selección y transformación**: mover / rotar / escalar con gizmo, duplicar objeto.
- **Material**: color, rugosidad, metalicidad, sombreado suave/plano.
- **Edición de malla**: subdividir, extrusión de cara superior, pincel de escultura.
- **Operaciones booleanas**: unión, resta, intersección
- **Deshacer / Rehacer**: `Ctrl+Z` / `Ctrl+Y`.
- **Exportar**: STL, OBJ, GLTF/GLB.
- **Autoguardado** local (cada 15s y en cada acción) y recuperación tras pérdida de contexto WebGL.

## Cómo usarlo

No requiere instalación.

## Privacidad

Esta app corre **100% en tu navegador**. No se envía ningún dato — modelos, diseños ni nada más — a ningún servidor externo. El autoguardado y la biblioteca de modelos se guardan solo en el almacenamiento local (`localStorage`) de tu propio navegador.

## Licencia

Todos los derechos reservados © 2026 Yoshio Carballo. Ver [LICENSE](./LICENSE).
