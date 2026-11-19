# Plantilla Canónica — Llamada RPC Segura en Nakama

```gdscript
func call_server_rpc(rpc_id: String, payload: Dictionary) -> Dictionary:
	if session == null or session.is_expired():
		return {}
	var res: NakamaAPI.ApiRpc = await client.rpc_async(session, rpc_id, JSON.stringify(payload))
	if res.is_exception():
		push_error("RPC %s failed: %s" % [rpc_id, res.get_exception().message])
		return {}
	var parsed: Variant = JSON.parse_string(res.payload)
	return parsed if parsed is Dictionary else {}
```
