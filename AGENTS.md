---
name: godot-nakama-agent-skill
description: Nakama client/session lifecycle, token refresh, realtime sockets, authoritative matches, RPCs and clean socket teardown in Godot 4.
---

# Godot 4 Nakama Multiplayer Agent Skill — Directiva de Habilidad

## Bootstrap de la Habilidad

Al detectar el trigger `$nakama` o archivos del dominio, cargar en orden:
1. `.skill/godot-nakama-agent-skill/SKILL.md`
2. `.skill/godot-nakama-agent-skill/core/commands.md`
3. `.skill/godot-nakama-agent-skill/core/brain.md`
4. `.skill/godot-nakama-agent-skill/core/path_map.md`

## Reglas Canónicas

1. **Cerrar sockets en `_exit_tree()`**: Desconectar señales y cerrar `NakamaSocket` limpiamente al salir o cambiar de escena.
2. **Refrescar sesión JWT antes de expirar**: Verificar `session.is_expired()` / `session.would_expire_in(...)` y llamar `session_refresh_async()`.
3. **Tipado estático GDScript 2.0 y `snake_case`**: Validar siempre `result.is_exception()` antes de leer payloads de Nakama.
4. **Autoridad en servidor para economía/combate**: Usar RPCs del servidor Nakama para recompensas, compras y validación de estado crítico.
5. **Configuración por entorno**: Nunca hardcodear IP/puertos de producción en escenas; inyectar desde configuración de entorno.
6. **Inviolabilidad de `.skill/`**: Nunca editar archivos dentro de `.skill/godot-nakama-agent-skill/` desde el proyecto cliente; registrar mejoras en `overview/learning.md` vía `$learnskill godot-nakama-agent-skill [propuesta]`.
