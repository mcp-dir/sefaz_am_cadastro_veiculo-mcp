---
name: sefaz_am_cadastro_veiculo-mcp
description: Skill da REST API do SEFAZ AM: Cadastro de Veículo (Outra UF) na MCP.AI: 1 endpoint em /api/sefaz_am_cadastro_veiculo. SEFAZ AM: Cadastro de Veículo (Outra UF), consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# SEFAZ AM: Cadastro de Veículo (Outra UF) — REST API skill

Você tem acesso à **SEFAZ AM: Cadastro de Veículo (Outra UF)** REST API na MCP.AI.

> SEFAZ AM: Cadastro de Veículo (Outra UF), consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/sefaz_am_cadastro_veiculo
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/sefaz_am_cadastro_veiculo/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"placa":"...","renavam":"...","dut":"...","uf_origem":"...","chassi":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/sefaz_am_cadastro_veiculo/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `sefaz_am_cadastro_veiculo_consultar`

SEFAZ AM: Cadastro de Veículo (Outra UF), consulta em fonte oficial. _(POST /api/sefaz_am_cadastro_veiculo/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `placa` | string | Sim | Parâmetro de consulta "placa". |
| `renavam` | string | Sim | Parâmetro de consulta "renavam". |
| `dut` | string | Sim | Parâmetro de consulta "dut". |
| `uf_origem` | string | Sim | Parâmetro de consulta "uf_origem". |
| `chassi` | string | Sim | Parâmetro de consulta "chassi". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_sefaz_am_cadastro_veiculo` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
