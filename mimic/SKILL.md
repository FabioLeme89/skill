---
name: mimic
description: Engenharia reversa visual de um site a partir da URL. Extrai o design system verificável (cores, tipografia, espaçamentos, raios, sombras, gradientes, animações, breakpoints) direto do HTML/CSS e de screenshots, e gera DESIGN.md, tokens.css, components.md e uma implementação de referência. Use quando o usuário pedir para clonar, copiar, replicar ou extrair o design system de um site, ou citar "mimic".
---

# Mimic — engenharia reversa visual de um site

Regra central: **não invente propriedades que possam ser verificadas**. Todo valor documentado deve vir do CSS baixado, do DOM renderizado ou de screenshot. O que não foi verificado vai marcado como `não verificado`.

## 1. Coleta (verificável)
Trabalhe em um diretório novo e vazio (scratchpad), nunca dentro do projeto.
1. `curl -sL -A "Mozilla/5.0" -o page.html <url>` e liste os `<link rel=stylesheet>`; baixe cada CSS.
2. DOM renderizado (JS executado): `chrome --headless=new --virtual-time-budget=20000 --dump-dom <url> > dom.html`.
   Chrome fica em `C:\Program Files\Google\Chrome\Application\chrome.exe`.
3. Screenshots desktop e mobile: `--screenshot=<caminho WINDOWS absoluto>` (use `cygpath -w` no Git Bash; caminho relativo dá "Acesso negado"). Desktop 1440 de largura; mobile 390 (o headless pode impor largura mínima, confirme com `@media` do CSS).
4. Concatene todos os `<style>` do `dom.html` em `all.css` e analise com Python (`python -I`).

## 2. Extração
Conte ocorrências (as mais frequentes são o sistema; as raras são ruído de plugin):
- cores HEX/rgb, custom properties (`--*`), `font-family`, `font-size` (inclusive `clamp`/`cqw`), `font-weight`, `line-height`
- `border-radius`, `box-shadow`, `backdrop-filter`, `linear/radial-gradient`
- `transition`, `@keyframes` (copie o corpo), `prefers-reduced-motion`
- `@media` (breakpoints reais), `max-width` de container, `gap`/`padding` recorrentes
- regras dos componentes (`btn`, `card`, `tab`, `accordion`...) com dimensões

Ignore cores de presets do WordPress/Gutenberg e de plugins (cookie banner, WhatsApp) salvo se fizerem parte da marca.

## 3. Análise visual
Leia os screenshots seção por seção (hero, prova social, abas, destaques, cards, banner, depoimento, FAQ, footer) e, para cada uma, registre estrutura, grid e comportamento mobile. Interações vêm do CSS (`:hover`, transitions) e do JS carregado, não de suposição.

## 4. Entregáveis (na pasta pedida pelo usuário; padrão `docs/design/<site>/`)
- `DESIGN.md`: princípios, paleta, tipografia, espaçamento, raios, sombras, gradientes, animações, breakpoints, seções. Cada valor com a fonte (`all.css`, variável, ou "screenshot").
- `tokens.css`: apenas `:root { --... }` com valores verificados.
- `components.md`: cada componente reutilizável com anatomia, medidas, estados e variantes.
- Implementação de referência: componentes reutilizáveis na stack do projeto, consumindo `tokens.css`.

## 5. Comparação e correção
Renderize a implementação com o mesmo Chrome headless e mesmas larguras, compare lado a lado com o original, liste as diferenças e corrija. Repita até as diferenças restantes serem só de conteúdo/imagens. Diga honestamente o que não conseguiu igualar.

## Cuidados
- Copie estrutura e tokens, não ativos protegidos (logos, fotos, textos de marca): use placeholders.
- Se o projeto tiver `AGENTS.md`/`CLAUDE.md`, siga as convenções da stack antes de escrever código.
