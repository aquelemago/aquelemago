# Design — Melhoria da seção "Tecnologias" no README.md

**Data:** 2026-07-28
**Autor:** Lucas Cabral (com assistência de agente)
**Status:** Aprovado

## Contexto

O README.md do perfil apresenta a seção "Tecnologias" usando uma única imagem da skillicons.dev com cinco ícones (Python, FastAPI, PostgreSQL, Git, Docker). O usuário identificou que o layout está pouco organizado: ícones sem rótulos, sem grade definida e com tamanho inconsistente entre si.

## Objetivo

Tornar a seção "Tecnologias" mais legível, escaneável e visualmente equilibrada, mantendo o estilo skillicons.dev.

## Design proposto

### Layout

- Tabela HTML com 2 colunas (`width="50%"`) e 3 linhas.
- Cada célula centralizada (`align="center"`, `valign="top"`).
- Cada célula contém:
  - Um ícone skillicons individual (ex.: `https://skillicons.dev/icons?i=python&theme=dark`).
  - Um rótulo de texto logo abaixo (`<sub>Python</sub>`).

### Tecnologias incluídas

| Tecnologia  | Ícone                              |
|-------------|-------------------------------------|
| Python      | skillicons `python`                 |
| FastAPI     | skillicons `fastapi`                |
| PostgreSQL  | skillicons `postgres`               |
| Playwright  | badge shields.io (ícone indisponível no skillicons) |
| Git         | skillicons `git`                    |
| Docker      | skillicons `docker`                 |

### Espaçamento

- `<br>` entre linhas para separação visual.
- Largura da tabela 100% do container.

## Trade-offs

- **Pró:** Mais legível; rótulos removem ambiguidade dos ícones; grade 2xN cria ritmo visual.
- **Contra:** Ocupa mais espaço vertical que uma barra única de badges.

## Justificativa

Mantém o estilo skillicons já presente no README, mas adiciona clareza textual e uniformidade geométrica. Para Playwright (sem ícone válido), usaremos um badge shields.io com a logo oficial.

## Critérios de sucesso

- Seção renderiza corretamente em modo dark do GitHub.
- Todos os ícones visíveis sem elementos invisíveis.
- Mantém responsividade em diferentes larguras.

## Próximo passo

- Após aprovação final do spec, acionar a skill `writing-plans` para gerar o plano de implementação.
