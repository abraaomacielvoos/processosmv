# Plano de Tarefas (Task Breakdown)

Este documento divide a `spec.md` em tarefas menores e gerenciáveis para o desenvolvimento.

## Fase 1: Fundação e Setup do Projeto
- [ ] 1.1. Inicializar o projeto Next.js com suporte a TypeScript.
- [ ] 1.2. Configurar ESLint, Prettier, TailwindCSS e biblioteca de componentes UI.
- [ ] 1.3. Criar o repositório no GitHub e fazer o primeiro commit.
- [ ] 1.4. Configurar projeto no Supabase (Banco de Dados PostgreSQL e Auth).
- [ ] 1.5. Inicializar o Prisma ORM conectado ao Supabase.
- [ ] 1.6. Configurar o projeto na Vercel e ligar ao repositório GitHub para deploy automático.

## Fase 2: Modelagem de Dados e Banco de Dados
- [ ] 2.1. Definir o schema Prisma para a entidade `User` (Usuários e Roles).
- [ ] 2.2. Definir o schema Prisma para `Process` e `ProcessStep` (Processos e Passos/Slides).
- [ ] 2.3. Definir o schema Prisma para `App` (Aplicativos) e sua relação `n:m` com `Process`.
- [ ] 2.4. Definir o schema Prisma para `UserLearningProgress` (Registro de quais passos/processos o usuário marcou como aprendidos).
- [ ] 2.5. Gerar e aplicar a primeira migration no banco de dados.

## Fase 3: Criação da Interface Base (Layout e Navegação)
- [ ] 3.1. Criar layout principal com barra de navegação lateral (Treinamentos, Criar Processos, Histórico).
- [ ] 3.2. Criar página inicial (Dashboard de Treinamento).
- [ ] 3.3. Configurar roteamento básico do Next.js.

## Fase 4: Módulo de Criação de Processos (Builder - Admin)
- [ ] 4.1. Criar página de listagem de Processos.
- [ ] 4.2. Criar formulário para adicionar novo Processo (Título e Descrição).
- [ ] 4.3. Implementar interface para adicionar e listar Passos dentro de um Processo (sem formulários de coleta de dados).
- [ ] 4.4. Criar rotas de API para CRUD de Processos e Passos.
- [ ] 4.5. Integrar interface frontend com a API de criação.
- [ ] 4.6. Criar interface e API para cadastro de Aplicativos (Upload de logo e nome).
- [ ] 4.7. Implementar suporte a links do YouTube nos passos (Player embutido).
- [ ] 4.8. Implementar sistema para vincular Aplicativos a um Processo.

## Fase 5: Módulo de Treinamento (Modo Apresentação - Usuários)
- [ ] 5.1. Criar página para o usuário listar processos disponíveis para estudo.
- [ ] 5.2. Criar interface "Modo Apresentação" exibindo os dados do passo como um slide.
- [ ] 5.3. Implementar botões de controle de mídia: Avançar, Voltar, Play (Avanço automático) e Pause.
- [ ] 5.4. Exibir os ícones dos Aplicativos vinculados no cabeçalho da apresentação.
- [ ] 5.5. Exibir o player de vídeo do YouTube incorporado quando um passo possuir link de vídeo.
- [ ] 5.6. Criar funcionalidade "Marcar como Aprendido" (Checkbox ou Botão).
- [ ] 5.7. Criar rota de API para salvar o progresso de aprendizado do usuário (`UserLearningProgress`).

## Fase 6: Dashboards e Relatórios
- [ ] 6.1. Alimentar o Dashboard do Usuário com seu próprio progresso de treinamento.
- [ ] 6.2. Criar página/dashboard para o Admin ver quem já concluiu os treinamentos da empresa.

## Fase 7: Autenticação e Permissões (Obrigatório)
- [ ] 7.1. Criar Tela de Login e integrar com Supabase Auth.
- [ ] 7.2. Implementar lógica de Roles (Admin vs Usuário Comum) no banco de dados.
- [ ] 7.3. Proteger rotas de criação/edição para que apenas administradores tenham acesso.
- [ ] 7.4. Restringir interface de Usuários Comuns apenas à visualização/treinamento de processos.
