# Critérios de Aceite e Testes (Acceptance Criteria)

Este documento define as condições que devem ser atendidas para que cada funcionalidade seja considerada pronta e funcional.

## 1. Autenticação e Permissões
*   **Login Restrito:** O sistema não deve permitir o acesso à plataforma sem um login válido no Supabase.
*   **Acesso Admin:** Apenas usuários com a role "Admin" devem conseguir visualizar os menus e telas de criação/edição de templates e gestão de apps.
*   **Acesso Usuário Comum:** Usuários sem a role "Admin" que tentarem acessar a URL de edição de um processo devem ser bloqueados. Eles só podem ver a lista de processos para treinamento.

## 2. Gestão de Processos (Documentação)
*   **Criação com Sucesso:** O sistema deve permitir que o Admin crie um novo processo informando título e adicione instruções textuais e de mídia (sem campos de input para coleta de dados).
*   **Persistência da Ordem:** Os passos adicionados devem manter a ordem exata em que foram inseridos após a página ser recarregada.
*   **Vídeos Embutidos:** O sistema deve aceitar a inserção de um link do YouTube num passo, validá-lo e garantir que o player seja exibido.
*   **Cadastro e Associação de Apps:** Deve ser possível cadastrar um "App" subindo sua logo. Ao documentar um processo, o Admin deve poder selecionar apps que ficarão vinculados visivelmente àquele processo.

## 3. Modo de Treinamento e Apresentação
*   **Controles da Apresentação:** A interface de estudo deve possuir botões de "Próximo" e "Anterior" funcionais. Deve existir um botão "Play" que passa os passos automaticamente em um intervalo de tempo, e um botão "Pause".
*   **Renderização de Mídia e Apps:** Durante a apresentação, os ícones dos aplicativos devem aparecer de forma clara. Se houver link de vídeo, o player do YouTube deve ser interativo.
*   **Navegação Livre:** Como o objetivo é aprendizado, o usuário não precisa estar "preso" a um passo. Ele pode avançar e voltar livremente pela apresentação.

## 4. Registro de Aprendizado
*   **Marcar como Aprendido:** O usuário deve ser capaz de clicar em um botão "Marcar como Aprendido" em cada passo ou ao final do processo.
*   **Persistência do Progresso:** O sistema deve salvar no banco de dados que aquele usuário específico aprendeu aquele passo, refletindo no seu progresso geral (ex: 50% concluído).

## 5. Requisitos Técnicos
*   **Hospedagem e CI/CD:** O projeto deve estar funcional no ambiente de produção da Vercel, e os deploys devem ocorrer automaticamente ao dar push para a branch principal no GitHub.
*   **TypeScript:** Todo o código fonte (front e back) não deve apresentar erros de compilação de tipagem TypeScript.
*   **Responsividade:** O Modo Apresentação deve funcionar perfeitamente em telas de smartphones.
