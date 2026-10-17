{{- $name := .File.ContentBaseName -}}
{{- if eq $name "index" -}}
  {{- $name = path.Base .File.Dir -}}
{{- end -}}
+++
title = '{{ replace $name "-" " " | title }}'
date = '{{ .Date }}'
draft = true
description = '' # Uma frase sobre o texto, usada em buscas e compartilhamentos.
tags = [] # Exemplo: ['vida', 'tecnologia']
showReadingTime = true

# Capa opcional: copie a imagem para esta pasta e descomente as quatro linhas.
# [cover]
# image = 'capa.jpg'
# alt = 'Descreva o que aparece na imagem.'
# relative = true
+++

<!--
Comece por uma cena, uma pergunta ou algo que você viveu.
Escreva sua abertura aqui, fora deste comentário.
Os títulos abaixo são sugestões: adapte ou apague conforme o texto pedir.
-->

## O que aconteceu

<!-- Conte a experiência ou apresente a questão com exemplos concretos. -->

## O que isso me fez pensar

<!-- Desenvolva sua interpretação, incluindo dúvidas e outros pontos de vista. -->

## O que fica

<!-- Termine com uma descoberta, uma pergunta ou uma imagem que faça sentido. -->

<!--
IMAGENS NO TEXTO
Copie a imagem para a mesma pasta deste index.md.
Depois, cole a linha abaixo no ponto desejado, fora deste comentário:

![Descrição da imagem](foto.jpg)

LINKS E REFERÊNCIAS
Use links junto da ideia que eles ajudam a explicar:

[Nome da referência](https://example.com)

ANTES DE PUBLICAR
- Revise título, descrição, texto e imagens na prévia do Hugo.
- Remova as seções que não usar e confira a data de publicação.
- Mude draft para false e envie o texto e as imagens no mesmo commit.
-->
