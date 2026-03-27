# Guia Completo: Dominando Git & GitHub para Iniciantes 🚀

Este guia foi desenvolvido para levar você do zero à primeira contribuição profissional. O objetivo aqui não é apenas decorar comandos, mas entender o fluxo de trabalho de um desenvolvedor de software.

> 📍 **Acesso Rápido:** Se você já passou pela configuração inicial e quer apenas o guia de consulta diária, vá para: [Workflow Profissional](#workflow-profissional-💼).

---

## 1. O que é Git e por que usá-lo? 📥

O **Git** é um sistema de controle de versão. Imagine que ele é uma "máquina do tempo" para o seu código, permitindo que você salve estados seguros do projeto e retorne a eles se algo der errado.

### Instalando no Windows:
1. Acesse [git-scm.com](https://git-scm.com/download/win).
2. Baixe o instalador de 64 bits.
3. Durante a instalação, o Git perguntará sobre o editor padrão e o comportamento do terminal. **Dica:** Para iniciantes, manter as opções padrão ("Next" até o fim) é o caminho mais seguro.
4. Para validar: Abra o **Prompt de Comando (CMD)** e digite `git --version`.

### Instalando no Mac:
1. Abra o **Terminal** (Command + Espaço e digite "Terminal").
2. Digite `git --version`. O macOS oferecerá a instalação automática das "Ferramentas de Linha de Comando" caso você não as tenha. Clique em **Instalar**.
3. Se preferir o instalador oficial, baixe em [git-scm.com](https://git-scm.com/download/mac).

---

## 2. Criando sua conta no GitHub 🌐

O **GitHub** é a plataforma onde seu código ficará guardado na nuvem e onde a mágica da colaboração acontece.

1. Acesse [github.com](https://github.com/).
2. Clique em **Sign up** e siga as instruções (e-mail, senha e usuário).
3. **Dica:** Escolha um nome de usuário profissional, pois ele será seu cartão de visitas para recrutadores.
4. Verifique seu e-mail para ativar a conta.

---

## 3. Identificando-se para o Git (Configuração Global) ⚙️

O Git precisa saber quem é o autor de cada linha de código.

Execute no terminal:
```bash
git config --global user.name "Seu Nome Completo"
git config --global user.email "seu-email@exemplo.com"
```
*Use o mesmo e-mail do GitHub.*

---

## 4. Conectando seu computador ao GitHub (Chave SSH) 🔑

Para enviar código sem digitar senha toda hora:

1. **Gerar a chave:** `ssh-keygen -t ed25519 -C "seu-email@exemplo.com"` (Aperte Enter em tudo).
2. **Copiar a chave:**
   - **Windows:** `clip < ~/.ssh/id_ed25519.pub`
   - **Mac:** `pbcopy < ~/.ssh/id_ed25519.pub`
3. **Colar no GitHub:** **Settings** -> **SSH and GPG keys** -> **New SSH key** -> Cole no campo "Key".

---

## 5. Clonando um Repositório 🖇️

1. No GitHub, clique em **<> Code**, selecione **SSH** e copie o link.
2. No terminal: `git clone [link-copiado]`

---

## 6. Branches: Trabalhando em Paralelo 🌿

Uma branch é um espaço seguro para testar código sem quebrar o projeto principal.
- **Criar e entrar:** `git checkout -b feature/nome-da-tarefa`
- **Voltar para a principal:** `git checkout main`

---

## Workflow Profissional (Melhores Práticas) 💼

Este é o ciclo real de um desenvolvedor em uma empresa. Siga estes passos rigorosamente em cada tarefa:

### Passo 1: O Começo
1. **Sincronize sua Main:** Antes de tudo, garanta que sua `main` local está igual à do servidor.
   ```bash
   git checkout main
   git pull origin main
   ```
2. **Crie sua Branch:** Use nomes claros com prefixos (`feature/`, `bugfix/`, `docs/`).
   ```bash
   git checkout -b feature/minha-nova-tela
   ```

### Passo 2: O Ciclo de Desenvolvimento (Repita várias vezes)
Não espere terminar tudo para salvar. Fez uma pequena parte que funciona? Salve!
1. **Prepare:** `git add .`
2. **Carimbe (Conventional Commits):**
   - `git commit -m "feat: adiciona botão de login"`
   - `git commit -m "fix: corrige alinhamento do texto"`
   *A mensagem deve explicar **o que** foi feito.*

### Passo 3: A Entrega
1. **Sincronização Final:** Antes de enviar, puxe as novidades da `main` para sua branch para resolver conflitos localmente:
   ```bash
   git pull origin main
   ```
2. **Envio:** Mande sua branch para o GitHub.
   ```bash
   git push origin nome-da-sua-branch
   ```
3. **Pull Request (PR):** No GitHub, abra o PR. Descreva o que você fez e peça revisão.

### Passo 4: Limpeza (Pós-Aprovação)
Após seu código ser aceito e unido (`merge`) à `main` no GitHub:
1. Volte para a main: `git checkout main`
2. Atualize sua máquina: `git pull origin main`
3. **Delete a branch usada:** (Para manter seu PC limpo)
   ```bash
   git branch -d feature/minha-nova-tela
   ```

---

### Dicas de Ouro 🏆
- **Commits Atômicos:** Commits pequenos facilitam a correção de erros.
- **Não tenha medo de conflitos:** Eles acontecem quando duas pessoas mexem na mesma linha. O Git avisará, e você só precisará escolher qual versão manter na sua IDE.

Parabéns! Você está trabalhando como um desenvolvedor de elite. 🚀
