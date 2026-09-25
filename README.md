# Riotec Mercado Livre OAuth

Repositório público destinado exclusivamente ao callback OAuth da integração desktop **Riotec / Mercado Livre**.

## GitHub Pages

URL base prevista:

`https://pdrxc1989-png.github.io/riotec-mercadolivre-oauth/`

Callback OAuth:

`https://pdrxc1989-png.github.io/riotec-mercadolivre-oauth/callback.html`

## Fluxo

1. O sistema Riotec gera `state`, `code_verifier` e `code_challenge` (PKCE).
2. O sistema abre a autorização do Mercado Livre no navegador.
3. O Mercado Livre redireciona para `callback.html`.
4. A página recebe apenas `code` e `state`.
5. A página encaminha os parâmetros para:
   `http://127.0.0.1:8765/mercadolivre/callback`
6. O aplicativo Riotec valida o `state` e troca o código por tokens usando o `code_verifier`.

## Segurança

**Nunca publicar neste repositório:**

- Client Secret
- Access Token
- Refresh Token
- code_verifier
- senhas
- certificados
- chaves privadas
- qualquer credencial da Riotec ou do Mercado Livre

A página de callback não armazena tokens nem credenciais.
