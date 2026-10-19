# Site do Lanche Digital

Site institucional do Lanche Digital, sistema de gestão para cantinas
escolares. Uma página estática, sem framework e sem etapa de build.

## Endereço

- Em produção: https://www.lanchedigital.com.br
- Enquanto o DNS não propaga: https://lanchedigital-site-production.up.railway.app

O domínio raiz, sem `www`, não é usado: o registro.br não aceita CNAME na
raiz e o Railway só oferece CNAME. O redirecionamento da raiz para o `www`
está pendente, e será feito pelo modo básico do painel do registro.br.

## Como abrir no computador

Duplo clique em `index.html`. Não precisa de servidor nem de instalar nada.

## Como publicar

Todo `push` na branch `main` dispara deploy automático no Railway, que serve
os arquivos com o Caddy na porta 8080. Não há etapa de build.

## Arquivos

| Arquivo | O que é |
|---|---|
| `index.html` | A página única. Todo o CSS e o JavaScript estão dentro dela. |
| `privacidade.html` | Política de privacidade, página independente. |
| `imagens/` | Logo normal e negativa, ilustração da cantina, favicon em SVG e ícones de aplicativo. |
| `favicon.ico` | Ícone da aba, nos tamanhos 16, 32 e 48. |
| `robots.txt` | Libera a indexação e aponta o sitemap. |
| `sitemap.xml` | Lista as duas páginas para os buscadores. |
| `site.webmanifest` | Dados para instalar o site como aplicativo no celular. |
| `CLAUDE.md` | Contexto do projeto para sessões de IA. |

## Decisões de arquitetura

1. Estático, sem framework e sem `package.json`. É uma página só, que não
   muda sozinha; um projeto Next.js aqui seria manutenção sem contrapartida.
2. CSS e JavaScript embutidos no `index.html`. Com um arquivo só, não há
   risco de uma peça subir sem a outra.
3. Sem Google Analytics, sem pixel, sem cookie. O site fala de dado de
   criança; rastreador ali seria contradição.
4. Repositório separado do sistema. O sistema tem cliente pagante em
   produção e não divide deploy com marketing.

## Lacuna conhecida

Os cabeçalhos de segurança `X-Content-Type-Options`, `X-Frame-Options`,
`Referrer-Policy` e `Permissions-Policy` não estão sendo enviados. Existia
um `vercel.json` com eles, escrito quando o destino era a Vercel; no Railway
ele era ignorado, e foi removido. Ativá-los exigiria substituir o Caddyfile
padrão do Railway, com risco de derrubar o site se feito errado.

O risco atual é baixo: a página não tem login, formulário, cookie nem dado
de usuário. Vale resolver quando o site ganhar qualquer uma dessas coisas.
