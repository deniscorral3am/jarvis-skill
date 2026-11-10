---
name: jarvis
description: Te monta tu propio Jarvis en un fin de semana - un asistente de IA que vive 24/7 en un ordenador viejo o en un servidor (VPS), piensa con el modelo que elijas (Claude, ChatGPT, Gemini), tiene manos y memoria (con un arnés de código abierto como OpenClaw o Hermes Agent), sabe quién eres y qué herramientas pagas, está conectado a tu correo, tu WhatsApp, tus documentos y tu base de datos, tiene skills para tus tareas repetitivas (facturas, documentos, entrega a clientes) y trabaja solo con tareas programadas mientras duermes. Te guía en 7 pasos, uno cada vez. Úsala cuando digan /jarvis, «comenta JARVIS», «quiero mi Jarvis», «asistente de IA 24/7», «montar OpenClaw», «montar Hermes Agent» o «un agente que trabaje mientras duermo».
---

# /jarvis: tu Jarvis en un fin de semana, en 7 pasos

Al terminar, el usuario tiene un asistente que vive en una máquina encendida 24/7, con el modelo que eligió, con
manos (herramientas) y memoria, que sabe quién es, que está conectado a sus herramientas, que tiene skills para lo que
repite cada semana y que hace tareas programadas solo, avisándole por el chat que use.

Habla en español, cercano, corto y sin tecnicismos. **Un paso cada vez** y una pregunta cada vez. Ejecuta tú los
comandos cuando puedas; si estás en un chat sin terminal (ChatGPT, Claude.ai), dale los comandos uno a uno y pídele
que te pegue lo que salga. **Nunca le pidas contraseñas ni claves en el chat**: se escriben en el asistente de
instalación o en el archivo de configuración, en su máquina.

`<skill>` = la carpeta de esta skill. Plantilla del perfil: `<skill>/plantillas/perfil.md`.

## Antes de empezar: elegir el arnés (2 preguntas)

1. **¿Por dónde quieres hablarle?** (WhatsApp, Telegram, Slack, Discord, iMessage…).
2. **¿Qué te importa más?** Que esté en muchos canales y en tus dispositivos → **OpenClaw**. Que aprenda solo,
   cree sus propias skills con la experiencia y programe tareas con frases normales → **Hermes Agent**.

Los dos son gratis, de código abierto (licencia MIT) y valen cualquiera de los 3 modelos. Si duda, OpenClaw (lo
usamos para el empleado de IA en WhatsApp). Lo que hace cada uno, según su propia documentación:

| | OpenClaw (github.com/openclaw/openclaw) | Hermes Agent (github.com/NousResearch/hermes-agent) |
|---|---|---|
| Instalar | `curl -fsSL https://openclaw.ai/install.sh \| bash` y después el asistente `openclaw onboard --install-daemon` | `curl -fsSL https://hermes-agent.nousresearch.com/install.sh \| bash` y después `hermes setup` |
| Modelo | Claude, Codex, modelos locales y otros proveedores (se cambian sin tocar lo demás) | El que quieras (OpenRouter, OpenAI, Nous Portal, tu propio servidor…); se cambia con `hermes model` |
| Canales | WhatsApp, Telegram, Slack, Discord, iMessage, Signal, Google Chat y más de 20 | Telegram, Discord, Slack, WhatsApp, Signal, correo y la terminal, desde un solo proceso |
| Memoria y skills | memoria, herramientas, skills y plugins (ClawHub) | memoria propia, crea skills solo tras tareas complejas y las mejora con el uso |
| Tareas programadas | `openclaw automations` (alias `openclaw cron`) | programador integrado: se le pide con frases («cada día a las 8…») |
| Dónde vive | portátil, servidor Linux o VPS (guías de Hetzner, DigitalOcean, Oracle Cloud, Raspberry Pi…) | portátil, VPS de unos 5 $ o servicios que hibernan cuando no trabaja |

No prometas nada que no salga en su documentación. Si un comando ha cambiado, mira su web (docs.openclaw.ai o
hermes-agent.nousresearch.com/docs) y sigue la versión actual.

## Paso 1. Su casa: dónde vive (24/7)

Tiene que estar encendido siempre para contestar y trabajar de noche. Dos opciones:

- **Un ordenador viejo** que tenga por casa (portátil o mini PC), enchufado y con internet, con Linux o macOS.
  Gratis, pero si se apaga o se va la luz, Jarvis se apaga.
- **Un servidor en la nube (VPS)**: una máquina alquilada que nunca se apaga, desde unos pocos euros al mes (Hetzner,
  DigitalOcean, Hostinger…; Oracle Cloud tiene una opción gratuita). Recomendado si quiere que funcione siempre.

Si elige VPS: Ubuntu, 2 GB de RAM como mínimo para empezar, y que entre por SSH. No le pidas la contraseña del
servidor: que se conecte él desde su terminal y te diga cuando está dentro.

## Paso 2. El cerebro: el modelo

ChatGPT, Claude o Gemini: el que ya pague o el que prefiera. Necesita **acceso por API** (o el inicio de sesión que
permita el arnés), que es distinto de la suscripción del chat. Explícaselo en una frase y dile dónde se saca la clave
(console.anthropic.com, platform.openai.com o aistudio.google.com). La clave la pega él **en el asistente de
instalación**, no en este chat. Avísale de que el uso por API se paga por consumo: que ponga un límite de gasto.

## Paso 3. El arnés: manos y memoria

Instala el arnés elegido con su comando (tabla de arriba) y completa su asistente de inicio (modelo, carpeta de
trabajo, canal). Comprueba que contesta: en OpenClaw, `openclaw gateway status` y `openclaw dashboard`; en Hermes,
`hermes` y `hermes doctor`. Mándale un mensaje de prueba y que conteste.

**Seguridad, antes de seguir:** que solo le hablen las personas que él apruebe (los dos traen emparejamiento o lista
de permitidos), que no lo exponga a internet sin leer su guía de seguridad y que trate como «no fiable» lo que entre
por mensajes de desconocidos. Las herramientas se ejecutan en su máquina: por eso mejor en una máquina dedicada.

## Paso 4. Enséñale quién eres

Rellena con él `<skill>/plantillas/perfil.md`: quién es, a qué se dedica, cómo habla, sus clientes tipo, sus horarios,
**qué herramientas usa y qué suscripciones paga** (para que Jarvis las use en vez de inventar otras) y lo que nunca
debe hacer sin preguntar (pagar, borrar, mandar algo a un cliente). Guárdalo donde el arnés lo lea siempre (en
OpenClaw, el espacio de trabajo del agente; en Hermes, su memoria o su perfil). Pregunta, no inventes: lo que no sepa
queda como PENDIENTE.

## Paso 5. Conéctalo a todo, hablándole

Uno cada vez, empezando por lo que más tiempo le quita:

- **WhatsApp / Telegram**: el canal para hablarle (si no lo hizo en el paso 3). En OpenClaw, WhatsApp va como
  dispositivo vinculado (WhatsApp Web), escaneando un QR. Mejor un número aparte para Jarvis.
- **Correo**: Gmail u otro (en OpenClaw hay automatizaciones con Gmail y correo IMAP; en Hermes, el correo es uno de
  sus canales). Empieza con permiso de leer y hacer borradores, no de enviar.
- **Documentos**: Google Drive o la carpeta donde los tenga.
- **Base de datos o CRM**: Google Sheets, Notion, Airtable, Supabase… lo que ya use. Con MCP o el conector que tenga.

Que lo conecte **pidiéndoselo a Jarvis con palabras** («conéctate a mi Gmail») y siguiendo lo que le diga el propio
arnés. Las claves y los permisos se dan en la pantalla de autorización de cada servicio, nunca en el chat. Después de
cada conexión, una prueba real («¿qué correos sin contestar tengo de hoy?»).

## Paso 6. Skills y mods para lo que repite

Pregúntale qué hace **todas las semanas igual**. Ejemplos: hacer facturas, preparar documentos o propuestas, el
onboarding y la entrega a un cliente, el resumen de una llamada, contestar las mismas preguntas. Por cada una:

1. Que se la explique a Jarvis una vez, paso a paso, con un ejemplo real.
2. Que Jarvis la guarde como skill (los dos arneses tienen skills; Hermes además las crea solo tras una tarea larga).
3. Probarla con un caso real y corregirla hasta que salga bien a la primera.

Empieza por 2-3 skills, no por 20.

## Paso 7. Tareas programadas: trabaja mientras duermes

Con él, elige 2-3 tareas que Jarvis haga solo y le avise por su canal. Ejemplos:

- Cada mañana a las 8: resumen de correos importantes, reuniones del día y lo que tiene pendiente.
- Cada noche: revisar leads nuevos y dejar los mensajes de seguimiento en borrador.
- Cada lunes: facturas pendientes de cobro y a quién reclamar.

En OpenClaw, con `openclaw automations` (crear, listar, ver ejecuciones). En Hermes, pidiéndoselo con una frase. Lanza
cada tarea una vez a mano para comprobar que funciona antes de dejarla programada.

## Al terminar

Resumen corto: dónde vive, qué modelo usa, qué arnés, qué sabe de él, a qué está conectado, sus skills y sus tareas
programadas con la hora. Y la regla de oro: **las primeras 2 semanas, que Jarvis prepare y él apruebe** (borradores,
no envíos). Cuando confíe, que le dé más permisos poco a poco.

## Reglas

- Nunca claves, contraseñas ni tokens en el chat ni en archivos que se compartan.
- Nada de enviar correos, mensajes a clientes, pagos o borrados sin su OK, al menos al principio.
- No inventes funciones de OpenClaw ni de Hermes: si no sabes si algo existe, míralo en su documentación.
- Si algo falla, el diagnóstico del arnés primero (`openclaw gateway status` / `hermes doctor`) y luego su guía.
