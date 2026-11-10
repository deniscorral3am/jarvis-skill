# Tu Jarvis en un fin de semana: el prompt

Por Denís Corral · @deniscorralvillarraso en Instagram · [Sell Your AI](https://sellyourai.io)

Un asistente de IA que vive 24/7 en un ordenador viejo o en un servidor, piensa con el modelo que elijas, tiene manos
y memoria, sabe quién eres, está conectado a tu correo, tu WhatsApp y tus documentos, y hace tareas solo mientras
duermes. Copia el recuadro y pégalo en Claude, en ChatGPT o en el que uses. Te guía en 7 pasos, uno cada vez.

Funciona mejor en Claude Code (o en cualquier IA que pueda ejecutar comandos en tu ordenador). En un chat normal, la IA
te da los comandos y tú los pegas en tu terminal.

¿Quieres la versión completa? Instala la skill:
`git clone https://github.com/deniscorral3am/jarvis-skill ~/.claude/skills/jarvis` y escribe `/jarvis` en Claude Code.

---

```
Quiero montarme mi propio Jarvis este fin de semana: un asistente de IA que viva 24/7, con manos y memoria,
conectado a mis herramientas, que me conozca y que haga tareas solo mientras duermo. Guíame en estos 7 pasos, UNO
CADA VEZ, en español, corto y sin tecnicismos. Hazme una sola pregunta cada vez y no pases al siguiente paso hasta
que el anterior funcione. Si no puedes ejecutar comandos, dámelos de uno en uno y pídeme que te pegue lo que salga.
NUNCA me pidas contraseñas, claves ni tokens en este chat: dime dónde pegarlos (el asistente de instalación o el
archivo de configuración de mi máquina). No te inventes funciones ni comandos: si dudas, dime que lo mire en la
documentación oficial.

ANTES DE EMPEZAR · EL ARNÉS
Pregúntame por dónde quiero hablarle (WhatsApp, Telegram, Slack…) y qué me importa más, y recomiéndame uno:
- OpenClaw (github.com/openclaw/openclaw, gratis, MIT): asistente que vive en tu máquina y te habla por WhatsApp,
  Telegram, Slack, Discord, iMessage y más de 20 canales. Instalación: curl -fsSL https://openclaw.ai/install.sh | bash
  y después openclaw onboard --install-daemon. Tareas programadas con openclaw automations. Docs: docs.openclaw.ai
- Hermes Agent (github.com/NousResearch/hermes-agent, gratis, MIT): agente que aprende solo, crea y mejora sus skills
  con el uso, tiene memoria entre conversaciones y programador de tareas en lenguaje normal. Habla por Telegram,
  Discord, Slack, WhatsApp, Signal y correo. Instalación: curl -fsSL https://hermes-agent.nousresearch.com/install.sh | bash
  y después hermes setup. Docs: hermes-agent.nousresearch.com/docs

PASO 1 · SU CASA (24/7)
Ayúdame a elegir: un ordenador viejo que tenga en casa (gratis, pero si se apaga, se apaga Jarvis) o un servidor en
la nube, un VPS (Hetzner, DigitalOcean, Hostinger, Oracle Cloud tiene opción gratis). Si elijo VPS: Ubuntu, 2 GB de RAM
mínimo, y guíame para entrar por SSH desde mi terminal.

PASO 2 · EL CEREBRO
Ayúdame a elegir modelo (ChatGPT, Claude o Gemini) y explícame que el acceso por API no es lo mismo que la suscripción
del chat. Dime dónde saco la clave (platform.openai.com, console.anthropic.com o aistudio.google.com) y recuérdame
poner un límite de gasto. La clave la pego yo en el asistente de instalación, no aquí.

PASO 3 · EL ARNÉS: MANOS Y MEMORIA
Guíame para instalar el arnés elegido y completar su asistente de inicio (modelo, canal, carpeta de trabajo).
Comprueba que funciona (OpenClaw: openclaw gateway status y openclaw dashboard; Hermes: hermes y hermes doctor) y que
me contesta a un mensaje de prueba. Antes de seguir: que solo le puedan hablar las personas que yo apruebe, que no
lo exponga a internet sin leer su guía de seguridad y que trate como no fiable lo que llegue de desconocidos.

PASO 4 · QUE SEPA QUIÉN SOY
Hazme preguntas una a una y escribe mi perfil: quién soy, a qué me dedico, mis clientes, cómo hablo, mis horarios,
QUÉ HERRAMIENTAS USO Y QUÉ SUSCRIPCIONES PAGO, y lo que nunca debe hacer sin preguntarme (enviar a clientes, pagar,
borrar). Guárdalo donde el arnés lo lea siempre. Lo que no sepa, PENDIENTE; no lo inventes.

PASO 5 · CONÉCTALO A TODO, HABLÁNDOLE
Uno cada vez, empezando por lo que más tiempo me quita: mi canal (WhatsApp o Telegram; mejor un número aparte para
Jarvis), mi correo (al principio solo leer y hacer borradores, no enviar), mis documentos (Drive o mi carpeta) y mi
base de datos o CRM (Sheets, Notion, Airtable, Supabase…). Que lo conecte pidiéndoselo a Jarvis con palabras y
siguiendo lo que diga el arnés. Los permisos se dan en la pantalla de autorización de cada servicio. Después de cada
conexión, una prueba real.

PASO 6 · SKILLS PARA LO QUE REPITO
Pregúntame qué hago igual todas las semanas (facturas, documentos, propuestas, la entrega de mi servicio a clientes,
resúmenes de llamadas). Elegimos 2 o 3. Para cada una: se la explico a Jarvis una vez con un ejemplo real, la guarda
como skill y la probamos hasta que salga bien a la primera.

PASO 7 · TAREAS PROGRAMADAS (MIENTRAS DUERMO)
Elegimos 2 o 3 tareas que haga solo y me avise por mi canal: un resumen cada mañana (correos importantes, reuniones,
pendientes), seguimientos de leads cada noche en borrador, cobros pendientes cada lunes. Créalas con el programador
del arnés y lanza cada una una vez a mano para comprobar que funciona.

AL TERMINAR
Resúmeme dónde vive, qué modelo usa, a qué está conectado, sus skills y sus tareas con la hora. Y recuérdame la
regla: las 2 primeras semanas, Jarvis prepara y yo apruebo.

Empieza por el arnés.
```

---

OpenClaw y Hermes Agent son proyectos independientes de código abierto. ChatGPT es de OpenAI, Claude de Anthropic y
Gemini de Google. Los comandos son los de su documentación en noviembre de 2026: si cambian, manda la de cada proyecto.
