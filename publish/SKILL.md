---
name: publish
description: Versiona e gera o ZIP de publicacao da Oferta 2026 (Git commit + tag + PRONTO-PARA-UPLOAD.zip). Use quando o usuario pedir para publicar, atualizar a oferta no ar, subir uma nova versao ou gerar um novo ZIP.
---

# Publicar Oferta 2026

Este projeto usa Git + um arquivo `VERSION` (semver) para rastrear cada publicacao.
O upload para a hospedagem/WordPress continua manual - este fluxo so prepara o pacote versionado.

## Passos

1. Rode `git status` no diretorio do projeto para ver o que mudou desde a ultima publicacao.
2. Se nao houver mudancas em `index.html`, `css/`, `js/`, `assets/` ou `LEIA-ME.txt`, avise o usuario que nada mudou e pergunte se ele quer gerar o ZIP da versao atual mesmo assim.
3. Se houver mudancas, decida o tipo de bump com base no que mudou (ou pergunte ao usuario se nao for obvio):
   - `patch`: ajuste pequeno (texto, cor, preco, imagem)
   - `minor`: nova secao, novo bonus, nova funcionalidade
   - `major`: redesign ou mudanca estrutural grande
4. Escreva um resumo curto e claro da mudanca (1 linha, em portugues) para entrar no changelog.
5. Rode o script:
   ```
   powershell -File scripts\publish.ps1 -Bump <patch|minor|major> -Message "<resumo>"
   ```
6. Informe ao usuario a nova versao publicada e o caminho do `PRONTO-PARA-UPLOAD.zip`, lembrando que o upload para a hospedagem ainda precisa ser feito manualmente.

Nunca faca `git push` ou upload automatico - isso e sempre uma decisao do usuario.
