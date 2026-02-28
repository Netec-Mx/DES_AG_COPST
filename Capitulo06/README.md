
# Estructura lógica multi-agente

---

## Descripción General

En esta actividad grupal avanzada, los equipos diseñarán e implementarán un ecosistema completo de agentes especializados para el sector bancario. Los participantes crearán al menos dos agentes especializados (por ejemplo: uno para productos de ahorro y otro para créditos) junto con un agente coordinador que derive consultas al especialista apropiado. Esta actividad integra todos los conceptos aprendidos en módulos anteriores y desafía a los equipos a resolver casos de uso bancarios complejos como solicitudes de crédito hipotecario, onboarding digital de nuevos clientes o gestión integral de reclamos. El enfoque está en diseñar arquitecturas escalables, configurar handoff efectivo entre agentes y compartir contexto conversacional de manera segura.


---

## Objetivos de Aprendizaje

- Diseñar arquitecturas de múltiples agentes especializados que colaboran efectivamente
- Implementar mecanismos de transferencia (handoff) y coordinación entre agentes
- Aplicar patrones de casos de uso bancarios complejos (onboarding, créditos, reclamos)
- Configurar contexto compartido entre agentes especializados de forma segura
- Evaluar cuándo usar un agente generalista versus múltiples agentes especializados

---

## Prerrequisitos

- Creación y configuración de agentes en Microsoft Copilot Studio
- Diseño de flujos conversacionales complejos con múltiples temas
- Integración con Power Automate y manejo de variables
- Comprensión de procesos bancarios end-to-end
- Experiencia con el agente creado en módulos anteriores

---

## Acceso Requerido

- Licencia activa de Microsoft Copilot Studio
- Permisos de creación de múltiples agentes en el ambiente de Power Platform
- Acceso al agente desarrollado en módulos previos
- Permisos de colaboración en equipo (3-4 personas por equipo)

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

**Preparación del Ambiente de Trabajo Grupal:**

Formar equipos de 3-4 personas
Designar roles dentro del equipo:
Arquitecto de Solución: Diseña la estructura multi-agente
Desarrollador Principal: Implementa agentes especializados
Especialista en Integración: Configura handoff y contexto compartido
Documentador: Registra decisiones y arquitectura
Verificar acceso compartido al ambiente de Power Platform
💡 Nota: Todos los miembros del equipo deben tener acceso al mismo ambiente de desarrollo para colaborar efectivamente.



---

##  Desarrollo del Laboratorio

## Paso 1: Selección y Diseño del Caso de Uso Bancario
Objetivo: Seleccionar un caso de uso bancario complejo y diseñar la arquitectura multi-agente apropiada.

## Instrucciones:

1.  Revisar los casos de uso disponibles (el equipo debe elegir UNO):

Opción A: Solicitud de Crédito Hipotecario

- Agente Coordinador: Recibe solicitud inicial
- Agente Especialista en Evaluación Crediticia: Analiza capacidad de pago
- Agente Especialista en Tasación de Propiedades: Gestiona valoración del inmueble

Opción B: Onboarding Digital de Nuevos Clientes

- Agente Coordinador: Guía el proceso general
- Agente Especialista en Verificación de Identidad: Validación KYC
- Agente Especialista en Productos: Recomienda productos bancarios iniciales

Opción C: Gestión Integral de Reclamos

- Agente Coordinador: Recibe y clasifica reclamos
- Agente Especialista en Reclamos de Tarjetas: Transacciones no reconocidas
- Agente Especialista en Reclamos de Servicio: Problemas operativos

2. Crear un diagrama de arquitectura en papel o herramienta digital que incluya:
- Flujo de conversación entre agentes
- Puntos de transferencia (handoff)
- Datos de contexto que se compartirán
- Criterios de enrutamiento

Documentar las decisiones de diseño en un documento compartido:

   ARQUITECTURA MULTI-AGENTE
   ========================
   Caso de Uso: [Nombre del caso seleccionado]

   Agentes Especializados:
   1. [Nombre Agente 1] - [Responsabilidad]
   2. [Nombre Agente 2] - [Responsabilidad]
   3. [Nombre Agente Coordinador] - [Responsabilidad]

   Criterios de Transferencia:
   - De Coordinador a Especialista 1: [Condición]
   - De Especialista 1 a Especialista 2: [Condición]

   Contexto Compartido:
   - Variable 1: [Nombre y propósito]
   - Variable 2: [Nombre y propósito]

Validar el diseño con todos los miembros del equipo antes de continuar.

- Resultado Esperado:

Un documento de diseño claro que todos los miembros del equipo comprenden y aprueban, incluyendo diagrama visual de la arquitectura.

Verificación:

- Se ha seleccionado un caso de uso específico
- El diagrama muestra claramente los 2-3 agentes especializados
- Los puntos de transferencia están identificados
- Las variables de contexto están documentadas
---

## Paso 2: Creación del Agente Coordinador
Objetivo: Implementar el agente coordinador que recibirá consultas iniciales y enrutará a especialistas.

Instrucciones:

1. Acceder a Microsoft Copilot Studio desde el navegador web:
   https://copilotstudio.microsoft.com
2. Crear un nuevo agente:
- Clic en "Create" > "New agent"
- Nombre: [NombreEquipo]_Coordinador_Bancario
- Descripción: Agente coordinador para [caso de uso seleccionado]
- Idioma: Español
- Clic en "Create"

Configurar el tema de bienvenida:
- Navegar a Topics > System > Greeting
- Editar el mensaje de bienvenida:

   ¡Bienvenido al sistema de [Nombre del Caso de Uso] del Banco!

   Soy tu asistente coordinador y te ayudaré a conectarte con el especialista
   adecuado para tu consulta.

   ¿En qué puedo asistirte hoy?
   - Solicitud de crédito hipotecario
   - Verificación de documentos
   - Consulta sobre tasación

3. Crear el tema de enrutamiento principal:
- Ir a Topics > + New topic > From blank
- Nombre: Enrutamiento Inicial
- Agregar trigger phrases:

     necesito un crédito
     quiero solicitar un préstamo
     información sobre hipotecas
     ayuda con mi solicitud

4. Configurar la lógica de enrutamiento:

Agregar nodo Question para identificar tipo de consulta:

     Para dirigirte al especialista correcto, ¿qué necesitas?

- Opciones (botones):
  Evaluación crediticia
  Tasación de propiedad
  Documentación requerida
- Guardar respuesta en variable TipoConsulta

5. Agregar nodo de mensaje antes de transferencia:

   Perfecto, te voy a conectar con nuestro especialista en [TipoConsulta].

   Le compartiré la información que me has proporcionado para que pueda
   ayudarte de inmediato.

Guardar el agente coordinador (Ctrl + S o botón Save).


Resultado Esperado:

Un agente coordinador funcional que puede recibir consultas iniciales, recopilar información básica y preparar la transferencia a especialistas.

Verificación:

- El agente coordinador está creado y guardado
- Las variables globales están configuradas
- El tema de enrutamiento identifica correctamente el tipo de consulta
- Los mensajes están en español y son claros
---

## Paso 3: Creación de Agentes Especializados
Objetivo: Crear los dos agentes especializados que manejarán aspectos específicos del caso de uso.

## Instrucciones:

1. Crear el primer agente especializado:
- En Copilot Studio, clic en "Create" > "New agent"
- Nombre: [NombreEquipo]_Especialista_[Área1]
- Ejemplo: EquipoA_Especialista_Creditos
- Descripción: Especialista en [área específica]
- Idioma: Español
- Clic en "Create"

2. Configurar el saludo especializado:
- Ir a Topics > System > Greeting
- Editar mensaje:

   Hola, soy el especialista en [Área].

   He recibido tu consulta desde nuestro coordinador y estoy aquí para
   ayudarte con [proceso específico].

   Vamos a comenzar...

3. Crear tema principal del especialista (ejemplo para Especialista en Créditos):
- Topics > + New topic > From blank
- Nombre: Evaluación de Capacidad Crediticia
- Agregar trigger phrases:

     evaluar mi crédito
     cuánto puedo pedir prestado
     análisis de capacidad de pago

4. Diseñar el flujo conversacional especializado:
- Agregar nodo Question para recopilar ingresos mensuales:

     ¿Cuál es tu ingreso mensual neto aproximado? (en pesos)

- Tipo: Number
- Guardar en variable: IngresoMensual

Agregar nodo Question para gastos mensuales:

     ¿Cuáles son tus gastos mensuales fijos aproximados? (en pesos)

- Tipo: Number
- Guardar en variable: GastosMensuales

Agregar nodo Question para monto solicitado:

     ¿Qué monto de crédito estás solicitando? (en pesos)

- Tipo: Number
- Guardar en variable: MontoSolicitado

Agregar lógica de evaluación básica:
- Insertar nodo Condition
- Condición: IngresoMensual - GastosMensuales > (MontoSolicitado / 240)

  (Asume plazo de 20 años = 240 meses)

Si cumple (rama True):

     ¡Excelente noticia! Según el análisis preliminar, tu capacidad de pago
     es adecuada para el monto solicitado.

     Tu capacidad de pago mensual disponible es: [IngresoMensual - GastosMensuales] pesos.

     El siguiente paso es conectarte con el especialista en tasación de propiedades.

Si no cumple (rama False):

     Según el análisis preliminar, el monto solicitado podría representar un
     desafío considerando tus ingresos y gastos actuales.

     Te recomiendo:
     1. Considerar un monto menor
     2. Evaluar la posibilidad de un co-deudor
     3. Revisar tus gastos mensuales

     ¿Te gustaría explorar estas opciones?

5. Crear el segundo agente especializado repitiendo los pasos 1-5 pero para el segundo área de especialización:
- Nombre: [NombreEquipo]_Especialista_[Área2]
- Ejemplo: EquipoA_Especialista_Tasaciones
- Diseñar flujo conversacional apropiado para su especialidad

Guardar ambos agentes especializados.


Resultado Esperado:

Dos agentes especializados completamente funcionales, cada uno con su flujo conversacional específico y lógica de negocio apropiada para su área de especialización.

Verificación:

-  Ambos agentes especializados están creados
- Cada agente tiene un saludo personalizado
- Los flujos conversacionales son específicos y coherentes
- Las variables capturan información relevante
- La lógica de negocio es apropiada para el caso de uso
---

## Paso 4: Configuración de Transferencias (Handoff) entre Agentes
Objetivo: Implementar la funcionalidad de transferencia entre el agente coordinador y los especialistas, incluyendo compartición de contexto.

## Instrucciones:

1. Regresar al agente coordinador:
- En Copilot Studio, abrir [NombreEquipo]_Coordinador_Bancario

2. Configurar la primera transferencia (del Coordinador al Especialista 1):
- Abrir el tema Enrutamiento Inicial
- Después del mensaje de preparación para transferencia, agregar nodo Transfer conversation (ubicado en agregar nodo, administrador de temas, transferir conversación)
- Configurar:
  Transfer to: Another agent
  Clic en Select agent
  Buscar y seleccionar: [NombreEquipo]_Especialista_[Área1]

3. Configurar variables de contexto para compartir:
En el nodo de transferencia, expandir Advanced options
Agregar Context variables to pass:

     ClienteID = [ClienteID]
     TipoConsulta = [TipoConsulta]
     EstadoProceso = "Iniciado"

4. Agregar mensaje de transición:
- Antes del nodo de transferencia, agregar nodo Message:

     Te estoy transfiriendo ahora con [Nombre del Especialista].

     Información que compartiré:
     - Tu identificación de cliente
     - El tipo de consulta: [TipoConsulta]
     - Estado del proceso: En curso

     Por favor espera un momento...

5. Configurar transferencia condicional basada en tipo de consulta:
- Agregar nodo Condition después de capturar TipoConsulta
- Condición 1: Si TipoConsulta = "Evaluación crediticia"
  Transferir a: [NombreEquipo]_Especialista_Creditos
- Condición 2: Si TipoConsulta = "Tasación de propiedad"
  Transferir a: [NombreEquipo]_Especialista_Tasaciones
- Condición 3 (Else): Cualquier otro caso
  Mensaje: "Déjame verificar con qué especialista necesitas hablar..."
  Transferir a agente predeterminado

Configurar recepción de contexto en agentes especializados:
- Abrir [NombreEquipo]_Especialista_[Área1]
- Ir a Settings > Variables
- Crear variables para recibir contexto:
  ClienteID_Recibido (tipo: String)
  TipoConsulta_Recibido (tipo: String)
  EstadoProceso_Recibido (tipo: String)

En el tema principal, agregar nodo Message inicial:

     Hola, veo que vienes derivado por nuestro coordinador.

     Cliente ID: [ClienteID_Recibido]
     Consulta: [TipoConsulta_Recibido]

     Continuemos con tu [TipoConsulta_Recibido]...

6. Configurar transferencia entre especialistas (si aplica):
- En [NombreEquipo]_Especialista_[Área1]
- Al final del flujo exitoso, agregar opción de transferencia:

     Hemos completado la [proceso del Área1].

     El siguiente paso es trabajar con el especialista en [Área2].
     ¿Te gustaría que te conecte ahora?

Agregar nodo Question con opciones:
- Sí, conectarme ahora
- No, continuaré más tarde
Si selecciona "Sí", agregar nodo Transfer conversation:
- Transfer to: [NombreEquipo]_Especialista_[Área2]
- Pasar variables de contexto actualizadas

7. Implementar transferencia de regreso al coordinador:
- En cada agente especializado, al finalizar su proceso:
- Agregar nodo Question:

     ¿Hay algo más en lo que pueda ayudarte?

- Si selecciona "Sí" o "Tengo otra consulta":
  Agregar nodo Transfer conversation de regreso al Coordinador
  Actualizar variable EstadoProceso = "Completado - [Área]"

8. Guardar todos los agentes con las configuraciones de transferencia.

Resultado Esperado:

Un ecosistema de agentes completamente integrado donde las conversaciones fluyen naturalmente entre coordinador y especialistas, con contexto compartido que se mantiene a lo largo de toda la interacción.

Verificación:

- Las transferencias están configuradas en el agente coordinador
- Los agentes especializados reciben y muestran el contexto compartido
- Las transferencias condicionales funcionan según el tipo de consulta
- Existe un camino de regreso al coordinador
- Las variables de contexto se actualizan correctamente
---

## Paso 5: Pruebas del Ecosistema Multi-Agente
Objetivo: Validar el funcionamiento completo del ecosistema de agentes mediante pruebas exhaustivas de diferentes escenarios.

## Instrucciones:

- Preparar escenarios de prueba:

1. Documentar al menos 3 escenarios en el documento del equipo:

   ESCENARIOS DE PRUEBA
   ====================

   Escenario 1: Flujo completo exitoso
   - Inicio: Usuario solicita crédito hipotecario
   - Coordinador: Identifica necesidad y transfiere
   - Especialista 1: Evalúa capacidad crediticia (aprobada)
   - Especialista 2: Gestiona tasación
   - Resultado esperado: Proceso completo sin errores

   Escenario 2: Flujo con evaluación negativa
   - Inicio: Usuario solicita monto muy alto
   - Especialista 1: Evalúa y rechaza
   - Resultado esperado: Ofrece alternativas

   Escenario 3: Transferencia múltiple
   - Inicio: Usuario cambia de consulta a mitad del proceso
   - Resultado esperado: Regresa a coordinador y redirige

2. Probar el agente coordinador:
- Abrir [NombreEquipo]_Coordinador_Bancario
- Clic en Test (esquina superior derecha)
- Iniciar conversación:

     Hola, necesito información sobre créditos hipotecarios

- Verificar:
  El saludo es apropiado
  Presenta opciones claras
  Captura correctamente el tipo de consulta
  El mensaje de transición aparece
- Probar la transferencia al primer especialista:
  Continuar en el panel de prueba
  Seleccionar la opción que activa la transferencia
  Observar: La conversación debe mostrarse como transferida
  Verificar que el especialista:
   Saluda apropiadamente
   Muestra el contexto recibido (ClienteID, TipoConsulta)
   Inicia su flujo conversacional

3. Probar el flujo completo del especialista:
- Responder todas las preguntas del especialista
- Para Especialista en Créditos, usar datos de prueba:

     Ingreso mensual: 50000
     Gastos mensuales: 20000
     Monto solicitado: 1500000

Verificar:
- Cálculos correctos
- Mensajes apropiados según resultado
- Opción de transferencia al siguiente especialista
Probar transferencia entre especialistas:
- Aceptar la transferencia al segundo especialista
- Verificar que el contexto se mantiene
- Completar el flujo del segundo especialista
Probar escenarios de error:
- Prueba A: Reiniciar conversación y proporcionar datos inválidos
  Ingreso mensual: -1000 (negativo)
  Verificar manejo de error
- Prueba B: Intentar "confundir" al coordinador
  Mensaje: "Quiero todo y nada a la vez"
  Verificar que solicita clarificación
 
4. Documentar resultados de pruebas:

Crear tabla de resultados:

   | Escenario | Resultado | Observaciones | Estado |
   |-----------|-----------|---------------|---------|
   | Flujo completo exitoso | ✓ Pasó | Transferencias fluidas | OK |
   | Evaluación negativa | ✓ Pasó | Ofrece alternativas correctamente | OK |
   | Datos inválidos | ✗ Falló | No valida números negativos | CORREGIR |

5. Realizar ajustes basados en pruebas:
- Para cada problema identificado:
  Asignar responsable de corrección
  Implementar la corrección
  Re-probar el escenario
6. Prueba final con todo el equipo:
- Cada miembro del equipo debe probar al menos un escenario completo
- Compartir observaciones
- Validar que todos los flujos funcionan

Resultado Esperado:
Un ecosistema de agentes completamente funcional y probado, con documentación clara de los resultados de pruebas y cualquier limitación identificada.

Verificación:

- Se han probado al menos 3 escenarios diferentes
- Las transferencias entre agentes funcionan correctamente
- El contexto se mantiene a lo largo de las transferencias
- Los mensajes son claros y en español
- Se han documentado y corregido los problemas encontrados
- Todo el equipo ha validado el funcionamiento
---

## Paso 6: Documentación de la Arquitectura y Justificación de Decisiones
Objetivo: Crear documentación completa de la arquitectura multi-agente y justificar las decisiones de diseño tomadas.

## Instrucciones:

Crear el documento de arquitectura final con la siguiente estructura:

   # ARQUITECTURA MULTI-AGENTE: [Nombre del Caso de Uso]
   ## Equipo: [Nombre del Equipo]

   ### 1. RESUMEN EJECUTIVO
   - Caso de uso seleccionado: [Nombre]
   - Número de agentes: [X]
   - Complejidad del flujo: [Alta/Media]
   - Tiempo estimado de implementación: [X minutos]

   ### 2. DIAGRAMA DE ARQUITECTURA
   [Insertar diagrama visual o descripción detallada]

   Agente Coordinador
         |
         |---> Especialista 1 [Área]
         |           |
         |           |---> Especialista 2 [Área]
         |                       |
         |<----------------------|

   ### 3. AGENTES IMPLEMENTADOS

   #### 3.1 Agente Coordinador
   - Nombre: [Nombre completo]
   - Responsabilidad: [Descripción]
   - Temas principales: [Lista]
   - Variables gestionadas: [Lista]

   #### 3.2 Especialista 1: [Nombre]
   - Responsabilidad: [Descripción]
   - Proceso que maneja: [Detalle]
   - Criterios de éxito: [Lista]
   - Puntos de transferencia: [Descripción]

   #### 3.3 Especialista 2: [Nombre]
   - Responsabilidad: [Descripción]
   - Proceso que maneja: [Detalle]
   - Criterios de éxito: [Lista]
   - Puntos de transferencia: [Descripción]

   ### 4. FLUJO DE CONTEXTO COMPARTIDO

   Variables compartidas entre agentes:
   - ClienteID: [Propósito y uso]
   - TipoConsulta: [Propósito y uso]
   - EstadoProceso: [Propósito y uso]
   - DatosRecopilados: [Propósito y uso]

   Estrategia de actualización:
   [Explicar cómo y cuándo se actualizan las variables]

   ### 5. DECISIONES DE DISEÑO Y JUSTIFICACIÓN
Justificar decisiones clave (completar cada sección):

   #### 5.1 ¿Por qué múltiples agentes vs. un agente generalista?

   Decisión: [Elegimos arquitectura multi-agente porque...]

   Justificación:
   - Ventaja 1: [Ej: Especialización permite respuestas más precisas]
   - Ventaja 2: [Ej: Mantenimiento más fácil de áreas específicas]
   - Ventaja 3: [Ej: Escalabilidad - se pueden agregar más especialistas]

   Desventajas consideradas:
   - [Ej: Mayor complejidad en la configuración inicial]
   - [Ej: Necesidad de gestionar transferencias]

   #### 5.2 Estrategia de enrutamiento

   Decisión: [Usamos enrutamiento basado en tipo de consulta porque...]

   Alternativas consideradas:
   - [Ej: Enrutamiento por intención detectada automáticamente]
   - [Ej: Menú de opciones explícito]

   Razón de la elección: [Explicación]

   #### 5.3 Gestión de contexto

   Decisión: [Compartimos X variables entre agentes porque...]

   Variables críticas identificadas:
   - [Variable]: [Por qué es crítica]

   Estrategia de seguridad:
   - [Ej: No compartimos datos sensibles como contraseñas]
   - [Ej: Usamos IDs en lugar de nombres completos]
Documentar limitaciones y mejoras futuras:

   ### 6. LIMITACIONES IDENTIFICADAS

   1. [Limitación 1]
      - Descripción: [Detalle]
      - Impacto: [Alto/Medio/Bajo]
      - Mitigación actual: [Cómo se maneja]

   2. [Limitación 2]
      - Descripción: [Detalle]
      - Impacto: [Alto/Medio/Bajo]
      - Mitigación actual: [Cómo se maneja]

   ### 7. MEJORAS FUTURAS PROPUESTAS

   Corto plazo (1-2 semanas):
   - [Mejora 1]: [Descripción y beneficio]
   - [Mejora 2]: [Descripción y beneficio]

   Mediano plazo (1-2 meses):
   - [Mejora 3]: [Descripción y beneficio]
   - [Mejora 4]: [Descripción y beneficio]

   Largo plazo (3+ meses):
   - [Mejora 5]: [Descripción y beneficio]
Agregar sección de lecciones aprendidas:

   ### 8. LECCIONES APRENDIDAS

   #### Aspectos técnicos:
   - [Lección 1]: [Ej: La configuración de variables de contexto requiere
                   planificación cuidadosa desde el inicio]
   - [Lección 2]: [Ej: Las pruebas de transferencia deben hacerse
                   frecuentemente durante el desarrollo]

   #### Aspectos de colaboración:
   - [Lección 3]: [Ej: La división de roles fue efectiva para trabajar
                   en paralelo]
   - [Lección 4]: [Ej: La documentación continua evitó confusiones]

   #### Aspectos de negocio:
   - [Lección 5]: [Ej: Entender el proceso bancario completo fue crucial
                   para diseñar los flujos]
Incluir métricas de implementación:

   ### 9. MÉTRICAS DE IMPLEMENTACIÓN

   - Tiempo total de desarrollo: [X minutos]
   - Número de temas creados: [X]
   - Número de nodos en flujos: [X]
   - Escenarios de prueba ejecutados: [X]
   - Problemas encontrados y resueltos: [X]
   - Miembros del equipo participantes: [X]
Crear sección de casos de uso reales:

   ### 10. APLICACIÓN A CASOS REALES

   Este ecosistema de agentes podría aplicarse a:

   1. [Banco Real 1]: [Cómo se usaría]
      - Volumen estimado: [X consultas/día]
      - Beneficio esperado: [Descripción]

   2. [Banco Real 2]: [Cómo se usaría]
      - Adaptaciones necesarias: [Lista]
      - ROI estimado: [Descripción]
Revisar y finalizar el documento:
Todo el equipo debe revisar el documento
Cada miembro firma/aprueba su sección
Exportar a PDF para presentación
Resultado Esperado:

Un documento de arquitectura completo y profesional que explica claramente el diseño multi-agente, justifica todas las decisiones importantes y proporciona una base sólida para futuras mejoras o implementaciones similares.

Verificación:

- El documento incluye todas las secciones requeridas
- Las decisiones de diseño están claramente justificadas
- Se han identificado y documentado limitaciones
- Las lecciones aprendidas son específicas y útiles
- Todo el equipo ha revisado y aprobado el documento
- El documento está listo para presentación


---
##  Recursos

- https://learn.microsoft.com/microsoft-copilot-studio/
- https://learn.microsoft.com/power-platform/
- https://learn.microsoft.com/ai-builder/

---

¡Felicitaciones por completar el laboratorio!