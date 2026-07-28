# Tecnologias — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Substituir a imagem única de skillicons da seção "Tecnologias" do README.md por uma grade 2xN com ícones individuais e rótulos de texto.

**Architecture:** HTML `<table>` dentro do Markdown com 2 colunas (`width="50%"`) e 3 linhas; cada célula combina ícone (skillicons.dev ou shields.io) + rótulo `<sub>`.

**Tech Stack:** GitHub Flavored Markdown, skillicons.dev, shields.io.

## Global Constraints

- Renderização correta no modo dark do GitHub.
- Sem dependências de scripts externos (somente imagens estáticas).
- Manter estilo visual coerente com o restante do README.
- Manter compatibilidade com GFM (GitHub Flavored Markdown).
- Não introduzir ícones invisíveis (Playwright não tem ícone válido no skillicons → usar shields.io).
- Não alterar outras seções além de "Tecnologias".
- Commitar em pt-BR, mensagens curtas e descritivas.

---

### Task 1: Refatorar seção "Tecnologias" para grade 2xN

**Files:**
- Modify: `README.md` (substituir bloco atual da seção "Tecnologias")

**Interfaces:**
- Consumes: bloco atual `<div align="center"><img src="https://skillicons.dev/icons?i=python,fastapi,postgres,git,docker&theme=dark" alt="Skills</div>`.
- Produces: tabela HTML com 6 células (Python, FastAPI, PostgreSQL, Playwright, Git, Docker), cada uma com ícone + rótulo.

- [ ] **Step 1: Localizar o bloco atual**

  Abrir `README.md` e localizar a linha contendo `### Tecnologias` e a linha subsequente que contém a tag `<img src="https://skillicons.dev/icons?i=python,fastapi,postgres,git,docker&theme=dark"`.

- [ ] **Step 2: Substituir pelo novo bloco de tabela**

  Remover a `<div>` com a imagem única e inserir a tabela abaixo:

  ```html
  <table>
    <tr>
      <td align="center" width="50%" valign="top">
        <img src="https://skillicons.dev/icons?i=python&theme=dark" alt="Python"><br>
        <sub>Python</sub>
     </td>
      <td align="center" width="50%" valign="top">
        <img src="https://skillicons.dev/icons?i=fastapi&theme=dark" alt="FastAPI"><br>
        <sub>FastAPI</sub>
     </td>
   </tr>
    <tr>
      <td align="center" width="50%" valign="top">
        <img src="https://skillicons.dev/icons?i=postgres&theme=dark" alt="PostgreSQL"><br>
        <sub>PostgreSQL</sub>
     </td>
      <td align="center" width="50%" valign="top">
        <img src="https://img.shields.io/badge/Playwright-2EA043?style=flat&logo=playwright&logoColor=white" alt="Playwright"><br>
        <sub>Playwright</sub>
     </td>
   </tr>
    <tr>
      <td align="center" width="50%" valign="top">
        <img src="https://skillicons.dev/icons?i=git&theme=dark" alt="Git"><br>
        <sub>Git</sub>
     </td>
      <td align="center" width="50%" valign="top">
        <img src="https://skillicons.dev/icons?i=docker&theme=dark" alt="Docker"><br>
        <sub>Docker</sub>
     </td>
   </tr>
 </table>
  ```

- [ ] **Step 3: Conferir indentação e linhas em branco**

  Garantir que haja uma linha em branco antes de `### Projetos` (próxima seção) para separação visual.

- [ ] **Step 4: Verificar resultado localmente**

  Abrir `README.md` em um editor com preview Markdown (VS Code, por exemplo) e confirmar:
  - A tabela renderiza em 2 colunas × 3 linhas.
  - Todos os 6 ícones aparecem (Playwright como badge shields.io verde com logo).
  - Rótulos `<sub>` exibem os nomes corretos.

- [ ] **Step 5: Commitar a mudança**

  Executar:

  ```bash
  git add README.md
  git commit -m "Refatorar secao de Tecnologias para grade 2xN com rotulos"
  ```

- [ ] **Step 6: Push para o remoto**

  Executar:

  ```bash
  git push origin main
  ```

- [ ] **Step 7: Validar visualmente no GitHub**

  Acessar `https://github.com/aquelemago/aquelemago` no navegador (modo dark) e confirmar que a seção "Tecnologias" mostra a grade com todos os ícones visíveis.
