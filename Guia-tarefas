# Guia do Estudante — Construindo um site em equipe com Git e GitHub
### Instituto JEF · 1º ano Técnico · siga este guia do começo ao fim

Vocês vão construir **juntos** um site de várias páginas. Cada um é dono de **uma página**. Para
juntar o trabalho de todos sem bagunça, vocês vão usar o GitHub: cada um envia sua parte, **pede a
aprovação de um colega**, o colega **aprova**, e aí a parte entra no site. No fim, o site fica
publicado na internet.

**Toda a atividade é feita no Prompt de Comando do Windows (o `cmd`).** Abra-o pelo menu Iniciar
digitando `cmd`.

> ### Como ler este guia
> - **👥 TODOS** = passo que **toda a equipe** faz, cada um no seu computador.
> - **⭐ SÓ [papel]** = passo que **só o aluno com aquele papel** faz. Se não é o seu papel, espere
>   e acompanhe.
> - Depois de cada passo há um **✅ Confira:** — só siga em frente quando aquilo aparecer.

---

## Parte 1 — Preparar o computador (👥 TODOS, uma vez)

1. Instale o **Git for Windows** (em git-scm.com).
   **Atenção na tela "Adjusting your PATH environment": escolha a opção do meio**, *"Git from the
   command line and also from 3rd-party software"*. Sem isso o `cmd` não vai achar o Git.
2. Instale o **GitHub CLI** (em cli.github.com). É ele que deixa vocês abrirem e aprovarem PRs pelo
   terminal.
3. Abra o `cmd` e diga ao Git quem é você:
   ```bat
   git config --global user.name "Seu Nome"
   git config --global user.email "seu-email@exemplo.com"
   ```
4. Faça login no GitHub (resolve tudo de uma vez):
   ```bat
   gh auth login
   ```
   Responda: **GitHub.com** → **HTTPS** → **Login with a web browser**. Abre o navegador, você entra
   na sua conta (com a verificação em 2 passos) e pronto.

> **✅ Confira:** digite `git --version` e depois `gh --version`. Os dois devem responder com um
> número de versão. Se aparecer *"'git' não é reconhecido"*, reinstale o Git escolhendo a opção de
> PATH do passo 1.

---

## Parte 2 — Descobrir seu papel e seu par de revisão

Cada um da equipe tem **uma responsabilidade**. Preencham juntos:

```
Tema do nosso site: _______________________________

Meu nome:        ____________________
Meu papel:       ____________________
Minha página:    paginas/aluno-________.html

Eu PEÇO aprovação para:  ____________  (o colega seguinte no círculo)
Eu APROVO o PR de:       ____________  (o colega anterior no círculo)
```

**Os papéis (cada aluno escolhe um):**

| Papel | O que é seu, além da sua página |
|---|---|
| **Arquiteto(a)** | Criar o repositório e convidar a equipe |
| **Integrador(a)** | Ser quem **mescla** os PRs já aprovados |
| **Revisor(a)-chefe** | Conferir que todo PR tem um revisor pedido |
| **Documentador(a)** | Escrever o `README.md` do projeto |
| **Versionador(a)** *(se houver 5º)* | Publicar o site e marcar a versão final |

**O círculo de revisão** (para todos pedirem e darem aprovação): cada um aprova o PR do colega
seguinte. Ex.: Aluno 1 aprova o do 2, o 2 aprova o do 3... e o último aprova o do primeiro.

---

## Parte 3 — ⭐ SÓ o(a) Arquiteto(a): criar o repositório

> O resto da equipe acompanha pela tela do arquiteto. Os outros passos começam na Parte 4.

1. No site github.com, clique em **New repository**. Dê um nome (ex.: `site-da-equipe`), deixe
   **Public**, e crie.
2. Em **Settings → Collaborators**, adicione cada colega pelo nome de usuário do GitHub.
3. Em **Settings → Branches → Add branch protection rule**: em *Branch name pattern* escreva
   `main`, marque **Require a pull request before merging** e **Require approvals: 1**. Salve.
   (Isso obriga que todo trabalho seja aprovado por um colega antes de entrar.)
4. Copie o endereço do repositório (botão verde **Code → HTTPS**) e mande no grupo da equipe.

> **✅ Confira:** todos os colegas conseguem abrir o repositório no navegador.

---

## Parte 4 — 👥 TODOS: criar sua página e enviar

> Faça tudo no `cmd`. Onde houver `________`, troque pelo valor da sua equipe (o endereço do repo, o
> seu nome etc.).

**Passo 1 — Baixar o projeto para o seu computador:**
```bat
git clone ENDERECO_DO_REPOSITORIO
cd site-da-equipe
```
> **✅ Confira:** digite `dir` e veja os arquivos do projeto.

**Passo 2 — Criar a sua branch (sua linha de trabalho separada):**
```bat
git checkout -b seu-nome
```
> Nunca trabalhe direto na `main`. **✅ Confira:** o `cmd` mostra *"Switched to a new branch
> 'seu-nome'"*.

**Passo 3 — Criar a sua página:**
Abra o **VS Code** (ou outro editor), crie um arquivo novo e salve-o como
`paginas/aluno-SEUNOME.html`. Escreva uma página HTML/CSS simples sobre a sua parte do tema (use o
que vocês já sabem). *Criar o arquivo é tarefa do editor, não do terminal.*

**Passo 4 — Salvar a mudança no Git:**
```bat
git add paginas/aluno-SEUNOME.html
git commit -m "Adiciona minha pagina sobre ..."
```
> Escreva uma mensagem que explique o que você fez. Ruim: `update`, `aaa`.

**Passo 5 — Enviar a sua branch para o GitHub:**
```bat
git push -u origin seu-nome
```
> **✅ Confira:** atualize a página do repositório no navegador — sua branch aparece lá.

**Passo 6 — Abrir o Pull Request e PEDIR aprovação:**
```bat
gh pr create --base main --fill
gh pr edit --add-reviewer USUARIO_DO_COLEGA
```
> `USUARIO_DO_COLEGA` é o nome de usuário, no GitHub, do colega que vai te aprovar (veja seu círculo
> na Parte 2). **✅ Confira:** rode `gh pr status` e veja seu PR na lista.

---

## Parte 5 — 👥 TODOS: aprovar o PR do colega

Cada um aprova o PR do colega que lhe coube no círculo.

1. Veja o número do PR que você precisa revisar:
   ```bat
   gh pr status
   ```
2. (Opcional) abra o código no navegador para ler:
   ```bat
   gh pr view NUMERO --web
   ```
3. Aprove, escrevendo um comentário de verdade (um elogio + uma sugestão):
   ```bat
   gh pr review NUMERO --approve --body "Ficou bom! Sugestao: ..."
   ```
> Troque `NUMERO` pelo número do PR. **Você não pode aprovar o seu próprio PR.**
> **✅ Confira:** no PR aparece a marca verde de *approved*.

---

## Parte 6 — ⭐ SÓ o(a) Integrador(a): juntar tudo na `main`

Depois que um PR foi **aprovado** por um colega, o integrador o mescla:
```bat
gh pr status
gh pr merge NUMERO --merge
```
> Faça isso para cada PR aprovado. Se o `cmd` recusar o merge, é porque ainda **falta a aprovação**
> de um colega — espere ela chegar. **✅ Confira:** no repositório, as páginas aparecem na `main`.

---

## Parte 7 — 👥 TODOS: trazer o trabalho de todos para o seu PC

Quando os PRs já entraram na `main`, atualize a sua cópia:
```bat
git checkout main
git pull origin main
```
> **✅ Confira:** abra a pasta `paginas/` no editor — agora estão lá as páginas de **todos** os
> colegas.

---

## Parte 8 — ⭐ SÓ o(a) Documentador(a): escrever o README

1. No editor, abra (ou crie) o `README.md` e escreva: título do projeto, nomes da equipe, o que tem
   em cada página e como abrir o site.
2. No `cmd`:
   ```bat
   git checkout -b doc-readme
   git add README.md
   git commit -m "Adiciona README do projeto"
   git push -u origin doc-readme
   gh pr create --base main --fill
   gh pr edit --add-reviewer USUARIO_DO_COLEGA
   ```
3. Um colega aprova (Parte 5) e o integrador mescla (Parte 6).

---

## Parte 9 — 👥 O desafio do conflito (façam com o professor por perto)

Até aqui não houve conflito porque cada um mexeu na sua página. Agora vocês vão provocar **um
conflito de propósito** para aprender a resolver.

1. **Dois alunos**, cada um na sua branch, abrem o `index.html` no editor e mudam **a mesma linha**
   (ex.: o título do site) de jeitos diferentes. Cada um faz `git add`, `git commit` e `git push`, e
   abre o PR.
2. O PR do **primeiro** é aprovado e mesclado normalmente.
3. O **segundo** atualiza a branch dele com a `main`:
   ```bat
   git checkout sua-branch
   git pull origin main
   ```
   O Git vai avisar **`CONFLICT`** no `index.html`. Isso é esperado!
4. Abram o `index.html` no editor. O Git marcou assim:
   ```
   <<<<<<< HEAD
   versão que já está na main
   =======
   sua versão
   >>>>>>> sua-branch
   ```
   Decidam juntos qual texto fica (ou juntem os dois) e **apaguem as três linhas de marcação**
   (`<<<<<<<`, `=======`, `>>>>>>>`).
5. Finalizem:
   ```bat
   git add index.html
   git commit -m "Resolve conflito no titulo"
   git push
   ```
> **✅ Confira:** o PR agora pode ser mesclado sem conflito.

---

## Parte 10 — ⭐ SÓ o(a) Arquiteto(a)/Versionador(a): publicar o site

1. No site, vá em **Settings → Pages**, em *Branch* escolha **main** e salve. Em alguns minutos o
   GitHub mostra o **link público** do site.
2. (Opcional) marque a versão final da entrega:
   ```bat
   git checkout main
   git pull origin main
   git tag v1.0
   git push origin v1.0
   ```
> **✅ Confira:** o link do GitHub Pages abre o site com as páginas de todos. **Colem o link no
> README.**

---

## Sua lista de entrega (confira antes de terminar)

- [ ] Minha página está em `paginas/` e entrou na `main` por um PR.
- [ ] Meus **commits** têm o meu nome e mensagens que explicam o que fiz.
- [ ] **Pedi aprovação** no meu PR (coloquei um revisor).
- [ ] **Aprovei** o PR do colega do meu círculo, com um comentário de verdade.
- [ ] A equipe resolveu **um conflito** no `index.html`.
- [ ] O `README.md` está preenchido e o site está **publicado** (link no README).

> Seu professor avalia pelo **histórico do GitHub**. Faça os seus próprios commits e a sua própria
> aprovação — o GitHub registra tudo com o seu nome.

---

## Se algo der errado

| O que apareceu | O que fazer |
|---|---|
| `'git' não é reconhecido` | Reinstale o Git for Windows escolhendo a opção de PATH (Parte 1); feche e abra o `cmd` de novo |
| Não consigo dar `git push` | Rode `gh auth login` de novo e entre pelo navegador |
| O merge foi recusado | Falta a **aprovação** de um colega no seu PR — peça e espere |
| Abriu um editor estranho no terminal e travou | Você esqueceu o `-m` no commit. Para sair: aperte `Esc`, digite `:q!` e Enter. Depois refaça com `git commit -m "mensagem"` |
| "Sumiu" o trabalho dos colegas | Você esqueceu de atualizar. Rode `git checkout main` e `git pull origin main` |

**Regra de ouro:** faça `git pull` (na `main`) **antes de começar** a trabalhar e **antes de dar
push**. Isso evita a maioria dos problemas.

---

## Cola de comandos (cmd)

> No `cmd`, linhas que começam com `rem` são só anotações — não precisa digitá-las.

```bat
rem PREPARAR (uma vez)
git config --global user.name "Seu Nome"
git config --global user.email "seu-email@exemplo.com"
gh auth login

rem COMECAR
git clone ENDERECO_DO_REPOSITORIO
cd site-da-equipe
git checkout -b seu-nome

rem TRABALHAR (depois de criar/editar sua pagina no editor)
git status
git add paginas/aluno-SEUNOME.html
git commit -m "mensagem clara"
git push -u origin seu-nome

rem PEDIR APROVACAO
gh pr create --base main --fill
gh pr edit --add-reviewer USUARIO_DO_COLEGA

rem APROVAR O COLEGA
gh pr status
gh pr review NUMERO --approve --body "..."

rem (INTEGRADOR) MESCLAR
gh pr merge NUMERO --merge

rem ATUALIZAR COM O TRABALHO DE TODOS
git checkout main
git pull origin main
```
