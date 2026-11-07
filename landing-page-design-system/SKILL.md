---
name: landing-page-design-system
description: Use this skill when designing, building, or reviewing the visual structure of a landing page / sales page / marketing site — layout, typography scale, spacing rhythm, breakpoints, button sizing, card/component dimensions. Provides a reusable, brand-agnostic sizing system (font sizes per breakpoint, spacing scale, border-radius, container widths, button/icon/avatar dimensions) extracted from a proven mobile-first responsive page. Colors, fonts, copy and imagery stay fully open per project. Trigger on: "landing page", "design system", "dimensionamento", "espaçamento", "tamanho de fonte", "breakpoints", "responsivo", "botões", "grid responsivo", "hero section", "seção", "CTA".
---

# Sistema de Dimensionamento para Landing Pages

Sistema estrutural de UI/UX (escala, não estilo) para construir páginas de vendas / landing
pages responsivas e mobile-first. Define **tamanhos, espaçamentos e proporções** — nunca cores,
fontes de marca, tom de voz ou conteúdo. Isso mantém a mesma "mão" de dimensionamento entre
projetos diferentes, mesmo quando a identidade visual muda completamente.

## Princípio central: separar ESTRUTURA de MARCA

Toda página construída com esta skill tem duas camadas independentes:

| Camada | O que inclui | Está fixo nesta skill? |
|---|---|---|
| **Estrutura** | escala de espaçamento, escala tipográfica fluida, breakpoints, raios de borda, dimensões de botão/ícone/avatar, grid responsivo | Sim — reutilize sempre |
| **Marca** | paleta de cores, família tipográfica, logotipo, imagens, copy, tom de voz, animações de marca | Não — decida por projeto |

Ao iniciar um projeto novo, pergunte (ou receba) os inputs de marca; nunca invente cores ou
fontes definitivas por conta própria. Aplique-os sobre o esqueleto estrutural abaixo.

Antes de escrever qualquer CSS, copie `reference/tokens.css` para o projeto e preencha apenas os
blocos marcados `/* BRAND */`. Os blocos `/* STRUCTURE */` já vêm prontos.

## 1. Breakpoints

Mobile-first: escreva o CSS base para mobile e adicione regras em `min-width` para telas maiores.

| Nome | min-width | Uso |
|---|---|---|
| Mobile | 0 (base) | 1 coluna, CTA empilhado, imagens full-bleed permitidas |
| Tablet | `640px` | 2 colunas em grids, CTA em linha |
| Desktop | `900px` | 3–4 colunas, hero em grid 2 colunas (`1.1fr 0.9fr`) |
| Wide (opcional) | `1200px` | Apenas se o conteúdo pedir mais densidade; raramente necessário |

Regra prática de colunas por breakpoint num grid de cards:

- Mobile: `1fr`
- ≥640px: `repeat(2, 1fr)`
- ≥900px: `repeat(3, 1fr)` (ou `repeat(4, 1fr)` para itens pequenos, ex. badges de persona)

Use `max-width: 899px` para overrides específicos de mobile que não podem ser resolvidos com
`clamp()` (ex. reposicionar uma imagem full-bleed, inverter ordem de blocos).

## 2. Container e largura

```
--maxw: 1140px;          /* largura máxima do conteúdo */
--maxw-narrow: 760px;    /* colunas de texto / seções de leitura */
--maxw-card: 600px;      /* cards de oferta / CTA final */
padding-inline: 24px;    /* respiro lateral do container em qualquer largura */
```

## 3. Escala de espaçamento (base 8pt)

Nunca use valores de margin/padding fora desta escala (exceto sub-escala de componentes na
seção 6). Isso é o que garante consistência vertical entre seções.

```
--s-1:  8px   /* gap entre ícone e texto, selos pequenos */
--s-2:  16px  /* gap padrão entre itens inline, margem de eyebrow */
--s-3:  24px  /* gap de grid entre cards, padding lateral do container */
--s-4:  32px  /* padding interno de cards, margem entre bloco de CTA e conteúdo */
--s-5:  48px  /* separação entre sub-blocos dentro de uma seção */
--s-6:  64px  /* padding vertical mínimo de seção (mobile) */
--s-7:  96px  /* padding vertical de seção em telas médias */
--s-8:  120px /* padding vertical máximo de seção (desktop) */
```

Ritmo vertical de seção (fluido, sem precisar de media query):

```css
.section        { padding-block: clamp(64px, 13vw, 120px); }
.section__head   { margin-bottom: clamp(40px, 7vw, 64px); max-width: 700px; }
```

## 4. Escala tipográfica fluida

Regra: qualquer título ou texto que precise se adaptar de mobile a desktop usa
`clamp(mínimo, preferido-em-vw, máximo)`. Isso evita a necessidade de reescrever font-size em
cada media query. Valores em `rem` (base 16px = 1rem).

| Papel | clamp() | Notas |
|---|---|---|
| Display / H1 (hero) | `clamp(2.3rem, 11vw, 4.4rem)` | maior elemento da página; line-height 1.04–1.1 |
| Título de seção / H2 | `clamp(1.9rem, 7vw, 3.4rem)` | |
| Número/valor grande (preço, big stat) | `clamp(3.6rem, 15vw, 5rem)` | line-height 1 |
| Subtítulo de destaque (offer/support head) | `clamp(1.5rem, 5.5vw, 2.1rem)` | |
| Lead / subtítulo de hero | `clamp(1rem, 3.4vw, 1.14rem)` a `clamp(1.04rem, 4vw, 1.22rem)` | |
| H3 de card (título de item) | `1.1rem`–`1.3rem` fixo | não precisa de clamp, variação pequena |
| Corpo de texto | `16px` base / `0.94rem`–`0.97rem` dentro de cards | line-height 1.65 |
| Legenda / meta (role, tag, timestamp) | `0.72rem`–`0.84rem` | maiúsculas + letter-spacing 0.04–0.2em quando for label |
| Eyebrow / kicker | `0.76rem`, letter-spacing `0.2em`, uppercase | |

Fórmula para criar um novo papel tipográfico: `clamp(min_mobile, X vw, max_desktop)`, onde
`X` é escolhido por tentativa até o texto ocupar visualmente o mesmo espaço relativo em telas
de 375px e 1440px. Como ponto de partida, `X ≈ (max - min) / (largura_alvo / 100)`.

**Exceção controlada**: se o layout mobile exigir um valor exato (ex. um título que precisa
quebrar em duas linhas específicas para não colidir com uma imagem), é válido travar um
`font-size` fixo dentro de `@media (max-width: 899px)`, sobrepondo o clamp. Use isso como
exceção pontual, não como padrão.

## 5. Botões

```
--radius-btn: 12px;
--ease: cubic-bezier(0.22, 1, 0.36, 1);
```

| Tamanho | padding | font-size | Uso |
|---|---|---|---|
| Small (topbar/pill CTA) | `6px 14px` a `7px 15px` | `0.82rem`–`0.84rem` | CTA secundário em barra fixa |
| Default | `14px 24px` | `0.96rem`–`1rem` | botão padrão em corpo de página |
| Large (`.btn--lg`) | `17px 30px` | `1.02rem` | CTA principal do hero / oferta |

Regras fixas de botão, independente do tamanho:

- `display: inline-flex; align-items:center; justify-content:center; gap:10px;`
- transições em `transform`, `box-shadow`, `background` com `0.25s var(--ease)`
- estado hover: `translateY(-2px)` + sombra mais forte (o valor de cor da sombra é de marca)
- variante `--block`: `width:100%`, usada em mobile para CTA full-width (`max-width:360px` se
  o botão estiver centralizado num container maior)
- ícone de seta/indicador dentro do botão anima `translateX(4px)` no hover do botão pai

## 6. Sub-escala de componentes (ícones, avatares, selos)

Estes elementos têm sua própria progressão de tamanho — não usam a escala de espaçamento
diretamente, mas seguem incrementos parecidos:

| Elemento | Tamanho | border-radius |
|---|---|---|
| Dot/pulse (indicador ao vivo) | `7px`–`8px` | `50%` |
| Selo circular pequeno (check, bullet numerado) | `22px`–`28px` | `50%` |
| Ícone flutuante decorativo | `44px`–`52px` | `14px` |
| Ícone de card (feature/step/persona) | `56px` | `16px` |
| Índice numerado de módulo | `44px` | `12px` |
| Avatar de depoimento | `46px` | `50%` |
| Foto de mentor/especialista | `72px` | `18px` |
| Selo de garantia (seal) | `60px` | `50%` |

Regra geral: ícone interno (`svg`) ocupa ~50% do container (ex. container 52px → svg 26px).

## 7. Cards e superfícies

```
--radius-card: 24px;
padding: var(--s-4);              /* 32px — padrão */
padding: clamp(28px, 5vw, 48px);  /* em blocos de destaque (support, offer) */
```

- Cards em grid usam `gap: var(--s-3)` (24px) entre si, nunca um valor diferente.
- Hover padrão de card: `translateY(-4px)` + sombra de destaque (cor de marca).
- Badges/pills (tag, status): `padding: 5px 12px` a `7px 15px`, `border-radius: 999px`.
- Bloco de nota/citação em destaque: borda esquerda de 3px na cor de marca + `border-radius:
  var(--radius-card)`.

## 8. Raios de borda — escala única

```
--radius-sm:   12px;  /* botões, faq items, guarantee box */
--radius-lg:   24px;  /* cards, offer card, support block */
--radius-full: 999px; /* pills, badges, tags */
```

Nunca introduza um terceiro valor de raio fora desses três sem justificativa de layout
específica (ex. o `22px 22px 8px 8px` de um mockup de dispositivo é uma ilustração pontual,
não um padrão a repetir).

## 9. CTA flutuante mobile (padrão opcional)

Para páginas de venda com CTA persistente em mobile:

```css
.floating-cta {
  position: fixed; left: 16px; right: 16px; bottom: 16px;
  padding: 15px; border-radius: var(--radius-btn);
  transform: translateY(160%);
  transition: transform 0.4s var(--ease);
}
.floating-cta.is-visible { transform: translateY(0); }
```
Ocultar em `≥640px` (`display: none`) quando o CTA principal já está sempre visível no layout
desktop.

## 10. Checklist de aplicação em um projeto novo

1. Colete os inputs de marca (cores, fonte, logo, imagens, tom). Se não vierem prontos,
   pergunte antes de inventar.
2. Copie `reference/tokens.css` para o projeto; preencha os blocos `/* BRAND */`.
3. Monte o container/grid com os breakpoints da seção 1 e larguras da seção 2.
4. Aplique a escala tipográfica (seção 4) a cada papel de texto usado na página — não crie
   tamanhos soltos fora da tabela sem necessidade real.
5. Construa os botões a partir da seção 5 (escolha small/default/large por contexto).
6. Dimensione ícones/avatares/selos pela sub-escala da seção 6.
7. Aplique espaçamento (seção 3) em todo padding/margin/gap — se um valor não existe na
   escala, prefira o mais próximo antes de criar um novo.
8. Teste visualmente em pelo menos 4 larguras: `375px`, `768px`, `1024px`, `1440px`.
9. Confirme `prefers-reduced-motion` desativando animações/transições (ver bloco final de
   `tokens.css`/CSS do projeto).
