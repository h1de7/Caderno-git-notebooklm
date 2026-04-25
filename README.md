# Caderno-git-notebooklm

# Fundamentos de Git - Caderno Temático com NotebookLM
> Projeto desenvolvido para o Desafio de Projeto da DIO | Inteligência Artificial na Aprendizagem Ativa

## Contexto e Objetivos
**Tema escolhido:** Fundamentos de Git e Controle de Versão

**Objetivos de estudo:**
- Compreender o modelo distribuído do Git e o ciclo de vida de um repositório (working directory, staging, local e remote)
- Dominar os comandos essenciais e o fluxo de versionamento (`init`, `add`, `commit`, `push`, `pull`, `branch`, `merge`, `rebase`)
- Identificar boas práticas de escrita de mensagens de commit e estratégias de trabalho colaborativo (Git Flow vs GitHub Flow)
- Criar um material de revisão rápida e consultas técnicas para uso no dia a dia e preparação para entrevistas

Este caderno foi construído utilizando o **Google NotebookLM** como ferramenta de aprendizagem ativa, onde fontes curadas foram analisadas, questionadas e sintetizadas por IA com referências cruzadas e rastreabilidade.

## Curadoria de Fontes
As fontes abaixo foram selecionadas com base em autoridade técnica, acesso aberto e atualização constante. Todas foram convertidas para `.pdf` ou `.txt` e carregadas no NotebookLM.

| # | Título | Autor/Fonte | Ano | Link | Justificativa |
|---|--------|-------------|-----|------|---------------|
| 1 | Pro Git (2ª Edição) | Scott Chacon & Ben Straub | 2014 (atualizado) | https://git-scm.com/book/pt-br/v2 | Documentação oficial de referência; cobre desde o básico até fluxos avançados com licença CC BY-NC-SA 3.0 |
| 2 | GitHub Docs: Introdução ao Git | GitHub Engineering | 2024-2026 | https://docs.github.com/pt/get-started | Focado no ecossistema real de colaboração e integração com plataformas modernas |
| 3 | Git Cheat Sheet Oficial | GitHub Training | 2023 | https://training.github.com/downloads/pt_BR/github-git-cheat-sheet.pdf | Material visual e objetivo; ideal para mapear comandos do dia a dia |
| 4 | Atlassian Git Tutorial | Atlassian | 2025 | https://www.atlassian.com/br/git/tutorials | Didática orientada a cenários de equipe; excelente para entender branching e merge |
| 5 | Version Control with Git & GitHub | MDN Web Docs (Mozilla) | 2024-2026 | https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Version_control | Guia prático e atualizado em inglês; cobre fluxo completo com exemplos de terminal e GitHub |

>  *Nota: Fontes 1 e 5 possuem licenças Creative Commons que permitem uso educacional com atribuição. Links verificados em 25/04/2026.*

## Engenharia de Prompts e "Cicatrizes" (Troubleshooting)
Abaixo está o registro iterativo das perguntas feitas ao NotebookLM, variações testadas, respostas obtidas e ajustes realizados para extrair o máximo das fontes.

### Prompt 1: "Explique a diferença entre staging area e working directory com exemplos práticos de comandos."
- **Variações testadas:** 
  - `"Explique como se eu fosse iniciante"`
  - `"Mostre o fluxo visual: arquivo criado → staging → commit"`
- **Resposta da IA:** A IA detalhou que o `working directory` é onde você edita os arquivos, enquanto o `staging area` é uma área de preparo controlada pelo `git add`. Gerou um fluxo passo a passo com `git status`, `git add .` e `git commit`.
- **Referências citadas pela IA:** Fonte 1 (Cap. 1.3), Fonte 3 (seção "Basic Snapshotting"), Fonte 5 (subseção "Tracking New Files")
- **Dificuldade/Ajuste (Cicatriz):** Na primeira tentativa, a IA misturou conceitos de GUI (GitHub Desktop) com CLI. Adicionei a restrição `"focar exclusivamente na linha de comando (CLI) e ignorar interfaces gráficas"`. Na segunda tentativa, a resposta ficou precisa e alinhada às fontes.

### Prompt 2: "Compare `git merge` e `git rebase`. Quando usar cada um e quais os riscos?"
- **Variações testadas:** 
  - `"Crie uma tabela comparativa"`
  - `"Explique o impacto no histórico de commits"`
- **Resposta da IA:** Gerou tabela comparando preservação de histórico (merge) vs linearização (rebase). Destacou que `rebase` reescreve o histórico e não deve ser usado em branches compartilhadas publicamente.
- **Referências citadas pela IA:** Fonte 1 (Cap. 3.6), Fonte 4 (seção "Merging vs. Rebasing")
- **Dificuldade/Ajuste (Cicatriz):** A IA trouxe exemplos de comandos avançados (`git rebase -i`) sem explicar o contexto. Adicionei `"mantenha o foco em casos de uso básicos e liste 2 cenários onde NÃO usar rebase"`. O ajuste removeu ruído e trouxe clareza prática.

### Prompt 3: "Como resolver conflitos de merge no Git passo a passo?"
- **Variações testadas:** 
  - `"Liste os markers que o Git insere no arquivo"`
  - `"Dê um exemplo real de conflito em um arquivo .js"`
- **Resposta da IA:** Explicou os blocos `<<<<<<<`, `=======`, `>>>>>>>`. Mostrou como editar manualmente, salvar, executar `git add` e finalizar com `git commit`.
- **Referências citadas pela IA:** Fonte 1 (Cap. 3.2), Fonte 2 (seção "Resolving merge conflicts")
- **Dificuldade/Ajuste (Cicatriz):** A resposta inicial focava apenas em terminal, ignorando editores modernos. Adicionei `"inclua como resolver via VS Code e como abortar o merge se necessário (`git merge --abort`)"`. Resultado: guia completo e seguro para iniciantes.

>  *O processo iterativo foi essencial para evitar generalizações e forçar a IA a ancorar as respostas nas fontes carregadas, citando capítulos/seções reais.*

## 📖 Miniguia de Estudo (Entrega Final)

### Resumo Estruturado
1. **O que é Git**: Sistema de controle de versão distribuído que rastreia mudanças no código, permitindo colaboração simultânea e histórico imutável de versões.
2. **Áreas do Git**: `Working Directory` (arquivos em edição) → `Staging Area` (`git add`, prepara o snapshot) → `Local Repository` (`git commit`, salva versão) → `Remote` (`git push/pull`, sincroniza com servidor).
3. **Branches e Fluxos**: `main/master` é a linha principal. `git branch` cria ramificações paralelas. `Git Flow` usa branches de release/hotfix/feature; `GitHub Flow` é mais simples, focado em PRs diretos para `main`.
4. **Resolução de Conflitos**: Ocorre quando duas branches alteram as mesmas linhas. O Git marca os trechos com `<<<<<<<`, `=======`, `>>>>>>>`. O desenvolvedor edita, salva, faz `git add` e `git commit` para finalizar.

### Glossário
| Termo | Definição |
|-------|-----------|
| **Commit** | Snapshot imutável do repositório em um momento específico, contendo hash, autor, data e mensagem descritiva |
| **Branch** | Ramificação paralela do histórico que permite desenvolver funcionalidades isoladamente |
| **Staging Area** | Área intermediária onde arquivos são selecionados para o próximo commit via `git add` |
| **Merge** | Integração de duas branches, criando um novo commit de união e preservando todo o histórico |
| **Rebase** | Reaplica os commits de uma branch sobre outra, criando histórico linear, mas reescrevendo hashes |
| **Remote** | Versão do repositório hospedada em servidor (ex: GitHub, GitLab) usada para backup e colaboração |
| **HEAD** | Ponteiro que indica qual branch/commit está atualmente ativo no diretório de trabalho |
| **Pull Request (PR)** | Mecanismo de solicitação de merge em plataformas como GitHub, permitindo revisão de código antes da integração |
| **Conflito** | Situação onde o Git não consegue mesclar automaticamente alterações concorrentes nas mesmas linhas |
| **Semantic Commits** | Padrão de mensagens (`feat:`, `fix:`, `docs:`, `refactor:`) que padroniza o histórico e facilita automações |

### Prompts Reutilizáveis para Revisão
Copie e adapte estes prompts para futuras sessões de estudo no NotebookLM:
- `"Gere 5 questões de múltipla escolha sobre fluxo Git (staging → commit → push) com gabarito comentado e referência à fonte."`
- `"Crie um mapa mental em texto (markdown) conectando branch, merge, rebase e pull request."`
- `"Explique a staging area usando uma analogia do mundo real e cite a página/fonte de origem."`
- `"Resuma em 3 tópicos o que há de mais prático neste material para quem está começando a usar Git no trabalho."`
- `"Identifique contradições ou nuances importantes entre as fontes carregadas sobre quando usar merge vs rebase e explique por quê."`

## Como Utilizar Este Caderno
1. Acesse o [NotebookLM](https://notebooklm.google.com/)
2. Crie um novo notebook e faça upload dos PDFs/TXTs listados na seção de fontes
3. Cole os prompts da seção `Prompts Reutilizáveis` e adapte conforme seu ritmo
4. Use o resumo e glossário como material de revisão rápida pré-entrevista ou estudo contínuo

## Atribuição de Licenças
Este projeto utiliza conteúdo das seguintes fontes sob licenças Creative Commons:

- **Pro Git (2ª Edição)** por Scott Chacon & Ben Straub está licenciado sob [CC BY-NC-SA 3.0](https://creativecommons.org/licenses/by-nc-sa/3.0/).  
  Fonte original: https://git-scm.com/book/pt-br/v2

- **MDN Web Docs: Version Control** por Mozilla Contributors está licenciado sob [CC-BY-SA 2.5+](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Writing_style_guide/Code_style_guide#attribution).  
  Fonte original: https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Version_control

> Este projeto segue os termos de atribuição e uso não comercial das respectivas licenças. O conteúdo aqui apresentado é para fins educacionais e de portfólio pessoal, sem fins lucrativos.

## Autoria
- **GitHub:** [h1de7](https://github.com/h1de7)
- **LinkedIn:** [Vitor Oliveira](www.linkedin.com/in/vitor-oliveira-817a00405)
- **Perfil DIO:** [https://web.dio.me/users/19vthlfg]
- **Data de conclusão:** 25/04/2026

---
 *Projeto construído com foco em transparência metodológica e aprendizagem ativa. Feedbacks são muito bem-vindos!*
