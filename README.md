# Resumo dos Comandos Git 🚀

Este é um resumo pessoal dos comandos mais importantes do Git, usado para treinar e relembrar.

---

## 🌎 O Básico (O Ciclo de Trabalho)

O fluxo mais comum do Git envolve 3 passos: **Modificar**, **Preparar** (Stage) e **Salvar** (Commit).

1.  `git status`
    * **O que faz:** Seu "GPS". Mostra o estado atual do seu repositório. Diz quais arquivos estão modificados, quais estão "prontos para o commit" (staged) e quais o Git nem conhece (untracked).
    * **Quando usar:** O tempo todo. Antes de adicionar, antes de "comitar", depois de "comitar". Sempre.

2.  `git add [nome-do-arquivo]`
    * **O que faz:** Prepara um arquivo para o próximo "commit". Tira ele da área "Modified" ou "Untracked" e coloca na "Staging Area" (Área de Preparação).
    * `git add .` (usando um ponto): Adiciona **TODOS** os arquivos modificados ou novos de uma vez.

3.  `git commit -m "Sua mensagem aqui"`
    * **O que faz:** Tira a "foto" (snapshot) de tudo que estava na "Staging Area" e salva permanentemente no histórico. A mensagem (`-m`) é **obrigatória** e deve explicar o que você fez.

---

## 🛰️ Comandos de Repositório Remoto (GitHub)

Para salvar seu código na nuvem (como no GitHub).

* `git push`
    * **O que faz:** **Envia** seus "commits" locais (que você salvou com `git commit`) para o repositório remoto (ex: `origin`).
    * `git push -u origin main`: Usado na primeira vez, para "subir" a branch `main` e conectar sua branch local com a remota. Depois, basta `git push`.

* `git pull`
    * **O que faz:** **Puxa** (baixa) as atualizações que estão no repositório remoto para o seu computador local. Essencial se você trabalha em equipe.

* `git clone [URL_DO_REPO]`
    * **O que faz:** "Clona" (copia) um repositório inteiro do GitHub (ou outro lugar) para o seu computador. É o que você faz para começar a trabalhar em um projeto que já existe.

* `git remote -v`
    * **O que faz:** Mostra quais repositórios remotos (`-v` de "verbose") estão configurados. É como você vê o link do seu `origin`.

---

## 🌿 Trabalhando com Branches (Ramos)

Branches são "linhas do tempo" paralelas. Você usa para criar uma nova funcionalidade sem bagunçar a linha principal (`main`).

* `git branch [nome-da-branch]`
    * **O que faz:** Cria uma nova branch (um novo "ramo").

* `git switch [nome-da-branch]`
    * **O que faz:** Muda sua "linha do tempo" para a branch que você especificou. (O comando antigo é `git checkout [nome]`, mas `switch` é mais moderno).

* `git merge [nome-da-branch]`
    * **O que faz:** Junta (mescla) as mudanças da branch especificada na sua branch atual. (Ex: você está na `main` e roda `git merge feature-login` para trazer as mudanças da `feature-login` para a `main`).

---

## ↩️ Desfazendo Coisas (Com Cuidado!)

* `git restore [nome-do-arquivo]`
    * **O que faz:** Descarta as mudanças que você fez em um arquivo **antes** de você usar `git add`. Volta o arquivo para como ele estava no último "commit".

* `git reset [nome-do-arquivo]`
    * **O que faz:** Tira um arquivo da "Staging Area". (Ex: você deu `git add` em um arquivo sem querer e quer "despreparar" ele antes do commit).

* `git log`
    * **O que faz:** Mostra o histórico de todos os "commits" que você já fez, com suas mensagens e códigos (hashes).