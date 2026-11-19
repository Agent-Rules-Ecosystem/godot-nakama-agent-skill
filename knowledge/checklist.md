# Checklist de Auditoría — `$nakama:audit`

- [ ] Todas las llamadas `await` validan `is_exception()`.
- [ ] `socket.close()` y desconexión de señales en `_exit_tree()`.
- [ ] Sesión verificada/refrescada antes de reconectar.
- [ ] Opcodes de match definidos en `enum` (sin números mágicos).
- [ ] Mutaciones sensibles ejecutadas vía RPC autoritativo.
