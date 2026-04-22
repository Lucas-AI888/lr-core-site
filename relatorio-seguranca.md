SECURITY AUDIT — lr-core-site.vercel.app
Data: 2026-04-22
Arquivo: index.html estático | Hospedagem: Vercel

═══════════════════════════════════════════════════

ALTO (corrigir antes de enviar para clientes):
- [ ] Links no Footer (Termos / Privacidade) apontam para "#", ou seja, são links mortos.
      → AÇÃO: Adicionar URLs reais das páginas correspondentes ou criar o modal de Termos.
- [ ] Número do WhatsApp (5511999999999) possui formato placeholder e necessita validação.
      → AÇÃO: Substituir para seu número comercial definitivo antes de começar ativamente o envio do link do portfólio a prospecções.
- [ ] Meta Tags para Redes Sociais (`og:image`, `og:title`, `og:description`) ausentes.
      → AÇÃO: Adicionar Tags de Open Graph no `<head>` para garantir um preview com ótima qualidade visual ao mandar a URL via WhatsApp.

MÉDIO:
- [ ] Ausência dos Headers de Segurança essenciais (`Content-Security-Policy`, `X-Content-Type-Options: nosniff` e `X-Frame-Options: DENY`).
      → RECOMENDAR: Criação de um `vercel.json` na raiz da aplicação com as políticas de roteamento seguras. 
- [ ] Redirecionamento da CDN de JS do projeto (cdnjs) sem SRI (Subresource Integrity).
      → RECOMENDAR: Adicionar preenchimento no atributo `integrity=""` e `crossorigin="anonymous"` para proteger a injeção do GSAP caso o provedor falhe.

BAIXA:
- [ ] Referrer-Policy e Permissions-Policy headers ausentes.
      → RECOMENDAR: Aplicar as restrições (`camera=()`, `geolocation=()`, etc) via `vercel.json`.

INFO (Aprovados!):
- [✓] CSS minificado, livre de dependências externas via CDN no projeto final (Hardened build CSS ✓).
- [✓] Proteção contra Tab-nabbing ativada (Todo `target="_blank"` contem corretament `rel="noopener noreferrer"`) ✓
- [✓] HTTPS com certificado SSL válido provisionado e transporte via TLS (Vercel) ✓
- [✓] Strict-Transport-Security ativo nativamente na Vercel  ✓
- [✓] Estrutura HTML limpa, livre de XSS por aval dos scripts inline lidos ✓
- [✓] Proteção de Dados: zero senhas, keys ou segredos expostos no Source-code ✓

═══════════════════════════════════════════════════

VEREDICTO: ⚠️ DEPLOY CONCLUÍDO, COM RESSALVAS. 

Motivo: A ausência de OpenGraph prejudicará severamente o review do link por WhatsApp (que é sua finalidade), links mortos do rodapé podem perder a credibilidade pro negócio.
Ação: Recomendo adequar os MetaOGs, incluir os links no rodapé e acrescentar um arquivo `vercel.json` no repósitório para mitigar injestão de rotas.

Você pode usar as evidências de validação listadas em "INFO" como laudo de auditoria automatizada nas objeções do cliente sobre segurança.
