# Historias de usuario
 
## HU-01: Autenticación de Operarios
Como Operario de Bodega, quiero iniciar sesión en la aplicación web mediante mis credenciales, para acceder a los proyectos autorizados y mantener la seguridad del sistema.
**Actividad TO-BE asociada:** Iniciar sesión en SnapSip desde celular.
**Criterios de aceptación:**
- CA1: **Dado** que el operario se encuentra en la pantalla de inicio, **Cuando** ingresa un correo y contraseña válidos y presiona "Ingresar", **Entonces** el sistema le da acceso al panel principal de proyectos.
- CA2: **Dado** que el operario intenta iniciar sesión, **Cuando** ingresa una contraseña incorrecta, **Entonces** el sistema muestra un mensaje de error "Credenciales inválidas" y deniega el acceso.
 
## HU-02: Gestión Autónoma de Proyectos
Como Operario de Bodega, quiero poder crear, visualizar y editar los proyectos y sus torres asociadas en el sistema, para organizar el almacenamiento físico sin depender de jefaturas.
**Actividad TO-BE asociada:** Crear/Editar Proyecto y Torres en SnapSip.
**Criterios de aceptación:**
- CA1: **Dado** que el operario está en la vista del panel principal, **Cuando** presiona "Nuevo Proyecto", llena el formulario y guarda, **Entonces** el sistema crea el proyecto y lo muestra inmediatamente en el listado activo.
- CA2: **Dado** que un proyecto ya no es necesario, **Cuando** el operario selecciona "Eliminar", **Entonces** el sistema borra el proyecto y sus torres de la base de datos tras una confirmación.

## HU-03: Filtrado Específico de Piezas
Como Operario de Bodega, quiero filtrar las piezas de una torre específica mediante una barra de búsqueda, para localizar rápidamente el material en la interfaz sin tener que hacer scroll infinito.
**Actividad TO-BE asociada:** Filtrar torre y abrir checklist.
**Criterios de aceptación:**
- CA1: **Dado** que el operario está visualizando el listado completo de piezas de una torre, **Cuando** ingresa el código "H1" en el buscador, **Entonces** el sistema oculta las demás piezas y muestra únicamente aquellas que coinciden con "H1".
- CA2: **Dado** que el buscador tiene texto ingresado, **Cuando** el operario borra el texto, **Entonces** el sistema vuelve a mostrar el listado completo de piezas de esa torre.

## HU-04: Checklist de Armado con Trazabilidad
Como Operario de Bodega, quiero marcar visualmente las piezas como "listas" en un checklist interactivo, para asegurar y registrar que la torre está completa antes del despacho.
**Actividad TO-BE asociada:** Verificar físicamente las piezas y marcar checklist en la app.
**Criterios de aceptación:**
- CA1: **Dado** que una pieza está en estado "pendiente" (gris), **Cuando** el operario presiona el botón de validación sobre ella, **Entonces** el sistema cambia su estado visual a "listo" (verde).
- CA2: **Dado** que el operario marcó una pieza como lista, **Cuando** el sistema guarda el cambio, **Entonces** registra automáticamente el usuario que hizo la acción, la fecha y la hora exacta en la base de datos (Timestamp).

## HU-05: Bloqueo de Guía de Despacho
Como Encargado de Despacho, quiero que el sistema bloquee la generación del documento PDF si la torre está incompleta, para evitar despachar camiones a medias y generar sobrecostos por fletes.
**Actividad TO-BE asociada:** Descargar Guía de Despacho PDF desde SnapSip.
**Criterios de aceptación:**
- CA1: **Dado** que una torre tiene una o más piezas con estado "pendiente" en su checklist, **Cuando** el Encargado revisa el estado del proyecto, **Entonces** el botón de "Generar PDF" se encuentra deshabilitado y bloqueado.
- CA2: **Dado** que la torre alcanzó el 100% de piezas "listas" en su checklist, **Cuando** el sistema actualiza el estado a Terminado, **Entonces** habilita automáticamente el botón de "Generar PDF" para su descarga.
