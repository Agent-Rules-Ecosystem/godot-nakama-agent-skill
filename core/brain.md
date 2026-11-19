# Brain — Godot 4 Nakama

- **Authoritative vs Relayed**: Juegos competitivos o con economía -> Authoritative Match (servidor valida opcodes); co-op casual -> Relayed Match.
- **Storage vs RPC**: Lectura de perfil/config -> Storage Engine; mutación de inventario/ranking -> RPC en servidor.
- **Auditoría**: `$nakama:audit` inspecciona `scripts/autoloads/nakama_manager.gd` y `scripts/multiplayer/`.
