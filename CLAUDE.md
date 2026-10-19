# CLAUDE.md — Lanche Digital (site institucional)

Atue como Engenheiro de Software Sênior, Especialista em Arquitetura.

## O que é este projeto

Site institucional do Lanche Digital, um sistema de gestão para cantinas
escolares. O site vende o sistema para donos de cantina. Não é o sistema
em si — o sistema é outro projeto, noutro repositório.

## Pasta e publicação

- Repositório: `C:\Users\Thiago\projetos\lanchedigital-site`
- GitHub: `robsonlopespb1-ux/lanchedigital-site`, branch `main`
- Publicação: Railway, projeto próprio, servidor estático (Caddy, porta
  8080). Todo push na `main` dispara deploy automático.
- Endereço atual: `lanchedigital-site-production.up.railway.app`
- Endereço final: `www.lanchedigital.com.br` (DNS ainda não propagado)

## JAMAIS TOCAR

`C:\Users\Thiago\projetos\Cantina` é o repositório do SISTEMA, com cliente
pagante em produção. Não leia, não altere, não rode git nele. Se algum
pedido parecer envolver essa pasta, PARE e pergunte.

## Decisões de arquitetura já tomadas — não propor alternativas

1. O site é ESTÁTICO. Nada de Next.js, React, Vite, Astro ou qualquer
   framework. Não criar `package.json`. Não instalar dependências.
2. Todo o CSS e o JavaScript ficam dentro do próprio `index.html`. Não
   separar em arquivos.
3. O endereço é com `www`. O domínio raiz não pode receber CNAME no
   registro.br, então não tente configurar a raiz.
4. Sem Google Analytics, sem pixel de rastreamento, sem cookie. O site
   fala de dado de criança; rastreador ali seria contradição.

## Arquivos

- `index.html` — a página única, com todo o CSS e o JS embutidos
- `privacidade.html` — política de privacidade, página independente
- `imagens/` — `logo.png`, `logo-negativo.png`, `favicon.svg`,
  `compartilhar.png` e os ícones de aplicativo
- `favicon.ico`, `robots.txt`, `sitemap.xml`, `site.webmanifest`,
  `vercel.json`

## A marca

- Azul profundo `#0B2D41` (texto, símbolo, faixas escuras)
- Âmbar `#F5A623` (só como forma e botão, NUNCA como cor de texto sobre
  fundo claro — não passa em contraste)
- Fontes: Archivo nos títulos, Plus Jakarta Sans no texto, Caveat só no
  bloco do caderno de fiado. Vêm do Google Fonts.
- As cores são declaradas como variáveis no `:root`, com versões para tema
  claro e escuro. Use sempre as variáveis, nunca um hexadecimal solto.

## Estrutura da página

A página é uma sequência de faixas de largura total, cada uma com um
`<div class="dentro">` que limita a largura e dá a margem lateral. Na
ordem: barra de contato, cabeçalho fixo, capa, promessas, cena ilustrada,
benefícios, como funciona, caderno de fiado, recursos, segurança,
dúvidas, chamada final, rodapé.

## Como o dono do projeto trabalha com você

O desenho do site é decidido fora daqui. Você vai receber instruções de
alteração com o trecho EXATO a substituir e o trecho EXATO que entra no
lugar. Sua função é aplicar a troca com precisão, não melhorar por conta
própria. Se achar que algo ficou ruim, avise no relatório em vez de
corrigir sozinho.

## Regras permanentes

- NUNCA comitar e NUNCA fazer push. O commit é sempre do dono do projeto,
  por último.
- Sempre ler e mapear os arquivos ANTES de alterar qualquer linha.
- No PowerShell, nunca usar `&&`; comandos separados por `;`.
- Nunca `git add .`; listar os arquivos um a um.
- Quando entregar comandos de Git, mandar todos de uma vez num único
  bloco de PowerShell, uma linha por comando, com o resultado esperado
  explicado FORA do bloco.
- Não validar interface abrindo navegador. A conferência visual é do dono
  do projeto.

## Estado atual (19/10/2026)

O site está no ar e funcionando. Os dois últimos commits foram o endereço
com www, a política de privacidade e os efeitos de rolagem. Está pendente
uma alteração na capa e a inserção de uma imagem.
