# Qué está comprobado

- 10/11/2026, leyendo sus repos y su documentación oficial:
  - **OpenClaw** (github.com/openclaw/openclaw, MIT): instalación `curl -fsSL https://openclaw.ai/install.sh | bash`,
    `openclaw onboard --install-daemon`, `openclaw gateway status`, `openclaw dashboard`; canales WhatsApp (WhatsApp
    Web, dispositivo vinculado), Telegram, Slack, Discord, iMessage, Signal, Google Chat y más; modelos Claude, Codex y
    locales como plugins; herramientas, skills y plugins (ClawHub); automatizaciones con `openclaw automations` (alias
    `openclaw cron`), webhooks, Gmail e IMAP; guías para servidor Linux y VPS; emparejamiento de desconocidos por
    defecto.
  - **Hermes Agent** (github.com/NousResearch/hermes-agent, MIT, de Nous Research): instalación
    `curl -fsSL https://hermes-agent.nousresearch.com/install.sh | bash`, `hermes setup`, `hermes model`,
    `hermes gateway`, `hermes doctor`; cualquier proveedor de modelos; Telegram, Discord, Slack, WhatsApp, Signal y
    correo; memoria, creación y mejora de skills; programador de tareas en lenguaje natural; corre en VPS.

## Sin probar todavía

- La instalación de punta a punta de cada arnés en un VPS limpio con esta skill (los comandos son los de su
  documentación; pueden cambiar).
- Las conexiones concretas de correo, Drive y CRM: dependen de la versión y de los plugins o MCP disponibles.
