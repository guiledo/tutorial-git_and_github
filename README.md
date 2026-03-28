# 🎓 Guia Básico Git & GitHub

Guia criado por [@guiledo](https://github.com/guiledo) para instruir colegas de faculdade no básico da utilização das ferramentas Git e GitHub.
<br>
### 📑 Resumo do Guia                                                                                        
  *   **Tópicos 1 a 5:** Tudo sobre a preparação e configuração inicial (instalação, conta, SSH e clonagem).   
  *   **Tópicos 6 a 8:** As operações básicas e o dia a dia utilizando a ferramenta.
  *   **Seção 💼 Workflow Profissional:** Fluxo de trabalho com Git/GitHub utilizado em ambientes profissionais.
<br>

> 📍 **Acesso Rápido:** Se você já configurou tudo e busca apenas o guia de consulta para o dia a dia profissional, pule para a seção: [💼 Workflow Profissional](#-workflow-profissional).
<br>

## 1. O que é o Git? (E por que ele salva vidas) 📥

Imagine que você está escrevendo um TCC. Você cria o arquivo `projeto.doc`, depois `projeto_final.doc`, depois `projeto_final_agora_vai.doc`. No código, isso seria um caos.

O **Git** é um sistema que tira "fotos" (snapshots) do seu projeto. Se você apagar algo importante por engano, você pode simplesmente usar o Git para voltar no tempo até o momento em que tudo funcionava.

<br>

### 🖥️ Instalando no Windows

1. Acesse o site oficial: [git-scm.com](https://git-scm.com/download/win).
2. Baixe o instalador (geralmente a versão *64-bit Git for Windows Setup*).
3. **Passo a passo da instalação:** Você verá muitas opções. Para iniciantes, a recomendação de ouro é: **apenas clique em "Next" em todas as telas**. As configurações padrão são excelentes.
4. **Como saber se deu certo?** Abra o seu menu iniciar, digite `CMD` (Prompt de Comando) e digite:
   ```bash
   git --version
   ```
   *Se aparecer algo como `git version 2.x.x`, parabéns! O motor está instalado.*
<br>

### 🍎 Instalando no Mac

1. O macOS costuma facilitar as coisas. Abra o seu **Terminal** (Command + Espaço e digite "Terminal").
2. Digite o comando: `git --version`.
3. Se o Git não estiver instalado, uma janelinha do sistema aparecerá perguntando se você deseja instalar as **"Ferramentas de Linha de Comando"**. Clique em **Instalar** e aguarde.
4. Alternativamente, você pode baixar o instalador oficial em [git-scm.com/download/mac](https://git-scm.com/download/mac).
<br>

## 2. Criando sua Identidade no GitHub 🌐

O **GitHub** é como uma "rede social" para programadores, mas com um propósito maior: hospedar seus códigos na nuvem para que outros possam colaborar ou para que você tenha um backup seguro.

1. Acesse [github.com](https://github.com/).
2. Clique em **Sign up** (Cadastrar).
3. Siga as instruções de e-mail e senha. Não esqueça de validar seu e-mail na caixa de entrada após o cadastro.
<br>

## 3. Dizendo ao Git quem você é (Configuração Global) ⚙️

Toda vez que você salva uma alteração no código (um commit), o Git anexa seu nome e e-mail a ela. Isso serve para que a equipe saiba quem fez cada parte do trabalho.

Abra o seu terminal e execute estes dois comandos (substituindo o que está entre aspas):

```bash
git config --global user.name "Seu Nome Completo"
git config --global user.email "seu-email@exemplo.com"
```

> **Atenção:** Use o **mesmo e-mail** que você usou para criar a conta no GitHub!
<br>

## 4. O "Aperto de Mão" Seguro (Chave SSH) 🔑

Para enviar código do seu computador para o GitHub, você precisaria digitar sua senha o tempo todo. Para evitar isso e manter a segurança máxima, usamos a **Chave SSH**. É como se o seu computador tivesse uma "impressão digital" que o GitHub reconhece.
<br>

### Passo 1: Gerar a sua "impressão digital"

No terminal, digite:
```bash
ssh-keygen -t ed25519 -C "seu-email@exemplo.com"
```
O terminal fará algumas perguntas (onde salvar, se quer senha). **Apenas aperte Enter** em todas elas até ver um desenho esquisito feito de caracteres. Isso significa que sua chave foi criada.
<br>

### Passo 2: Copiar a chave para a área de transferência

Agora precisamos copiar o conteúdo da chave para "colar" no site do GitHub.
- **No Windows:** `clip < ~/.ssh/id_ed25519.pub`
- **No Mac:** `pbcopy < ~/.ssh/id_ed25519.pub`
<br>

### Passo 3: Entregar a chave ao GitHub

1. No [GitHub](https://github.com/), clique na sua foto (canto superior direito) e vá em **Settings** (Configurações).
2. No menu lateral, procure por **SSH and GPG keys**.
3. Clique no botão verde **New SSH key**.
4. No campo **Title**, dê um nome (ex: "Meu PC de Estudos").
5. No campo **Key**, dê um `Ctrl + V` (ou `Cmd + V`).
6. Clique em **Add SSH key**. Pronto! Seu computador e o GitHub agora são "confiáveis" um para o outro.
<br>

## 5. Trazendo um Projeto para sua Máquina (Clone) 🖇️

Clonar é o ato de baixar um repositório que já existe no GitHub para o seu computador pela primeira vez.

1. No GitHub, entre na página do repositório que deseja.
2. Clique no botão verde **<> Code**.
3. **Muito importante:** Selecione a aba **SSH** (se usar HTTPS, ele pedirá senha o tempo todo). Copie o link que começa com `git@github.com...`.
4. No terminal, vá até a pasta onde quer guardar seus estudos e digite:
   ```bash
   git clone [cole-o-link-aqui]
   ```
<br>

## 6. O Ciclo de Trabalho (Entendendo os Comandos) 🧙‍♂️

Sempre que você altera o código, você segue um ciclo. Imagine que você está enviando uma encomenda pelo correio:

1. **`git pull`**: Antes de tudo, você verifica se chegou algo novo para você. Isso evita que você tente enviar algo baseado em uma versão antiga do projeto.
2. **`git add .`**: Você coloca seus arquivos alterados dentro da "caixa" de envio. O ponto (`.`) diz: "pegue tudo que eu mexi dentro do diretório atual".
3. **`git commit -m "mensagem"`**: Você lacra a caixa e escreve um bilhete do lado de fora explicando o que tem dentro (ex: "ajusta a cor do cabeçalho").
4. **`git push`**: Você entrega a caixa no balcão do correio para que ela seja enviada para o servidor (GitHub).
<br>

## 7. Branches: Trabalhando sem Medo de Quebrar 🌿

Branches (ramos) são como "universos paralelos". Você cria uma branch para fazer uma tarefa. Se der tudo errado, a versão principal (`main`) continua intacta e segura.

- **Para criar uma tarefa nova:** `git checkout -b feature/nome-da-tarefa`
- **Para voltar para a versão principal:** `git checkout main`
- **Para ver onde você está:** `git branch` (a branch com um asterisco `*` é a que você está usando).
<br>

## 8. Pull Request (PR): A Hora da Revisão 🤝

O **Pull Request** é o momento em que você avisa ao time: "Terminei minha parte na minha branch, podem dar uma olhada e colocar na versão principal?".

1. Após dar o `git push` da sua branch, vá ao site do GitHub.
2. Um botão amarelo aparecerá escrito **"Compare & pull request"**.
3. Escreva o que você fez e clique em **Create pull request**. Agora, outros desenvolvedores podem comentar e aprovar seu código.
<br>

---

## 💼 Workflow Profissional

Este é o padrão de ouro seguido nas melhores empresas do mundo. Memorize este ciclo:
<br>

### 1. Preparação (Sempre comece aqui)

```bash
git checkout main          # Garante que você está na branch principal
git pull origin main       # Puxa as últimas atualizações dos seus colegas
```
<br>

### 2. Criação (Iniciando uma tarefa)

```bash
git checkout -b feature/nome-da-sua-tarefa   # Cria seu universo paralelo
```
<br>

### 3. Desenvolvimento (Mão na massa)

Fez uma pequena parte que funciona? Salve! Não deixe para o final.
```bash
git add .
git commit -m "feat: explica o que você acabou de fazer"
```
*Repita o Passo 3 várias vezes durante o dia.*
<br>

### 4. Sincronização e Conflitos (Segurança)

Antes de enviar, verifique se alguém mexeu na `main` enquanto você trabalhava:
```bash
git pull origin main       # Resolve conflitos agora para não dar erro no PR
```
<br>

### 5. Entrega (GitHub)

```bash
git push origin nome-da-sua-branch
```
Vá ao GitHub e abra o [**Pull Request**](#8-pull-request-pr-a-hora-da-revisão).
<br>

### 6. Limpeza (Pós-Merge)

Após seu PR ser aceito e unido à main no GitHub:
```bash
git checkout main
git pull origin main       # Traz seu próprio trabalho agora oficializado na main
git branch -d feature/nome-da-sua-tarefa  # Apaga a branch antiga para não poluir seu PC
```
<br>

---

### 🏆 Dicas de Ouro

- **Errou o comando?** O terminal geralmente te dá uma dica do comando certo logo abaixo do erro. Leia com atenção!
- **Commit Atômico:** Quanto menor o commit, mais fácil é de entender e de consertar se algo der errado.
- **Mensagens Claras:** "Ajuste da margem da hero page" é melhor que "Ajustes" ou "Finalizado".
<br>

---

🚀 Caso tenha algum problema ou dúvida ao longo do guia, contate-me em:

[![WhatsApp](https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white)](https://wa.me/5511980904699)
