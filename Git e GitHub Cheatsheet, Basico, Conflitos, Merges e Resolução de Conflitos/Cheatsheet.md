# Guia de Comandos Git

## Inicializar um Repositório
Para começar a usar o Git, inicialize um novo repositório com:

bash
git init

## Clonar um Repositório

-   **Comando:** `git clone <url_do_repositório>`
-   **Explicação:** Cria uma cópia de um repositório Git existente.
-   **Exemplo:**

```bash
git clone https://github.com/user/repo.git
```

## Verificar o Status do Repositório

-   **Comando:** `git status`
-   **Explicação:** Mostra o status das alterações como não rastreadas, modificadas ou preparadas.
-   **Exemplo:**

```bash
git status
```

## Adicionar Alterações à Área de Preparação

-   **Comando:** `git add <arquivo>` ou `git add .`
-   **Explicação:** Adiciona alterações no diretório de trabalho à área de preparação.
-   **Exemplo:**

```bash
git add arquivo.txt
git add .
``` 

## Comitar Alterações

-   **Comando:** `git commit -m "mensagem do commit"`
-   **Explicação:** Registra alterações no repositório com uma mensagem descritiva.
-   **Exemplo:**

```bash
git commit -m "Adicionar nova funcionalidade"
```


## Ver Histórico de Commits

-   **Comando:** `git log`
-   **Explicação:** Mostra uma lista de todos os commits no branch atual.
-   **Exemplo:**

```bash
git log
```

## 🔄 Trabalhando com Branches

Branches permitem que você trabalhe em diferentes versões de um repositório ao mesmo tempo.

### Criar um Novo Branch

-   **Comando:** `git branch <nome_do_branch>`
-   **Explicação:** Cria um novo branch.
-   **Exemplo:**

```bash
git branch branch-de-funcionalidade
```

### Trocar para um Branch

-   **Comando:** `git checkout <nome_do_branch>`
-   **Explicação:** Troca para o branch especificado.
-   **Exemplo:**

```bash
git checkout branch-de-funcionalidade
```

### Mesclar um Branch

-   **Comando:** `git merge <nome_do_branch>`
-   **Explicação:** Mescla o branch especificado no branch atual.
-   **Exemplo:**

```bash
git merge branch-de-funcionalidade
```

## 🌐 Colaboração com GitHub

O GitHub é uma plataforma de hospedagem de código-fonte com controle de versão usando Git. Ele facilita a colaboração, permitindo que múltiplos desenvolvedores trabalhem em projetos juntos.

### Enviar Alterações para o Repositório Remoto

-   **Comando:** `git push <remoto> <branch>`
-   **Explicação:** Envia commits para um repositório remoto.
-   **Exemplo:**

```bash
git push origin main 
```

### Puxar Alterações do Repositório Remoto

-   **Comando:** `git pull <remoto> <branch>`
-   **Explicação:** Busca e mescla alterações de um repositório remoto.
-   **Exemplo:**

```bash
git pull origin main
```

### Criar um Pull Request

Um pull request permite notificar outros sobre as alterações que você enviou para um branch em um repositório no GitHub. Isso é feito diretamente na interface do GitHub.

-   **Passos:**
    -   Envie seu branch para o GitHub.
    -   Navegue até o repositório no GitHub.
    -   Clique no botão **“Compare & pull request”**.
    -   Adicione uma descrição e envie o pull request.

## 📄 Lidando com Conflitos

### Entender Conflitos de Merge

Conflitos de merge ocorrem quando duas alterações diferentes são feitas na mesma linha de um arquivo ou quando uma parte é modificada em um branch e removida em outro. Git não pode resolver esses conflitos automaticamente e requer intervenção manual.

### 🔄 Comandos de Merge e Resolução de Conflitos

#### Mesclar um Branch

-   **Comando:** `git merge <nome_do_branch>`
-   **Explicação:** Mescla o branch especificado no branch atual. Se ocorrerem conflitos, o Git sinalizará os arquivos conflitantes.
-   **Exemplo:**

```bash
git merge feature-branch
``` 

#### Verificar Conflitos de Merge

-   **Comando:** `git status`
-   **Explicação:** Mostra os arquivos com conflitos e o estado do merge.
-   **Exemplo:**

```bash
git status
```

### 📄 Resolver Conflitos de Merge

#### Identificar Conflitos

-   **Explicação:** Abra o arquivo com conflito. Git marca os conflitos com os seguintes delimitadores:

```plaintext
<<<<<<< HEAD
alterações no branch atual
=======
alterações no branch mesclado
>>>>>>> nome_do_branch` 
```

-   **Exemplo:**

```plaintext
<<<<<<< HEAD
Esta é a linha do branch atual.
=======
Esta é a linha do branch mesclado.
>>>>>>> feature-branch
``` 

#### Editar o Arquivo com Conflito

-   **Explicação:** Edite o arquivo para resolver os conflitos, mantendo as alterações desejadas e removendo os marcadores `<<<<<<<`, `=======` e `>>>>>>>`.
-   **Exemplo:**

```plaintext
Esta é a linha combinada após resolver o conflito. 
```

#### Adicionar Arquivos Resolvidos

-   **Comando:** `git add <arquivo>`
-   **Explicação:** Adiciona o arquivo resolvido à área de preparação.
-   **Exemplo:**

```bash
git add arquivo_com_conflito.txt
```

#### Concluir o Merge

-   **Comando:** `git commit`
-   **Explicação:** Completa o merge e cria um commit de merge. Se um commit de merge automático já foi criado, use `git commit --amend` para editá-lo.
-   **Exemplo:**

```bash
git commit -m "Resolver conflitos de merge entre main e feature-branch"
```

#### Desfazer um Merge

-   **Comando:** `git merge --abort`
-   **Explicação:** Cancela o processo de merge em andamento e restaura o estado anterior do branch.
-   **Exemplo:**

```bash
git merge --abort
```

## 🌐 Dicas Adicionais

Ferramentas de Resolução de Conflitos existem para facilitar o processo, como:

-   KDiff3
-   Meld
-   Beyond Compare

Muitas IDEs e editores de texto, como **VS Code** e **PyCharm**, possuem suporte integrado para resolução de conflitos.