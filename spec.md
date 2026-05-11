# Especificação do Projeto: Sistema de Treinamento e Documentação de Processos (SOPs)

## 1. Visão Geral
O projeto consiste em uma aplicação web desenvolvida em **TypeScript** para registrar e documentar processos empresariais (Standard Operating Procedures - SOPs). A plataforma permitirá que gestores criem guias passo a passo claros sobre como executar rotinas da vida real. Os usuários utilizarão o sistema exclusivamente para aprender os processos através de um "Modo Apresentação", registrando o que já foi aprendido.

## 2. Pesquisa de Mercado e Referências
A pesquisa de mercado apontou abordagens em ferramentas similares:
*   **Scribe / Tango:** Criação rápida de guias visuais capturando a tela.
*   **Trainual:** Foco em integração de funcionários (onboarding) e retenção de conhecimento corporativo.
*   **Process Street:** Foco em checklists executáveis.
**Nosso diferencial e foco:** O projeto terá uma abordagem voltada para o **treinamento e documentação clara (semelhante ao Trainual/Tango)**. A ferramenta **não** serve para o funcionário preencher dados durante o trabalho. Ela serve para documentar o processo real. Haverá um modo focado (Apresentação) para estudo, onde o funcionário navega pelos passos e marca o que já aprendeu.

## 3. Arquitetura e Modelagem de Entidades
O sistema possuirá níveis de acesso baseados em **Roles (Cargos)** e duas vertentes principais de uso:
*   **Admin:** Pode criar, editar e montar todos os processos, além de gerenciar apps.
*   **Usuário Comum:** Apenas leitura e estudo dos processos. Não pode editar a estrutura.
*   **Processo (SOP):** A documentação de uma rotina. (Ex: "Como fazer o fechamento do caixa").
*   **Passos do Processo:** As instruções sequenciais, modeladas para funcionar como slides em uma apresentação.
*   **Registro de Aprendizado:** Um vínculo no banco de dados que indica que o usuário "X" marcou o passo "Y" (ou o processo inteiro) como "Aprendido".
*   **Aplicativos (Apps):** Ferramentas externas (ex: ERP, CRM, Excel) cadastradas no sistema com suas respectivas logos, que podem ser associadas aos processos para fins visuais.

## 4. Funcionalidades Principais (Core Features)

### 4.0. Autenticação e Autorização
*   **Tela de Login:** Acesso seguro via e-mail/senha conectado ao Supabase Auth.
*   **Controle de Acesso:** Telas de criação/edição restritas a usuários com role "Admin". Usuários comuns são focados apenas no treinamento.

### 4.1. Gestão de Processos (Para Administradores)
*   **Criar/Editar Processos:** Definir título, descrição e montar a sequência de passos.
*   **Conteúdo dos Passos:**
    *   Textos explicativos e imagens/gifs.
    *   **Vídeo Embutido:** Inserção de um link do YouTube (inclusive vídeos privados/não listados) que será renderizado como um player visual no passo.
*   **Associação de Apps:** Selecionar quais aplicativos (previamente cadastrados) serão utilizados, exibindo seus ícones na apresentação para esclarecer as ferramentas necessárias.

### 4.2. Treinamento e Estudo (Para Usuários/Funcionários)
*   **Modo Apresentação (Step-by-Step):** Uma interface interativa simulando uma apresentação. Os passos aparecem na ordem configurada.
*   **Controles de Mídia:** O usuário pode usar botões de Play (para avanço automático), Pause, Avançar (Próximo) e Voltar (Anterior).
*   **Marcação de Aprendizado:** O usuário pode marcar um step específico ou o processo inteiro como "Aprendido", registrando seu progresso de treinamento.

### 4.3. Monitoramento de Treinamento
*   **Dashboard Administrativo:** Gestores visualizam quem já aprendeu quais processos e o progresso geral da equipe.
*   **Dashboard do Usuário:** O usuário vê quais processos ele já completou o treinamento e quais faltam.

### 4.4. Gestão de Aplicativos (Apps)
*   **Cadastro:** Criar um novo "App" informando seu nome e fazendo o upload da sua logo (ícone).
*   **Exibição Visual:** Utilizar as logos cadastradas para criar referências visuais claras no cabeçalho do modo de apresentação.

## 5. Stack Tecnológica Recomendada
*   **Linguagem:** TypeScript (para segurança e escalabilidade).
*   **Frontend / Backend:** Next.js (com API Routes) e TailwindCSS para um design moderno e responsivo.
*   **Banco de Dados e Autenticação:** Supabase (PostgreSQL serverless e sistema de login/roles integrado). ORM recomendado: Prisma.
*   **Hospedagem:** Vercel (deploy contínuo focado em Next.js).
*   **Controle de Versão:** Código hospedado e comittado no GitHub.
