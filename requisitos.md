# Clasificación de requisitos

## Requisitos de producto

| ID | Requisito | Tipo (funcional/no funcional) | Actividad TO-BE asociada |
|----|-----------|--------------------------------|----------------------------|
| RP-01 | El sistema debe proveer una estructura jerárquica de visualización para organizar la información de Proyectos, Tipos, Torres y Paneles almacenados en la base de datos. | Funcional | Monitoreo y control de piezas del proyecto |
| RP-02 | La interfaz de usuario debe cumplir con heurísticas de usabilidad y contar con una representación gráfica de las torres y sus paneles asociados. | No funcional | Monitoreo y control de piezas del proyecto |
| RP-03 | El sistema debe permitir la búsqueda y el filtrado eficiente de registros de paneles específicos dentro de los proyectos. | Funcional | Monitoreo y control de piezas del proyecto |
| RP-04 | El sistema debe requerir autenticación de usuarios mediante credenciales para restringir el acceso a los operarios. | Funcional | Inicio de sesión y autenticación de usuario |
| RP-05 | El sistema debe registrar automáticamente en la base de datos la trazabilidad de las acciones (identificador de usuario, fecha y hora exacta) al completar un checklist. | Funcional | Verificación y armado de torres en terreno |
| RP-06 | El sistema debe permitir actualizar el estado de una Torre o de un Proyecto a "Terminado" una vez que se valide la completitud de su checklist respectivo. | Funcional | Verificación y armado de torres en terreno |
| RP-07 | El sistema debe permitir la generación y exportación de un documento en formato PDF ("Guía de Despacho") con los datos de los paneles procesados para respaldo de bodega. | Funcional | Despacho y generación de guía PDF |
| RP-08 | El sistema debe gestionar el control de acceso mediante al menos dos roles: Administrador (con privilegios de gestión de datos) y Operario (con privilegios de lectura y actualización de checklists). | Funcional | Inicio de sesión y autenticación de usuario |
| RP-09 | La solución debe implementarse como una aplicación web con diseño responsivo, accesible desde dispositivos móviles en faena mediante conexión a internet. | No funcional | Verificación y armado de torres en terreno |
| RP-10 | La arquitectura del sistema (servidor web y base de datos) debe garantizar alta disponibilidad para asegurar la continuidad operativa durante el horario de trabajo. | No funcional | (General de plataforma) |

## Requisitos de proyecto

| ID | Requisito |
|----|-----------|
| RY-01 | El alcance del proyecto finaliza con la entrega del software funcional. No se contempla soporte técnico, mantenimiento evolutivo ni actualizaciones posteriores a la entrega del sistema y de las credenciales de administración al cliente. |

## Requisito derivado

**Requisito origen:** [RP-07] El sistema debe permitir la generación y exportación de un documento en formato PDF ("Guía de Despacho") con los datos de los paneles procesados para respaldo de bodega.

**Requisito derivado:** La funcionalidad para exportar la Guía de Despacho en PDF debe estar restringida por el sistema hasta que los registros del checklist de la torre asociada indiquen un 100% de completitud.

**Justificación:** El proceso TO-BE incorpora una validación de integridad para mitigar el riesgo de piezas faltantes. A nivel de sistema, se bloquea la emisión del documento oficial si los registros en la base de datos indican que la torre está incompleta, forzando lógicamente al operario a finalizar la verificación previa a la carga del camión.
