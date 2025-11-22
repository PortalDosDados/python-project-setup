# 🐍 Protocolo de Iniciação de Projetos Python

> "Primeiro organizamos o ambiente, depois executamos a estratégia."

Este documento descreve o fluxo de trabalho padrão para iniciar qualquer projeto de desenvolvimento em Python, garantindo isolamento de dependências, higiene de repositório e controle de versão adequado desde o "Dia Zero".

---

## 🧭 O Fluxo Visual

```mermaid
graph TD
    A[1. Criar Pasta do Projeto] --> B[2. Criar Ambiente Virtual .venv]
    B --> C[3. CRIAR .gitignore]
    C --> D[4. Iniciar Git (git init)]
    D --> E[5. Ativar .venv]
    E --> F[6. Instalar Libs & Congelar]
    F --> G[7. Começar a Codar]

    style C fill:#ffcccc,stroke:#333,stroke-width:4px,color:red
    style D fill:#ccffcc,stroke:#333,stroke-width:2px,color:black
```

-----

## 🛠️ Passo a Passo Detalhado (Windows/PowerShell)

### 1\. Criar a Pasta do Projeto

Crie a pasta e abra-a no VS Code. Certifique-se de que o terminal está apontando para ela.

### 2\. Criar o Ambiente Virtual (`.venv`)

Crie a "bolha" isolada antes de qualquer outra coisa.

```powershell
python -m venv .venv
```

### 3\. Criar o `.gitignore` (CRÍTICO 🚨)

**Faça isso ANTES de iniciar o Git.** Isso impede que o ambiente virtual seja rastreado acidentalmente.

Crie um arquivo chamado `.gitignore` na raiz e cole o conteúdo abaixo:

```gitignore
# --- Ambiente Virtual e Logs ---
.venv/
venv/
env/
/Scripts/
__pycache__/

# --- Configurações Locais e Senhas ---
.env
.vscode/

# --- Arquivos de Sistema ---
.DS_Store
Thumbs.db
```

### 4\. Iniciar o Git

Agora que a "porta de segurança" (`.gitignore`) está instalada, inicie o monitoramento.

```powershell
git init
git add .
git commit -m "Initial: Estrutura do projeto e gitignore"
```

### 5\. Ativar o Ambiente

Entre na bolha para começar a trabalhar.

```powershell
.\.venv\Scripts\activate
```

*Verifique se apareceu `(.venv)` verde à esquerda do terminal.*

### 6\. Instalar e Congelar Dependências

Instale o que o projeto precisa (ex: Pandas, Streamlit) e crie o registro imediatamente.

```powershell
# Exemplo de instalação
pip install pandas streamlit

# Gerar o arquivo de requisitos
pip freeze > requirements.txt
```

### 7\. Desenvolvimento (`Main.py`)

Agora o ambiente está seguro e pronto. Pode criar seu arquivo `app.py`, `main.py` ou `dashboard.py` e começar a programar a lógica do negócio.

-----

## 💡 Comandos Úteis para o Dia a Dia

  * **Sair do ambiente virtual:**
    ```powershell
    deactivate
    ```
  * **Adicionar nova biblioteca:**
    ```powershell
    pip install nova-lib
    pip freeze > requirements.txt  # Lembre-se sempre de atualizar a lista!
    ```
  * **Adicionar arquivo secreto (Senha/Excel):**
    1.  Adicione o nome do arquivo no `.gitignore`.
    2.  Salve o arquivo.

-----

**Autor:** Dione Nascimento
**Revisão:** Gemini (Lancelot)

```

---

### Dica de Ouro
Você pode salvar esse texto no **Notion**, **Obsidian** ou até mesmo em um Gist no GitHub para ter fácil acesso.

Sempre que tiver uma ideia nova ("Vou fazer um script para ler PDF"), abra esse guia e siga os 7 passos. O sucesso é garantido.

Podemos fechar essa sessão de mentoria de Setup?
```

