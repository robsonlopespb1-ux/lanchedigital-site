# Site institucional — Lanche Digital

Site de apresentação do **Lanche Digital**, sistema de gestão para cantina escolar.
Publicado em **https://lanchedigital.com.br**.

É um site **estático**: um único `index.html`, imagens, favicon, manifesto, `robots.txt` e
`sitemap.xml`. Não há build, framework, `package.json` nem dependências — o que está aqui é
exatamente o que o navegador recebe.

O **sistema** (a aplicação que as cantinas usam) é outro projeto, em outro repositório, e
responde em `app.lanchedigital.com.br`. Este repositório é só a vitrine.

## Estrutura

```
index.html          página única do site
favicon.ico         ícone clássico (48×48)
site.webmanifest    nome, cores e ícones para "adicionar à tela inicial"
robots.txt          libera a indexação e aponta o sitemap
sitemap.xml         lista a página para os buscadores
imagens/            logo, logo negativo, favicon SVG, ícones de app e imagem de compartilhamento
vercel.json         cabeçalhos de segurança enviados pela Vercel (não afeta o conteúdo)
```

## Como abrir localmente

Não precisa de servidor: basta abrir o `index.html` no navegador (clique duplo). As fontes
vêm do Google Fonts, então é preciso estar conectado à internet para vê-las; sem conexão o
site abre com a fonte padrão do sistema.

## Como publicar

A publicação é automática pela **Vercel**: todo `git push` na branch `main` gera um deploy
novo. Não há comando de build — a Vercel serve os arquivos como estão.

Para alterar o site: edite o `index.html` (ou as imagens), confira no navegador, faça o
commit e o push. Em um ou dois minutos a versão nova está no ar.

## Domínio

`lanchedigital.com.br` está registrado no registro.br e aponta para a Vercel. O `www` também
resolve e é redirecionado para o domínio sem `www`. Os registros de DNS são configurados no
painel do registro.br; o certificado HTTPS é emitido e renovado pela própria Vercel.
