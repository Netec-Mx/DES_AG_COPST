
# Ajusta y optimiza el comportamiento del agente

# Agrega razonamiento y uso de herramientas

---

## Descripción General

En esta actividad grupal práctica, los equipos integrarán su agente de Copilot Studio con servicios externos mediante Power Automate, creando una solución bancaria inteligente y automatizada. Los participantes desarrollarán flujos que ejecuten acciones reales como envío de correos de confirmación, registro de solicitudes en SharePoint/Dataverse, consulta de APIs simuladas de sistemas bancarios, y generación de documentos. Esta actividad consolida el aprendizaje del módulo al aplicar conceptos de conectores, autenticación, manejo de errores y paso de parámetros en un escenario realista del sector bancario.


---

## Objetivos de Aprendizaje

- Crear flujos de Power Automate para extender las capacidades del agente de Copilot Studio
-  Configurar acciones personalizadas en Copilot Studio que invoquen flujos automatizados
- Implementar conectores preconfigurados para integrar servicios bancarios (Office 365, SharePoint, Dataverse, HTTP)
- Gestionar el paso de parámetros entre el agente y los flujos de automatización
- Aplicar manejo de errores y respuestas en integraciones con sistemas externos

---

## Prerrequisitos

- Completar Módulo 4.0 con agente personalizado funcional en Copilot Studio
- Comprensión básica de conceptos de APIs REST y conectores
- Familiaridad con variables y tipos de datos en Copilot Studio
- Conocimiento básico de JSON para estructurar datos

---

## Acceso Requerido

- Cuenta de Microsoft 365 con suscripción activa (Business, Enterprise o Education)
- Acceso a Microsoft Copilot Studio
- Acceso a Microsoft Teams para colaboración
- Acceso a Microsoft Word o OneNote para documentación
- Acceso a Microsoft PowerPoint para presentación

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

Preparación del Entorno de Equipo:

Formar equipos de 3-4 personas
Designar roles:
Líder de integración: Coordina las actividades
Especialista en Power Automate: Crea y prueba flujos
Especialista en Copilot Studio: Configura acciones en el agente
Documentador: Registra configuraciones y decisiones
Verificar acceso a recursos compartidos del equipo
Verificación de Acceso a Servicios:

Cada miembro del equipo debe verificar acceso ejecutando estas comprobaciones:

Abrir navegador y acceder a: https://make.powerautomate.com
Verificar que puede ver el entorno de trabajo
Acceder a: https://copilotstudio.microsoft.com
Confirmar que el agente del módulo anterior está disponible
Acceder a SharePoint del equipo: https://[tenant].sharepoint.com/sites/[sitio-equipo]
Nota: Si algún miembro no tiene acceso, contactar al instructor antes de continuar.



---

##  Desarrollo del Laboratorio

## Paso 1: Preparar Repositorio de Datos en SharePoint
Objetivo: Crear una lista de SharePoint para almacenar solicitudes de crédito procesadas por el agente.

## Instrucciones:

- Acceder al sitio de SharePoint del equipo:
Navegar a https://[tenant].sharepoint.com/sites/[sitio-equipo]
Reemplazar [tenant] con el nombre de su organización
Reemplazar [sitio-equipo] con el nombre del sitio asignado
- Crear una nueva lista personalizada:
Hacer clic en ⚙️ Configuración > Contenido del sitio
Hacer clic en + Nuevo > Lista
Seleccionar Lista en blanco
Nombre: Solicitudes de Crédito
Descripción: Registro de solicitudes procesadas por el agente bancario
Hacer clic en Crear
- Agregar columnas personalizadas a la lista:
- Configurar cada columna:
Hacer clic en + Agregar columna
Seleccionar el tipo correspondiente
Para columnas de tipo "Elección", agregar las opciones listadas arriba
Marcar como requerido según la tabla
Hacer clic en Guardar
- Copiar la URL de la lista para uso posterior:
Hacer clic derecho en Solicitudes de Crédito en el menú lateral
Seleccionar Copiar vínculo
Guardar en un documento del equipo

| Nombre de Columna   | Tipo           | Requerido | Descripción                                               |
|--------------------|----------------|-----------|-----------------------------------------------------------|
| NombreCliente      | Texto          | Sí        | Nombre completo del cliente                               |
| CorreoCliente      | Texto          | Sí        | Email del cliente                                         |
| MontoSolicitado    | Número         | Sí        | Monto en moneda local                                     |
| TipoCredito        | Elección       | Sí        | Personal, Hipotecario, Automotriz, Empresarial            |
| EstadoSolicitud    | Elección       | Sí        | Pendiente, En Revisión, Aprobado, Rechazado               |
| FechaSolicitud     | Fecha y hora   | Sí        | Fecha de creación                                         |
| IDConversacion     | Texto          | No        | ID de la conversación en Copilot Studio                   |


Salida Esperada:

Una lista de SharePoint con las siguientes columnas visibles:

Title (por defecto)
NombreCliente
CorreoCliente
MontoSolicitado
TipoCredito
EstadoSolicitud
FechaSolicitud
IDConversacion

---

## Paso 2: Crear Flujo de Power Automate para Registro de Solicitudes
Objetivo: Desarrollar un flujo que reciba datos del agente y cree un registro en SharePoint.

## Instrucciones:

- Acceder a Power Automate:
Navegar a https://make.powerautomate.com
Verificar que está en el entorno correcto (esquina superior derecha)
- Crear un nuevo flujo instantáneo:
Hacer clic en + Crear en el menú lateral
Seleccionar Flujo de nube instantáneo
Nombre del flujo: Registrar Solicitud de Crédito
Seleccionar desencadenador: Power Virtual Agents
Hacer clic en Crear
- Configurar el desencadenador de Power Virtual Agents:
El desencadenador ya está agregado automáticamente
Hacer clic en + Agregar una entrada
Agregar las siguientes entradas (una por una):
- Agregar acción para crear elemento en SharePoint:
Hacer clic en + Nuevo paso
Buscar: SharePoint
Seleccionar acción: Crear elemento
Configurar la conexión si es necesario (autenticar con cuenta M365)
- Configurar la acción de SharePoint:
Dirección del sitio: Seleccionar el sitio de SharePoint del equipo
Nombre de lista: Seleccionar Solicitudes de Crédito
Title: Escribir Solicitud - y agregar contenido dinámico NombreCliente
NombreCliente: Contenido dinámico NombreCliente
CorreoCliente: Contenido dinámico CorreoCliente
MontoSolicitado: Contenido dinámico MontoSolicitado
TipoCredito: Contenido dinámico TipoCredito
EstadoSolicitud: Escribir manualmente Pendiente
FechaSolicitud: Hacer clic en Expresión y escribir utcNow()
IDConversacion: Contenido dinámico IDConversacion
- Agregar acción para responder a Power Virtual Agents:
Hacer clic en + Nuevo paso
Buscar: Power Virtual Agents
Seleccionar acción: Devolver valores a Power Virtual Agents
Hacer clic en + Agregar una salida
Agregar salida de tipo Texto:
Nombre: Resultado
Valor: Solicitud registrada exitosamente con ID: (agregar contenido dinámico ID de la acción anterior de SharePoint)
Agregar otra salida de tipo Número:
Nombre: IDSolicitud
Valor: Contenido dinámico ID de SharePoint
Guardar y probar el flujo:
Hacer clic en Guardar (esquina superior derecha)
Hacer clic en Probar
Seleccionar Manualmente
Hacer clic en Probar
Ingresar valores de prueba:
NombreCliente: Juan Pérez
CorreoCliente: juan.perez@ejemplo.com
MontoSolicitado: 50000
TipoCredito: Personal
IDConversacion: test-123
Hacer clic en Ejecutar flujo

| Nombre           | Tipo    | Descripción          |
|------------------|---------|----------------------|
| NombreCliente    | Texto   | Nombre del cliente   |
| CorreoCliente    | Texto   | Email del cliente    |
| MontoSolicitado  | Número  | Monto solicitado     |
| TipoCredito      | Texto   | Tipo de crédito      |
| IDConversacion   | Texto   | ID de conversación   |


Salida Esperada:

Flujo ejecutado correctamente
✓ Power Virtual Agents (desencadenador)
✓ Crear elemento (SharePoint)
✓ Devolver valores a Power Virtual Agents

Salidas:
- Resultado: "Solicitud registrada exitosamente con ID: 1"
- IDSolicitud: 1

---

## Paso 3: Configurar Acción en Copilot Studio
Objetivo: Integrar el flujo de Power Automate como una acción invocable desde el agente.

## Instrucciones:

- Acceder a Copilot Studio:
Navegar a https://copilotstudio.microsoft.com
Seleccionar el agente creado en el módulo anterior
- Navegar a la sección de Acciones:
En el panel lateral izquierdo, hacer clic en Acciones
Hacer clic en + Agregar una acción
- Seleccionar el flujo de Power Automate:
Seleccionar la pestaña Power Automate
Buscar el flujo: Registrar Solicitud de Crédito
Hacer clic en el flujo para seleccionarlo
Hacer clic en Siguiente
- Revisar la configuración de la acción:
Nombre de la acción: RegistrarSolicitudCredito
Verificar que las entradas y salidas se detectaron automáticamente:
Entradas: NombreCliente, CorreoCliente, MontoSolicitado, TipoCredito, IDConversacion
Salidas: Resultado, IDSolicitud
Hacer clic en Finalizar
- Crear un nuevo tema para solicitud de crédito:
Hacer clic en Temas en el panel lateral
Hacer clic en + Agregar un tema > Desde cero
Nombre del tema: Solicitar Crédito Personal
Descripción: Procesa solicitudes de crédito personal de clientes
- Configurar frases desencadenadoras:
En la sección Frases desencadenadoras, agregar:
Quiero solicitar un crédito
Necesito un préstamo personal
Solicitar crédito
Aplicar para un crédito
Préstamo personal
- Diseñar el flujo conversacional:
Hacer clic en + Agregar nodo debajo de las frases desencadenadoras
Seleccionar Enviar un mensaje
Mensaje: Perfecto, te ayudaré con tu solicitud de crédito personal. Necesito algunos datos.
- Agregar pregunta para nombre del cliente:
Hacer clic en + Agregar nodo
Seleccionar Hacer una pregunta
Pregunta: ¿Cuál es tu nombre completo?
Identificar: Seleccionar Persona
Guardar respuesta como: Crear nueva variable nombreCliente
- Agregar pregunta para correo electrónico:
Hacer clic en + Agregar nodo
Seleccionar Hacer una pregunta
Pregunta: ¿Cuál es tu correo electrónico?
Identificar: Seleccionar Email
Guardar respuesta como: Crear nueva variable correoCliente
- Agregar pregunta para monto:
Hacer clic en + Agregar nodo
Seleccionar Hacer una pregunta
Pregunta: ¿Qué monto necesitas? (Ingresa solo el número)
Identificar: Seleccionar Número
Guardar respuesta como: Crear nueva variable montoSolicitado
- Invocar la acción de Power Automate:
Hacer clic en + Agregar nodo
Seleccionar Llamar a una acción
Seleccionar la acción: RegistrarSolicitudCredito
Mapear los parámetros de entrada:
NombreCliente: Variable nombreCliente
CorreoCliente: Variable correoCliente
MontoSolicitado: Variable montoSolicitado
TipoCredito: Escribir directamente Personal
IDConversacion: Seleccionar variable del sistema System.Conversation.Id
- Configurar respuesta con resultado:
Hacer clic en + Agregar nodo debajo de la acción
Seleccionar Enviar un mensaje
Mensaje: ¡Excelente! Tu solicitud ha sido registrada. {Topic.RegistrarSolicitudCredito.Resultado}
Agregar otro mensaje:
Tu número de solicitud es: {Topic.RegistrarSolicitudCredito.IDSolicitud}. Recibirás un correo de confirmación pronto.
Guardar el tema:
Hacer clic en Guardar en la esquina superior derecha

Salida Esperada:
Un tema conversacional completo con la siguiente estructura:

Frases desencadenadoras configuradas
Mensaje de bienvenida
Tres preguntas para recopilar datos
Invocación de acción de Power Automate
Mensajes de confirmación con datos dinámicos

---

## Paso 4: Crear Flujo de Envío de Correo de Confirmación
Objetivo: Desarrollar un flujo que envíe un correo electrónico de confirmación al cliente después de registrar la solicitud.

## Instrucciones:

- Regresar a Power Automate:
Navegar a https://make.powerautomate.com
- Crear un nuevo flujo instantáneo:
Hacer clic en + Crear
Seleccionar Flujo de nube instantáneo
Nombre: Enviar Confirmación de Solicitud
Desencadenador: Power Virtual Agents
Hacer clic en Crear
- Configurar entradas del desencadenador:
Agregar las siguientes entradas:
- Agregar acción para enviar correo:
Hacer clic en + Nuevo paso
Buscar: Office 365 Outlook
Seleccionar acción: Enviar un correo electrónico (V2)
Autenticar si es necesario
- Configurar el correo electrónico:
Para: Contenido dinámico CorreoCliente
Asunto: Confirmación de Solicitud de Crédito - # (agregar IDSolicitud)
Cuerpo: Hacer clic en el icono para cambiar a HTML y pegar:
   <html>
   <body style="font-family: Arial, sans-serif;">
       <h2 style="color: #0078D4;">Confirmación de Solicitud de Crédito</h2>
       <p>Estimado/a <strong>{NombreCliente}</strong>,</p>
       <p>Hemos recibido tu solicitud de crédito con los siguientes detalles:</p>
       <table style="border-collapse: collapse; width: 100%; max-width: 500px;">
           <tr>
               <td style="padding: 8px; border: 1px solid #ddd;"><strong>Número de Solicitud:</strong></td>
               <td style="padding: 8px; border: 1px solid #ddd;">{IDSolicitud}</td>
           </tr>
           <tr>
               <td style="padding: 8px; border: 1px solid #ddd;"><strong>Tipo de Crédito:</strong></td>
               <td style="padding: 8px; border: 1px solid #ddd;">{TipoCredito}</td>
           </tr>
           <tr>
               <td style="padding: 8px; border: 1px solid #ddd;"><strong>Monto Solicitado:</strong></td>
               <td style="padding: 8px; border: 1px solid #ddd;">$ {MontoSolicitado}</td>
           </tr>
       </table>
       <p>Nuestro equipo revisará tu solicitud en las próximas 24-48 horas. Te contactaremos pronto.</p>
       <p style="color: #666; font-size: 12px;">Este es un correo automático, por favor no responder.</p>
   </body>
   </html>
Reemplazar los placeholders {NombreCliente}, {IDSolicitud}, {TipoCredito}, {MontoSolicitado} con contenido dinámico correspondiente
Importancia: Seleccionar Normal
- Agregar manejo de errores con ámbito:
Antes de la acción de correo, hacer clic en + Agregar una acción
Buscar: Ámbito
Seleccionar Ámbito
Arrastrar la acción "Enviar un correo electrónico" dentro del ámbito
- Configurar acción en caso de error:
Hacer clic en + Agregar una acción paralela fuera del ámbito
Buscar: Ámbito
Seleccionar Ámbito nuevamente
Nombrar este ámbito: Manejo de Errores
Hacer clic en los ... del ámbito "Manejo de Errores"
Seleccionar Configurar ejecución posterior
Cambiar a ha fallado
En el dropdown, seleccionar el nombre del primer ámbito
Hacer clic en Listo
- Agregar registro de error:
Dentro del ámbito "Manejo de Errores", agregar acción
Buscar: Redactar
Seleccionar Redactar
En Entradas, escribir: Error al enviar correo a: (agregar contenido dinámico CorreoCliente)
- Devolver valores a Power Virtual Agents:
Hacer clic en + Nuevo paso (fuera de ambos ámbitos)
Buscar: Power Virtual Agents
Seleccionar: Devolver valores a Power Virtual Agents
Agregar salida de tipo Texto:
Nombre: EstadoEnvio
Valor: Hacer clic en Expresión y escribir:
     if(equals(actions('Ámbito')?['status'], 'Succeeded'), 'Correo enviado exitosamente', 'Error al enviar correo')
Reemplazar 'Ámbito' con el nombre exacto del primer ámbito si es diferente
- Guardar el flujo:
Hacer clic en Guardar
- Probar el flujo manualmente:
Hacer clic en Probar > Manualmente
Ingresar valores de prueba (usar su propio correo para recibir la confirmación)
Hacer clic en Ejecutar flujo

| Nombre          | Tipo    |
|-----------------|---------|
| NombreCliente   | Texto   |
| CorreoCliente   | Texto   |
| MontoSolicitado | Número  |
| IDSolicitud     | Número  |
| TipoCredito     | Texto   |



Salida Esperada:

Flujo ejecutado correctamente
✓ Power Virtual Agents
✓ Ámbito (Succeeded)
  ✓ Enviar un correo electrónico (V2)
⊘ Ámbito - Manejo de Errores (Skipped)
✓ Devolver valores a Power Virtual Agents

Salidas:
- EstadoEnvio: "Correo enviado exitosamente"
Debe recibir un correo electrónico con formato HTML conteniendo los detalles de la solicitud.

---

## Paso 5: Integrar Envío de Correo en el Tema de Copilot Studio
Objetivo: Agregar la acción de envío de correo al flujo conversacional del agente.

## Instrucciones:

- Regresar a Copilot Studio:
Navegar a https://copilotstudio.microsoft.com
Abrir el agente y el tema "Solicitar Crédito Personal"
- Agregar la nueva acción al catálogo:
Hacer clic en Acciones en el panel lateral
Hacer clic en + Agregar una acción
Seleccionar pestaña Power Automate
Buscar y seleccionar: Enviar Confirmación de Solicitud
Hacer clic en Siguiente y luego Finalizar
- Modificar el tema para incluir envío de correo:
Abrir el tema Solicitar Crédito Personal
Ubicar el nodo después de la acción RegistrarSolicitudCredito
Antes de los mensajes de confirmación, hacer clic en + Agregar nodo
Seleccionar Llamar a una acción
Seleccionar: EnviarConfirmacionDeSolicitud
- Mapear parámetros de entrada:
NombreCliente: Variable nombreCliente
CorreoCliente: Variable correoCliente
MontoSolicitado: Variable montoSolicitado
IDSolicitud: Topic.RegistrarSolicitudCredito.IDSolicitud
TipoCredito: Escribir Personal
- Actualizar mensaje de confirmación:
Modificar el mensaje existente para incluir estado de envío:
¡Excelente! Tu solicitud ha sido registrada. {Topic.RegistrarSolicitudCredito.Resultado}
Agregar nuevo mensaje:
Estado del correo: {Topic.EnviarConfirmacionDeSolicitud.EstadoEnvio}
Mantener el mensaje con número de solicitud
- Agregar condición para verificar envío:
Hacer clic en + Agregar nodo después de la acción de envío
Seleccionar Agregar una condición
Configurar condición:
Variable: Topic.EnviarConfirmacionDeSolicitud.EstadoEnvio
Operador: es igual a
Valor: Correo enviado exitosamente
- Configurar ramas de la condición:
Rama "Verdadero" (correo enviado):
Agregar mensaje: Revisa tu correo electrónico para más detalles.
Rama "Falso" (error en envío):
Agregar mensaje: Hubo un problema al enviar el correo de confirmación, pero tu solicitud fue registrada. Puedes consultar el estado con tu número de solicitud.
Guardar el tema:
Hacer clic en Guardar
Salida Esperada:

Flujo conversacional actualizado con:

Primera acción: Registro en SharePoint
Segunda acción: Envío de correo
Condición que verifica éxito del envío
Mensajes personalizados según resultado

---

## Paso 6: Crear Flujo de Consulta a API Simulada
Objetivo: Implementar un flujo que consulte una API REST simulada para validar elegibilidad de crédito.

## Instrucciones:

- Crear API simulada con webhook.site (alternativa gratuita):
Abrir una nueva pestaña y navegar a: https://webhook.site
Copiar la URL única generada (ejemplo: https://webhook.site/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx)
Guardar esta URL para uso posterior
- Crear nuevo flujo en Power Automate:
Navegar a https://make.powerautomate.com
Hacer clic en + Crear > Flujo de nube instantáneo
Nombre: Validar Elegibilidad Crédito
Desencadenador: Power Virtual Agents
Hacer clic en Crear
- Configurar entradas del desencadenador:
Agregar entradas:
- Agregar acción HTTP para consultar API:
Hacer clic en + Nuevo paso
Buscar: HTTP
Seleccionar acción: HTTP
Configurar la solicitud:
Método: POST
URI: Pegar la URL de webhook.site copiada anteriormente
Encabezados: Hacer clic en Agregar nuevo elemento
Clave: Content-Type
Valor: application/json
Cuerpo: Hacer clic en para cambiar a expresión y escribir:
     {
       "montoSolicitado": @{triggerBody()?['MontoSolicitado']},
       "ingresoMensual": @{triggerBody()?['IngresoMensual']},
       "timestamp": "@{utcNow()}"
     }

- Agregar acción para analizar respuesta JSON:
Hacer clic en + Nuevo paso
Buscar: Análisis del archivo JSON
Seleccionar: Análisis del archivo JSON
Contenido: Contenido dinámico Cuerpo de la acción HTTP
Esquema: Hacer clic en Usar una carga de ejemplo para generar el esquema
Pegar el siguiente JSON de ejemplo:
   {
     "elegible": true,
     "razon": "Ingreso suficiente",
     "relacionDeudaIngreso": 0.35,
     "montoMaximoAprobado": 100000
   }

- Agregar lógica de validación local (simulación):
Hacer clic en + Nuevo paso
Buscar: Redactar
Seleccionar: Redactar
En Entradas, hacer clic en Expresión y escribir:
   div(triggerBody()?['MontoSolicitado'], triggerBody()?['IngresoMensual'])
Esto calcula la relación monto/ingreso

- Agregar condición de elegibilidad:
Hacer clic en + Nuevo paso
Seleccionar: Condición
Configurar:
Salidas de Redactar (del paso anterior)
Operador: es menor o igual que
Valor: 5
- Configurar rama "Verdadero" (elegible):
Agregar acción: Redactar
En Entradas, escribir (usando contenido dinámico):
   {
     "elegible": true,
     "razon": "La relación monto/ingreso es aceptable",
     "relacionDeudaIngreso": [Salidas de Redactar del paso 6],
     "montoMaximoAprobado": [IngresoMensual * 5]
   }
Para calcular montoMaximoAprobado, usar expresión: mul(triggerBody()?['IngresoMensual'], 5)
- Configurar rama "Falso" (no elegible):
Agregar acción: Redactar
En Entradas, escribir:
   {
     "elegible": false,
     "razon": "La relación monto/ingreso excede el límite permitido",
     "relacionDeudaIngreso": [Salidas de Redactar del paso 6],
     "montoMaximoAprobado": [IngresoMensual * 5]
   }

- Unificar resultados y devolver a Power Virtual Agents:
Después de la condición, hacer clic en + Nuevo paso
Buscar: Power Virtual Agents
Seleccionar: Devolver valores a Power Virtual Agents
Agregar salidas:
Elegible (Booleano): Expresión if(equals(outputs('Redactar_2')?['elegible'], true), true, false) (ajustar nombres según corresponda)
Razon (Texto): Usar expresión para obtener el valor según rama ejecutada
MontoMaximo (Número): Usar expresión similar

| Nombre          | Tipo    |
|-----------------|---------|
| MontoSolicitado | Número  |
| IngresoMensual  | Número  |


Nota: Para simplificar, puede usar variables para almacenar los resultados de cada rama antes de devolverlos.

- Alternativa simplificada para devolver valores:
En lugar de expresiones complejas, agregar dentro de cada rama de la condición:
Rama Verdadero: Agregar acción Inicializar variable
Nombre: varElegible
Tipo: Boolean
Valor: true
Agregar otra variable:
Nombre: varRazon
Tipo: String
Valor: La relación monto/ingreso es aceptable
Rama Falso: Agregar acción Establecer variable
Nombre: varElegible
Valor: false
Establecer varRazon con mensaje correspondiente
- Devolver variables a Power Virtual Agents:
Después de la condición, agregar: Devolver valores a Power Virtual Agents

Salidas:
Elegible (Booleano): Variable varElegible
Razon (Texto): Variable varRazon
MontoMaximo (Número): Expresión mul(triggerBody()?['IngresoMensual'], 5)

- Guardar y probar:
Hacer clic en Guardar
Hacer clic en Probar > Manualmente
Ingresar valores:
MontoSolicitado: 30000
IngresoMensual: 10000
Ejecutar y verificar resultado (debería ser elegible)

- Salida Esperada:
Flujo ejecutado correctamente
✓ Power Virtual Agents
✓ HTTP (solicitud enviada)
✓ Análisis del archivo JSON
✓ Redactar (cálculo de relación)
✓ Condición (evaluada como True)
✓ Rama Verdadero ejecutada
✓ Devolver valores a Power Virtual Agents

Salidas:
- Elegible: true
- Razon: "La relación monto/ingreso es aceptable"
- MontoMaximo: 50000

- Verificación:

- El flujo se ejecuta sin errores
- La solicitud HTTP aparece en webhook.site
- El cálculo de relación es correcto (30000/10000 = 3)
- La condición evalúa correctamente (3 <= 5 = true)
- Las salidas contienen los valores esperados
---

## Paso 7: Integrar Validación de Elegibilidad en el Agente
Objetivo: Incorporar la validación de elegibilidad antes de registrar la solicitud de crédito.

## Instrucciones:

- Agregar la acción de validación en Copilot Studio:
Navegar a Acciones > + Agregar una acción
Seleccionar Power Automate
Buscar: Validar Elegibilidad Crédito
Agregar la acción
- Modificar el tema "Solicitar Crédito Personal":
Abrir el tema en edición
Después de la pregunta del monto, agregar nueva pregunta para ingreso
- Agregar pregunta de ingreso mensual:
Hacer clic en + Agregar nodo después de la pregunta del monto
Seleccionar Hacer una pregunta
Pregunta: ¿Cuál es tu ingreso mensual aproximado?
Identificar: Número
Guardar respuesta como: Variable ingresoMensual
- Invocar validación de elegibilidad:
Hacer clic en + Agregar nodo
Seleccionar Llamar a una acción
Seleccionar: ValidarElegibilidadCredito
Mapear entradas:
MontoSolicitado: Variable montoSolicitado
IngresoMensual: Variable ingresoMensual
- Agregar condición basada en elegibilidad:
Hacer clic en + Agregar nodo
Seleccionar Agregar una condición
Variable: Topic.ValidarElegibilidadCredito.Elegible
Operador: es igual a
Valor: true
- Configurar rama "Verdadero" (cliente elegible):
Agregar mensaje: ¡Buenas noticias! Eres elegible para este crédito. {Topic.ValidarElegibilidadCredito.Razon}
Agregar mensaje adicional: Tu monto máximo aprobable es: ${Topic.ValidarElegibilidadCredito.MontoMaximo}
Después, mantener el flujo original:
Acción: RegistrarSolicitudCredito
Acción: EnviarConfirmacionDeSolicitud
Mensajes de confirmación
- Configurar rama "Falso" (cliente no elegible):
Agregar mensaje: Lamentablemente, no cumples con los requisitos para el monto solicitado. {Topic.ValidarElegibilidadCredito.Razon}
Agregar mensaje: El monto máximo que podrías solicitar es: ${Topic.ValidarElegibilidadCredito.MontoMaximo}
Agregar pregunta: ¿Deseas ajustar tu solicitud a este monto? (Sí/No)
Identificar: Booleano
Guardar respuesta como: Variable ajustarMonto
- Agregar condición para ajuste:
Dentro de la rama "Falso", después de la pregunta
Agregar Condición
Variable: ajustarMonto
Operador: es igual a
Valor: true
- Configurar sub-rama "Verdadero" (ajustar monto):
Agregar acción: Establecer valor de variable
Variable: montoSolicitado
Valor: Topic.ValidarElegibilidadCredito.MontoMaximo
Continuar con el flujo de registro (copiar nodos de la rama elegible)
- Configurar sub-rama "Falso" (no ajustar):
Agregar mensaje: Entiendo. Si cambias de opinión o deseas explorar otras opciones, no dudes en contactarnos nuevamente.
Agregar nodo: Finalizar conversación
- Reorganizar el flujo para claridad:
Asegurar que todas las ramas lleven a conclusiones apropiadas
Verificar que no haya caminos sin salida
- Guardar el tema:
Hacer clic en Guardar
Salida Esperada:

Flujo conversacional con bifurcaciones:

[Preguntas iniciales]
    ↓
[Validación de elegibilidad]
    ↓
[Condición: ¿Elegible?]
    ↓                    ↓
[SÍ]                [NO]
    ↓                    ↓
[Registrar]         [Ofrecer ajuste]
    ↓                    ↓
[Enviar correo]     [¿Ajustar?]
    ↓                ↓        ↓
[Confirmación]    [SÍ]      [NO]
                     ↓        ↓
                [Registrar] [Despedida]
- Verificación:

- La validación se ejecuta antes del registro
- Los clientes elegibles continúan con el proceso normal
- Los clientes no elegibles reciben opción de ajuste
- El monto se actualiza correctamente cuando se acepta el ajuste
- Todas las ramas terminan apropiadamente
---

## Paso 8: Implementar Logging y Auditoría
Objetivo: Crear un sistema de registro de todas las transacciones para auditoría y análisis.

## Instrucciones:

- Crear tabla en Dataverse para logs:
Navegar a https://make.powerapps.com
Seleccionar Dataverse > Tablas
Hacer clic en + Nueva tabla > Crear nueva tabla
Configurar:
Nombre para mostrar: Log de Transacciones
Nombre plural: Logs de Transacciones
Descripción: Registro de auditoría de transacciones del agente
Hacer clic en Guardar
- Agregar columnas personalizadas:
Hacer clic en + Nueva columna para cada una:
- Crear flujo de logging en Power Automate:
Navegar a https://make.powerautomate.com
Crear Flujo de nube instantáneo
Nombre: Registrar Log de Transacción
Desencadenador: Power Virtual Agents
- Configurar entradas del flujo:
Agregar entradas:
- Agregar acción para crear registro en Dataverse:
Hacer clic en + Nuevo paso
Buscar: Dataverse
Seleccionar: Agregar una nueva fila
Nombre de tabla: Logs de Transacciones
Mapear campos:
-- Nombre: Contenido dinámico Accion + - + IDConversacion
-- ID Conversación: Contenido dinámico IDConversacion
-- Acción Ejecutada: Contenido dinámico Accion
-- Estado: Contenido dinámico Estado
-- Detalles: Contenido dinámico Detalles
-- Usuario: Contenido dinámico Usuario
-- Timestamp: Expresión utcNow()
- Devolver confirmación:
Agregar acción: Devolver valores a Power Virtual Agents
Salida:
LogCreado (Booleano): true
- Guardar el flujo
- Modificar flujos existentes para incluir logging:
Abrir el flujo Registrar Solicitud de Crédito
Después de crear el elemento en SharePoint, agregar + Nuevo paso
Buscar y agregar: Ejecutar un flujo secundario
Seleccionar: Registrar Log de Transacción
Mapear parámetros:
IDConversacion: Contenido dinámico IDConversacion
Accion: Registro de Solicitud en SharePoint
Estado: Éxito
Detalles: Solicitud ID: + contenido dinámico ID de SharePoint
Usuario: Contenido dinámico CorreoCliente
- Agregar logging en caso de error:
En el ámbito de manejo de errores, agregar llamada al flujo de logging
Configurar con Estado: Error
Detalles: Descripción del error
- Repetir para el flujo de envío de correo:
Agregar logging después de enviar correo exitosamente
Agregar logging en caso de error
- Guardar todos los flujos modificados

| Nombre para mostrar | Tipo de datos                          | Requerido |
|---------------------|----------------------------------------|-----------|
| ID Conversación     | Texto                                  | Sí        |
| Acción Ejecutada    | Texto                                  | Sí        |
| Estado              | Elección (Éxito, Error, Advertencia)   | Sí        |
| Detalles            | Texto de varias líneas                 | No        |
| Usuario             | Texto                                  | No        |
| Timestamp           | Fecha y hora                           | Sí        |

| Nombre        | Tipo  |
|---------------|-------|
| IDConversacion| Texto |
| Accion        | Texto |
| Estado        | Texto |
| Detalles      | Texto |
| Usuario       | Texto |


Sistema de logging que registra automáticamente:

Cada solicitud registrada en SharePoint
Cada correo enviado
Cada error que ocurra
Timestamp y detalles de cada transacción
---

## Paso 9: Probar Integración Completa
Objetivo: Realizar pruebas end-to-end del agente con todas las integraciones activas.

## Instrucciones:

- Publicar el agente:
En Copilot Studio, hacer clic en Publicar
Confirmar la publicación
- Abrir el panel de prueba:
Hacer clic en el icono Probar el bot en la esquina superior derecha
El panel de chat se abrirá
- Ejecutar Caso de Prueba 1 - Cliente Elegible:
Escribir: Quiero solicitar un crédito
Responder a las preguntas:
Nombre: María González
Correo: [su-correo-de-prueba]@ejemplo.com
Monto: 40000
Ingreso mensual: 15000
Observar el flujo completo
- Verificar resultados del Caso 1:
[ ] El agente confirma elegibilidad
[ ] Muestra monto máximo aprobable
[ ] Registra la solicitud
[ ] Envía correo de confirmación
[ ] Proporciona número de solicitud
Verificar en SharePoint: nueva fila con datos de María
Verificar correo: debe llegar confirmación
Verificar Dataverse: logs de las transacciones
- Ejecutar Caso de Prueba 2 - Cliente No Elegible (sin ajuste):
Iniciar nueva conversación: hacer clic en Restablecer
Escribir: Necesito un préstamo personal
Responder:
Nombre: Carlos Ruiz
Correo: carlos.ruiz@ejemplo.com
Monto: 80000
Ingreso mensual: 10000
Cuando pregunte si desea ajustar: No
- Verificar resultados del Caso 2:
[ ] El agente indica que no es elegible
[ ] Muestra razón de rechazo
[ ] Ofrece monto alternativo (50000)
[ ] Respeta decisión de no ajustar
[ ] Finaliza conversación apropiadamente
Verificar SharePoint: NO debe haber registro de Carlos
Verificar Dataverse: debe haber log de validación
- Ejecutar Caso de Prueba 3 - Cliente No Elegible (con ajuste):
Iniciar nueva conversación
Escribir: Solicitar crédito
Responder:
Nombre: Ana Martínez
Correo: [su-correo-de-prueba-2]@ejemplo.com
Monto: 70000
Ingreso mensual: 12000
Cuando pregunte si desea ajustar: Sí
- Verificar resultados del Caso 3:
[ ] El agente indica no elegibilidad inicial
[ ] Ofrece ajuste a 60000 (12000 * 5)
[ ] Acepta ajuste del cliente
[ ] Registra solicitud con monto ajustado
[ ] Envía correo de confirmación
Verificar SharePoint: registro de Ana con monto 60000
Verificar correo: confirmación recibida
Verificar Dataverse: logs completos del proceso
- Probar manejo de errores:
Iniciar nueva conversación
Ingresar correo inválido (ejemplo: correo-sin-arroba)
Observar cómo el agente maneja la validación
Verificar que los logs registran cualquier error
Revisar Analytics en Copilot Studio:
Hacer clic en Analytics en el panel lateral
Navegar a Sesiones
Revisar las conversaciones de prueba
Verificar que todas las sesiones se registraron
- Documentar resultados:
Crear documento compartido del equipo
Registrar:
Casos de prueba ejecutados
Resultados obtenidos
Errores encontrados
Observaciones y mejoras sugeridas
Salida Esperada:

| Caso de Prueba     | Elegibilidad        | Registro SharePoint        | Correo Enviado | Logs Dataverse |
|-------------------|---------------------|----------------------------|----------------|----------------|
| Caso 1 (María)    | ✓ Elegible          | ✓ Creado                   | ✓ Enviado      | ✓ Completo     |
| Caso 2 (Carlos)   | ✗ No elegible       | ✗ No creado                | ✗ No enviado   | ✓ Validación   |
| Caso 3 (Ana)      | ✗ → ✓ Ajustado      | ✓ Creado (ajustado)        | ✓ Enviado      | ✓ Completo     |


---
##  Recursos

- https://learn.microsoft.com/microsoft-copilot-studio/
- https://learn.microsoft.com/power-platform/
- https://learn.microsoft.com/ai-builder/

---

¡Felicitaciones por completar el laboratorio!
