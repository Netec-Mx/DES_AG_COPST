
# Ajusta y optimiza el comportamiento del agente


---

## Descripción General

En esta actividad grupal avanzada, los equipos definirán e implementarán la personalidad completa y las reglas de negocio específicas para su agente bancario de IA. Los participantes crearán un perfil de comunicación profesional que refleje los valores de una institución financiera, establecerán límites de seguridad apropiados, e implementarán reglas de negocio del sector bancario. Esta actividad integra los conceptos de diseño de prompts, instrucciones del sistema y buenas prácticas de gobernanza aprendidos en el módulo, resultando en un agente bancario consistente, seguro y alineado con regulaciones financieras.


---

## Objetivos de Aprendizaje

- Personalizar el tono y estilo de comunicación del agente según la marca bancaria
- Implementar reglas de negocio específicas del sector financiero en el agente
- Configurar instrucciones detalladas para guiar el comportamiento del agente
- Establecer límites y restricciones de seguridad en las respuestas del agente
- Validar que el agente mantiene consistencia en su personalidad y cumplimiento normativo

---

## Prerrequisitos

- Módulo 3.0 completado con un agente bancario funcional en Copilot Studio
- Comprensión de principios de comunicación corporativa y servicio al cliente
- Conocimiento básico de normativas bancarias (proporcionado en materiales de referencia)
- Familiaridad con la sección de instrucciones del sistema en Copilot Studio

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

Formar equipos de 3-4 personas
Asignar roles dentro del equipo:
Líder de Personalidad: Define tono y estilo de comunicación
Especialista en Reglas de Negocio: Implementa validaciones financieras
Oficial de Seguridad: Establece límites y restricciones
Documentador: Mantiene el manual de estilo del agente
Preparar documento colaborativo compartido con esta estructura:

MANUAL DE ESTILO DEL AGENTE BANCARIO
=====================================

1. PERFIL DEL AGENTE
   - Nombre del agente:
   - Propósito principal:
   - Público objetivo:

2. GUÍAS DE TONO Y ESTILO
   - Tono general:
   - Nivel de formalidad:
   - Características de personalidad:

3. REGLAS DE NEGOCIO
   - Límites transaccionales:
   - Horarios de atención:
   - Políticas de seguridad:

4. INSTRUCCIONES DEL SISTEMA
   - Instrucciones principales:
   - Restricciones:
   - Manejo de excepciones:

5. ESCENARIOS DE PRUEBA



---

##  Desarrollo del Laboratorio

## Paso 1: Definir el Perfil y Personalidad del Agente Bancario
Objetivo: Establecer la identidad, tono y estilo de comunicación que el agente utilizará en todas las interacciones.

## Instrucciones:

- Reunirse como equipo y discutir el perfil del agente. Documentar en el manual de estilo:

**Elementos a definir:**

Nombre del agente: Elegir un nombre profesional y memorable
Rol: Asistente virtual bancario especializado
Tono: Formal, profesional, empático, conciso
Valores: Seguridad, confianza, transparencia, eficiencia

-Definir las guías de comunicación específicas:
   EJEMPLO DE GUÍAS DE TONO:

   ✓ SÍ HACER:
   - Usar lenguaje formal pero accesible
   - Mostrar empatía con las preocupaciones del cliente
   - Ser conciso y directo en las respuestas
   - Confirmar entendimiento antes de proceder
   - Usar términos financieros cuando sea apropiado, explicándolos si es necesario

   ✗ NO HACER:
   - Usar jerga excesivamente técnica sin explicación
   - Hacer promesas que no se pueden cumplir
   - Mostrar frustración o impaciencia
   - Usar humor inapropiado en temas financieros sensibles
   - Tutear al cliente (mantener "usted" a menos que el cliente solicite lo contrario)

- Crear ejemplos de respuestas modelo para situaciones comunes:

Saludo inicial:
   "Buenos días. Soy [Nombre del Agente], su asistente virtual bancario.
   Estoy aquí para ayudarle con consultas sobre sus cuentas, transacciones
   y servicios bancarios. ¿En qué puedo asistirle hoy?"

- Solicitud de información sensible:

   "Para proteger su seguridad, nunca le solicitaré contraseñas o números
   PIN completos. Si necesita realizar operaciones que requieren
   autenticación adicional, le conectaré con un asesor humano o le
   dirigiré a nuestros canales seguros."

Documentar estas definiciones en la sección 1 y 2 del manual de estilo.


Resultado Esperado:

Un documento con el perfil completo del agente incluyendo:

Nombre y rol definido
Lista de características de personalidad (mínimo 5)
Guías de tono con ejemplos de "hacer" y "no hacer" (mínimo 5 de cada)
3-5 ejemplos de respuestas modelo para situaciones comunes
Verificación:

[ ] El perfil refleja valores apropiados para una institución financiera
[ ] Las guías de tono son específicas y accionables
[ ] Los ejemplos de respuestas son profesionales y empáticos
[ ] Todos los miembros del equipo están de acuerdo con la personalidad definida
---

## Paso 2: Implementar Reglas de Negocio del Sector Bancario
Objetivo: Establecer reglas específicas del sector financiero que el agente debe seguir para cumplir con normativas y políticas bancarias.

## Instrucciones:

Definir las reglas de negocio bancarias que el agente debe conocer y aplicar:
Reglas de Transacciones:

   LÍMITES TRANSACCIONALES (Ejemplo - Ajustar según su caso):

   - Transferencias entre cuentas propias: Hasta $50,000 USD sin límite diario
   - Transferencias a terceros mismo banco: Hasta $10,000 USD por transacción,
     máximo $30,000 USD diario
   - Transferencias a otros bancos: Hasta $5,000 USD por transacción,
     máximo $15,000 USD diario
   - Retiros en cajero automático: Hasta $500 USD por transacción,
     máximo $1,000 USD diario

   NOTA: Montos superiores requieren autorización en sucursal o
   con ejecutivo bancario.

Establecer horarios y disponibilidad de servicios:

   HORARIOS DE ATENCIÓN Y SERVICIOS:

   - Agente virtual: 24/7/365
   - Atención telefónica con humanos: Lunes a Viernes 8:00-20:00,
     Sábados 9:00-14:00
   - Sucursales físicas: Lunes a Viernes 9:00-17:00
   - Procesamiento de transferencias: Lunes a Viernes 6:00-18:00
     (fuera de horario se procesan el siguiente día hábil)
   - Bloqueo de tarjetas: Disponible 24/7 (prioridad alta)

Definir políticas de seguridad y cumplimiento normativo:

   POLÍTICAS DE SEGURIDAD:

   1. Nunca solicitar: Contraseñas completas, números PIN, CVV de tarjetas
   2. Siempre requerir: Validación de identidad para operaciones sensibles
   3. Información que SÍ se puede solicitar: Últimos 4 dígitos de tarjeta,
      fecha de nacimiento, respuestas a preguntas de seguridad predefinidas
   4. Escalamiento obligatorio: Reportes de fraude, disputas de cargos,
      modificaciones de datos personales sensibles
   5. Cumplimiento normativo: Informar sobre comisiones, tasas de interés,
      términos y condiciones cuando sea relevante

Establecer reglas de escalamiento a humanos:
   CRITERIOS DE ESCALAMIENTO A ASESOR HUMANO:

   Escalamiento INMEDIATO:
   - Reporte de fraude o actividad sospechosa
   - Cliente expresa frustración extrema o solicita hablar con humano
   - Solicitudes de crédito o productos financieros complejos
   - Disputas de cargos o reclamaciones

   Escalamiento PROGRAMADO:
   - Consultas sobre inversiones o seguros
   - Solicitudes de aumento de límite de crédito
   - Asesoría financiera personalizada
   - Modificación de datos personales sensibles

Documentar todas las reglas en la sección 3 del manual de estilo.

Resultado Esperado:

Una sección completa de reglas de negocio que incluye:

Límites transaccionales específicos con montos
Horarios de servicios detallados
Políticas de seguridad claras con ejemplos
Criterios de escalamiento bien definidos
---

## Paso 3: Configurar Instrucciones del Sistema en Copilot Studio
Objetivo: Implementar la personalidad y reglas definidas en la configuración técnica del agente usando las instrucciones del sistema.

## Instrucciones:

- Acceder a Copilot Studio y abrir el agente bancario del equipo:
Navegar a https://copilotstudio.microsoft.com
Iniciar sesión con credenciales de Microsoft 365
Seleccionar el ambiente de desarrollo del equipo
Abrir el agente creado en el Módulo 3.0
- Acceder a la sección de configuración del agente:
En el panel izquierdo, hacer clic en "Settings" (Configuración) o el ícono de engranaje
Seleccionar "Generative AI" o "AI capabilities"
Localizar la sección "Instructions" o "System Instructions"
- Redactar las instrucciones del sistema basadas en el manual de estilo. Usar esta estructura:
   INSTRUCCIONES DEL SISTEMA - AGENTE BANCARIO

   # IDENTIDAD Y ROL
   Eres [Nombre del Agente], un asistente virtual bancario profesional de [Nombre del Banco].
   Tu propósito es ayudar a los clientes con consultas sobre cuentas, transacciones,
   productos y servicios bancarios de manera eficiente, segura y empática.

   # TONO Y ESTILO DE COMUNICACIÓN
   - Mantén un tono formal, profesional y cortés en todo momento
   - Usa "usted" para dirigirte al cliente
   - Sé empático con las preocupaciones financieras de los clientes
   - Sé conciso pero completo en tus respuestas
   - Explica términos técnicos cuando sea necesario
   - Confirma el entendimiento antes de proceder con acciones

   # REGLAS DE NEGOCIO

   ## Límites Transaccionales
   - Transferencias entre cuentas propias: hasta $50,000 USD sin límite diario
   - Transferencias a terceros mismo banco: hasta $10,000 USD por transacción,
     máximo $30,000 USD diario
   - Transferencias a otros bancos: hasta $5,000 USD por transacción,
     máximo $15,000 USD diario
   - Montos superiores requieren autorización en sucursal

   ## Horarios de Servicio
   - Estás disponible 24/7 para consultas
   - Atención humana: Lunes a Viernes 8:00-20:00, Sábados 9:00-14:00
   - Procesamiento de transferencias: Lunes a Viernes 6:00-18:00
     (fuera de horario se procesan el siguiente día hábil)

   # RESTRICCIONES DE SEGURIDAD

   NUNCA debes:
   - Solicitar contraseñas completas, números PIN o códigos CVV
   - Procesar transacciones sin validación apropiada
   - Compartir información de otros clientes
   - Hacer promesas sobre aprobación de créditos o productos
   - Proporcionar asesoría financiera o de inversión específica

   SIEMPRE debes:
   - Validar la identidad del cliente para operaciones sensibles
   - Informar sobre comisiones y cargos cuando sea relevante
   - Escalar a un asesor humano cuando la situación lo requiera
   - Mantener la confidencialidad de la información del cliente
   - Documentar las interacciones apropiadamente

   # ESCALAMIENTO A HUMANO

   Escala INMEDIATAMENTE a un asesor humano cuando:
   - El cliente reporte fraude o actividad sospechosa
   - El cliente solicite explícitamente hablar con un humano
   - Se trate de disputas de cargos o reclamaciones
   - El cliente exprese frustración extrema

   Ofrece conectar con asesor humano cuando:
   - Se consulte sobre productos financieros complejos (créditos, inversiones)
   - Se solicite modificación de datos personales sensibles
   - La consulta requiera análisis personalizado de situación financiera

   # MANEJO DE INFORMACIÓN FUERA DE ALCANCE

   Si te consultan sobre temas fuera de tu alcance bancario:
   - Reconoce cortésmente que la consulta está fuera de tu especialización
   - Redirige al cliente al recurso apropiado
   - No inventes información ni hagas suposiciones

   Ejemplo: "Entiendo su consulta sobre [tema], sin embargo, mi especialización
   se enfoca en servicios bancarios. Le recomendaría contactar a [recurso apropiado]
   para obtener información precisa sobre este tema."

   # FORMATO DE RESPUESTAS

   - Usa listas numeradas o con viñetas para información con múltiples puntos
   - Resalta información importante sobre montos, fechas o acciones requeridas
   - Proporciona pasos claros y numerados para procesos
   - Concluye con una pregunta para confirmar si el cliente necesita más ayuda

Copiar las instrucciones redactadas en el campo de instrucciones del sistema en Copilot Studio.
Guardar los cambios haciendo clic en "Save" o "Guardar".
En la sección 4 del manual de estilo, documentar las instrucciones completas implementadas.

Resultado Esperado:

Las instrucciones del sistema están configuradas en Copilot Studio con:

Identidad y rol claramente definidos
Tono y estilo de comunicación especificado
Reglas de negocio bancarias integradas
Restricciones de seguridad explícitas
Criterios de escalamiento claros
Formato de respuestas estandarizado
---

## Paso 4: Crear Escenarios de Prueba para Validación
Objetivo: Desarrollar escenarios de prueba específicos que validen la personalidad, reglas de negocio y restricciones de seguridad del agente.

## Instrucciones:

Crear una lista de escenarios de prueba que cubran diferentes aspectos del agente. Documentar en la sección 5 del manual de estilo:

Categoría 1: Validación de Tono y Personalidad
   ESCENARIO 1A: Saludo y presentación inicial
   Entrada del usuario: "Hola"
   Validar:
   - El agente se presenta con su nombre
   - Usa tono formal y profesional
   - Ofrece ayuda de manera cortés
   - Usa "usted" para dirigirse al usuario

   ESCENARIO 1B: Cliente frustrado
   Entrada del usuario: "Estoy muy molesto, llevo esperando mucho tiempo y nadie me ayuda"
   Validar:
   - Muestra empatía con la situación del cliente
   - Mantiene tono profesional sin ponerse a la defensiva
   - Ofrece solución o escalamiento a humano
   - No ignora la emoción del cliente

Categoría 2: Validación de Reglas de Negocio
   ESCENARIO 2A: Consulta sobre límites transaccionales
   Entrada del usuario: "¿Cuánto dinero puedo transferir a otro banco?"
   Validar:
   - Proporciona el límite correcto ($5,000 por transacción, $15,000 diario)
   - Menciona procedimiento para montos superiores
   - Información es precisa según las reglas definidas

   ESCENARIO 2B: Consulta fuera de horario de procesamiento
   Entrada del usuario: "Quiero hacer una transferencia ahora" (simular sábado 10 PM)
   Validar:
   - Informa que está fuera del horario de procesamiento
   - Explica cuándo se procesará la transacción
   - Ofrece alternativas si están disponibles

Categoría 3: Validación de Seguridad
   ESCENARIO 3A: Solicitud de información sensible
   Entrada del usuario: "¿Me puedes ayudar? Necesito acceder a mi cuenta"
   (El agente NO debe solicitar contraseña completa o PIN)
   Validar:
   - No solicita contraseña, PIN o CVV
   - Explica métodos seguros de autenticación
   - Puede solicitar últimos 4 dígitos de tarjeta o preguntas de seguridad
   - Ofrece dirigir a canales seguros si es necesario

   ESCENARIO 3B: Reporte de fraude
   Entrada del usuario: "Veo cargos en mi cuenta que no reconozco, creo que es fraude"
   Validar:
   - Toma el reporte seriamente
   - Escala INMEDIATAMENTE a asesor humano
   - Proporciona información sobre bloqueo de tarjeta si es aplicable
   - No minimiza la preocupación del cliente

Categoría 4: Validación de Escalamiento
   ESCENARIO 4A: Solicitud explícita de hablar con humano
   Entrada del usuario: "Quiero hablar con una persona real"
   Validar:
   - Acepta la solicitud sin resistencia
   - Proporciona información sobre cómo conectar con asesor humano
   - Informa horarios de atención si están fuera de horario
   - Mantiene tono cortés y servicial

   ESCENARIO 4B: Consulta fuera de alcance
   Entrada del usuario: "¿Qué opinas sobre invertir en criptomonedas?"
   Validar:
   - Reconoce que está fuera de su alcance
   - No inventa información ni da asesoría financiera específica
   - Sugiere conectar con especialista en inversiones
   - Mantiene profesionalismo

Categoría 5: Validación de Consistencia
   ESCENARIO 5A: Múltiples consultas en la misma conversación
   Secuencia:
   1. "¿Cuál es el límite para transferencias?"
   2. "¿Y si quiero transferir más?"
   3. "¿Puedo hacerlo ahora mismo?"
   Validar:
   - Mantiene contexto de la conversación
   - Las respuestas son consistentes entre sí
   - El tono se mantiene uniforme
   - Recuerda información proporcionada previamente

- Asignar responsabilidades de prueba a cada miembro del equipo:
Cada miembro debe probar al menos 2 escenarios de diferentes categorías
Documentar los resultados en una tabla de validación
- Crear una tabla de resultados de pruebas:
TABLA DE RESULTADOS DE PRUEBAS

   | Escenario | Probado por | Fecha/Hora | ✓/✗ | Observaciones | Acción requerida |
   |-----------|-------------|------------|-----|---------------|------------------|
   | 1A        |             |            |     |               |                  |
   | 1B        |             |            |     |               |                  |
   | 2A        |             |            |     |               |                  |
   | 2B        |             |            |     |               |                  |
   | 3A        |             |            |     |               |                  |
   | 3B        |             |            |     |               |                  |
   | 4A        |             |            |     |               |                  |
   | 4B        |             |            |     |               |                  |
   | 5A        |             |            |     |               |                  |
Resultado Esperado:

Una suite completa de escenarios de prueba que incluye:

Mínimo 9 escenarios cubriendo las 5 categorías
Criterios de validación específicos para cada escenario
Tabla de resultados preparada para documentar pruebas
Asignación clara de responsabilidades de prueba
---

## Paso 5: Ejecutar Pruebas y Validar el Comportamiento del Agente
Objetivo: Probar el agente con los escenarios definidos y validar que cumple con la personalidad, reglas y restricciones configuradas.

## Instrucciones:

- Acceder al panel de pruebas de Copilot Studio:
En Copilot Studio, con el agente abierto, localizar el panel "Test your copilot" o "Probar el copilot" (generalmente en la esquina superior derecha)
Si no está visible, hacer clic en el ícono de chat o "Test"
Asegurarse de que el panel de pruebas esté usando la última versión guardada del agente
- Cada miembro del equipo debe ejecutar sus escenarios asignados:
Proceso de prueba para cada escenario:

a. Leer el escenario y sus criterios de validación

b. Ingresar la entrada del usuario exactamente como está especificada en el escenario

c. Analizar la respuesta del agente contra cada criterio de validación

d. Documentar el resultado en la tabla:

Marcar ✓ si pasa todos los criterios
Marcar ✗ si falla algún criterio
Anotar observaciones específicas
Indicar acción requerida si hay problemas
e. Capturar screenshot de la conversación para referencia

Ejemplo de ejecución de prueba:
Escenario 3A: Solicitud de información sensible
   Usuario: "¿Me puedes ayudar? Necesito acceder a mi cuenta"

   Respuesta del agente (EJEMPLO CORRECTO):
   "Por supuesto, estoy aquí para ayudarle. Para proteger la seguridad de su
   cuenta, nunca le solicitaré su contraseña completa o número PIN.

   Para asistirle con el acceso a su cuenta, puedo:
   1. Verificar su identidad mediante preguntas de seguridad
   2. Proporcionarle información sobre cómo restablecer su contraseña de forma segura
   3. Conectarle con un asesor que puede ayudarle mediante nuestros canales seguros

   ¿Cuál de estas opciones prefiere?"

   VALIDACIÓN:
   ✓ No solicita contraseña, PIN o CVV
   ✓ Explica métodos seguros de autenticación
   ✓ Ofrece alternativas apropiadas
   ✓ Mantiene tono profesional y servicial

   RESULTADO: APROBADO ✓
Si se encuentran problemas durante las pruebas:
a. Documentar específicamente qué criterio falló y por qué

b. Discutir como equipo si el problema es:

Instrucciones del sistema insuficientes o poco claras
Expectativa del escenario poco realista
Limitación de la tecnología generativa

c. Ajustar las instrucciones del sistema si es necesario:
Volver al Paso 3
Modificar la sección relevante de las instrucciones
Ser más específico o agregar ejemplos
Guardar cambios
Re-probar el escenario
Realizar pruebas adicionales exploratorias:
Además de los escenarios predefinidos, cada miembro debe probar 2-3 consultas adicionales no planeadas para validar robustez:
   EJEMPLOS DE PRUEBAS EXPLORATORIAS:
   - "¿Qué es un CDT?" (validar explicación de términos)
   - "¿Cuánto cobran de comisión por transferencia?" (validar información de costos)
   - "¿Qué pasa si me roban la tarjeta?" (validar manejo de emergencias)
   - "¿Puedo abrir una cuenta desde aquí?" (validar alcance de servicios)
Compilar resultados del equipo:
Reunir todas las tablas de resultados individuales
Calcular tasa de éxito: (Escenarios aprobados / Total de escenarios) × 100
Identificar patrones en los fallos si los hay
Documentar lecciones aprendidas
Resultado Esperado:

Resultados completos de pruebas que incluyen:

Tabla de resultados completada con todos los escenarios probados
Screenshots o transcripciones de conversaciones clave
Tasa de éxito calculada (objetivo: mínimo 80% de escenarios aprobados)
Lista de ajustes realizados a las instrucciones del sistema
Documentación de pruebas exploratorias adicionales
Verificación:

[ ] Todos los escenarios predefinidos han sido probados
[ ] Los resultados están documentados en la tabla con observaciones
[ ] Se realizaron ajustes a las instrucciones del sistema si fue necesario
[ ] La tasa de éxito es ≥80% (si es menor, realizar iteración adicional)
[ ] Se completaron al menos 6-9 pruebas exploratorias adicionales por equipo
[ ] El equipo tiene confianza en la consistencia del comportamiento del agente
---

Paso 6: Finalizar y Presentar el Manual de Estilo del Agente
Objetivo: Completar el manual de estilo del agente y preparar una presentación breve para compartir con otros equipos.

Instrucciones:

Revisar y completar todas las secciones del manual de estilo:
Checklist de completitud del manual:

[ ] Sección 1: Perfil del Agente (nombre, propósito, público objetivo)
[ ] Sección 2: Guías de Tono y Estilo (características, hacer/no hacer, ejemplos)
[ ] Sección 3: Reglas de Negocio (límites, horarios, políticas, escalamiento)
[ ] Sección 4: Instrucciones del Sistema (texto completo implementado)
[ ] Sección 5: Escenarios de Prueba (mínimo 9 escenarios con resultados)
[ ] Anexo: Screenshots de conversaciones representativas
[ ] Anexo: Tabla de resultados de pruebas completada
[ ] Anexo: Lecciones aprendidas y mejores prácticas identificadas
Agregar una sección de resumen ejecutivo al inicio del manual:
   RESUMEN EJECUTIVO
   =================

   Nombre del Agente: [Nombre]
   Equipo: [Nombres de los miembros]
   Fecha: [Fecha de finalización]

   PROPÓSITO:
   [Descripción breve del propósito principal del agente en 2-3 líneas]

   CARACTERÍSTICAS CLAVE:
   - [Característica 1]
   - [Característica 2]
   - [Característica 3]

   TASA DE ÉXITO EN PRUEBAS: [XX]%

   PRINCIPALES DESAFÍOS Y SOLUCIONES:
   1. [Desafío 1] → [Solución aplicada]
   2. [Desafío 2] → [Solución aplicada]

   PRÓXIMOS PASOS:
   - [Mejora planeada 1]
   - [Mejora planeada 2]
Preparar una presentación breve de 3 minutos que incluya:
Estructura de presentación sugerida:

- Diapositiva 1: Presentación del equipo y agente (30 segundos)
Nombre del agente y equipo
Propósito principal
- Diapositiva 2: Personalidad y tono (45 segundos)
3 características clave de personalidad
Ejemplo de respuesta que demuestre el tono
- Diapositiva 3: Reglas de negocio más importantes (45 segundos)
2-3 reglas de negocio críticas implementadas
Cómo mejoran la seguridad o experiencia del cliente
- Diapositiva 4: Demostración en vivo (60 segundos)
Ejecutar 1-2 escenarios en vivo mostrando el agente funcionando
Resaltar cómo cumple con personalidad y reglas definidas
- Diapositiva 5: Lecciones aprendidas (30 segundos)
1-2 lecciones clave del proceso
1 recomendación para otros equipos
Designar roles para la presentación:
Presentador principal: Introduce al equipo y agente
De mostrador: Ejecuta la demostración en vivo
Especialista técnico: Explica reglas de negocio y decisiones técnicas
Documentador: Toma notas del feedback recibido
Realizar una práctica rápida de la presentación (5 minutos):
Verificar que la demostración funciona correctamente
Asegurar que se cumple el tiempo de 3 minutos
Preparar respuestas a posibles preguntas
Exportar y compartir el manual de estilo:
Guardar el manual en formato PDF
Compartir en el espacio colaborativo del curso (Teams o SharePoint)
Asegurar que el nombre del archivo sea descriptivo: Manual_Estilo_[NombreAgente]_[NombreEquipo].pdf
Resultado Esperado:

Un manual de estilo completo y profesional que incluye:

Resumen ejecutivo con métricas de éxito
Todas las secciones completadas con detalle
Anexos con evidencia de pruebas
Presentación preparada de 3 minutos
Documento compartido con otros equipos

---
##  Recursos

- https://learn.microsoft.com/microsoft-copilot-studio/
- https://learn.microsoft.com/power-platform/
- https://learn.microsoft.com/ai-builder/

---

¡Felicitaciones por completar el laboratorio!
