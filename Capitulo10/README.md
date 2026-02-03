
# Públicalo en una interfaz (Microsoft Teams)

---

## Descripción General

En esta actividad grupal final, los equipos publicarán su agente bancario de IA desarrollado con Microsoft Copilot Studio en Microsoft Teams, configurando controles de acceso apropiados y estableciendo estrategias de despliegue controlado. Esta actividad simula un escenario real de producción donde los equipos implementarán un despliegue por fases (piloto y producción), configurarán monitoreo de uso, y crearán documentación de soporte para usuarios finales. Los participantes aplicarán buenas prácticas de gobernanza y seguridad en el proceso de publicación.

---

## Objetivos de Aprendizaje

Al completar este laboratorio, usted será capaz de:

- Publicar un agente de IA en Microsoft Teams para usuarios reales
- Configurar controles de acceso y permisos apropiados utilizando grupos de seguridad
- Implementar estrategias de despliegue controlado (fase piloto y producción)
- Configurar monitoreo y análisis de uso del agente publicado
- Documentar procedimientos de mantenimiento y actualización post-publicación

---

## Prerrequisitos

Conocimientos Requeridos
- Comprensión de conceptos de publicación de aplicaciones empresariales
- Familiaridad con Microsoft Teams y gestión de aplicaciones
- Conocimiento de grupos de seguridad en Azure Active Directory
- Experiencia previa con Copilot Studio (Módulos 1-9 completados)

---

## Acceso Requerido
- Cuenta de Microsoft 365 con licencia Business Standard o superior
- Licencia activa de Microsoft Copilot Studio
- Permisos de administrador en Microsoft Teams o aprobación de administrador para publicación
- Acceso a Azure Active Directory para gestión de grupos
- Agente de IA completamente funcional y validado del Módulo 9

---

##  Entorno de Laboratorio

### Hardware

| Componente | Especificación |
|----------|---------------|
| CPU | Intel Core i5 o equivalente |
| RAM | 8 GB mínimo |
| Disco | 10 GB libres |
| Resolución | 1366x768 |
| Internet | ≥ 10 Mbps |

### Software

- Microsoft Edge o Google Chrome
- Microsoft 365
- Copilot Studio
- Power Platform
- Microsoft Teams

---

## Configuración Inicial

Antes de comenzar, cada equipo debe verificar:

1. Agente validado: El agente bancario debe estar completamente funcional con todas las características implementadas en módulos anteriores
2. Permisos de publicación: Confirmar acceso a la función de publicación en Copilot Studio
3. Grupos de usuarios: Identificar o crear grupos de seguridad para fase piloto (3-5 usuarios) y producción
4. Plantilla de documentación: Descargar la plantilla de documentación de usuario proporcionada por el instructor

---

##  Desarrollo del Laboratorio

## Paso 1: Preparación Pre-Publicación y Checklist de Seguridad
Objetivo: Validar que el agente cumple con todos los requisitos de seguridad y funcionalidad antes de publicarlo en producción.

## Instrucciones:

1. Abra Microsoft Copilot Studio y navegue hasta su agente bancario desarrollado en módulos anteriores.
2. Acceda a la sección de "Configuración" (Settings) del agente y verifique los siguientes elementos del checklist de seguridad:
 ✅ Autenticación configurada: Verifique que la autenticación esté habilitada
 ✅ Manejo de datos sensibles: Confirme que no hay información real de clientes
 ✅ Temas de error: Valide que existan temas de error personalizados
 ✅ Límites de conversación: Verifique configuración de timeouts y límites
 ✅ Transferencia a humano: Confirme que la escalación funciona correctamente
3. Realice una prueba final completa del agente utilizando el panel de "Prueba" (Test):
   Escenarios de prueba:
   - Consulta de saldo de cuenta
   - Solicitud de información sobre préstamos
   - Pregunta fuera de alcance (debe escalar apropiadamente)
   - Consulta con datos sensibles (debe manejarse con seguridad)
4. Documente cualquier problema encontrado en la plantilla proporcionada bajo la sección "Validación Pre-Publicación".
5. En la sección "Detalles" (Details) del agente, verifique que:
- El nombre del agente sea profesional y descriptivo
- El icono sea apropiado para contexto bancario
- La descripción explique claramente el propósito del agente

Salida Esperada:

Un checklist completado sin problemas críticos pendientes, con el agente listo para publicación.

Verificación:

- Todos los elementos del checklist de seguridad están marcados como completados
- Las pruebas finales se ejecutaron exitosamente sin errores críticos
- La documentación de validación está completa
---

## Paso 2: Configuración del Canal de Publicación en Microsoft Teams
Objetivo: Configurar Microsoft Teams como canal de publicación para el agente de IA.

## Instrucciones:

1. En Copilot Studio, con su agente abierto, haga clic en "Canales" (Channels) en el menú lateral izquierdo.
2. Localice el canal "Microsoft Teams" y haga clic en "Activar" (Turn on) o "Editar" (Edit) si ya está activado.
3. En la página de configuración de Teams, configure los siguientes parámetros:
- Nombre de la aplicación: Asistente Bancario Virtual [Nombre del Equipo]
- Descripción corta: Agente de IA para consultas bancarias y soporte al cliente
- Descripción larga: Proporcione una descripción detallada de las capacidades del agente (mínimo 80 caracteres)
- Sitio web del desarrollador: URL de su organización o sitio de documentación
- Política de privacidad: URL de política de privacidad (puede usar una plantilla proporcionada)
- Términos de uso: URL de términos de uso
4. En la sección "Configuración de aplicación" (App settings):
- Seleccione "Personal" como alcance inicial (para chat uno-a-uno)
- Deje deshabilitadas las opciones de "Equipo" y "Chat grupal" para la fase piloto
5. Haga clic en "Guardar" (Save) para aplicar la configuración.
6. Haga clic en "Abrir en Teams" (Open in Teams) para generar el paquete de aplicación.
7. Teams se abrirá automáticamente con una vista previa del agente. NO instale todavía, primero configuraremos los permisos.

Salida Esperada:

El canal de Microsoft Teams está configurado y el paquete de aplicación está generado, listo para configuración de permisos.

Verificación:

- El canal de Teams muestra estado "Activado" en Copilot Studio
- La vista previa en Teams muestra correctamente el nombre, icono y descripción
- Todos los campos obligatorios están completados
---

## Paso 3: Configuración de Audiencias y Permisos (Fase Piloto)
Objetivo: Definir grupos de usuarios para un despliegue controlado comenzando con un grupo piloto reducido.

## Instrucciones:

1. En Microsoft Teams, haga clic en "Aplicaciones" (Apps) en la barra lateral izquierda.
2. Haga clic en "Administrar las aplicaciones" (Manage your apps) y luego en "Cargar una aplicación" (Upload an app).
3. Seleccione "Cargar una aplicación personalizada" (Upload a custom app).
> Nota: Si no tiene permisos, deberá solicitar a su administrador de Teams que cargue la aplicación o que le otorgue permisos de carga de aplicaciones personalizadas.

4. Seleccione el paquete de aplicación que Copilot Studio generó (si se descargó automáticamente) o descárguelo desde Copilot Studio:
- En Copilot Studio, vaya a Canales > Microsoft Teams
- Haga clic en "Descargar paquete de aplicación" (Download app package)
- Guarde el archivo .zip
5. Cargue el archivo .zip en Teams. Aparecerá una vista previa de la aplicación.
6. Para configurar el despliegue controlado (Fase Piloto), contacte a su administrador de Microsoft 365 o siga estos pasos si tiene permisos administrativos:
a. Abra el Centro de administración de Microsoft Teams (https://admin.teams.microsoft.com)

b. Navegue a "Aplicaciones de Teams" > "Administrar aplicaciones"

c. Busque su aplicación por nombre: Asistente Bancario Virtual [Nombre del Equipo]

d. Haga clic en la aplicación y seleccione "Permisos" (Permissions)

e. Configure una Política de permisos de aplicación para el grupo piloto:

   Nombre de la política: Piloto_Asistente_Bancario
   Aplicaciones personalizadas: Permitir aplicaciones específicas
   Aplicaciones permitidas: [Su aplicación]
   Usuarios asignados: [Grupo piloto de 3-5 usuarios]

Documente los usuarios del grupo piloto en su plantilla:
   Grupo Piloto - Fase 1:
   - Usuario 1: [nombre] - [rol] - [correo]
   - Usuario 2: [nombre] - [rol] - [correo]
   - Usuario 3: [nombre] - [rol] - [correo]

7. Notifique a los usuarios del grupo piloto que el agente está disponible y proporcione instrucciones de acceso:
Abrir Microsoft Teams
Ir a "Aplicaciones"
Buscar "Asistente Bancario Virtual [Nombre del Equipo]"
Hacer clic en "Agregar" para instalar
Iniciar una conversación

Salida Esperada:

El agente está desplegado para un grupo piloto reducido con permisos configurados apropiadamente.

Verificación:

- La aplicación aparece en el Centro de administración de Teams
- La política de permisos está configurada para el grupo piloto
- Los usuarios piloto pueden encontrar e instalar la aplicación
- Los usuarios fuera del grupo piloto NO pueden acceder al agente
---

## Paso 4: Configuración de Analytics y Monitoreo
Objetivo: Establecer métricas de monitoreo para rastrear el uso y rendimiento del agente en producción.

## Instrucciones:

1. Regrese a Microsoft Copilot Studio y abra su agente bancario.
2. Haga clic en "Analytics" en el menú lateral izquierdo.
3. Familiarícese con las métricas disponibles:
- Resumen: Sesiones totales, tasa de resolución, tasa de escalación
- Compromiso del cliente: Sesiones por día, usuarios activos
- Rendimiento de temas: Temas más utilizados, temas con mayor abandono
- Satisfacción: Puntuaciones de satisfacción del cliente (si está configurado)
4. Configure alertas de monitoreo (si está disponible en su versión):

a. Vaya a "Configuración" > "Notificaciones" (Settings > Notifications)

b. Configure las siguientes alertas:

   Alerta 1: Tasa de escalación > 30%
   Alerta 2: Tasa de resolución < 60%
   Alerta 3: Errores del sistema > 5 por día

5. Cree un dashboard personalizado de métricas clave para el grupo piloto:

a. Abra Power BI (si tiene acceso) o prepare una hoja de cálculo para seguimiento manual

b. Defina las siguientes métricas a rastrear diariamente durante la fase piloto:

   Métricas Diarias - Fase Piloto:
   - Número de conversaciones iniciadas
   - Número de usuarios únicos
   - Tasa de resolución (%)
   - Tasa de escalación (%)
   - Tiempo promedio de conversación
   - Temas más consultados (top 5)
   - Errores o problemas reportados

6. En Copilot Studio, vaya a "Analytics" > "Sesiones" y configure el período de retención de datos:
- Asegúrese de que las conversaciones se guarden por al menos 30 días
- Verifique que el análisis de transcripciones esté habilitado
7. Documente el plan de monitoreo en su plantilla:

   Plan de Monitoreo - Fase Piloto (Duración: 1 semana)

   Revisiones diarias:
   - Responsable: [Nombre del miembro del equipo]
   - Hora de revisión: [Hora específica]
   - Métricas a revisar: [Lista de métricas]

   Revisión semanal:
   - Fecha: [Fecha de revisión]
   - Participantes: [Todo el equipo]
   - Objetivo: Decidir expansión a producción

8. Configure un canal de Microsoft Teams para reportes de monitoreo:

a. Cree un canal en su equipo llamado "Monitoreo-Agente-IA"

b. Publique el primer reporte de baseline (línea base):

   REPORTE INICIAL - FASE PILOTO
   Fecha: [Fecha actual]
   Estado: Piloto iniciado
   Usuarios piloto: [Número]
   Métricas baseline: Se establecerán después de primeras 24 horas

Salida Esperada:

Un sistema de monitoreo configurado con métricas claras, alertas establecidas, y un plan de seguimiento documentado.

Verificación:

- El dashboard de Analytics en Copilot Studio muestra datos correctamente
- Las métricas clave están identificadas y documentadas
- El plan de monitoreo está completo con responsables asignados
- El canal de Teams para reportes está creado y operativo
---

## Paso 5: Documentación de Usuario y Procedimientos de Soporte
Objetivo: Crear documentación completa para usuarios finales y procedimientos de mantenimiento post-publicación.

## Instrucciones:

Cree un documento de "Guía de Usuario" utilizando Microsoft Word o SharePoint:
Estructura del documento:

   GUÍA DE USUARIO - ASISTENTE BANCARIO VIRTUAL

   1. Introducción
      - ¿Qué es el Asistente Bancario Virtual?
      - ¿Qué puede hacer por mí?

   2. Cómo Acceder al Asistente
      - Paso 1: Abrir Microsoft Teams
      - Paso 2: Buscar la aplicación
      - Paso 3: Iniciar conversación
      [Incluir capturas de pantalla]

   3. Funcionalidades Principales
      - Consulta de saldo
      - Información sobre productos bancarios
      - Solicitud de soporte
      [Incluir ejemplos de preguntas]

   4. Preguntas Frecuentes (FAQ)
      - ¿Qué hago si el asistente no entiende mi pregunta?
      - ¿Cómo escalo a un agente humano?
      - ¿Es seguro compartir información con el asistente?

   5. Contacto y Soporte
      - Canal de soporte: [Información de contacto]
      - Horario de atención

Cree un documento de "Procedimientos de Mantenimiento" para el equipo técnico:
Contenido del documento:

   PROCEDIMIENTOS DE MANTENIMIENTO POST-PUBLICACIÓN

   1. Monitoreo Diario
      - Revisar Analytics en Copilot Studio
      - Verificar alertas de sistema
      - Leer transcripciones de conversaciones problemáticas

   2. Actualizaciones de Contenido
      - Frecuencia: Semanal o según necesidad
      - Proceso:
        a. Identificar temas que requieren mejora
        b. Actualizar respuestas en Copilot Studio
        c. Probar cambios en ambiente de prueba
        d. Publicar actualización
        e. Notificar a usuarios si es cambio significativo

   3. Gestión de Feedback
      - Recopilar feedback de usuarios piloto
      - Categorizar feedback (bugs, mejoras, nuevas funcionalidades)
      - Priorizar items para implementación
      - Actualizar backlog de mejoras

   4. Procedimiento de Escalación
      - Nivel 1: Problemas técnicos menores → [Responsable]
      - Nivel 2: Problemas de funcionalidad → [Responsable]
      - Nivel 3: Problemas de seguridad o datos → [Responsable + Admin]

   5. Actualizaciones de Seguridad
      - Revisar permisos mensualmente
      - Auditar accesos trimestralmente
      - Actualizar políticas de privacidad según regulaciones

   6. Plan de Backup y Recuperación
      - Exportar configuración del agente: Mensual
      - Backup de bases de conocimiento: Semanal
      - Procedimiento de restauración: [Documentar pasos]

Cree un formulario de "Reporte de Feedback de Usuario" en Microsoft Forms:

a. Abra Microsoft Forms (https://forms.office.com)

b. Cree un nuevo formulario con el título: "Feedback - Asistente Bancario Virtual"

c. Agregue las siguientes preguntas:

   1. ¿Con qué frecuencia ha utilizado el Asistente Bancario Virtual?
      (Opción múltiple: Diariamente, Semanalmente, Ocasionalmente, Primera vez)

   2. ¿El asistente respondió satisfactoriamente su consulta?
      (Opción múltiple: Sí, completamente / Parcialmente / No)

   3. ¿Qué tan fácil fue usar el asistente?
      (Escala: 1-5, donde 5 es muy fácil)

   4. ¿Qué funcionalidad le gustaría que el asistente tuviera?
      (Texto largo)

   5. Describa cualquier problema técnico que haya experimentado
      (Texto largo, opcional)

   6. Comentarios adicionales
      (Texto largo, opcional)

d. Configure las opciones del formulario:

- Permitir una respuesta por persona
- Registrar nombre del respondiente
- Enviar confirmación por correo

e. Copie el enlace del formulario

Publique toda la documentación en un sitio de SharePoint:

a. Cree una biblioteca de documentos llamada "Documentación Asistente IA"

b. Organice los documentos en carpetas:

   📁 Documentación Asistente IA/
   ├── 📁 Para Usuarios/
   │   ├── Guía de Usuario.docx
   │   ├── FAQ.docx
   │   └── Video Tutorial (si aplica)
   ├── 📁 Para Equipo Técnico/
   │   ├── Procedimientos de Mantenimiento.docx
   │   ├── Plan de Monitoreo.xlsx
   │   └── Registro de Cambios.xlsx
   └── 📁 Feedback/
       └── Enlace a Formulario de Feedback
c. Configure permisos apropiados:

- Usuarios finales: Solo lectura en carpeta "Para Usuarios"
- Equipo técnico: Edición en todas las carpetas

Envíe un correo de bienvenida a los usuarios del grupo piloto:

Plantilla de correo:

   Asunto: Bienvenido al Asistente Bancario Virtual - Grupo Piloto

   Estimado/a [Nombre],

   Es un placer invitarte a formar parte del grupo piloto de nuestro nuevo
   Asistente Bancario Virtual, desarrollado con Microsoft Copilot Studio.

   ¿Qué es el Asistente Bancario Virtual?
   Es un agente de IA disponible en Microsoft Teams que puede ayudarte con:
   - Consultas sobre saldos y transacciones
   - Información sobre productos bancarios
   - Soporte general y preguntas frecuentes

   Cómo empezar:
   1. Abre Microsoft Teams
   2. Ve a "Aplicaciones"
   3. Busca "Asistente Bancario Virtual [Nombre del Equipo]"
   4. Haz clic en "Agregar"
   5. ¡Comienza a chatear!

   Documentación: [Enlace a SharePoint]

   Tu opinión es valiosa:
   Como miembro del grupo piloto, tu feedback es esencial para mejorar
   el asistente. Por favor completa esta breve encuesta después de usar
   el asistente: [Enlace a Microsoft Forms]

   Soporte:
   Si experimentas algún problema, contacta a: [Información de contacto]

   Duración del piloto: [Fecha inicio] - [Fecha fin]

   ¡Gracias por tu participación!

   Equipo de Desarrollo
   [Nombre del Equipo]

Documente el plan de expansión a producción:

   PLAN DE EXPANSIÓN A PRODUCCIÓN

   Criterios de éxito para pasar de Piloto a Producción:
   ✓ Tasa de resolución > 70%
   ✓ Tasa de escalación < 25%
   ✓ Satisfacción de usuarios piloto > 4/5
   ✓ Cero problemas críticos de seguridad
   ✓ Menos de 3 errores técnicos por día

   Fases de expansión:

   Fase 1 - Piloto (Semana 1):
   - Usuarios: 3-5 usuarios seleccionados
   - Monitoreo: Diario
   - Ajustes: Inmediatos según feedback

   Fase 2 - Piloto Extendido (Semana 2):
   - Usuarios: 15-20 usuarios (expandir grupo)
   - Monitoreo: Diario
   - Ajustes: Según prioridad

   Fase 3 - Producción Limitada (Semana 3):
   - Usuarios: Departamento completo (50-100 usuarios)
   - Monitoreo: Cada 2 días
   - Ajustes: Semanal

   Fase 4 - Producción Completa (Semana 4+):
   - Usuarios: Toda la organización
   - Monitoreo: Semanal
   - Ajustes: Según roadmap planificado

   Responsable de aprobación de cada fase: [Nombre y cargo]

Salida Esperada:

Documentación completa para usuarios y equipo técnico, formulario de feedback configurado, y plan de comunicación implementado.

Verificación:

- La guía de usuario está completa con capturas de pantalla
- Los procedimientos de mantenimiento están documentados
- El formulario de feedback está publicado y funcional
- El sitio de SharePoint está organizado y accesible
- El correo de bienvenida fue enviado a usuarios piloto
- El plan de expansión está documentado con criterios claros
---

## Paso 6: Presentación del Agente y Demostración en Vivo
Objetivo: Presentar el agente funcionando en Microsoft Teams al resto de la clase, demostrando las capacidades implementadas.

## Instrucciones:

Prepare una presentación de 5 minutos que incluya:
Estructura de la presentación (sugerencia):

   Diapositiva 1: Portada
   - Nombre del agente
   - Nombre del equipo
   - Logotipo/Icono del agente

   Diapositiva 2: Problema que resuelve
   - Desafío bancario identificado
   - Usuarios objetivo
   - Valor de negocio

   Diapositiva 3: Funcionalidades principales
   - Lista de capacidades implementadas
   - Integraciones (Power Automate, AI Builder, SharePoint)
   - Características de seguridad

   Diapositiva 4: Arquitectura y tecnologías
   - Diagrama de componentes
   - Tecnologías utilizadas
   - Flujos de datos

   Diapositiva 5: Métricas y resultados
   - Métricas de prueba
   - Feedback recibido
   - Lecciones aprendidas

Prepare el ambiente para la demostración en vivo:

a. Abra Microsoft Teams en modo presentación

b. Tenga el agente ya instalado y listo para usar

c. Prepare 3-4 escenarios de demostración que muestren (sugerencia):

   Escenario 1: Consulta simple exitosa
   Usuario: "¿Cuál es mi saldo actual?"
   [Mostrar respuesta del agente]

   Escenario 2: Consulta compleja con múltiples pasos
   Usuario: "Quiero información sobre préstamos hipotecarios"
   [Mostrar cómo el agente guía al usuario]

   Escenario 3: Uso de base de conocimiento (SharePoint)
   Usuario: "¿Cuáles son las tasas de interés vigentes?"
   [Mostrar cómo el agente consulta documentos]

   Escenario 4: Escalación a agente humano
   Usuario: "Necesito reportar un fraude"
   [Mostrar proceso de escalación]

d. Tenga capturas de pantalla de backup en caso de problemas técnicos

Durante la presentación, asigne roles a los miembros del equipo:
   Rol 1 - Presentador principal: Introduce el proyecto y navega las diapositivas
   Rol 2 - Demostrador: Realiza la demostración en vivo en Teams
   Rol 3 - Experto técnico: Explica arquitectura y responde preguntas técnicas
   Rol 4 - Analista de resultados: Presenta métricas y lecciones aprendidas

Realice la demostración en vivo:

a. Comparta su pantalla mostrando Microsoft Teams

b. Abra el chat con el Asistente Bancario Virtual

c. Ejecute cada escenario preparado, narrando lo que está sucediendo:
   Narración ejemplo:
   "Ahora voy a hacer una consulta sobre saldos. Como pueden ver,
   el agente responde inmediatamente con información personalizada.
   Noten que la respuesta incluye opciones de seguimiento para
   mejorar la experiencia del usuario..."
d. Muestre el panel de Analytics en Copilot Studio con métricas reales

Abra una sesión de preguntas y respuestas (2-3 minutos):
- Esté preparado para responder preguntas sobre decisiones de diseño
- Comparta desafíos enfrentados y cómo los resolvieron
- Discuta planes futuros de mejora

Después de todas las presentaciones, participe en la sesión de retroalimentación grupal:
a. Tome notas de ideas interesantes de otros equipos

b. Identifique al menos 2 funcionalidades de otros equipos que podría incorporar

c. Proporcione feedback constructivo a otros equipos

Salida Esperada:

Una presentación profesional de 5 minutos con demostración en vivo exitosa del agente funcionando en Microsoft Teams.

Verificación:

- La presentación cubre todos los elementos requeridos
- La demostración en vivo muestra al menos 3 escenarios diferentes
- Todos los miembros del equipo participaron activamente
- Se respondieron preguntas de la audiencia satisfactoriamente
- Se documentó feedback recibido de otros equipos
---

## Validación y Pruebas
### Criterios de Éxito

[ ] El agente está publicado exitosamente en Microsoft Teams
[ ] Los controles de acceso están configurados correctamente (grupo piloto puede acceder, otros usuarios no)
[ ] El sistema de monitoreo está capturando métricas de uso
[ ] La documentación de usuario está completa y publicada en SharePoint
[ ] El formulario de feedback está funcional y accesible
[ ] Los procedimientos de mantenimiento están documentados
[ ] El plan de expansión a producción está definido con criterios claros
[ ] La presentación y demostración en vivo se completaron exitosamente

Procedimiento de Prueba

Prueba de acceso de usuario piloto:
Solicite a uno de los usuarios piloto que realice los siguientes pasos:

   1. Abrir Microsoft Teams
   2. Ir a "Aplicaciones"
   3. Buscar el agente por nombre
   4. Instalar la aplicación
   5. Iniciar una conversación de prueba
Resultado esperado: El usuario puede encontrar, instalar y usar el agente sin problemas.

Prueba de restricción de acceso:
Solicite a un usuario que NO esté en el grupo piloto que intente acceder:

   1. Abrir Microsoft Teams
   2. Buscar el agente por nombre
Resultado esperado: El agente no aparece en los resultados de búsqueda o muestra mensaje de acceso restringido.

Prueba de captura de métricas:
   1. Realice 3-5 conversaciones de prueba con el agente en Teams
   2. Espere 5-10 minutos para procesamiento de datos
   3. Abra Copilot Studio > Analytics
   4. Verifique que las conversaciones aparezcan en el dashboard
Resultado esperado: Las métricas reflejan las conversaciones realizadas.

Prueba de formulario de feedback:
   1. Abra el enlace del formulario de feedback
   2. Complete todas las preguntas
   3. Envíe el formulario
   4. Verifique que la respuesta se registre en Microsoft Forms
Resultado esperado: El formulario se envía correctamente y la respuesta es visible para el equipo.

Prueba de acceso a documentación:
   1. Abra el sitio de SharePoint con la documentación
   2. Verifique que todos los documentos sean accesibles
   3. Descargue la Guía de Usuario
   4. Confirme que el contenido es legible y completo
Resultado esperado: Toda la documentación es accesible y está completa.


---
##  Recursos

- https://learn.microsoft.com/microsoft-copilot-studio/
- https://learn.microsoft.com/power-platform/
- https://learn.microsoft.com/ai-builder/

---

¡Felicitaciones por completar el laboratorio!
