
# Agrega memoria y tus propios datos

---

## Descripción General

En esta actividad grupal práctica, los equipos implementarán una solución completa de RAG (Retrieval Augmented Generation) conectando su agente bancario de Copilot Studio con documentos corporativos almacenados en SharePoint Online. Los participantes configurarán bases de conocimiento que permitirán al agente proporcionar respuestas contextuales precisas basadas en documentación oficial del banco, incluyendo políticas de crédito, manuales de productos, términos y condiciones, y procedimientos internos. Esta integración permite que el agente responda consultas complejas citando fuentes documentales verificadas, mejorando significativamente la precisión y confiabilidad de las respuestas.


---

## Objetivos de Aprendizaje

Al completar este laboratorio, usted será capaz de:

- Crear y configurar bases de conocimiento en Microsoft Copilot Studio conectadas a fuentes documentales
- Conectar el agente con bibliotecas de documentos de SharePoint Online y configurar la indexación
- Implementar búsqueda semántica sobre documentos corporativos utilizando capacidades de RAG
- Configurar permisos y seguridad para acceso controlado a documentos internos
- Optimizar respuestas del agente basadas en contenido documental y validar citación de fuentes

---

## Prerrequisitos

Conocimiento Requerido

- Comprensión de conceptos básicos de Copilot Studio y creación de agentes de IA
- Familiaridad con SharePoint Online y gestión de bibliotecas de documentos
- Conocimiento de principios básicos de seguridad y permisos en Microsoft 365
- Experiencia con el agente bancario desarrollado en módulos anteriores

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

Cada equipo debe designar roles antes de comenzar:

- Coordinador de SharePoint: Responsable de crear el sitio y gestionar documentos
- Especialista en Copilot Studio: Configura la conexión y fuentes de conocimiento
- Analista de Calidad: Prueba y valida las respuestas del agente
- Documentador: Registra configuraciones y resultados

Verificación de Acceso:
- Confirmar acceso a Copilot Studio: https://copilotstudio.microsoft.com
- Verificar acceso a SharePoint: https://[tenant].sharepoint.com
- Confirmar que el agente bancario del módulo anterior está disponible



---

##  Desarrollo del Laboratorio

## Paso 1: Crear Sitio de SharePoint y Estructura de Documentos
Objetivo: Establecer un sitio de SharePoint dedicado con bibliotecas organizadas para almacenar documentos bancarios que alimentarán la base de conocimiento del agente.

## Instrucciones:

1. Navegue a SharePoint Online en su navegador:

   https://[su-tenant].sharepoint.com

2. Haga clic en "+ Crear sitio" en la página principal de SharePoint.
3. Seleccione "Sitio de equipo" y complete la información:
- Nombre del sitio: Banco Digital - Base de Conocimiento
- Descripción: Documentación corporativa para agente de IA bancario
- Idioma: Español
- Privacidad: Privado (solo miembros pueden acceder)
4. Haga clic en "Siguiente" y agregue a los miembros de su equipo como propietarios o miembros del sitio.
- Una vez creado el sitio, cree las siguientes bibliotecas de documentos:
- En el sitio, haga clic en "+ Nuevo" → "Biblioteca de documentos"
- Cree estas cuatro bibliotecas:
  Políticas de Crédito
  Manuales de Productos
  Términos y Condiciones
  Procedimientos Internos
5. Configure metadatos para las bibliotecas:
- Seleccione cada biblioteca
- Haga clic en el ícono de engranaje (⚙️) → "Configuración de biblioteca"
- En "Columnas", agregue columna personalizada:
  Nombre: Categoría
  Tipo: Opción (menú desplegable)
  Opciones: Créditos, Cuentas, Tarjetas, Inversiones, General

Salida Esperada:

Debe tener un sitio de SharePoint con URL similar a:


https://[tenant].sharepoint.com/sites/BancoDigitalBasedeConocimiento
Y cuatro bibliotecas de documentos visibles en la página principal del sitio.

Verificación:

- El sitio de SharePoint está creado y accesible
- Las cuatro bibliotecas de documentos están visibles
- Todos los miembros del equipo tienen acceso al sitio
- La columna "Categoría" aparece en cada biblioteca
---

## Paso 2: Cargar y Organizar Documentos Bancarios de Ejemplo
Objetivo: Poblar las bibliotecas de SharePoint con documentos bancarios ficticios que servirán como fuente de conocimiento para el agente.

## Instrucciones:

1. Crear documentos de ejemplo (cada equipo debe crear al menos 8-10 documentos):

Documento 1 - Política de Crédito Hipotecario (Word/PDF):
- Biblioteca: Políticas de Crédito
- Contenido sugerido:

     POLÍTICA DE CRÉDITO HIPOTECARIO

     Requisitos generales:
     - Edad mínima: 21 años, máxima: 65 años al final del crédito
     - Ingresos mínimos demostrables: $15,000 MXN mensuales
     - Enganche mínimo: 20% del valor de la propiedad
     - Antigüedad laboral: Mínimo 2 años

     Tasas de interés vigentes:
     - Tasa fija 10 años: 9.5% anual
     - Tasa fija 15 años: 10.2% anual
     - Tasa fija 20 años: 10.8% anual

     Documentación requerida:
     - Identificación oficial vigente
     - Comprobantes de ingresos últimos 3 meses
     - Estados de cuenta bancarios últimos 3 meses
     - Avalúo de la propiedad

2- Documento 2 - Manual de Tarjetas de Crédito (Word/PDF):

Biblioteca: Manuales de Productos
Contenido sugerido:

     MANUAL DE TARJETAS DE CRÉDITO

     Tarjeta Clásica:
     - Línea de crédito: $10,000 - $50,000 MXN
     - Tasa de interés: 45% anual
     - Anualidad: $500 MXN (sin costo primer año)
     - Programa de recompensas: 1 punto por cada $20 MXN

     Tarjeta Oro:
     - Línea de crédito: $50,000 - $150,000 MXN
     - Tasa de interés: 38% anual
     - Anualidad: $1,200 MXN
     - Programa de recompensas: 2 puntos por cada $20 MXN
     - Beneficios: Acceso a salas VIP en aeropuertos

     Tarjeta Platinum:
     - Línea de crédito: $150,000+ MXN
     - Tasa de interés: 32% anual
     - Anualidad: $2,500 MXN
     - Programa de recompensas: 3 puntos por cada $20 MXN
     - Beneficios: Concierge 24/7, seguros de viaje

3. Documento 3 - Términos y Condiciones Cuenta de Ahorro (Word/PDF):

Biblioteca: Términos y Condiciones
Contenido sugerido:

     TÉRMINOS Y CONDICIONES - CUENTA DE AHORRO

     1. APERTURA DE CUENTA
     - Monto mínimo de apertura: $1,000 MXN
     - Sin saldo mínimo requerido
     - Sin comisión por manejo de cuenta

     2. RENDIMIENTOS
     - Tasa de interés anual: 2.5% sobre saldo promedio mensual
     - Capitalización: Mensual
     - Pago de intereses: Último día hábil del mes

     3. RETIROS Y DEPÓSITOS
     - Retiros ilimitados sin comisión en cajeros de la red
     - Retiros en cajeros de otros bancos: $15 MXN por transacción
     - Depósitos sin límite ni comisión

     4. CANCELACIÓN
     - Sin penalización por cancelación
     - Saldo debe ser retirado completamente

4. Cargar documentos a SharePoint:
- Navegue a cada biblioteca correspondiente
- Haga clic en "Cargar" → "Archivos"
- Seleccione los documentos creados
- Complete el campo "Categoría" para cada documento

5. Agregar metadatos adicionales:
- Para cada documento cargado, haga clic en los tres puntos (⋯) → "Detalles"
- Complete información adicional si está disponible

6. Crear al menos 6 documentos adicionales cubriendo:
- Procedimiento de apertura de cuenta
- Política de crédito automotriz
- Manual de inversiones
- Términos de seguros bancarios
- FAQ sobre banca en línea
- Política de protección de datos
- Salida Esperada:

Cada biblioteca debe contener al menos 2-3 documentos relevantes, totalizando 8-10 documentos en el sitio completo.

Verificación:

- Al menos 8 documentos están cargados en las bibliotecas
- Cada documento tiene asignada una categoría
- Los documentos contienen información bancaria realista y detallada
- Los archivos son accesibles y se pueden visualizar correctamente
---

## Paso 3: Configurar Fuente de Conocimiento en Copilot Studio
Objetivo: Conectar el agente de Copilot Studio con las bibliotecas de documentos de SharePoint para habilitar búsqueda semántica y generación de respuestas basadas en documentos.

## Instrucciones:

1. Abra Microsoft Copilot Studio en su navegador:

   https://copilotstudio.microsoft.com

2. Seleccione su agente bancario creado en módulos anteriores desde la página principal.
3. En el panel izquierdo, haga clic en "Conocimiento" o "Knowledge" (dependiendo del idioma de la interfaz).
4. Haga clic en "+ Agregar conocimiento" o "+ Add knowledge".
5. Seleccione "SharePoint" como fuente de conocimiento.
6. En el cuadro de diálogo de configuración:
- Haga clic en "Agregar" o "Add"
- Aparecerá un selector de sitios de SharePoint
7. Busque y seleccione el sitio creado: Banco Digital - Base de Conocimiento
8. Seleccione las bibliotecas específicas a incluir:
☑ Políticas de Crédito
☑ Manuales de Productos
☑ Términos y Condiciones
☑ Procedimientos Internos
9. Configure las opciones de indexación:
- Nombre de la fuente: Documentación Bancaria Corporativa
- Descripción: Base de conocimiento con políticas, manuales y procedimientos del banco
- Mantenga las opciones predeterminadas para indexación
10. Haga clic en "Agregar" y espere a que se complete la indexación inicial (puede tomar 2-5 minutos).
11. Una vez agregada la fuente, haga clic en ella para ver las opciones de configuración avanzada:
- Revise el "Estado de sincronización": Debe mostrar "Activo" o "Sincronizado"
- Verifique el "Número de documentos indexados": Debe coincidir con el total de documentos cargados

Salida Esperada:

En la sección de Conocimiento, debe ver la fuente Documentación Bancaria Corporativa con estado "Activo" y el número correcto de documentos indexados.

Verificación:

- La fuente de conocimiento de SharePoint está agregada correctamente
- El estado de sincronización muestra "Activo" o "Sincronizado"
- El número de documentos indexados coincide con los documentos cargados
- No hay errores de conexión o permisos mostrados
---

## Paso 4: Configurar Comportamiento de Búsqueda y Respuesta
Objetivo: Ajustar la configuración del agente para optimizar cómo utiliza la base de conocimiento al generar respuestas, incluyendo relevancia, citación de fuentes y manejo de casos sin información.

## Instrucciones:

1. En Copilot Studio, con su agente abierto, navegue a "Configuración" o "Settings" (ícono de engranaje en la esquina superior derecha).
2. Seleccione la sección "IA generativa" o "Generative AI" en el menú lateral.
3. Localice la subsección "Conocimiento" o "Knowledge" dentro de la configuración de IA generativa.
4. Configure los siguientes parámetros:

Nivel de contenido:

- Seleccione: "Medio" o "Medium"
- Esto equilibra entre respuestas concisas y detalladas

Instrucciones de contenido:

Agregue las siguientes instrucciones personalizadas en el campo de texto:

   Cuando respondas preguntas utilizando la base de conocimiento:
   1. Siempre cita la fuente del documento de donde obtuviste la información
   2. Si la información está en múltiples documentos, menciona todas las fuentes relevantes
   3. Si no encuentras información específica en los documentos, indícalo claramente
   4. Proporciona respuestas completas pero concisas, enfocándote en lo más relevante
   5. Utiliza un tono profesional y amigable apropiado para servicios bancarios
   6. Si la pregunta requiere información que no está en los documentos, sugiere contactar a un asesor

5. En la sección "Moderación de contenido":
- Active: "Moderación estricta"
- Esto asegura que las respuestas cumplan con estándares de seguridad

6. Desplácese hacia abajo hasta "Comportamiento cuando no hay respuesta":
- Seleccione: "Mensaje personalizado"
- Ingrese el siguiente mensaje:

   Lo siento, no encuentro información específica sobre tu consulta en nuestra documentación oficial. Te recomiendo contactar a un asesor bancario al 800-BANCO-01 o visitar tu sucursal más cercana para obtener información precisa y actualizada.

7. Habilite la opción "Mostrar fuentes citadas" o "Show cited sources" si está disponible.
8. Haga clic en "Guardar" en la parte superior derecha.

Salida Esperada:

Las configuraciones deben guardarse exitosamente y aparecer un mensaje de confirmación.

Verificación:

- Las instrucciones de contenido están guardadas correctamente
- El nivel de contenido está configurado en "Medio"
- El mensaje personalizado para casos sin respuesta está configurado
- La moderación de contenido está activa
- Los cambios se guardaron sin errores
---

## Paso 5: Crear Tópico de Prueba para Consultas Documentales
Objetivo: Crear un tópico específico que demuestre cómo el agente utiliza la base de conocimiento para responder consultas sobre productos y políticas bancarias.

## Instrucciones:

1. En Copilot Studio, navegue a la sección "Tópicos" o "Topics" en el panel izquierdo.
2. Haga clic en "+ Agregar tópico" → "Desde cero" o "+ New topic" → "From blank".
3. Configure el nuevo tópico:
- Nombre: Consultas sobre Documentación Bancaria
- Descripción: Maneja consultas sobre políticas, productos y procedimientos usando la base de conocimiento
4. En el editor de tópicos, configure las frases desencadenadoras (trigger phrases):
- Haga clic en "Editar" bajo "Frases desencadenadoras"
- Agregue las siguientes frases:

     ¿Cuáles son los requisitos para un crédito hipotecario?
     Información sobre tarjetas de crédito
     Quiero saber sobre las cuentas de ahorro
     ¿Qué documentos necesito para un crédito?
     Términos y condiciones de productos
     Políticas del banco
     Información sobre tasas de interés

5. En el canvas del tópico, agregue un nodo "Crear respuesta generativa" o "Create generative answer":
- Haga clic en el "+" debajo del nodo de activación
- Seleccione "Enviar un mensaje" → "Respuesta generativa"
6. Configure el nodo de respuesta generativa:
- En "Fuentes de datos" o "Data sources", asegúrese de que esté seleccionada: "Documentación Bancaria Corporativa"
- En "Instrucciones de contenido" (si está disponible a nivel de nodo), agregue:

     Busca en la documentación oficial del banco y proporciona una respuesta detallada.
     Siempre menciona de qué documento obtuviste la información.

7. Agregue un nodo de mensaje de seguimiento:
- Haga clic en el "+" debajo del nodo de respuesta generativa
- Seleccione "Enviar un mensaje"
- Escriba el mensaje:

     ¿Hay algo más sobre nuestros productos o políticas que te gustaría saber?

Agregue opciones de respuesta rápida:
- Debajo del mensaje de seguimiento, agregue un nodo "Pregunta" → "Opción múltiple"
- Opciones:
  Sí, tengo otra pregunta
  No, eso es todo
  Hablar con un asesor
8. Configure las rutas de respuesta:
"Sí, tengo otra pregunta": Redirigir al inicio del tópico (crear loop)
"No, eso es todo": Mensaje de despedida
"Hablar con un asesor": Mensaje con información de contacto
9. Haga clic en "Guardar" en la parte superior.

Salida Esperada:

Un tópico funcional que aparece en la lista de tópicos con estado "Activado".

Verificación:

- El tópico está creado y guardado
- Las frases desencadenadoras están configuradas correctamente
- El nodo de respuesta generativa está conectado a la fuente de SharePoint
- Las opciones de seguimiento están configuradas
- El tópico está en estado "Activado"
---

## Paso 6: Probar Búsqueda Semántica y Respuestas Documentales
Objetivo: Validar que el agente puede recuperar información precisa de los documentos de SharePoint y generar respuestas contextuales con citación de fuentes.

## Instrucciones:

- En Copilot Studio, haga clic en el botón "Probar" o "Test" en la esquina inferior derecha (ícono de chat).
- Espere a que el panel de prueba se abra completamente.

1. Prueba 1 - Consulta sobre Crédito Hipotecario:
- Escriba en el chat de prueba:

   ¿Cuáles son los requisitos para solicitar un crédito hipotecario?
Observe la respuesta:

- Debe incluir información sobre edad, ingresos, enganche, y antigüedad laboral
- Debe citar el documento "Política de Crédito Hipotecario"
- Debe mostrar un enlace o referencia al documento fuente

2. Prueba 2 - Consulta sobre Tarjetas de Crédito:
Escriba:

   ¿Qué tipos de tarjetas de crédito ofrecen y cuáles son sus beneficios?

Verifique que la respuesta:
- Mencione las tres tarjetas (Clásica, Oro, Platinum)
- Incluya información sobre tasas, anualidades y beneficios
- Cite el "Manual de Tarjetas de Crédito"

3. Prueba 3 - Consulta sobre Términos y Condiciones:

Escriba:

   ¿Cuál es la tasa de interés de la cuenta de ahorro y cómo se pagan los intereses?

Confirme que la respuesta:

- Indique la tasa de 2.5% anual
- Mencione capitalización mensual
- Cite "Términos y Condiciones - Cuenta de Ahorro"

4. Prueba 4 - Consulta Compleja Multi-documento:

Escriba:

   Quiero comparar las tasas de interés entre créditos hipotecarios y tarjetas de crédito

Verifique que:

- La respuesta incluya información de ambos documentos
- Cite ambas fuentes
- Proporcione una comparación clara

5. Prueba 5 - Consulta sin Información Disponible:

Escriba:

   ¿Cuáles son las promociones actuales para créditos personales?

Confirme que:
- El agente indique que no tiene información específica
- Aparezca el mensaje personalizado configurado
- Sugiera contactar a un asesor

Documentar resultados:
- Para cada prueba, capture pantalla de la respuesta
- Anote si las fuentes fueron citadas correctamente
- Registre cualquier problema o respuesta imprecisa

Salida Esperada:
El agente debe responder a las primeras 4 consultas con información precisa extraída de los documentos, citando las fuentes correctas. Para la consulta 5, debe mostrar el mensaje personalizado de no disponibilidad.

Verificación:

- Las respuestas contienen información precisa de los documentos
- Las fuentes documentales son citadas correctamente
- Las respuestas son coherentes y bien estructuradas
- El mensaje de "sin información" aparece cuando corresponde
- Los enlaces a documentos fuente son funcionales (si están disponibles)
---

## Paso 7: Configurar Permisos y Seguridad Documental
Objetivo: Implementar controles de acceso apropiados para asegurar que solo usuarios autorizados puedan acceder a documentos sensibles a través del agente.

## Instrucciones:

Configurar permisos en SharePoint:
a. Regrese al sitio de SharePoint: Banco Digital - Base de Conocimiento

b. Haga clic en el ícono de engranaje (⚙️) → "Permisos del sitio"

c. Revise los grupos de permisos actuales:

Propietarios: Control total
Miembros: Editar
Visitantes: Solo lectura
d. Para la biblioteca "Procedimientos Internos" (contenido más sensible):

Navegue a la biblioteca
Haga clic en el ícono de engranaje (⚙️) → "Configuración de biblioteca"
Seleccione "Permisos de esta biblioteca de documentos"
Haga clic en "Detener heredar permisos"
Remueva el grupo "Visitantes"
Esto restringe acceso solo a miembros y propietarios
Configurar seguridad en Copilot Studio:
a. En Copilot Studio, vaya a "Configuración" → "Seguridad" o "Security"

b. Localice la sección "Autenticación" o "Authentication"

c. Configure:

Tipo de autenticación: "Solo para usuarios de Teams" o "Manual" (según su caso de uso)
Si selecciona "Manual", configure Azure AD authentication
d. En "Acceso a datos":

Verifique que esté habilitado: "Respetar permisos de SharePoint"
Esto asegura que el agente solo muestre información de documentos a los que el usuario tiene acceso
Crear documento de prueba restringido:
a. En SharePoint, vaya a la biblioteca "Procedimientos Internos"

b. Cree un nuevo documento: Procedimiento de Manejo de Fraude.docx

c. Contenido sugerido:


      PROCEDIMIENTO INTERNO - CONFIDENCIAL
      Manejo de Casos de Fraude

      Este documento es de acceso restringido solo para personal autorizado.

      Pasos a seguir al detectar fraude:
      1. Bloquear inmediatamente la cuenta afectada
      2. Notificar al departamento de seguridad
      3. Documentar todos los detalles del incidente
      4. Iniciar investigación interna
d. Después de cargar, configure permisos específicos del documento:

Clic derecho en el documento → "Administrar acceso"
Remueva permisos heredados si es necesario
Agregue solo usuarios específicos de su equipo
Probar respeto de permisos:
a. En el panel de prueba de Copilot Studio, escriba:


      ¿Cuál es el procedimiento para manejar casos de fraude?
b. Si está autenticado como usuario con permisos:

Debe ver información del documento
c. Si prueba con un usuario sin permisos (o en modo no autenticado):

El agente debe indicar que no tiene acceso o no encuentra información
Salida Esperada:

Los permisos de SharePoint están configurados con diferentes niveles de acceso, y el agente respeta estos permisos al generar respuestas.

Verificación:

- La biblioteca "Procedimientos Internos" tiene permisos restringidos
- El documento de prueba tiene permisos específicos configurados
- La autenticación está configurada en Copilot Studio
- El agente respeta los permisos de SharePoint
- Los usuarios sin permisos no pueden acceder a contenido restringido a través del agente
---

## Paso 8: Optimizar Relevancia y Calidad de Respuestas
Objetivo: Ajustar la configuración de búsqueda y respuesta para mejorar la precisión y relevancia de las respuestas generadas por el agente.

## Instrucciones:

Analizar calidad de respuestas actuales:
En el panel de prueba, realice las siguientes consultas y evalúe la calidad:


   ¿Cuánto es el enganche mínimo para un crédito hipotecario?

   ¿Qué beneficios tiene la tarjeta Platinum?

   ¿Hay comisión por retiros en cajeros?

Para cada respuesta, evalúe:

✓ Precisión: ¿La información es correcta?
✓ Completitud: ¿Responde completamente la pregunta?
✓ Concisión: ¿Es breve pero suficiente?
✓ Citación: ¿Menciona la fuente correctamente?
Mejorar estructura de documentos si es necesario:
Si las respuestas no son óptimas, considere mejorar los documentos en SharePoint:

a. Agregue encabezados claros y estructura jerárquica:


      # Título Principal
      ## Sección
      ### Subsección
b. Use listas numeradas o con viñetas para información clave

c. Incluya tablas para comparaciones (ej: tabla comparativa de tarjetas)

d. Agregue un resumen ejecutivo al inicio de documentos largos

Refinar instrucciones de contenido:
a. Vaya a "Configuración" → "IA generativa" → "Conocimiento"

b. Actualice las instrucciones de contenido con directrices más específicas:


   Cuando respondas preguntas utilizando la base de conocimiento:

   ESTRUCTURA DE RESPUESTA:
   1. Proporciona la respuesta directa primero (1-2 oraciones)
   2. Agrega detalles relevantes si son necesarios
   3. Cita la fuente específica entre paréntesis: (Fuente: [nombre del documento])

   PRECISIÓN:
   - Usa solo información de los documentos, no inventes datos
   - Si hay números o porcentajes, cítalos exactamente
   - Si la información está desactualizada, menciona la fecha del documento

   TONO:
   - Profesional pero amigable
   - Claro y directo
   - Evita jerga técnica excesiva

   CASOS ESPECIALES:
   - Si no tienes información completa, sé honesto
   - Si la pregunta requiere cálculos personalizados, sugiere contactar un asesor
   - Para temas sensibles (fraude, legal), recomienda canales oficiales
c. Guarde los cambios

Agregar variaciones de documentos para mejorar cobertura:
Cree un documento FAQ consolidado en SharePoint:

a. En la biblioteca "Manuales de Productos", cree: FAQ - Preguntas Frecuentes.docx

b. Incluya preguntas y respuestas concisas extraídas de los otros documentos:


   PREGUNTAS FRECUENTES

   P: ¿Cuál es el enganche mínimo para crédito hipotecario?
   R: 20% del valor de la propiedad. (Ref: Política de Crédito Hipotecario)

   P: ¿Cuánto cuesta la anualidad de la tarjeta Oro?
   R: $1,200 MXN. (Ref: Manual de Tarjetas de Crédito)

   P: ¿Hay saldo mínimo en la cuenta de ahorro?
   R: No, no hay saldo mínimo requerido. (Ref: Términos y Condiciones Cuenta de Ahorro)

   [Agregar 10-15 preguntas más]

Forzar re-indexación:
a. En Copilot Studio, vaya a "Conocimiento"

b. Localice la fuente "Documentación Bancaria Corporativa"

c. Haga clic en los tres puntos (⋯) → "Actualizar" o "Refresh"

d. Espere 2-3 minutos para que se complete la re-indexación

Volver a probar con las mismas consultas:
Repita las consultas del paso 1 y compare las respuestas:

- ¿Son más precisas?
- ¿Son más concisas?
- ¿Las citaciones son más claras?

Salida Esperada:

Las respuestas del agente deben ser más precisas, concisas y mejor estructuradas después de las optimizaciones.

Verificación:

- Las respuestas son más precisas que en las pruebas iniciales
- Las citaciones de fuentes son claras y consistentes
- El documento FAQ está creado y indexado
- Las instrucciones de contenido están actualizadas
- La re-indexación se completó exitosamente
---

## Paso 9: Implementar Casos de Uso Bancarios Específicos
Objetivo: Crear y probar escenarios reales de consultas bancarias que demuestren el valor de la integración con la base de conocimiento.

## Instrucciones:

Caso de Uso 1: Cliente consultando requisitos de crédito
Pruebe la siguiente conversación completa:

   Usuario: Hola, quiero solicitar un crédito hipotecario
   [Esperar respuesta del agente]

   Usuario: ¿Cuáles son los requisitos que debo cumplir?
   [Esperar respuesta - debe mencionar edad, ingresos, enganche, antigüedad]

   Usuario: ¿Qué documentos necesito presentar?
   [Esperar respuesta - debe listar: identificación, comprobantes de ingresos, estados de cuenta, avalúo]

   Usuario: ¿Cuál es la tasa de interés?
   [Esperar respuesta - debe mostrar las tres opciones de tasas según plazo]

Documente si el agente:

- Mantiene contexto entre preguntas
- Proporciona información completa
- Cita fuentes consistentemente
- Caso de Uso 2: Comparación de productos

Pruebe:

   Usuario: Quiero comparar las tarjetas de crédito que ofrecen
   [Esperar respuesta - debe presentar las tres tarjetas]

   Usuario: ¿Cuál me conviene si gasto aproximadamente $20,000 al mes?
   [Esperar respuesta - debe recomendar basándose en líneas de crédito]

   Usuario: ¿La tarjeta Oro tiene acceso a salas VIP?
   [Esperar respuesta - debe confirmar que sí]

Caso de Uso 3: Consulta sobre términos y condiciones
Pruebe:

   Usuario: ¿Cuánto me cobran por usar cajeros de otros bancos?
   [Esperar respuesta - debe indicar $15 MXN]

   Usuario: ¿Y si uso los cajeros de su red?
   [Esperar respuesta - debe indicar que es sin comisión]

   Usuario: ¿Hay algún costo por mantener la cuenta de ahorro?
   [Esperar respuesta - debe indicar sin comisión por manejo]

Caso de Uso 4: Consulta compleja multi-producto
Pruebe:
   Usuario: Estoy buscando opciones de inversión. ¿Qué me conviene más, dejar mi dinero en cuenta de ahorro o buscar otras alternativas?
   [Esperar respuesta - debe mencionar tasa de 2.5% de cuenta de ahorro y sugerir consultar sobre inversiones]
Caso de Uso 5: Manejo de información no disponible
Pruebe:

   Usuario: ¿Cuáles son las promociones de este mes?
   [Esperar respuesta - debe indicar que no tiene esa información y sugerir contactar asesor]

   Usuario: ¿Puedo solicitar un crédito en línea?
   [Esperar respuesta - si no está en documentos, debe sugerir contactar asesor]

Documentar resultados de casos de uso:
Cree una tabla en un documento compartido del equipo:

- Caso de Uso	Consultas Exitosas	Consultas Fallidas	Observaciones
- Requisitos de crédito	X/X	X/X	[Notas]
- Comparación de productos	X/X	X/X	[Notas]
- Términos y condiciones	X/X	X/X	[Notas]
- Consulta multi-producto	X/X	X/X	[Notas]
-Información no disponible	X/X	X/X	[Notas]

Salida Esperada:

El agente debe manejar exitosamente al menos el 80% de las consultas en cada caso de uso, proporcionando información precisa con citaciones correctas.

Verificación:

- Todos los 5 casos de uso fueron probados completamente
- El agente mantiene contexto entre preguntas relacionadas
- Las respuestas son precisas y relevantes
- Las fuentes son citadas consistentemente
- Los casos sin información son manejados apropiadamente
- Los resultados están documentados en la tabla

---
##  Recursos

- https://learn.microsoft.com/microsoft-copilot-studio/
- https://learn.microsoft.com/power-platform/
- https://learn.microsoft.com/ai-builder/

---

¡Felicitaciones por completar el laboratorio!
