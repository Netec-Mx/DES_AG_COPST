
# Desarrollo básico de Agentes de IA con Copilot Studio 

---

## Información General del Curso

- **Curso:** Desarrollo básico de Agentes de IA con Copilot Studio y Power Platform  
- **Módulo:** 1 – Fundamentos de Copilot Studio y Power Platform  
- **Tipo de actividad:** Laboratorio grupal práctico  
- **Duración estimada:** 53 minutos  
- **Nivel:** Principiante  
- **Nivel de Bloom:** Aplicar  

---

## Descripción General

En esta actividad grupal práctica, los equipos explorarán **Microsoft Copilot Studio** y crearán su primer **agente de IA básico** orientado al sector bancario.

Los participantes:
- Navegarán por la plataforma Copilot Studio
- Identificarán componentes fundamentales de arquitectura de agentes
- Documentarán casos de uso bancarios reales
- Implementarán buenas prácticas iniciales de seguridad
- Evaluarán capacidades y limitaciones de Power Platform

Este laboratorio consolida los conceptos introductorios del curso y establece la base para el desarrollo de agentes más complejos en módulos posteriores.

---

## Objetivos de Aprendizaje

- Identificar los componentes clave de un agente de IA conversacional
- Navegar eficientemente por Copilot Studio, Power Automate y AI Builder
- Analizar casos de uso bancarios reales aplicables a agentes de IA
- Crear un agente de IA simple siguiendo buenas prácticas de seguridad
- Evaluar capacidades y limitaciones de las herramientas de Power Platform

---

## Prerrequisitos

- Navegación básica en navegadores web
- Uso general de Microsoft 365
- Comprensión básica de atención al cliente en banca
- Conceptos básicos de IA (opcional)

---

## Acceso Requerido

- Cuenta activa de Microsoft 365
- Licencia de Microsoft Copilot Studio o Power Virtual Agents
- Acceso a Power Platform con permisos de creador
- Equipo de trabajo de 3 a 4 personas

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

##  Desarrollo del Laboratorio

### Paso 1 – Exploración de la Interfaz de Copilot Studio
Familiarizarse con la navegación y componentes principales de Microsoft Copilot Studio.

-Instrucciones

1. Acceda a Copilot Studio en su navegador: https://copilotstudio.microsoft.com
2. En la página principal, identifique y explore las siguientes secciones
- Home (Inicio): Panel principal con acceso rápido
- Agents (Agentes): Lista de agentes existentes
- Settings (Configuración): Opciones del entorno
3. Haga clic en "Create" (Crear) en la barra superior y observe las opciones disponibles.
4. Navegue a la sección "Documentación" en el botón de ayuda disponible en  y revise los recursos de documentación disponibles.
5. Verifique el ambiente activo haciendo clic en el ícono de ambiente en la esquina superior derecha. Confirme que está en el ambiente correcto asignado a su equipo.


### Paso 2 – Arquitectura de Agentes
Intenciones, entidades, tópicos y respuestas generativas.

1. En Copilot Studio, haga clic en "Create" → "New agent".
2. Observe la estructura de configuración inicial que incluye:
- Name (Nombre): Identificador del agente
- Description (Descripción): Propósito del agente
- Instructions (Instrucciones): Comportamiento base del agente
- Language (Idioma): Idioma principal de interacción
3. En equipo, discutan y documenten los siguientes conceptos:
- Intenciones (Intents): Qué quiere lograr el usuario
- Entidades (Entities): Información específica extraída de mensajes
- Tópicos (Topics): Flujos de conversación estructurados
- Respuestas generativas: Respuestas creadas dinámicamente por IA

### Paso 3 – Casos de Uso Bancarios
Documentación de 3 casos de uso reales del sector.

1. En equipo, realicen una lluvia de ideas sobre problemas o necesidades comunes en la banca que podrían resolverse con agentes de IA.
1. Consideren las siguientes categorías:
- Atención al cliente: Consultas frecuentes, horarios, ubicaciones
- Operaciones transaccionales: Consultas de saldo, transferencias, pagos
- Productos y servicios: Información sobre cuentas, tarjetas, préstamos
- Soporte técnico: Problemas con banca en línea, aplicaciones móviles
- Cumplimiento y seguridad: Reportes de fraude, actualización de datos
1. Seleccionen los tres casos de uso más relevantes basándose en:
- Frecuencia de la necesidad
- Impacto en experiencia del cliente
- Viabilidad técnica con Copilot Studio
- Potencial de automatización
1. Para cada caso de uso seleccionado, documenten en formato estructurado:
   Caso de Uso #: [Número]
   Nombre: [Título descriptivo]
   Categoría: [Categoría del punto 2]

   Descripción: [2-3 oraciones explicando el problema]

   Usuario típico: [Perfil del cliente que lo necesita]

   Interacción esperada:
   - Usuario: [Ejemplo de mensaje inicial]
   - Agente: [Tipo de respuesta esperada]
   - Usuario: [Posible seguimiento]
   - Agente: [Resolución]

   Beneficios:
   - [Beneficio 1]
   - [Beneficio 2]

   Datos necesarios:
   - [Tipo de información requerida 1]
   - [Tipo de información requerida 2]

   Consideraciones de seguridad:
   - [Aspecto de seguridad relevante]


### Paso 4 – Creación del Agente
Configuración inicial y pruebas básicas.

1. En Copilot Studio, haga clic en "Create" → "New agent".
1. Configure los parámetros iniciales:
- Name: Asistente Bancario [Nombre del Equipo]
- - Ejemplo: Asistente Bancario Equipo1
- Descripción: 
"Agente de IA para atención inicial de clientes bancarios.
     Proporciona información general, direcciona consultas y
     ofrece asistencia básica con operaciones comunes."
- Instrucciones:
"Eres un asistente virtual profesional de un banco.
     Tu objetivo es saludar cordialmente a los clientes,
     entender sus necesidades y proporcionar ayuda de manera
     clara y segura. Siempre mantén un tono amigable pero
     profesional. Nunca solicites información sensible como
     contraseñas completas o números de tarjeta completos.
     Si no puedes resolver algo, ofrece derivar a un
     representante humano."
3.  Haga clic en "Create" (o "guardar"si ya ha creado el agente) para generar el agente.
4. Una vez creado, explore la interfaz del editor.
- Topics (panel izquierdo): Tópicos de conversación
- Canvas central: Área de diseño del flujo
- Test bot (panel derecho): Chat de prueba
5. Localice el tópico predeterminado "Greeting" o "Conversational boosting" en el panel de Topics.
6. Haga clic en el tópico de saludo para ver su estructura básica.
7. En el panel de prueba a la derecha, haga clic en "Test your agent" o el ícono de chat.
8. Escriba un mensaje de prueba: "Hola, necesito ayuda" y observe la respuesta del agente.

### Paso 5 – Seguridad Básica
Privacidad, autenticación y gobernanza inicial.

1. En el editor del agente, haga clic en "Settings" (Configuración) en la barra superior.
1. Navegue a la sección "Security" (Seguridad).
1. Configure las siguientes opciones:

Authentication (Autenticación):

- Revise la configuración actual 
- Documente que para producción se requeriría autenticación
- NO cambie la configuración por ahora (se configurará en módulos posteriores)
1. Navegue a "Data & Privacy" o "Privacy" (Privacidad):
- Habilite "Save conversation history" (Guardar historial de conversaciones) si está disponible
- Verifique que esté habilitada la opción de análisis de datos
2. Vaya a "General" en Settings:
- Verifique el Environment (Ambiente) asignado
- Confirme la región de datos (Data location)
- Documente esta información en su documento del equipo
3. Navegue a "Advanced" o "AI capabilities":
- Revise las configuraciones de Generative AI
- Verifique que esté habilitado "Generative answers" o similar
- Observe las opciones de moderación de contenido si están disponibles
4. Haga clic en "Save" (Guardar) para aplicar cualquier cambio realizado
5. En el documento del equipo, agregue una sección:
"   CONFIGURACIÓN DE SEGURIDAD - AGENTE INICIAL

   Fecha: [Fecha actual]
   Agente: [Nombre del agente]

   Configuraciones aplicadas:
   - Autenticación: [Estado actual]
   - Historial de conversaciones: [Habilitado/Deshabilitado]
   - Región de datos: [Región]
   - Respuestas generativas: [Habilitado/Deshabilitado]

   Pendientes para producción:
   - [ ] Configurar autenticación de usuarios
   - [ ] Implementar políticas de DLP
   - [ ] Configurar límites de rate limiting
   - [ ] Revisar cumplimiento regulatorio bancario"


### Paso 6 – Bienvenida
Personalización del flujo inicial.

Instrucciones:

1. En el editor del agente, localice el tópico de "Greeting" o "Conversation Start" en el panel izquierdo.
1. Haga clic en el tópico para abrirlo en el canvas central.
1. Observe la estructura del flujo:
- Trigger phrases (Frases disparadoras): Frases que activan este tópico
- Message nodes (Nodos de mensaje): Respuestas del agente
- Question nodes (Nodos de pregunta): Solicitudes de información al usuario
4. Modifique o agregue el primer nodo de mensaje para incluir un saludo bancario profesional:

Haga clic en el nodo de mensaje existente y edite el texto:

"   ¡Bienvenido al Asistente Virtual de [Nombre del Banco]!

   Estoy aquí para ayudarte con:
   • Consultas sobre productos y servicios
   • Información de sucursales y horarios
   • Preguntas frecuentes sobre tu cuenta
   • Orientación sobre operaciones básicas

   ¿En qué puedo asistirte hoy?"

1. Si no existe un nodo de pregunta, agregue uno:
- Haga clic en el ícono "+" debajo del mensaje
- Seleccione "Ask a question" (Hacer una pregunta)
- Configure:
- - Question: ¿Cuál es el motivo de tu consulta?
- - Identify: Seleccione "User's entire response" (Respuesta completa del usuario)
- - Save response as: motivoConsulta
2. Agregue un nodo de mensaje de confirmación:
- Haga clic en "+" después de la pregunta
- Seleccione "Send a message"
Texto:

"     Entiendo que necesitas ayuda con: {motivoConsulta}

     Estoy procesando tu solicitud..."

3. Guarde los cambios haciendo clic en "Save" en la parte superior.
4. Pruebe el flujo actualizado en el panel de prueba:
- Haga clic en "Reset" (Reiniciar) en el chat de prueba
- Escriba: Hola
- Observe la nueva bienvenida
- Responda con: Quiero información sobre cuentas de ahorro
- Verifique que el agente confirma correctamente

### Paso 7 – Power Automate y AI Builder
Exploración de flujos y modelos de IA.

1. Abra una nueva pestaña en su navegador y navegue a Power Automate: https://make.powerautomate.com
2. Inicie sesión con las mismas credenciales de Microsoft 365.
3. Explore la interfaz principal:
- Home: Panel de inicio
- My flows: Sus flujos de automatización
- Templates: Plantillas predefinidas
- Connectors: Conectores disponibles
4. Haga clic en "+ Create" (Crear) y observe los tipos de flujos disponibles:
- Automated cloud flow (Flujo de nube automatizado)
- Instant cloud flow (Flujo de nube instantáneo)
- Scheduled cloud flow (Flujo de nube programado)
- Desktop flow (Flujo de escritorio)
5. En la barra de búsqueda superior, busque: Copilot Studio
6. Observe los conectores y plantillas disponibles que integran Copilot Studio con Power Automate.
7. En el menú lateral, haga clic en "AI Builder" (puede estar en "More" o "Más").
8. Explore los modelos de IA disponibles:
- Form processing (Procesamiento de formularios)
- Text recognition (Reconocimiento de texto)
- Sentiment analysis (Análisis de sentimiento)
- Entity extraction (Extracción de entidades)
- Business card reader (Lector de tarjetas de negocio)
9. Haga clic en "Explore" en uno de los modelos para ver una demostración.
10. Regrese a su documento del equipo y agregue una sección:
    
"EXPLORACIÓN DE POWER PLATFORM

    Power Automate:
    - Propósito: [Descripción breve del equipo]
    - Casos de uso bancarios identificados:
      1. [Caso de uso 1]
      2. [Caso de uso 2]

    AI Builder:
    - Modelos relevantes para banca:
      • [Modelo 1]: [Aplicación bancaria]
      • [Modelo 2]: [Aplicación bancaria]

    Integraciones potenciales con nuestro agente:
    - [Integración 1]
    - [Integración 2]
Discutan en equipo (5 minutos) cómo estas herramientas podrían complementar el agente de IA creado."


### Paso 8 – Pruebas
Pruebas sistemáticas y mejoras.

Instrucciones:

1. Regrese a la pestaña de Copilot Studio con su agente abierto.
2. En el panel de prueba, haga clic en "Reset" para iniciar una conversación nueva.
3. Realice las siguientes pruebas sistemáticas y documente los resultados:

Prueba 1: Saludo estándar

- Usuario: Hola
- Documente: ¿Responde apropiadamente?

Prueba 2: Saludo informal

- Usuario: Qué onda
- Documente: ¿Reconoce saludos informales?

Prueba 3: Consulta directa

- Usuario: Quiero abrir una cuenta
- Documente: ¿Cómo responde sin pasar por el saludo?

Prueba 4: Pregunta fuera de alcance

- Usuario: ¿Cuál es el clima hoy?
- Documente: ¿Maneja apropiadamente temas fuera de contexto?

Prueba 5: Consulta de seguridad sensible

- Usuario: ¿Cuál es mi contraseña?
- Documente: ¿Rechaza apropiadamente solicitudes inseguras?

Prueba 6: Múltiples consultas

- Usuario: Necesito información sobre cuentas y también sobre tarjetas de crédito
- Documente: ¿Maneja múltiples intenciones?

Para cada prueba, capture una captura de pantalla de la conversación.
En su documento del equipo, cree una tabla de resultados:
   RESULTADOS DE PRUEBAS - AGENTE INICIAL

   | # | Tipo de Prueba | Entrada | Respuesta | Apropiada (Sí/No) | Observaciones |
   |---|----------------|---------|-----------|-------------------|---------------|
   | 1 | Saludo estándar | Hola | [Resumen] | Sí/No | [Comentarios] |
   | 2 | Saludo informal | Qué onda | [Resumen] | Sí/No | [Comentarios] |
   | ... | ... | ... | ... | ... | ... |

Identifique al menos tres áreas de mejora basadas en las pruebas:

   ÁREAS DE MEJORA IDENTIFICADAS:

   1. [Área 1]
      Problema: [Descripción]
      Mejora propuesta: [Solución]
      Prioridad: Alta/Media/Baja

   2. [Área 2]
      Problema: [Descripción]
      Mejora propuesta: [Solución]
      Prioridad: Alta/Media/Baja

   3. [Área 3]
      Problema: [Descripción]
      Mejora propuesta: [Solución]
      Prioridad: Alta/Media/Baja

Guarde todas las capturas de pantalla en una carpeta compartida del equipo.

### Paso 9 – Evaluación
Capacidades, limitaciones y preguntas críticas.

- ¿Puede el agente manejar información sensible de forma segura?
- ¿Qué nivel de personalización es posible?
- ¿Cómo se integraría con sistemas bancarios existentes?
- ¿Qué requisitos regulatorios podrían ser desafiantes?

---

##  Recursos

- https://learn.microsoft.com/microsoft-copilot-studio/
- https://learn.microsoft.com/power-platform/
- https://learn.microsoft.com/ai-builder/

---

¡Felicitaciones por completar el laboratorio!
