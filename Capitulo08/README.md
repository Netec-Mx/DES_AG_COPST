
# Añade capacidades de voz o visión 

---

## Descripción General

En esta actividad grupal de fin de módulo, los equipos implementarán capacidades avanzadas de IA multimodal en su agente bancario, incluyendo entrada y salida de voz, y procesamiento inteligente de documentos. Los participantes configurarán funcionalidades de speech-to-text y text-to-speech para crear experiencias conversacionales naturales, y utilizarán AI Builder para extraer automáticamente información estructurada de documentos bancarios como DNI, recibos de sueldo y formularios. Esta actividad integra múltiples modalidades de interacción para crear una experiencia bancaria completa y accesible.

---

## Objetivos de Aprendizaje

Al completar este laboratorio, serás capaz de:

- Configurar capacidades de entrada y salida de voz en el agente utilizando Azure Speech Services
- Implementar modelos de AI Builder para reconocimiento y procesamiento de documentos
- Integrar procesamiento de documentos con flujos del agente bancario
- Extraer información estructurada de documentos bancarios (DNI, recibos, formularios)
- Crear experiencias multimodales combinando texto, voz y documentos
- Manejar niveles de confianza en las extracciones de AI Builder
- Validar y corregir datos extraídos automáticamente

---

## Prerrequisitos

Conocimientos Requeridos
- Completar exitosamente el Módulo 7.0 (Bases de conocimiento con SharePoint)
- Comprensión de flujos de trabajo en Copilot Studio
- Conocimiento básico de Power Automate
- Familiaridad con conceptos de machine learning y confianza de predicciones

---

## Acceso Requerido
- Cuenta de Microsoft 365 con licencia activa
- Acceso a Microsoft Copilot Studio con permisos de edición
- Acceso a AI Builder con créditos disponibles (mínimo 1,000 créditos)
- Acceso a Power Automate
- Permisos para crear y modificar flujos
- Documentos de ejemplo para entrenar modelos (DNI, recibos de sueldo, formularios bancarios)

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

Preparación del Equipo:

Cada equipo debe designar roles:

- Líder de Integración: Coordina las actividades y tiempos
- Especialista en Voz: Configura capacidades de speech
- Especialista en Documentos: Implementa AI Builder
- Tester: Valida funcionalidades y documenta resultados

Materiales Necesarios:

Descargar el paquete de documentos de ejemplo desde el repositorio del curso:

5 ejemplos de DNI (ficticios)
5 ejemplos de recibos de sueldo (ficticios)
3 ejemplos de formularios de solicitud de préstamo
⚠️ Importante: Utilizar ÚNICAMENTE datos ficticios. Nunca usar documentos reales con información personal.

---

##  Desarrollo del Laboratorio

## Paso 1: Configurar Entrada de Voz (Speech-to-Text)
Objetivo: Habilitar la capacidad de que los usuarios interactúen con el agente mediante voz.

## Instrucciones:

- Accede a tu agente bancario en Microsoft Copilot Studio
- En el panel izquierdo, selecciona "Configuración" (Settings) > "Canales" (Channels)
- Localiza la sección "Capacidades de Voz" (Voice Capabilities)
- Activa el interruptor "Habilitar entrada de voz" (Enable voice input)
- Configura los parámetros de voz:
-- Idioma principal: Español (España) o Español (México)
-- Idioma alternativo: Español (Latinoamérica)
-- Nivel de ruido: Medio
-- Timeout de silencio: 3 segundos
- En la sección "Configuración avanzada", habilita:
✅ Detección automática de fin de frase
✅ Filtro de palabras de relleno (eh, mm, este)
✅ Normalización de números y fechas
- Haz clic en "Guardar" para aplicar los cambios
- Crea un nuevo tema llamado "Prueba de Voz" para validar la funcionalidad:
-- Trigger: "quiero probar la voz"
-- Agrega un nodo de mensaje: "Perfecto, puedes hablarme ahora. ¿Cuál es tu consulta?"
-- Agrega un nodo de pregunta que capture la respuesta en una variable {consultaVoz}
-- Agrega un nodo de mensaje: "Entendí: {consultaVoz}"

Salida Esperada:

Al publicar y probar en el panel de prueba, deberías ver un icono de micrófono que permite grabar audio.

Verificación:

- El icono de micrófono aparece en la interfaz de chat
- Al hacer clic, el agente comienza a escuchar
- El texto transcrito aparece correctamente en español
- Los números y fechas se normalizan correctamente
---

## Paso 2: Configurar Salida de Voz (Text-to-Speech)
Objetivo: Permitir que el agente responda con voz sintetizada para crear una experiencia más natural.

## Instrucciones:

1. En "Configuración" > "Canales", localiza "Salida de Voz" (Voice Output)
2. Activa el interruptor "Habilitar salida de voz" (Enable voice output)
3. Configura la voz del agente:
- Voz: Selecciona "es-MX-DaliaNeural" (femenina) o "es-MX-JorgeNeural" (masculina)
- Velocidad: 1.0x (normal)
- Tono: 0 (neutro)
- Volumen: 100%
4. Configura cuándo usar voz:
✅ Respuestas principales del agente
✅ Mensajes de confirmación
⬜ Mensajes de error (opcional, mantener solo texto)
5. En "Configuración avanzada de voz":
- Habilita "Énfasis en palabras clave"
- Habilita "Pausas naturales"
- Configura "Estilo de habla": Amigable y profesional
6. Modifica el tema "Prueba de Voz" creado anteriormente:
- Agrega la etiqueta [SPEAK] al inicio de los mensajes que deseas que se lean en voz alta
- Ejemplo: [SPEAK] Perfecto, puedo escucharte ahora. ¿Cuál es tu consulta?
- Guarda los cambios y publica el agente

Salida Esperada:

Las respuestas del agente deben reproducirse automáticamente en audio con la voz seleccionada.

Verificación:

- Los mensajes marcados con [SPEAK] se reproducen en audio
- La voz es clara y en español
- La velocidad y tono son apropiados
- Aparece un control de reproducción en cada mensaje con audio
---

## Paso 3: Crear Modelo de AI Builder para Extracción de DNI
Objetivo: Entrenar un modelo personalizado para extraer datos estructurados de documentos de identidad.

## Instrucciones:

1. Abre una nueva pestaña y navega a https://make.powerapps.com
2. En el panel izquierdo, selecciona "AI Builder" > "Crear"
3. Selecciona el tipo de modelo "Procesamiento de documentos" (Document Processing)
4. Elige "Modelo personalizado" y haz clic en "Crear"
5. Nombra el modelo: "Extractor DNI Bancario"
6. Define los campos a extraer:
- Haz clic en "Agregar campo"
- Campo 1: nombreCompleto (tipo: Texto)
- Campo 2: numeroDocumento (tipo: Texto)
- Campo 3: fechaNacimiento (tipo: Fecha)
- Campo 4: nacionalidad (tipo: Texto)
- Campo 5: fechaEmision (tipo: Fecha)
7. Haz clic en "Siguiente" para pasar a la fase de entrenamiento
8. Sube los 5 documentos de ejemplo de DNI:
- Haz clic en "Agregar documentos"
- Selecciona los archivos de DNI ficticios
- Espera a que se procesen
9. Etiqueta los campos en cada documento:
- Selecciona el primer documento
- Dibuja un rectángulo alrededor del nombre completo
- Asigna al campo nombreCompleto
- Repite para cada campo en cada documento
- Importante: Etiqueta al menos 5 ejemplos de cada campo
10. Una vez etiquetados todos los documentos, haz clic en "Entrenar"
11. Espera de 5-10 minutos mientras el modelo se entrena

Salida Esperada:

Estado del modelo: Entrenamiento completado
Precisión general: 85-95%
Campos entrenados: 5/5
Documentos de entrenamiento: 5

Verificación:

- El modelo muestra estado "Entrenado"
- La precisión es superior al 80% para cada campo
- Todos los campos están correctamente identificados
- El modelo está listo para publicar
---

## Paso 4: Publicar y Probar el Modelo de AI Builder
Objetivo: Hacer el modelo disponible para uso en flujos y validar su funcionamiento.

## Instrucciones:

1. En la página del modelo entrenado, haz clic en "Publicar"
2. Confirma la publicación haciendo clic en "Publicar" nuevamente
3. Espera la confirmación: "Modelo publicado correctamente"
4. Haz clic en "Prueba rápida" (Quick test)
5. Sube un documento de DNI que NO hayas usado en el entrenamiento
6. Observa los resultados de la extracción:
- Revisa cada campo extraído
- Verifica el nivel de confianza (confidence score)
- Confirma que los datos son correctos
7. Anota el ID del modelo (lo necesitarás en el siguiente paso):
- Aparece en la URL o en la sección "Detalles del modelo"
- Formato: /providers/Microsoft.PowerApps/models/[ID]
8. Verifica el consumo de créditos:
- Navega a "AI Builder" > "Uso"
- Confirma que tienes créditos suficientes restantes

Salida Esperada:

Extracción completada:
- Nombre Completo: "María Fernanda González López" (Confianza: 98%)
- Número Documento: "12345678A" (Confianza: 99%)
- Fecha Nacimiento: "15/03/1985" (Confianza: 95%)
- Nacionalidad: "Mexicana" (Confianza: 97%)
- Fecha Emisión: "10/01/2020" (Confianza: 94%)

Verificación:

- El modelo extrae correctamente todos los campos
- Los niveles de confianza son superiores al 85%
- El formato de las fechas es correcto
- No hay errores de extracción evidentes
---

## Paso 5: Crear Flujo de Power Automate para Procesamiento de Documentos
Objetivo: Integrar el modelo de AI Builder con el agente mediante un flujo automatizado.

## Instrucciones:

1. En Copilot Studio, con tu agente abierto, navega a "Temas" > "Agregar tema"
2. Nombra el nuevo tema: "Verificación de Identidad con DNI"
3. Agrega triggers:
- "necesito verificar mi identidad"
- "quiero subir mi DNI"
- "verificación de documento"
4. En el flujo del tema, agrega un nodo de "Mensaje":

   Para verificar tu identidad, necesito que subas una foto o escaneo de tu DNI.
   Asegúrate de que todos los datos sean legibles.

5. Agrega un nodo de "Pregunta" configurado como:
- Tipo: Archivo adjunto
- Variable: {archivoDocumento}
- Formatos permitidos: JPG, PNG, PDF
- Tamaño máximo: 5 MB

6. Agrega un nodo "Llamar una acción" > "Crear un flujo"
7. Se abrirá Power Automate. Configura el flujo:
Trigger:

- Tipo: "Power Virtual Agents"
- Entrada: DocumentoBase64 (texto)

Acción 1: Extraer información con AI Builder

- Busca: "Predecir" (AI Builder)
- Selecciona: "Predecir con modelo de procesamiento de documentos"
- Modelo: Selecciona "Extractor DNI Bancario"
- Contenido del documento: {DocumentoBase64}

Acción 2: Condición - Verificar confianza

- Condición: outputs('Predecir')?['body/confidence'] mayor que 0.85
- Si es verdadero:

Acción: "Devolver valores a Power Virtual Agents"
Valores a devolver:
     nombreExtraido: outputs('Predecir')?['body/fields/nombreCompleto/value']
     documentoExtraido: outputs('Predecir')?['body/fields/numeroDocumento/value']
     fechaNacimientoExtraida: outputs('Predecir')?['body/fields/fechaNacimiento/value']
     confianzaExtraccion: outputs('Predecir')?['body/confidence']
     estadoVerificacion: "Exitoso"

Si es falso:

- Acción: "Devolver valores a Power Virtual Agents"
- Valores a devolver:

     estadoVerificacion: "Confianza insuficiente"
     confianzaExtraccion: outputs('Predecir')?['body/confidence']

- Guarda el flujo con el nombre: "Procesar DNI con AI Builder"
- Regresa a Copilot Studio y actualiza la lista de flujos

Salida Esperada:

El flujo aparece disponible en la lista de acciones del agente.

Verificación:

- El flujo se guarda sin errores
- Aparece en la lista de acciones de Copilot Studio
- Las variables de entrada y salida están correctamente definidas
- La lógica de confianza funciona correctamente
---

## Paso 6: Integrar el Flujo en el Tema del Agente
Objetivo: Conectar el flujo de procesamiento con el tema para crear una experiencia completa.

## Instrucciones:

1. En el tema "Verificación de Identidad con DNI", después del nodo de pregunta de archivo
2. Agrega un nodo "Llamar una acción"
3. Selecciona el flujo "Procesar DNI con AI Builder"
4. Mapea la entrada:
  DocumentoBase64 = {archivoDocumento.content}
5. Captura las salidas en variables:
- {nombreExtraido}
- {documentoExtraido}
- {fechaNacimientoExtraida}
- {confianzaExtraccion}
- {estadoVerificacion}
6. Agrega un nodo "Condición":
- Si {estadoVerificacion} es igual a "Exitoso"
7. Rama Verdadera (Éxito):
- Nodo de mensaje:

     Documento verificado exitosamente

     He extraído la siguiente información:
     - Nombre: {nombreExtraido}
     - Número de documento: {documentoExtraido}
     - Fecha de nacimiento: {fechaNacimientoExtraida}
     - Nivel de confianza: {confianzaExtraccion}%

     ¿Es correcta esta información?

- Nodo de pregunta (Sí/No): Variable {confirmacionDatos}
- Si confirma: "Perfecto, tu identidad ha sido verificada. ¿En qué más puedo ayudarte?"
- Si no confirma: "Por favor, intenta subir el documento nuevamente asegurándote de que esté bien iluminado y enfocado."

8. Rama Falsa (Confianza insuficiente):
Nodo de mensaje:

     No pude procesar el documento con suficiente confianza.
     Nivel de confianza: {confianzaExtraccion}%

     Por favor, intenta nuevamente asegurándote de que:
     - La imagen esté bien iluminada
     - Todos los datos sean legibles
     - El documento esté completo en la foto

     ¿Quieres intentar de nuevo?

Guarda el tema

Salida Esperada:

Un flujo conversacional completo que procesa documentos y maneja diferentes escenarios.

Verificación:

- El flujo se ejecuta sin errores
- Los datos extraídos se muestran correctamente
- La lógica de confirmación funciona
- Los mensajes de error son claros
---

## Paso 7: Implementar Procesamiento de Recibos de Sueldo
Objetivo: Crear un segundo modelo de AI Builder para validar ingresos mediante recibos de sueldo.

## Instrucciones:

- Regresa a AI Builder en https://make.powerapps.com
- Crea un nuevo modelo de "Procesamiento de documentos"
- Nombra el modelo: "Extractor Recibos Sueldo"
- Define los campos a extraer:
-- nombreEmpleado (Texto)
-- empresaEmpleadora (Texto)
-- salarioBruto (Número)
-- salarioNeto (Número)
-- periodoInicio (Fecha)
-- periodoFin (Fecha)

- Sube los 5 ejemplos de recibos de sueldo ficticios
- Etiqueta cuidadosamente cada campo en cada documento
- Entrena el modelo (5-10 minutos de espera)
- Publica el modelo una vez entrenado
- Realiza una prueba rápida con un recibo no usado en entrenamiento
- Crea un nuevo tema en Copilot Studio: "Validación de Ingresos"
Configura triggers:
  "necesito validar mis ingresos"
  "subir recibo de sueldo"
  "comprobante de ingresos"
Crea un flujo similar al del DNI pero usando el modelo de recibos:
- Nombre del flujo: "Procesar Recibo Sueldo"
- Misma estructura pero con los campos de recibos
- Validación adicional: verificar que salarioBruto > salarioNeto

Integra el flujo en el tema con mensajes apropiados:

    Recibo procesado correctamente

    Información detectada:
    - Empleado: {nombreEmpleado}
    - Empresa: {empresaEmpleadora}
    - Salario Bruto: ${salarioBruto}
    - Salario Neto: ${salarioNeto}
    - Período: {periodoInicio} - {periodoFin}

    Basado en tus ingresos, puedes calificar para préstamos de hasta ${salarioNeto * 5}

Salida Esperada:

Un segundo flujo de procesamiento de documentos completamente funcional para recibos de sueldo.

Verificación:

- El modelo de recibos tiene precisión > 80%
- Los campos numéricos se extraen correctamente
- Las fechas se interpretan bien
- El cálculo de préstamo elegible funciona
---

## Paso 8: Crear Experiencia Multimodal Completa
Objetivo: Combinar voz, texto y documentos en un flujo de solicitud de préstamo completo.

## Instrucciones:

Crea un nuevo tema: "Solicitud de Préstamo Multimodal"
Agrega triggers:
"quiero solicitar un préstamo"
"necesito un crédito"
"solicitar financiamiento"
Diseña el flujo conversacional completo:
Paso 1: Bienvenida con voz

   [SPEAK] Bienvenido al proceso de solicitud de préstamo.
   Voy a guiarte paso a paso. Puedes responderme por voz o por texto,
   como prefieras.

Paso 2: Recopilar información básica (por voz o texto)

Pregunta: "¿Cuál es el monto que necesitas?" → {montoPrestamo}
Pregunta: "¿Para qué necesitas el préstamo?" → {proposito}
Pregunta: "¿En cuántos meses deseas pagarlo?" → {plazoMeses}

Paso 3: Validación de identidad

Mensaje: [SPEAK] Ahora necesito verificar tu identidad. Por favor, sube una foto de tu DNI.
Llamar al flujo de DNI
Validar resultado

Paso 4: Validación de ingresos

Mensaje: [SPEAK] Perfecto. Ahora necesito validar tus ingresos. Sube tu último recibo de sueldo.
Llamar al flujo de Recibos
Validar resultado
Paso 5: Evaluación automática

Crear una variable {capacidadPago} = {salarioNeto} * 0.30
Condición: Si {montoPrestamo} / {plazoMeses} <= {capacidadPago}
Si aprueba:

   [SPEAK] ¡Excelentes noticias! Tu solicitud ha sido pre-aprobada.

   Resumen de tu solicitud:
   - Monto: ${montoPrestamo}
   - Plazo: {plazoMeses} meses
   - Cuota mensual estimada: ${montoPrestamo / plazoMeses}
   - Tasa de interés: 12% anual

   Un ejecutivo se contactará contigo en las próximas 24 horas para finalizar el proceso.
Si no aprueba:

   [SPEAK] Lamentablemente, según tu capacidad de pago actual,
   no podemos aprobar el monto solicitado.

   Basado en tus ingresos de ${salarioNeto}, podemos ofrecerte:
   - Monto máximo: ${capacidadPago * plazoMeses}
   - Plazo: {plazoMeses} meses

   ¿Te gustaría proceder con este monto ajustado?

- Agrega manejo de errores en cada paso
- Guarda y publica el tema
- Salida Esperada:

Un flujo conversacional completo que integra voz, texto y procesamiento de documentos.

Verificación:

- El flujo funciona de inicio a fin
- La voz se reproduce correctamente
- Los documentos se procesan
- Los cálculos son correctos
- Los mensajes son claros y profesionales
---

## Paso 9: Pruebas Integrales del Agente Multimodal
Objetivo: Validar todas las funcionalidades implementadas mediante pruebas exhaustivas.

## Instrucciones:

1. En Copilot Studio, haz clic en "Probar el agente" (panel derecho)
2. Prueba 1: Interacción por voz
- Activa el micrófono
- Di: "Quiero solicitar un préstamo"
- Verifica que el agente responde con voz
- Continúa la conversación por voz

3. Prueba 2: Procesamiento de DNI
- Inicia el flujo de solicitud
- Cuando se solicite el DNI, sube un documento de prueba
- Verifica que los datos se extraen correctamente
- Confirma que el nivel de confianza es adecuado

4. Prueba 3: Procesamiento de recibo de sueldo
- Continúa el flujo
- Sube un recibo de sueldo de prueba
- Verifica la extracción de datos
- Confirma que los cálculos de capacidad de pago son correctos

5. Prueba 4: Flujo completo multimodal
- Inicia una nueva conversación
- Usa voz para las respuestas iniciales
- Sube documentos cuando se soliciten
- Completa todo el proceso hasta obtener una decisión

Prueba 5: Manejo de errores
- Sube un documento borroso o mal iluminado
- Verifica que el agente solicita reintentar
- Sube un documento de tipo incorrecto
- Confirma mensajes de error apropiados

Documenta los resultados en una tabla:
Identifica y documenta cualquier problema encontrado

Prueba	Resultado	Observaciones
Entrada de voz	✅/❌	
Salida de voz	✅/❌	
Extracción DNI	✅/❌	
Extracción recibo	✅/❌	
Flujo completo	✅/❌	
Manejo de errores	✅/❌	

Salida Esperada:

Todas las pruebas deben pasar exitosamente con una tasa de éxito del 80% o superior.

Verificación:

- El agente responde consistentemente
- La voz es clara y natural
- Los documentos se procesan con alta confianza (>85%)
- Los cálculos son precisos
- Los errores se manejan apropiadamente
- La experiencia es fluida y profesional
---

## Paso 10: Optimización y Documentación Final
Objetivo: Refinar el agente y documentar la implementación para referencia futura.

## Instrucciones:

1. Optimizar mensajes de voz:
- Revisa todos los mensajes marcados con [SPEAK]
- Acorta mensajes muy largos (máximo 2-3 oraciones)
- Elimina caracteres especiales que puedan causar problemas de pronunciación
- Agrega pausas naturales con puntos y comas

2. Ajustar umbrales de confianza:
- Analiza los niveles de confianza obtenidos en las pruebas
- Si son consistentemente altos (>95%), puedes mantener el umbral en 85%
- Si son variables, considera aumentar el umbral a 90% para mayor precisión

4. Mejorar manejo de errores:
- Agrega mensajes más específicos para diferentes tipos de errores
- Ejemplo: "El documento parece estar cortado" vs "No puedo leer el documento"
- Implementa un contador de intentos (máximo 3)

5. Crear documentación del equipo:
- Crea un documento con las siguientes secciones:

a) Resumen Ejecutivo

Descripción del agente multimodal
Funcionalidades implementadas
Casos de uso principales
b) Arquitectura Técnica

Diagrama de flujo del proceso completo
Modelos de AI Builder utilizados
Flujos de Power Automate creados
Temas de Copilot Studio implementados
c) Modelos de AI Builder

Nombre y propósito de cada modelo
Campos extraídos
Precisión obtenida
Cantidad de documentos de entrenamiento
d) Configuración de Voz

Voz seleccionada
Parámetros configurados
Temas que usan voz
e) Métricas de Desempeño

Tiempo promedio de procesamiento de documentos
Precisión promedio de extracción
Tasa de éxito en flujo completo
f) Lecciones Aprendidas

Desafíos encontrados
Soluciones implementadas
- Mejoras futuras sugeridas
- Preparar presentación del equipo:
- Crear 3-5 diapositivas resumiendo el trabajo
- Incluir una demo en vivo del flujo completo
- Preparar ejemplos de documentos procesados
- Guarda toda la documentación en el repositorio del equipo

Salida Esperada:

Documentación completa y profesional lista para presentación.

Verificación:

- Documento de arquitectura completo
- Métricas documentadas
- Presentación preparada
- Demo funcional lista
- Lecciones aprendidas documentadas

---
##  Recursos

- https://learn.microsoft.com/microsoft-copilot-studio/
- https://learn.microsoft.com/power-platform/
- https://learn.microsoft.com/ai-builder/

---

¡Felicitaciones por completar el laboratorio!