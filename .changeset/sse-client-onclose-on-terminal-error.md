---
'@modelcontextprotocol/client': patch
---

`SSEClientTransport` now fires `onclose` when a connected SSE stream ends for good, for example when the reconnect is answered with a 503 or with a 401 that `onUnauthorized` cannot fix. Before, only `onerror` fired and the client stayed connected to a closed stream. `close()` fires `onclose` only once.
