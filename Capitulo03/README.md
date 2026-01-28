
# Diseña entradas y salidas estructuradas


---

## Descripción General

Esta actividad grupal integradora permite aplicar todos los conceptos del módulo 2 en un ejercicio práctico colaborativo de diseño de agentes de IA. Los equipos de 3-4 personas trabajarán para definir completamente un agente de IA desde su concepción hasta un plan de desarrollo estructurado, incluyendo funcionalidades, público objetivo, tipos de salida y consideraciones de seguridad y ética. Al finalizar, cada equipo presentará su plan documentado al resto de la clase para retroalimentación y discusión.


---

## Objetivos de Aprendizaje

- Definir claramente qué hará el agente de IA identificando funcionalidades específicas y casos de uso
- Identificar el público objetivo del agente determinando a quién ayudará y qué problemas resolverá
- Especificar los tipos de salida que generará el agente (texto, datos, recomendaciones, acciones)
- Crear un plan de desarrollo estructurado del agente de IA con roles, objetivos y alcance definidos
- Aplicar buenas prácticas de seguridad, privacidad y ética en el diseño del agente
- Colaborar efectivamente en equipos para tomar decisiones de diseño consensuadas
- Documentar de manera profesional el plan completo del agente de IA

---

## Prerrequisitos

- Completar Módulo 2.0 con plan de agente aprobado y documentado
- Comprensión de flujos de conversación básicos y lógica condicional
- Familiaridad con conceptos de variables y entidades en sistemas conversacionales
- Conocimiento básico de procesos bancarios (consultas de saldo, transferencias, productos)

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

Antes de comenzar, cada equipo debe:

- Verificar acceso al ambiente de desarrollo:
Navegar a https://copilotstudio.microsoft.com
Iniciar sesión con credenciales de Microsoft 365
Confirmar que pueden ver el ambiente asignado a su equipo
- Revisar documentación del módulo anterior:
Plan de agente aprobado con casos de uso definidos
Diagramas de flujo de conversación
Lista de entidades y variables identificadas
- Organizar roles del equipo:
Líder técnico: Coordina la implementación y toma decisiones de diseño
Desarrollador de tópicos: Crea y configura tópicos de conversación
Especialista en experiencia: Diseña mensajes y formatos de salida
Documentador: Registra configuraciones y decisiones técnicas



---

##  Desarrollo del Laboratorio

## Paso 1: Crear y configurar el agente bancario
Objetivo: Inicializar un nuevo agente en Copilot Studio con los parámetros básicos apropiados para un contexto bancario.

## Instrucciones:

- Acceder a Microsoft Copilot Studio desde el navegador:
Navegar a https://copilotstudio.microsoft.com
Iniciar sesión con las credenciales proporcionadas
Crear un nuevo agente:
Hacer clic en "+ Crear" en el panel izquierdo
Seleccionar "Nuevo agente"
En el campo "Nombre", ingresar: Asistente Bancario [NombreEquipo]
En "Descripción", escribir: Agente de IA para asistencia bancaria automatizada - Equipo [NombreEquipo]
Seleccionar el idioma: Español
Hacer clic en "Crear"
- Configurar parámetros básicos del agente:
Una vez creado el agente, hacer clic en "Configuración" (ícono de engranaje) en la parte superior derecha
En la sección "General":
Zona horaria: Seleccionar la zona horaria local (ej: (UTC-05:00) Bogotá, Lima, Quito)
Icono del agente: Mantener por defecto o personalizar si hay tiempo disponible
En la sección "Seguridad":
Autenticación: Seleccionar Solo para usuarios de Teams y Power Apps (seguridad básica)
Hacer clic en "Guardar" en la parte superior
- Configurar el mensaje de bienvenida personalizado:
En el panel izquierdo, hacer clic en "Tópicos"
Buscar y seleccionar el tópico "Saludo" (viene preconfigurado)
Hacer clic en "Ir al lienzo de creación"
Localizar el nodo de mensaje que dice "Hola, soy un asistente virtual..."

- Reemplazar el texto con:

   ¡Bienvenido al Asistente Bancario Virtual! 👋

   Estoy aquí para ayudarte con:
   • Consulta de saldos y movimientos
   • Transferencias entre cuentas
   • Información sobre productos bancarios
   • Solicitud de tarjetas de crédito

   ¿En qué puedo ayudarte hoy?

Hacer clic en "Guardar" en la parte superior derecha

Salida Esperada:

Agente creado con nombre identificable del equipo
Configuración de idioma en español confirmada
Zona horaria configurada correctamente
Mensaje de bienvenida personalizado visible en el editor

- Verificación:
En el panel de "Información general", confirmar que el nombre del agente aparece correctamente
Hacer clic en "Probar el agente" (panel derecho) y verificar que el mensaje de bienvenida personalizado se muestra en español
Confirmar que no hay errores de validación en la parte superior del editor
---

## Paso 2: Crear entidades personalizadas para datos bancarios
Objetivo: Definir entidades personalizadas que el agente utilizará para capturar información específica del dominio bancario.

## Instrucciones:

- Acceder a la sección de entidades:
En el panel izquierdo de Copilot Studio, hacer clic en "Entidades"
Hacer clic en "+ Nueva entidad"
Seleccionar "Entidad cerrada" (lista predefinida de valores)
- Crear entidad para tipos de cuenta:
Nombre de la entidad: TipoCuenta
Descripción: Tipos de cuentas bancarias disponibles
En la sección "Elementos de lista", agregar los siguientes valores:
-- Elemento 1:
Nombre canónico: Cuenta de Ahorros
Sinónimos: ahorros, ahorro, cuenta ahorro
-- Elemento 2:
Nombre canónico: Cuenta Corriente
Sinónimos: corriente, cuenta corriente, chequera
-- Elemento 3:
Nombre canónico: Cuenta Nómina
Sinónimos: nómina, nomina, cuenta de nómina
Hacer clic en "Guardar"
- Crear entidad para tipos de producto bancario:
Hacer clic nuevamente en "+ Nueva entidad"
Seleccionar "Entidad cerrada"
Nombre de la entidad: ProductoBancario
Descripción: Productos bancarios disponibles para consulta
Agregar elementos:
-- Elemento 1:
Nombre canónico: Tarjeta de Crédito
Sinónimos: tarjeta crédito, TC, tarjeta, crédito
-- Elemento 2:
Nombre canónico: Préstamo Personal
Sinónimos: préstamo, prestamo, crédito personal, financiamiento
-- Elemento 3:
Nombre canónico: Cuenta de Inversión
Sinónimos: inversión, inversion, cuenta inversión, fondos
-- Elemento 4:
Nombre canónico: Seguro
Sinónimos: póliza, poliza, seguro bancario
Hacer clic en "Guardar"
- Crear entidad para tipos de transacción:
Hacer clic en "+ Nueva entidad"
Seleccionar "Entidad cerrada"
Nombre de la entidad: TipoTransaccion
Descripción: Tipos de transacciones bancarias
Agregar elementos:
-- Elemento 1:
Nombre canónico: Transferencia
Sinónimos: transferir, enviar dinero, transferencia bancaria
-- Elemento 2:
Nombre canónico: Pago de Servicios
Sinónimos: pagar servicios, pago servicio, servicios
-- Elemento 3:
Nombre canónico: Retiro
Sinónimos: retirar, sacar dinero, retiro efectivo
Hacer clic en "Guardar"

Salida Esperada:

Tres entidades personalizadas creadas: TipoCuenta, ProductoBancario, TipoTransaccion
Cada entidad contiene múltiples elementos con sinónimos configurados
Las entidades aparecen en la lista de entidades del agente
---

## Paso 3: Crear tópico para consulta de saldo con entrada numérica
Objetivo: Implementar un flujo conversacional que capture un número de cuenta (entrada numérica) y proporcione información de saldo.

## Instrucciones:

- Crear un nuevo tópico:
En el panel izquierdo, hacer clic en "Tópicos"
Hacer clic en "+ Nuevo tópico"
Seleccionar "Desde cero"
En el campo "Nombre", escribir: Consulta de Saldo
En "Descripción", escribir: Permite al usuario consultar el saldo de su cuenta bancaria
- Configurar frases de activación:
En la sección "Frases de activación", agregar las siguientes frases:
consultar saldo
cuanto tengo en mi cuenta
ver mi saldo
saldo disponible
revisar cuenta
Hacer clic en el lienzo de creación para comenzar a diseñar el flujo
- Agregar mensaje inicial:
El nodo de activación ya está presente
Hacer clic en el símbolo "+" debajo del nodo de activación
Seleccionar "Enviar un mensaje"
En el campo de texto, escribir:
   "Claro, te ayudaré a consultar tu saldo."
-Agregar pregunta para capturar número de cuenta:
Hacer clic en el símbolo "+" debajo del mensaje
Seleccionar "Hacer una pregunta"
En el campo de pregunta, escribir:
   "Por favor, ingresa los últimos 4 dígitos de tu número de cuenta:"
En "Identificar", seleccionar "Número" de la lista desplegable
En "Guardar respuesta como", el sistema creará automáticamente una variable (ej: Var1)
Renombrar la variable a: NumeroCuenta (hacer clic en el lápiz junto a la variable)
- Agregar validación condicional del número de cuenta:
Hacer clic en el símbolo "+" debajo de la pregunta
Seleccionar "Agregar una condición"
Configurar la condición:
Variable: NumeroCuenta
Operador: es mayor que
Valor: 999 (asegura que sean al menos 4 dígitos)
Esto creará dos ramas: Condición cumplida y Todas las demás condiciones
- Configurar respuesta para cuenta válida:
En la rama "Condición cumplida", hacer clic en el símbolo "+"
Seleccionar "Enviar un mensaje"
Escribir el siguiente mensaje:
   Cuenta verificada: ****{NumeroCuenta}

   Información de saldo:
   • Saldo disponible: $15,432.50 MXN
   • Saldo retenido: $500.00 MXN
   • Saldo total: $15,932.50 MXN

   Última actualización: Hoy, 14:30 hrs

-- Nota: Para insertar la variable, escribir { y seleccionar NumeroCuenta del menú desplegable

- Configurar respuesta para cuenta inválida:
En la rama "Todas las demás condiciones", hacer clic en el símbolo "+"
Seleccionar "Enviar un mensaje"
Escribir:
   El número ingresado no es válido.

   Por favor, asegúrate de ingresar los 4 dígitos de tu cuenta (ejemplo: 1234).

Hacer clic en el símbolo "+" debajo de este mensaje
Seleccionar "Ir a otro tópico"
Elegir "Redirigir a este tópico" (Consulta de Saldo) para reintentar

- Agregar mensaje de cierre:
En la rama de cuenta válida, después del mensaje de saldo, hacer clic en "+"
Seleccionar "Enviar un mensaje"
Escribir:
   "¿Hay algo más en lo que pueda ayudarte?"
Hacer clic en "Guardar" en la parte superior derecha

Salida Esperada:

Tópico "Consulta de Saldo" creado con 5 frases de activación
Flujo conversacional con captura de entrada numérica
Validación condicional implementada con dos ramas
Variable NumeroCuenta correctamente configurada y utilizada en mensajes

Verificación:

Hacer clic en "Probar el agente" en el panel derecho
Escribir: quiero consultar mi saldo
Confirmar que el agente activa el tópico correcto
Ingresar un número válido (ej: 1234) y verificar que muestra el saldo
Reiniciar la conversación e ingresar un número inválido (ej: 12) para verificar el mensaje de error
Confirmar que no hay errores de validación en el editor
---

## Paso 4: Crear tópico para selección de producto con opciones múltiples
Objetivo: Diseñar un flujo que utilice opciones de selección múltiple y la entidad personalizada ProductoBancario.

## Instrucciones:

- Crear un nuevo tópico:
Hacer clic en "+ Nuevo tópico"
Seleccionar "Desde cero"
Nombre: Información de Productos
Descripción: Proporciona información sobre productos bancarios disponibles
- Configurar frases de activación:
Agregar las siguientes frases:
información de productos
qué productos tienen
productos bancarios
quiero conocer sus servicios
servicios disponibles
- Agregar mensaje de introducción:
En el lienzo, hacer clic en "+" debajo del nodo de activación
Seleccionar "Enviar un mensaje"
Escribir:
   "Tenemos varios productos diseñados para ti."
- Agregar pregunta con opciones múltiples:
Hacer clic en "+" debajo del mensaje
Seleccionar "Hacer una pregunta"
Escribir la pregunta:
   "¿Sobre qué producto te gustaría recibir información?"
En "Identificar", buscar y seleccionar la entidad personalizada: ProductoBancario
En "Guardar respuesta como", renombrar la variable a: ProductoSeleccionado
En la sección "Opciones para el usuario", hacer clic en "+ Agregar opción"
Agregar las siguientes opciones (el sistema las vinculará automáticamente con la entidad):
Tarjeta de Crédito
Préstamo Personal
Cuenta de Inversión
Seguro
- Crear ramificación condicional por producto:
Hacer clic en "+" debajo de la pregunta
Seleccionar "Agregar una condición"
Configurar la primera condición:
-- Variable: ProductoSeleccionado
-- Operador: es igual a
--- Valor: Tarjeta de Crédito
Hacer clic en "+ Nueva condición" para agregar más ramas:
-- Condición 2: ProductoSeleccionado es igual a Préstamo Personal
-- Condición 3: ProductoSeleccionado es igual a Cuenta de Inversión
-- Condición 4: ProductoSeleccionado es igual a Seguro

Configurar respuesta para Tarjeta de Crédito:
En la rama de "Tarjeta de Crédito", hacer clic en "+"
Seleccionar "Enviar un mensaje"
Escribir:
   **Tarjeta de Crédito Premium**

   Beneficios destacados:
   ✓ Hasta 50 días sin intereses
   ✓ Programa de recompensas con 2% de cashback
   ✓ Sin anualidad el primer año
   ✓ Seguro de compra incluido

   Tasa de interés: 24% anual
   Límite de crédito: Desde $10,000 hasta $150,000

   ¿Te gustaría solicitar esta tarjeta?

- Configurar respuesta para Préstamo Personal:
En la rama de "Préstamo Personal", hacer clic en "+"
Seleccionar "Enviar un mensaje"
Escribir:
   **Préstamo Personal Flexible**

   Características:
   ✓ Montos desde $5,000 hasta $500,000
   ✓ Plazos de 12 a 60 meses
   ✓ Tasa competitiva desde 18% anual
   ✓ Aprobación en 24 horas
   ✓ Sin comisión por apertura

   Requisitos mínimos:
   • Edad: 18-65 años
   • Ingresos mínimos: $8,000 mensuales
   • Antigüedad laboral: 6 meses

   ¿Deseas iniciar una solicitud?

- Configurar respuesta para Cuenta de Inversión:
En la rama de "Cuenta de Inversión", hacer clic en "+"
Seleccionar "Enviar un mensaje"

Escribir:
   📈 **Cuenta de Inversión Inteligente**

   Opciones disponibles:
   ✓ Fondos de inversión diversificados
   ✓ Rendimientos competitivos (hasta 8% anual)
   ✓ Inversión mínima: $1,000
   ✓ Liquidez en 48 horas
   ✓ Asesoría personalizada incluida

   Perfiles de riesgo:
   • Conservador: 4-5% anual
   • Moderado: 6-7% anual
   • Agresivo: 8-10% anual

   ¿Te interesa agendar una asesoría?

- Configurar respuesta para Seguro:
En la rama de "Seguro", hacer clic en "+"
Seleccionar "Enviar un mensaje"
Escribir:
   **Seguros Bancarios**

   Coberturas disponibles:
   ✓ Seguro de vida
   ✓ Seguro de auto
   ✓ Seguro de hogar
   ✓ Seguro de gastos médicos

   Beneficios exclusivos:
   • Descuentos por cliente bancario (hasta 15%)
   • Atención 24/7
   • Proceso de reclamación simplificado
   • Cobertura desde el primer día

   ¿Sobre qué tipo de seguro necesitas información específica?

Agregar mensaje de cierre común:
Después de cada una de las 4 ramas, hacer clic en "+"
Seleccionar "Finalizar con encuesta" (esto cerrará la conversación de manera ordenada)
Hacer clic en "Guardar"

Salida Esperada:

Tópico "Información de Productos" con frases de activación configuradas
Pregunta con 4 opciones de selección múltiple vinculadas a la entidad ProductoBancario
Cuatro ramas condicionales con información detallada de cada producto
Variable ProductoSeleccionado correctamente utilizada en las condiciones

---

## Paso 5: Crear tópico de confirmación de transacción con respuestas rápidas
Objetivo: Implementar un flujo de confirmación simple (sí/no) utilizando respuestas rápidas y validación de decisiones del usuario.

## Instrucciones:

- Crear un nuevo tópico:
Hacer clic en "+ Nuevo tópico"
Seleccionar "Desde cero"
Nombre: Confirmación de Transferencia
Descripción: Confirma una transferencia bancaria antes de procesarla
- Configurar frases de activación:
Agregar:
hacer una transferencia
transferir dinero
enviar dinero
quiero transferir
realizar transferencia
- Agregar mensaje de introducción:
Hacer clic en "+" debajo del nodo de activación
Seleccionar "Enviar un mensaje"
Escribir:
   "Perfecto, te ayudaré a realizar una transferencia."
Capturar monto de transferencia:
Hacer clic en "+"
Seleccionar "Hacer una pregunta"
Escribir:
   "¿Cuál es el monto que deseas transferir?"
En "Identificar", seleccionar "Número"
Renombrar la variable a: MontoTransferencia
Capturar cuenta destino:
Hacer clic en "+"
Seleccionar "Hacer una pregunta"
Escribir:
   "¿A qué número de cuenta deseas transferir? (Ingresa los últimos 4 dígitos)"
En "Identificar", seleccionar "Número"
Renombrar la variable a: CuentaDestino
Mostrar resumen de transferencia:
Hacer clic en "+"
Seleccionar "Enviar un mensaje"
Escribir:
   **Resumen de Transferencia**

   Monto: ${MontoTransferencia} MXN
   Cuenta destino: ****{CuentaDestino}
   Cuenta origen: Tu cuenta principal
   Comisión: $0.00 (transferencia entre cuentas propias)

   Total a debitar: ${MontoTransferencia} MXN
Agregar pregunta de confirmación con respuestas rápidas:
Hacer clic en "+"
Seleccionar "Hacer una pregunta"
Escribir:
   "¿Confirmas esta transferencia?"
En "Identificar", seleccionar "Booleano (sí o no)"
Renombrar la variable a: ConfirmacionUsuario
En "Opciones para el usuario", el sistema mostrará automáticamente dos botones: Sí y No
- Crear ramificación condicional para la confirmación:
Hacer clic en "+" debajo de la pregunta de confirmación
Seleccionar "Agregar una condición"
Configurar:
Variable: ConfirmacionUsuario
Operador: es igual a
Valor: Verdadero (True)
- Configurar respuesta para confirmación positiva:
En la rama "ConfirmacionUsuario es igual a Verdadero", hacer clic en "+"
Seleccionar "Enviar un mensaje"
Escribir:
   **Transferencia Exitosa**

   Tu transferencia ha sido procesada correctamente.

   Detalles:
   • Monto: ${MontoTransferencia} MXN
   • Cuenta destino: ****{CuentaDestino}
   • Fecha: {System.Today}
   • Número de referencia: REF-{System.Timestamp}

   Recibirás una notificación por correo electrónico con los detalles completos.

   ¿Hay algo más en lo que pueda ayudarte?
Nota: {System.Today} y {System.Timestamp} son variables del sistema disponibles

- Configurar respuesta para confirmación negativa:
En la rama "Todas las demás condiciones", hacer clic en "+"
Seleccionar "Enviar un mensaje"
Escribir:
    **Transferencia Cancelada**

    La transferencia ha sido cancelada. No se realizó ningún cargo a tu cuenta.

    Si deseas realizar una transferencia diferente, puedo ayudarte. Solo dime "hacer transferencia".
Guardar el tópico:
-- Hacer clic en "Guardar" en la parte superior derecha

Salida Esperada:

Tópico "Confirmación de Transferencia" completamente funcional
Captura de dos valores numéricos: monto y cuenta destino
Resumen de transferencia con variables interpoladas
Pregunta de confirmación con botones de respuesta rápida (Sí/No)
Dos ramas condicionales con mensajes apropiados

---

## Paso 6: Diseñar una tarjeta adaptativa para presentación de información
Objetivo: Crear una salida visual enriquecida utilizando Adaptive Cards para presentar información bancaria de manera estructurada y atractiva.

## Instrucciones:

- Crear un nuevo tópico para promociones:
Hacer clic en "+ Nuevo tópico"
Seleccionar "Desde cero"
Nombre: Promociones Bancarias
Descripción: Muestra promociones actuales usando tarjetas adaptativas
- Configurar frases de activación:
Agregar:
promociones
ofertas disponibles
descuentos bancarios
beneficios actuales
- Agregar mensaje de introducción:
Hacer clic en "+" debajo del nodo de activación
Seleccionar "Enviar un mensaje"
Escribir:
   "¡Tenemos excelentes promociones para ti!"
- Agregar una tarjeta adaptativa:
Hacer clic en "+" debajo del mensaje
Seleccionar "Enviar un mensaje"
En el editor de mensaje, hacer clic en el ícono "..." (más opciones)
Seleccionar "Tarjeta adaptativa"
Se abrirá el editor de código JSON de la tarjeta
- Configurar el contenido de la tarjeta adaptativa:
Reemplazar el contenido JSON predeterminado con el siguiente código:
{
  "type": "AdaptiveCard",
  "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
  "version": "1.4",
  "body": [
    {
      "type": "Container",
      "items": [
        {
          "type": "TextBlock",
          "text": "💳 Promoción Tarjeta Premium",
          "weight": "Bolder",
          "size": "Large",
          "color": "Accent"
        },
        {
          "type": "TextBlock",
          "text": "¡Aprovecha nuestra oferta exclusiva!",
          "wrap": true,
          "size": "Medium"
        }
      ]
    },
    {
      "type": "Container",
      "separator": true,
      "spacing": "Medium",
      "items": [
        {
          "type": "FactSet",
          "facts": [
            {
              "title": "Beneficio:",
              "value": "Sin anualidad por 2 años"
            },
            {
              "title": "Cashback:",
              "value": "5% en compras de supermercado"
            },
            {
              "title": "Puntos:",
              "value": "10,000 puntos de bienvenida"
            },
            {
              "title": "Vigencia:",
              "value": "Hasta 31 de Diciembre"
            }
          ]
        }
      ]
    },
    {
      "type": "Container",
      "spacing": "Medium",
      "items": [
        {
          "type": "TextBlock",
          "text": "Requisitos:",
          "weight": "Bolder",
          "size": "Medium"
        },
        {
          "type": "TextBlock",
          "text": "✓ Ingresos mínimos: $15,000/mes\n✓ Edad: 21-65 años\n✓ Sin adeudos en buró de crédito",
          "wrap": true,
          "spacing": "Small"
        }
      ]
    }
  ],
  "actions": [
    {
      "type": "Action.OpenUrl",
      "title": "Solicitar Ahora",
      "url": "https://www.ejemplo.com/solicitud"
    },
    {
      "type": "Action.Submit",
      "title": "Más Información",
      "data": {
        "action": "mas_info_tarjeta"
      }
    }
  ]
}
- Validar y guardar la tarjeta:
Hacer clic en "Validar JSON" para asegurar que no hay errores de sintaxis
Si la validación es exitosa, hacer clic en "Aceptar"
La tarjeta se mostrará como vista previa en el editor
- Agregar mensaje de seguimiento:
Hacer clic en "+" debajo de la tarjeta adaptativa
Seleccionar "Enviar un mensaje"
Escribir:
   "¿Te gustaría conocer más promociones o necesitas ayuda con algo más?"
Guardar el tópico:
Hacer clic en "Guardar" en la parte superior derecha

Salida Esperada:
Tópico "Promociones Bancarias" con tarjeta adaptativa integrada
Tarjeta visualmente estructurada con:
Título destacado con emoji
Conjunto de hechos (FactSet) con información clave
Lista de requisitos
Dos botones de acción en la parte inferior
Vista previa de la tarjeta visible en el editor
---

## Paso 7: Implementar flujo con ramificación condicional compleja
Objetivo: Crear un flujo de conversación con múltiples niveles de condiciones anidadas para manejar diferentes escenarios de usuario.

## Instrucciones:

- Crear un nuevo tópico para evaluación de elegibilidad:
Hacer clic en "+ Nuevo tópico"
Seleccionar "Desde cero"
Nombre: Evaluación de Elegibilidad para Crédito
Descripción: Evalúa si el usuario califica para productos de crédito según múltiples criterios
- Configurar frases de activación:
Agregar:
puedo solicitar un crédito
califico para préstamo
evaluar elegibilidad
requisitos para crédito
puedo obtener una tarjeta
- Agregar mensaje de introducción:
Hacer clic en "+"
Seleccionar "Enviar un mensaje"
Escribir:
   "Te ayudaré a verificar si calificas para nuestros productos de crédito."

   Necesito hacerte algunas preguntas rápidas.

- Capturar edad del usuario:
Hacer clic en "+"
Seleccionar "Hacer una pregunta"
Escribir: ¿Cuál es tu edad?
En "Identificar", seleccionar "Número"
Renombrar la variable a: EdadUsuario
- Validar rango de edad (primera condición):
Hacer clic en "+"
Seleccionar "Agregar una condición"
Configurar:
Variable: EdadUsuario
Operador: es mayor o igual que
Valor: 18
Hacer clic en "Agregar" para agregar una segunda condición en el mismo nivel
En la misma rama de condición, hacer clic en "Y" para agregar condición adicional:
Variable: EdadUsuario
Operador: es menor o igual que
Valor: 65
- Capturar ingresos mensuales (dentro de la rama de edad válida):
En la rama "EdadUsuario es mayor o igual que 18 Y EdadUsuario es menor o igual que 65", hacer clic en "+"
Seleccionar "Hacer una pregunta"
Escribir: ¿Cuál es tu ingreso mensual aproximado? (en pesos)
En "Identificar", seleccionar "Número"
Renombrar la variable a: IngresoMensual
- Validar ingresos (segunda condición anidada):
Hacer clic en "+" debajo de la pregunta de ingresos
Seleccionar "Agregar una condición"
Configurar:
Variable: IngresoMensual
Operador: es mayor o igual que
Valor: 8000
- Preguntar sobre historial crediticio (dentro de rama de ingresos válidos):
En la rama "IngresoMensual es mayor o igual que 8000", hacer clic en "+"
Seleccionar "Hacer una pregunta"
Escribir: ¿Tienes adeudos o reportes negativos en tu historial crediticio?
En "Identificar", seleccionar "Booleano (sí o no)"
Renombrar la variable a: TieneAdeudos
Configurar opciones:
Opción 1: Sí, tengo adeudos
Opción 2: No, mi historial está limpio
- Configurar respuesta para usuario elegible (historial limpio):
Hacer clic en "+" debajo de la pregunta de historial
Seleccionar "Agregar una condición"
Configurar:
Variable: TieneAdeudos
Operador: es igual a
Valor: Falso (False)
En esta rama, hacer clic en "+"
Seleccionar "Enviar un mensaje"
Escribir:
   **¡Excelentes noticias!**

   Cumples con todos los requisitos para nuestros productos de crédito.

   Productos disponibles para ti:
   💳 Tarjeta de Crédito Premium (límite hasta $80,000)
   💰 Préstamo Personal (hasta $300,000)
   🏠 Crédito Hipotecario (sujeto a evaluación adicional)

   Tu perfil:
   • Edad: {EdadUsuario} años ✓
   • Ingresos: ${IngresoMensual} mensuales ✓
   • Historial crediticio: Limpio ✓

   ¿Te gustaría iniciar una solicitud?

- Configurar respuesta para usuario con adeudos:
En la rama "Todas las demás condiciones" de la pregunta de historial, hacer clic en "+"
Seleccionar "Enviar un mensaje"
Escribir:
    **Evaluación Parcial**

    Cumples con los requisitos de edad e ingresos, pero detectamos que tienes adeudos en tu historial.

    Opciones disponibles:
    📞 Asesoría para reparación de crédito
    💳 Tarjeta de Crédito Básica (límite reducido)
    📋 Préstamo con aval

    Te recomendamos:
    1. Regularizar tus adeudos actuales
    2. Agendar cita con un asesor financiero
    3. Revisar opciones de consolidación de deuda

    ¿Deseas hablar con un asesor?

- Configurar respuesta para ingresos insuficientes:
En la rama "Todas las demás condiciones" de la validación de ingresos, hacer clic en "+"
Seleccionar "Enviar un mensaje"
Escribir:
    **Requisitos No Cumplidos**

    Lamentablemente, tus ingresos actuales (${IngresoMensual}) no alcanzan el mínimo requerido de $8,000 mensuales.

    Alternativas disponibles:
    💳 Tarjeta de débito con beneficios
    💰 Cuenta de ahorro con rendimientos
    📱 Banca móvil sin comisiones

    Cuando tus ingresos aumenten, estaremos encantados de reevaluar tu solicitud.

    ¿Te interesa conocer nuestros productos sin requisitos de ingreso?

- Configurar respuesta para edad fuera de rango:
En la rama "Todas las demás condiciones" de la validación de edad inicial, hacer clic en "+"
Seleccionar "Enviar un mensaje"
Escribir:
    **Edad No Elegible**

    Lo sentimos, nuestros productos de crédito están disponibles para personas entre 18 y 65 años.

    Tu edad: {EdadUsuario} años

    Si eres menor de edad:
    • Cuenta de ahorro juvenil
    • Tarjeta de débito con control parental

    Si eres mayor de 65 años:
    • Productos de inversión para retiro
    • Cuenta de ahorro senior con beneficios especiales

    ¿Deseas información sobre estos productos alternativos?
Guardar el tópico:
Hacer clic en "Guardar"

Salida Esperada:

Tópico con flujo de conversación de 3 niveles de profundidad
Validación secuencial de edad, ingresos e historial crediticio
Múltiples ramas condicionales con respuestas personalizadas
Variables correctamente utilizadas en mensajes de salida
Lógica condicional anidada funcionando correctamente


- Verificación:

Prueba 1 - Usuario elegible:
Escribir: puedo solicitar un crédito
Edad: 30
Ingresos: 15000
Adeudos: No, mi historial está limpio
Verificar mensaje de aprobación completa
Prueba 2 - Usuario con adeudos:
Reiniciar conversación
Edad: 35
Ingresos: 20000
Adeudos: Sí, tengo adeudos
Verificar mensaje de evaluación parcial
Prueba 3 - Ingresos insuficientes:
Reiniciar conversación
Edad: 25
Ingresos: 5000
Verificar mensaje de requisitos no cumplidos
Prueba 4 - Edad no elegible:
Reiniciar conversación
Edad: 17
Verificar mensaje de edad no elegible
---

## Paso 8: Configurar variables globales y gestión de contexto
Objetivo: Implementar variables globales que puedan ser utilizadas en múltiples tópicos para mantener contexto de usuario a lo largo de la conversación.

## Instrucciones:

- Acceder a la sección de variables:
En el panel izquierdo de Copilot Studio, hacer clic en "Variables"
Hacer clic en "+ Nueva variable"
- Crear variable global para nombre de usuario:
En el panel de creación de variable:
Nombre: NombreUsuario
Tipo de datos: Texto
Ámbito: Seleccionar "Global" (disponible en todos los tópicos)
Valor predeterminado: Dejar vacío
Descripción: Almacena el nombre del usuario para personalización
Hacer clic en "Guardar"
- Crear variable global para tipo de cliente:
Hacer clic nuevamente en "+ Nueva variable"
Configurar:
-- Nombre: TipoCliente
-- Tipo de datos: Texto
-- Ámbito: Global
-- Valor predeterminado: Nuevo
-- Descripción: Identifica si el usuario es cliente nuevo o existente
Hacer clic en "Guardar"
- Crear variable global para número de cliente:
Hacer clic en "+ Nueva variable"
Configurar:
-- Nombre: NumeroCliente
-- Tipo de datos: Número
-- Ámbito: Global
-- Valor predeterminado: 0
-- Descripción: Número de identificación del cliente en el sistema
Hacer clic en "Guardar"
- Modificar el tópico de Saludo para capturar nombre:
Ir a "Tópicos" y seleccionar el tópico "Saludo"
Después del mensaje de bienvenida personalizado que creamos en el Paso 1, hacer clic en "+"
Seleccionar "Hacer una pregunta"
Escribir: Antes de comenzar, ¿cómo te llamas?
En "Identificar", seleccionar "Persona" (captura nombres)
En "Guardar respuesta como", hacer clic en el menú desplegable
Seleccionar "Crear una nueva variable"
Buscar y seleccionar la variable global: NombreUsuario
- Agregar pregunta para identificar tipo de cliente:
Hacer clic en "+" debajo de la pregunta de nombre
Seleccionar "Hacer una pregunta"
Escribir: Gracias {NombreUsuario}. ¿Ya eres cliente de nuestro banco?
En "Identificar", seleccionar "Booleano (sí o no)"
Crear una variable local temporal llamada: EsClienteExistente
- Configurar lógica para asignar tipo de cliente:
Hacer clic en "+"
Seleccionar "Agregar una condición"
Configurar:
Variable: EsClienteExistente
Operador: es igual a
Valor: Verdadero (True)
- Asignar valor a variable global según respuesta:
En la rama de "EsClienteExistente es igual a Verdadero", hacer clic en "+"
Seleccionar "Establecer valor de variable"
Configurar:
Variable: TipoCliente
Valor: Existente (escribir directamente el texto)
Hacer clic en "+" en la misma rama
Seleccionar "Enviar un mensaje"
Escribir:
   ¡Qué gusto verte de nuevo, {NombreUsuario}! 😊

   Como cliente existente, tienes acceso a todos nuestros servicios.


- Configurar rama para cliente nuevo:
En la rama "Todas las demás condiciones", hacer clic en "+"
Seleccionar "Establecer valor de variable"
Configurar:
Variable: TipoCliente
Valor: Nuevo
Hacer clic en "+"
Seleccionar "Enviar un mensaje"
Escribir:
   ¡Bienvenido {NombreUsuario}! 

   Es un placer que consideres nuestros servicios bancarios. Estoy aquí para ayudarte a conocer todo lo que podemos ofrecerte.

- Guardar cambios en el tópico de Saludo:
Hacer clic en "Guardar"
- Modificar tópico existente para usar variables globales:
Ir al tópico "Consulta de Saldo" creado en el Paso 3
En el primer mensaje del tópico (antes de pedir el número de cuenta), editar el texto:
Cambiar de:
    Claro, te ayudaré a consultar tu saldo. 💳
A:
    Claro {NombreUsuario}, te ayudaré a consultar tu saldo. 💳
Hacer clic en "Guardar"
- Crear un tópico de prueba para verificar contexto:
Hacer clic en "+ Nuevo tópico"
Nombre: Verificación de Contexto
Descripción: Tópico de prueba para verificar variables globales
Agregar frases de activación:
mostrar mi información
verificar contexto
quién soy
- Mostrar información de contexto:
En el lienzo, hacer clic en "+"
Seleccionar "Enviar un mensaje"
Escribir:
    **Información de Contexto**

    Nombre: {NombreUsuario}
    Tipo de Cliente: {TipoCliente}
    Número de Cliente: {NumeroCliente}

    Esta información se mantiene durante toda tu sesión.
Hacer clic en "Guardar"

Salida Esperada:

Tres variables globales creadas: NombreUsuario, TipoCliente, NumeroCliente
Tópico de Saludo modificado para capturar y almacenar nombre y tipo de cliente
Variables globales correctamente asignadas según respuestas del usuario
Tópico de Consulta de Saldo personalizado con nombre del usuario
Tópico de verificación que muestra el contexto almacenado
Verificación:

En el panel "Probar el agente", iniciar una nueva conversación
El agente debe preguntar automáticamente el nombre
Responder con un nombre (ej: "María")
Responder si es cliente existente (ej: "Sí")
Escribir: consultar saldo y verificar que el mensaje incluye el nombre
Escribir: mostrar mi información y verificar que se muestran todos los valores de variables globales
Reiniciar la conversación y verificar que las variables se reinician correctamente
---
##  Recursos

- https://learn.microsoft.com/microsoft-copilot-studio/
- https://learn.microsoft.com/power-platform/
- https://learn.microsoft.com/ai-builder/

---

¡Felicitaciones por completar el laboratorio!
