# Jarvis · tu asistente de IA 24/7 en un fin de semana

Un asistente que vive en un ordenador viejo o en un servidor, piensa con el modelo que elijas (Claude, ChatGPT o
Gemini), tiene manos y memoria, sabe quién eres, está conectado a tus herramientas y trabaja solo mientras duermes.
Esta skill te lo monta en 7 pasos, uno cada vez, con un arnés de código abierto: OpenClaw o Hermes Agent.

| Paso | Qué hace |
|---|---|
| 1 · Su casa | Un ordenador viejo o un servidor en la nube (VPS) encendido 24/7 |
| 2 · Cerebro | ChatGPT, Claude o Gemini, el modelo que elijas |
| 3 · Arnés | Manos (herramientas) y memoria: OpenClaw o Hermes Agent |
| 4 · Quién eres | Tu perfil, tus herramientas y lo que pagas, para que no invente |
| 5 · Conéctalo | Correo, WhatsApp, documentos y base de datos, pidiéndoselo con palabras |
| 6 · Skills | Facturas, documentos, entrega a clientes: lo que repites cada semana |
| 7 · Tareas programadas | Lo que hace solo mientras duermes y te avisa por el chat |

Hecha por Denís Corral · [@deniscorralvillarraso](https://instagram.com/deniscorralvillarraso) · [Sell Your AI](https://sellyourai.io)

## Instalación

```bash
git clone https://github.com/deniscorral3am/jarvis-skill ~/.claude/skills/jarvis
```

Abre Claude Code y escribe `/jarvis`.

¿Usas ChatGPT u otro? Copia el prompt de [`PROMPT.md`](PROMPT.md) y pégalo.

## Qué necesitas

- Un ordenador que pueda estar siempre encendido, o un VPS (desde unos pocos euros al mes).
- Acceso por API a un modelo (OpenAI, Anthropic o Google), que se paga por uso. Pon un límite de gasto.
- Un fin de semana.

## Bueno saber

- [OpenClaw](https://github.com/openclaw/openclaw) y [Hermes Agent](https://github.com/NousResearch/hermes-agent) son
  gratis, de código abierto (MIT) y no son nuestros. La skill sigue su documentación y no les añade nada.
- Las claves nunca se pegan en el chat: van en el asistente de instalación de cada herramienta.
- Las primeras semanas, que Jarvis prepare y tú apruebes (borradores, no envíos).

## Licencia

MIT
