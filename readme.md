# N2 Bank

> Seu dinheiro. Sua chave. Seu ledger.

Cofre bancário local-first para Pix. Desktop (Tauri + Rust + React),
ledger double-entry imutável, cifrado com chave derivada do seu PIN.
100% gratuito, auditável e desenhado para sobreviver ao pior dia.

## O que ele faz
- Envia e recebe Pix via BaaS, com idempotência e reconciliação
- Mantém um ledger auditável no seu dispositivo (SQLCipher)
- Verifica cada resposta do BaaS (TLS pinning + HMAC)
- Exige confirmação nativa + biometria para operações sensíveis
- Nunca interpreta conteúdo remoto como HTML

## O que ele não faz
- Não custodia dinheiro
- Não confia no servidor por padrão
- Não funciona offline para envio (só para leitura)
- Não é multi-tenant

## Infra
- Backend: Cloudflare Workers + D1 (free tier, sem pausa)
- Desktop: Tauri + SQLCipher (local)
- Distribuição: GitHub Releases (assinado + minisign)
- Domínio: `n2bank.is-a.dev` → Pages/Workers
