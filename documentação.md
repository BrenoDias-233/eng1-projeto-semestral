
# DOCUMENTAÇÃO

## 1. Requisitos Funcionais (RF)

| Código | Descrição |
|--------|-----------|
| RF01 | O sistema deve permitir a criação de uma conta com nome, e-mail e senha. |
| RF02 | O sistema deve autenticar usuários para que acessem a plataforma utilizando e-mail e senha válidos. |
| RF03 | O usuário deve poder criar projetos com nome e descrição. |
| RF04 | O usuário deve ser capaz de excluir os projetos criados. |
| RF05 | O sistema deve permitir a criação de tarefas em um projeto, contendo título, descrição, responsável (opcional), status e data de criação. |
| RF06 | O usuário deve ser capaz de atribuir uma tarefa a um membro do projeto. |
| RF07 | O sistema deve permitir a alteração ou exclusão das tarefas existentes. |
| RF08 | O sistema deve classificar o status das tarefas entre: a fazer, em progresso e concluído. |
| RF09 | O sistema deve permitir a criação de comentários nas tarefas. |
| RF10 | O sistema deve gerar notificações em eventos como atribuição de tarefas, mudança de status, novos comentários, entrada de novo membro no projeto, nova tarefa atribuída, novo comentário em tarefa atribuída ao usuário e mudanças de status. |
| RF11 | O sistema deve registrar e apresentar um histórico contendo alterações de status, mudanças de responsáveis e edições em tarefas. |

## Requisitos Não Funcionais (RNF)

| Código | Descrição |
|--------|-----------|
| RNF01 | O sistema deve ser intuitivo e de fácil aprendizado. |
| RNF02 | O sistema deve ser compatível com os navegadores mais populares do mercado. |
| RNF03 | O sistema deve realizar logout automático após 1 hora de inatividade. |

## 2. Cartões de tarefas (XP)

| Cartão | Descrição | Critérios |
|--------|-----------|-----------|
| Criar conta | Como visitante, quero criar uma conta para acessar a plataforma e participar de projetos. | Cadastro usa nome, e-mail e senha; e-mail deve ser único; senha deve atender aos critérios mínimos definidos. |
| Autenticação de usuário | Como usuário registrado quero fazer login com e-mail e senha para acessar meus projetos e tarefas. | E-mail e senha devem ser validados. |
| Criar projeto | Como usuário, quero criar projetos para organizar tarefas do meu grupo. | Nome é obrigatório; a descrição é opcional. |
| Excluir projeto | Como criador do projeto, quero poder excluir para remover informações não mais úteis. | Exibir aviso de confirmação; tarefas do projeto devem ser excluídas. |
| Criar tarefas | Como membro do projeto, quero criar tarefas para organizar e registrar atividades. | Deve conter título, descrição, responsável (opcional), status e data de criação; status inicial = A Fazer. |
| Atribuir tarefa a membro | Como usuário, quero atribuir uma tarefa a um membro para distribuir responsabilidades dentro da equipe. | Alteração deve gerar notificação; apenas o dono do projeto pode atribuir tarefas. |
| Editar e excluir tarefas | Como usuário, quero editar ou excluir tarefas para mantê-las atualizadas ou remover tarefas não úteis. | Apenas usuários autorizados podem editar/excluir; exclusão deve pedir confirmação; alterações devem ser notificadas. |
| Alterar status da tarefa | Como membro do projeto, quero alterar o status das tarefas para indicar seu andamento. | Mudanças registradas no histórico; deve gerar notificação. |
| Criar comentários em tarefas | Como membro do projeto, quero comentar em tarefas para compartilhar informações. | Comentários devem exibir autor e data. |
| Notificações | Como usuário, quero receber notificações sobre eventos para acompanhar mudanças no projeto. | Eventos: atribuição de tarefas; mudança de status; novos comentários; nova tarefa criada. |
| Histórico de Alterações | Como usuário, quero ter acesso ao histórico de uma tarefa para entender o que mudou, quando e quem fez. | Deve registrar mudanças de status; mudança de responsável; edições feitas. |

## **3. Spikes**

### **Spike 01 -- Estudo sobre notificações em tempo real**

Nós precisamos entender quais tecnologias são mais adequadas para
implementar notificações em tempo real no sistema, já que os usuários
devem receber atualizações instantâneas sobre tarefas, comentários e
mudanças nos projetos. Vamos pesquisar opções como WebSockets,
Socket.io, SSE e também soluções de push, como Firebase Cloud Messaging.
Nosso objetivo é identificar qual alternativa oferece melhor desempenho,
integra bem com o backend e o frontend escolhidos, e ainda permite
integrar notificações por e-mail, conforme os requisitos do projeto.

### **Spike 02 -- Análise de ferramentas para upload de arquivos**

Antes de desenvolver a funcionalidade de envio de arquivos, vamos testar
algumas ferramentas que permitam realizar uploads de forma segura e
organizada. Avaliaremos bibliotecas como Multer (caso utilizemos
Node.js) e serviços de armazenamento em nuvem, como Firebase Storage,
Supabase e AWS S3. Pretendemos comparar segurança, permissões,
facilidade de implementação e suporte a histórico de alterações, que é
algo previsto no projeto.

### **Spike 03 -- Escolha do banco de dados ideal**

Para armazenar usuários, projetos, tarefas, comentários, notificações e
o histórico de mudanças, vamos analisar diferentes bancos de dados
recomendados: PostgreSQL, MySQL, MongoDB e Firestore. O objetivo é
avaliar desempenho, flexibilidade da modelagem, suporte a consultas mais
complexas, integração com o backend e comportamento em cenários de uso
simultâneo. Ao final, escolheremos o banco mais adequado e
justificaremos tecnicamente a decisão.

### **Spike 04 -- Teste de ferramentas para criação dos mockups**

Antes de começar a desenhar as telas do sistema, vamos testar algumas
ferramentas de prototipação para identificar qual facilita mais o
trabalho do grupo. Entre as opções que iremos analisar estão Figma,
Canva e Balsamiq. Vamos comparar facilidade de uso, colaboração entre os
integrantes, qualidade da prototipação e recursos para documentar o
design de maneira clara e organizada.

### **Spike 05 -- Modelagem para organização de tarefas e tópicos**

Este spike tem como objetivo estudar a melhor forma de modelar a
organização de tarefas e tópicos de estudo dentro do sistema. Vamos
pesquisar estruturas de tabelas, tipos de relacionamentos e estratégias
de indexação que deixem as consultas mais eficientes. Também vamos
considerar as diferenças entre modelagens relacionais e NoSQL,
garantindo que a estrutura suporte múltiplos usuários colaborando ao
mesmo tempo sem perda de desempenho.

## 4. Mockups (imagens anexadas à pasta)

- Tela 1 – Login  
- Tela 2 – Mural  
- Tela 3 – Tarefas  
- Tela 4 – Perfil  

## 5. Cronograma (Gantt)

| Fase | Atividade | Início | Fim | Duração |
|------|-----------|--------|------|----------|
| 1 | Levantamento do sistema | 01/11 | 03/11 | 3 dias |
| 2 | Definição de requisitos | 03/11 | 05/11 | 2 dias |
| 3 | Cartões de tarefas (XP) | 05/11 | 06/11 | 1 dia |
| 4 | Spikes | 05/11 | 08/11 | 3 dias |
| 5 | Mockups | 08/11 | 11/11 | 3 dias |
| 6 | Repositório GitHub | 10/11 | 11/11 | 2 dias |


## 6. Linguagens de Programação e Tecnologias Utilizadas

Para o desenvolvimento do sistema, optamos por utilizar tecnologias amplamente adotadas no mercado, que oferecem bom desempenho, facilidade de integração e suporte da comunidade.

No backend, utilizamos o **Node.js**, pois ele permite a construção de aplicações web eficientes e escaláveis. Como o Node.js utiliza JavaScript, a mesma linguagem empregada no frontend, isso facilita a padronização do desenvolvimento e a comunicação entre as partes do sistema, além de tornar o código mais simples de manter.

O frontend foi desenvolvido com **React**, uma biblioteca JavaScript voltada para a criação de interfaces de usuário. Escolhemos o React por possibilitar a criação de componentes reutilizáveis, o que torna a interface mais organizada, dinâmica e de fácil manutenção. Além disso, o React se integra bem com APIs REST, sendo adequado para aplicações web modernas.

Para o armazenamento dos dados, utilizamos o **MySQL**, um sistema gerenciador de banco de dados relacional. Essa escolha se deu por conta da estrutura bem definida do sistema, que envolve entidades como usuários, projetos e tarefas. O MySQL oferece estabilidade, bom desempenho e fácil integração com o Node.js, atendendo às necessidades do projeto.

O versionamento do código foi realizado com o **Git**, permitindo que todos os integrantes da equipe trabalhassem de forma colaborativa. Com o Git, foi possível acompanhar o histórico de alterações, organizar o desenvolvimento em versões e reduzir problemas relacionados a conflitos de código.

Para a prototipação das telas, utilizamos o **Canvas**, que permite a criação de representações visuais das interfaces do sistema. O uso do Canvas possibilitou desenhar e planejar a estrutura das telas antes da implementação, auxiliando na definição do layout, disposição dos elementos e fluxo de navegação do sistema.

Por fim, os testes das APIs foram realizados com o **Postman**, uma ferramenta que permite simular requisições HTTP e validar o funcionamento dos endpoints desenvolvidos. Com o uso do Postman, conseguimos testar autenticação, envio e retorno de dados, garantindo que a integração entre frontend e backend ocorresse corretamente.

---

## 7. Planejamento de Sprints

## Sprint 1: Autenticação e Base do Sistema

### Milestone 1

**Objetivo:** Criar a base do sistema com autenticação de usuários e infraestrutura inicial.

**Itens do Milestone:**
- Modelagem inicial do banco  
- Login  
- Tela de cadastro  
- Validações tela de cadastro  
- Tela de login  
- Integração das telas com backend  
- Auto Logout após 1h de inatividade  

---

## Sprint 2: Projetos

### Milestone 2

**Objetivo:** Permitir que usuários criem, visualizem e excluam projetos.

**Itens do Milestone:**
- Tela “Meus Projetos”  
- Criar / excluir / listar projetos  
- Integração frontend e backend  

---

## Sprint 3: Tarefas e Atribuições

### Milestone 3

**Objetivo:** Gerenciar tarefas dentro dos projetos, com status e permissões.

**Itens do Milestone:**
- CRUD de tarefas  
- Tela de visualização das tarefas  
- Atribuição de tarefas e permissões  
- Classificação de status  

---

## Sprint 4: Comentários e Notificações

### Milestone 4

**Objetivo:** Permitir interação entre usuários através de comentários e notificações.

**Itens do Milestone:**
- Comentários  
- Interface de comentários  
- Sistema de notificações  
- Eventos automáticos  

---

## Sprint 5: Histórico e Polimento Final

### Milestone 5

**Objetivo:** Registrar histórico das tarefas e melhorar a experiência do usuário.

**Itens do Milestone:**
- Registro de histórico no backend  
- Tela de histórico por tarefa  
- Ajustes de UX / UI  

---

# Cronograma de Sprints

## Sprint 1: Autenticação e Base do Sistema

**Duração:** 1ª semana  
**Milestone:** Autenticação e infraestrutura  

| Dia | Atividades |
|----|-----------|
| Dia 1 | Planejamento do Sprint + criação das issues e milestones no GitHub |
| Dia 1 | Configuração inicial do projeto (repositório, estrutura, dependências) |
| Dia 2 | Modelagem do banco de dados |
| Dia 2 | Início da tela de cadastro |
| Dia 3 | Endpoint de cadastro de usuário |
| Dia 3 | Validação do formulário de cadastro |
| Dia 4 | Endpoint de login com JWT |
| Dia 4 | Tela de login + integração com backend |
| Dia 5 | Auto Logout após 1h de inatividade |
| Dia 5 | Testes iniciais e ajustes |
| Dia 5 (Review) | Review do Sprint + entrega da Milestone |

---

## Sprint 2: Projetos

**Duração:** 2ª semana  
**Milestone:** Gerenciamento de Projetos  

| Dia | Atividades |
|----|-----------|
| Dia 1 | Revisão do backlog + planejamento do Sprint |
| Dia 1 | Criação dos endpoints de projetos |
| Dia 2 | Listagem de projetos no backend |
| Dia 2 | Tela “Meus Projetos” |
| Dia 3 | Formulário de criação de projeto |
| Dia 3 | Endpoint de exclusão de projeto |
| Dia 4 | Confirmação visual para exclusão |
| Dia 4 | Integração frontend ↔ backend |
| Dia 5 | Testes de CRUD de projetos |
| Dia 5 (Review) | Review + ajustes finais |

---

## Sprint 3 — Tarefas e Atribuições

**Duração:** 3ª semana  
**Milestone:** Tarefas e permissões  

| Dia | Atividades |
|----|-----------|
| Dia 1 | Planejamento do Sprint |
| Dia 1 | CRUD de tarefas (backend) |
| Dia 2 | Tela de tarefas do projeto |
| Dia 2 | Formulário de criação/edição de tarefas |
| Dia 3 | Endpoint de atribuição de tarefas |
| Dia 3 | Implementação de permissões |
| Dia 4 | Status das tarefas (A Fazer, Em Progresso, Concluído) |
| Dia 4 | Integração frontend ↔ backend |
| Dia 5 | Testes gerais de tarefas |
| Dia 5 (Review) | Review do Sprint |

---

## Sprint 4 — Comentários e Notificações

**Duração:** 4ª semana  
**Milestone:** Comunicação e alertas  

| Dia | Atividades |
|----|-----------|
| Dia 1 | Planejamento do Sprint |
| Dia 1 | Endpoint de comentários |
| Dia 2 | Interface de comentários |
| Dia 2 | Sistema de notificações (backend) |
| Dia 3 | Exibição de notificações (frontend) |
| Dia 3 | Eventos automáticos (atribuição, comentários, status) |
| Dia 4 | Integração e testes de notificações |
| Dia 5 | Ajustes finais |
| Dia 5 (Review) | Review do Sprint |

---

## Sprint 5 — Histórico e Refinamento

**Duração:** 5ª semana  
**Milestone:** Histórico e UX  

| Dia | Atividades |
|----|-----------|
| Dia 1 | Planejamento final |
| Dia 1 | Registro de histórico no backend |
| Dia 2 | Tela de histórico por tarefa |
| Dia 3 | Ajustes de UX/UI |
| Dia 3 | Testes finais do sistema |
| Dia 4 | Correções gerais |
| Dia 4 | Documentação final |
| Dia 5 | Apresentação / entrega final |

---

## 8. Questionário para entrevistas com stakeholders
https://docs.google.com/forms/d/e/1FAIpQLSfSO7omAWEUYoFCL6f0mgsgUtmuAD_2x5h6ACbte9V3GCrZUQ/viewform?usp=dialog
