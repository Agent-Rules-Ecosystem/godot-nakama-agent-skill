# Patrones — Nakama en Godot 4

## 1. Verificación Obligatoria de Excepciones
Toda respuesta asíncrona de Nakama (`NakamaSession`, `NakamaAPI.*`, `NakamaAsyncResult`) puede ser una excepción: validar siempre `if res.is_exception():`.

## 2. Opcodes Tipados en `enum`
Definir `enum MatchOpCode { STATE_SYNC = 1, PLAYER_INPUT = 2, MATCH_END = 3 }` y serializar payloads JSON/binarios compactos.

## 3. Reconexión con Backoff
Al recibir `socket.closed`, reconectar con backoff exponencial verificando primero si la sesión requiere `session_refresh_async()`.
