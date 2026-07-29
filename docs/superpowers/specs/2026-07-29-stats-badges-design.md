# Design — Substituir cards de stats por badges estáticos

**Data:** 2026-07-29
**Autor:** Lucas Cabral (com assistência de agente)
**Status:** Aprovado

## Contexto

A seção "Estatísticas do GitHub" do README.md usa dois cards do serviço `github-readme-stats.vercel.app`. O serviço tem apresentado HTTP 503/404 intermitente, tornando os cards bugados. O usuário quer corrigir.

## Objetivo

Substituir os dois cards dinâmicos por badges estáticos confiáveis que sempre renderizam.

## Design proposto

### Layout

- Manter o cabeçalho `### Estatísticas do GitHub`.
- Substituir o conteúdo atual por três badges lado a lado (ou em uma linha), centralizados.

### Badges a incluir

| Métrica        | Origem                                              | Tipo        |
|----------------|-----------------------------------------------------|-------------|
| Stars total    | `https://img.shields.io/github/stars/aquelemago?style=for-the-badge&logo=github` | Dinâmico (shields.io) |
| Followers      | `https://img.shields.io/github/followers/aquelemago?style=for-the-badge&logo=github` | Dinâmico (shields.io) |
| Public Repos   | Badge estático: `Public Repos 5` (verde)            | Estático    |

### HTML de exemplo

```html
<div align="center">
  <a href="https://github.com/aquelemago?tab=repositories">
    <img src="https://img.shields.io/github/stars/aquelemago?style=for-the-badge&logo=github&logoColor=white&color=181717" alt="Stars">
 </a>
  <a href="https://github.com/aquelemago">
    <img src="https://img.shields.io/github/followers/aquelemago?style=for-the-badge&logo=github&logoColor=white&color=181717" alt="Followers">
 </a>
  <img src="https://img.shields.io/badge/Public_Repos-5-2EA043?style=for-the-badge&logo=github&logoColor=white" alt="Public Repos">
</div>
```

(O número 5 vem da API do GitHub consultada em 2026-07-29.)

## Trade-offs

- **Pró:** sem dependência de serviço intermitente; sempre renderiza; leve.
- **Contra:** perde os gráficos visuais do github-readme-stats; o badge de repos é estático (precisa atualizar manualmente se mudar o número).

## Critérios de sucesso

- Os três badges aparecem corretamente no modo dark do GitHub.
- Nenhum 404 ou 503.
- O título da seção permanece como "Estatísticas do GitHub".
