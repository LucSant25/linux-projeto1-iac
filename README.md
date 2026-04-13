# Projeto de Infraestrutura como Código (IaC) - Linux

Este repositório contém um script de automação para provisionamento de infraestrutura em servidores Linux. O objetivo é padronizar a criação de usuários, grupos e diretórios, aplicando permissões de segurança específicas para cada departamento.

## 📋 Detalhes do Projeto

O script realiza as seguintes operações automaticamente:

1.  **Estrutura de Diretórios:** Cria pastas para os setores Administrativo (`/adm`), Vendas (`/ven`), Secretariado (`/sec`) e uma pasta pública (`/publico`).
2.  **Gestão de Grupos:** Cria os grupos `GRP_ADM`, `GRP_VEN` e `GRP_SEC`.
3.  **Usuários e Segurança:** - Cria 9 usuários vinculados aos seus respectivos grupos.
    - Define o shell padrão como `/bin/bash`.
    - Define senhas criptografadas utilizando `openssl`.
4.  **Políticas de Permissão:**
    - O diretório `/publico` tem acesso total (read/write/execute) para todos.
    - Diretórios específicos de cada grupo são restritos: apenas o dono (root) e os membros do grupo possuem acesso total; outros usuários não possuem nenhuma permissão.

## 🚀 Como executar o projeto

### Pré-requisitos
* Sistema Operacional Linux (Ubuntu, Debian, etc.).
* Permissões de superusuário (root ou sudo).
* Pacote `openssl` instalado (geralmente já vem nativo).

### Passo a passo

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/LucSant25/linux-projeto1-iac.git](https://github.com/LucSant25/linux-projeto1-iac.git)
    cd linux-projeto1-iac
    ```

2.  **Dê permissão de execução ao script:**
    ```bash
    chmod +x script.sh
    ```

3.  **Execute o script como root:**
    ```bash
    sudo ./script.sh
    ```

## 🛠️ Tecnologias Utilizadas
* **Bash Script:** Linguagem de script para automação.
* **Linux Permissions:** Gerenciamento de acessos via `chmod` e `chown`.
* **OpenSSL:** Utilizado para geração de hash de senhas.
