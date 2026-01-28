## 🏗 Gestão de Tarefas (Kanban)

Nosso quadro de tarefas é centralizado no **GitHub Projects da Organização**. Ele consolida as demandas de todos os repositórios em um único lugar.

### As 5 Colunas do Nosso Fluxo
1.  **To Do:** Tarefas priorizadas e prontas para serem iniciadas.
2.  **Doing:** Tarefas em desenvolvimento ativo.
3.  **Code Review:** O código foi submetido (Pull Request aberto) e aguarda revisão.
4.  **Testing:** O código foi aprovado e está sendo validado em ambiente de teste/staging.
5.  **Done:** Tarefa concluída, mergeada e entregue.

### Como criar uma nova Task
1.  Acesse o **Project** da Organização.
2.  Na coluna **To Do**, clique em **"+ Add item"**.
3.  Digite o título da tarefa e selecione o repositório correspondente.
4.  **Configuração da Issue:**
    * **Assignees:** Atribua a tarefa a você mesmo (quem vai executar).
    * **Labels:** Classifique (ex: `bug`, `feature`, `documentation`).
    * **Description:** Adicione detalhes mínimos sobre o que precisa ser feito.

---

## 💻 Fluxo de Desenvolvimento (Git & PRs)

### 0. Clonando e Preparando a Branch
Antes de iniciar qualquer codificação, você precisa ter o repositório localmente e garantir que está trabalhando na versão mais recente.

```bash
git clone https://github.com/Codeye-Corporation/nome-do-repositorio.git
```

### 1. Preparando a Branch
Nunca trabalhe diretamente na branch `main`. Toda alteração deve vir de uma branch secundária.

#### Sincronize seu ambiente local
```bash
git checkout main
git pull origin main
```

#### Crie sua branch (padrão: tipo/id-da-issue)
```bash
git checkout -b feature/12-setup-login
```

### 2. Abrindo o Pull Request (PR)

Assim que terminar as alterações no código, siga o fluxo abaixo para enviar seu trabalho:

1.  **Prepare as alterações (Stage):** Adicione os arquivos modificados para a área de preparação:
    ```bash
    git add .
    ```
2.  **Grave as alterações (Commit):** Crie um commit com uma mensagem clara e objetiva:
    ```bash
    git commit -m "feat: descrição curta da funcionalidade"
    ```
3.  **Envie seu código (Push):** Suba sua branch para o repositório remoto:
    ```bash
    git push origin feature/nome-da-sua-branch
    ```
4.  **Inicie o PR:** No GitHub, clique no botão **"Compare & pull request"** que aparecerá no topo do repositório.
5.  **Vínculo Automático (Obrigatório):** Na descrição do PR, você deve utilizar uma palavra-chave para vincular a Issue. Escreva:
    > `Closes #ID_DA_ISSUE`
    > *(Exemplo: Closes #15)*
    > **Nota:** Isso garante que a tarefa seja fechada e movida para a coluna **Done** automaticamente quando o merge ocorrer.
6.  **Movimentação do Kanban:** Mova o card manualmente para a coluna **Code Review**.
7.  **Solicite Review:** Na barra lateral direita do PR, em **Reviewers**, selecione pelo menos um colega de equipe para revisar seu código.
