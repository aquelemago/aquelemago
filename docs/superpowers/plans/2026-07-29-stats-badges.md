# Stats Badges — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Substituir os dois cards do github-readme-stats na seção "Estatísticas do GitHub" por três badges estáticos (Stars, Followers, Public Repos).

**Architecture:** Substituir o conteúdo dentro de `<div align="center">` da seção "Estatísticas do GitHub" por três badges shields.io.

**Tech Stack:** GitHub Flavored Markdown, shields.io.

## Global Constraints

- Renderização correta no modo dark do GitHub.
- Sem dependência de serviços intermitentes.
- Manter compatibilidade com GFM.
- Não introduzir ícones invisíveis.
- Não alterar outras seções.
- Mensagem de commit em pt-BR.

---

### Task 1: Substituir cards de stats por badges

**Files:**
- Modify: `README.md` (substituir conteúdo dentro de `<div align="center">` da seção "Estatísticas do GitHub")

**Interfaces:**
- Consumes: bloco atual:

```html
<div align="center">
  <img height="160" src="https://github-readme-stats.vercel.app/api?username=aquelemago&theme=dark&show_icons=true&count_private=true&include_all_commits=true&cache_seconds=86400" alt="Stats">
  <img height="160" src="https://github-readme-stats.vercel.app/api/top-langs/?username=aquelemago&theme=dark&layout=compact&langs_count=6&cache_seconds=86400" alt="Top Languages">
</div>
```

- Produces:

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

- [ ] **Step 1: Localizar a seção "Estatísticas do GitHub" no `README.md`**

  Abrir o arquivo e encontrar a linha `### Estatísticas do GitHub` seguida do bloco `<div align="center">` com os dois cards `github-readme-stats.vercel.app`.

- [ ] **Step 2: Substituir o bloco**

  Remover o conteúdo antigo e inserir o novo bloco exatamente como especificado acima.

- [ ] **Step 3: Verificar renderização**

  Abrir o `README.md` em preview Markdown e confirmar:
  - 3 badges aparecem lado a lado.
  - Nenhum erro 404 ou 503.
  - Os badges são clicáveis para o repositório correto.

- [ ] **Step 4: Commitar**

  ```bash
  git add README.md
  git commit -m "Substituir cards de stats por badges estaticos"
  ```

- [ ] **Step 5: Push**

  ```bash
  git push origin main
  ```
