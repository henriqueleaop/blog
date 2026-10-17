# Obscura

Blog pessoal feito com Hugo e o tema PaperMod, publicado no GitHub Pages.

## Preparação

Abra `C:\Projects\pessoal\blog` no VS Code. Para criar posts automaticamente e
visualizar o blog no computador, instale o
[Hugo Extended](https://gohugo.io/installation/windows/) (versão 0.146.0 ou superior,
exigida pelo tema atual). Confirme no terminal com `hugo version`.

Se estiver clonando o projeto em outro computador, baixe também o tema:

```powershell
git submodule update --init --recursive
```

Execute os comandos abaixo no terminal da pasta do projeto.

## Criar um post

```powershell
hugo new content posts/nome-do-post
```

Use um nome curto, com hífens, sem espaços nem acentos. Esse comando usa o modelo
em `archetypes/posts/index.md` e cria uma pasta com o texto:

```text
content/posts/nome-do-post/
├── index.md
├── foto.jpg       (adicione quando precisar)
└── capa.jpg       (opcional)
```

Abra o `index.md`, ajuste o título e escreva. O modelo começa com `draft = true`,
preenche a data automaticamente e inclui sugestões de estrutura para um ensaio,
relato ou reflexão. Os títulos são opcionais; você pode escrever sem seções.
As orientações entre `<!--` e `-->` são comentários e não aparecem para o leitor.

No cabeçalho:

- `title`: título exibido no blog.
- `date`: data do post. Datas futuras ficam fora da publicação até uma nova
  geração do site após essa data; o deploy atual não tem agendamento.
- `draft`: mantenha `true` enquanto escreve; use `false` para publicar.
- `description`: uma frase sobre o texto para buscas e compartilhamentos.
- `tags`: assuntos do texto, por exemplo `['vida', 'tecnologia']`.

Para criar manualmente, faça a pasta e o `index.md` no VS Code. Use este cabeçalho
e escreva abaixo dele, substituindo título e data:

```toml
+++
title = 'Título do seu texto'
date = '2026-10-17'
draft = true
description = ''
tags = []
+++
```

## Adicionar imagens

Copie as imagens para a mesma pasta do `index.md` e insira no texto:

```markdown
![Uma descrição do que aparece na foto](foto.jpg)
```

O texto entre colchetes descreve a imagem para leitores de tela. Para uma legenda
visível, use o recurso `figure` do Hugo:

```text
{{< figure src="foto.jpg" alt="Uma descrição da foto" caption="Legenda e créditos da imagem." >}}
```

Para exibir uma capa no topo do post e na listagem, descomente o bloco `[cover]`
do modelo e ajuste `image` e `alt`. Mantenha `relative = true` para que a imagem
da pasta também seja referenciada corretamente nos metadados de compartilhamento.

Prefira nomes simples, como `caminhada-ao-entardecer.jpg`, e confira maiúsculas e
minúsculas. Reduza fotos muito grandes antes de adicioná-las. Imagens próprias do
post ficam na pasta dele; não edite a pasta `public`, que é gerada pelo Hugo.

## Revisar

```powershell
hugo server -D
```

Abra o endereço exibido no terminal. O `-D` inclui rascunhos apenas nessa prévia.
Salve no VS Code para ver as alterações no navegador. Para visualizar também um
post com data futura, use `hugo server -D -F`. Encerre a prévia com `Ctrl+C`.

O VS Code também oferece uma prévia básica com `Ctrl+Shift+V`, mas ela não mostra
o visual do PaperMod nem interpreta recursos como `figure`.

## Publicar

1. Revise o texto, os links e as imagens na prévia do Hugo.
2. Confira título e data; altere `draft` para `false`.
3. Pelo controle de versão do VS Code, revise e inclua o texto e suas imagens.
4. Faça commit e push para `main`.
5. Confira o resultado na [aba Actions](https://github.com/henriqueleaop/blog/actions).

O workflow `.github/workflows/hugo.yml` gera o site e publica no GitHub Pages
quando recebe alterações na `main`. O arquivo `.github/hugo.yml`, fora da pasta
de workflows, não é executado como automação.

Site configurado: [Obscura](https://henriqueleaop.github.io/blog/).
