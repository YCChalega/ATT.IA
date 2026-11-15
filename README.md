# Rotina Leve

Aplicação web simples para ajudar estudantes a organizar hábitos de estudo e acompanhar sua consistência ao longo da semana.

## 1. Termo de Abertura do Projeto (Project Charter)

### Problema real

Estudantes que tentam manter uma rotina de estudos podem ter dificuldade para lembrar as atividades planejadas e perceber se estão conseguindo manter a regularidade. Anotações espalhadas ou ferramentas com muitos recursos tornam o acompanhamento menos prático.

### Proposta de valor

O Rotina Leve reúne hábitos de estudo em uma lista clara, permite registrar a conclusão diária e mostra o progresso da semana. A proposta é oferecer um acompanhamento rápido, sem exigir cadastro ou configuração complexa.

### Escopo

**Dentro do escopo desta versão:**

- Cadastrar um hábito de estudo com nome e frequência semanal.
- Exibir, editar e excluir hábitos cadastrados.
- Marcar um hábito como concluído no dia atual e desfazer essa marcação.
- Consultar o progresso da semana por hábito.
- Salvar os dados no navegador para que permaneçam disponíveis após fechar e reabrir a aplicação no mesmo dispositivo e navegador.

**Fora do escopo desta versão:**

- Criação de contas, autenticação e sincronização entre dispositivos.
- Notificações, alarmes ou integração com calendários.
- Compartilhamento de hábitos ou acompanhamento por professores.
- Aplicativo móvel nativo e funcionamento sincronizado entre navegadores.
- Recomendações automáticas ou recursos de inteligência artificial.

## 2. Histórias de Usuário (User Stories)

1. Como estudante, quero cadastrar um hábito de estudo com uma frequência semanal, para que eu possa planejar minha rotina.
2. Como estudante, quero marcar um hábito como concluído no dia atual, para que eu acompanhe o que já realizei.
3. Como estudante, quero visualizar meu progresso semanal, para que eu perceba se estou mantendo a frequência planejada.
4. Como estudante, quero editar ou excluir um hábito, para que a lista continue refletindo meus objetivos atuais.

## 3. Requisitos do Sistema

### Requisitos Funcionais (RF)

- **RF01:** O sistema deve permitir cadastrar um hábito informando seu nome e a quantidade de dias por semana desejada.
- **RF02:** O sistema deve listar os hábitos cadastrados e permitir editar seus dados ou removê-los.
- **RF03:** O sistema deve permitir marcar e desmarcar a conclusão de cada hábito no dia atual.
- **RF04:** O sistema deve apresentar, para cada hábito, quantos dias foram concluídos na semana atual em relação à frequência planejada.
- **RF05:** O sistema deve salvar e recuperar os hábitos e suas marcações usando o armazenamento local do navegador.
- **RF06:** O sistema deve validar os campos do cadastro e informar quando os dados forem inválidos.

### Requisitos Não Funcionais (RNF)

- **RNF01 — Usabilidade:** As ações principais (cadastrar hábito e marcar conclusão) devem estar disponíveis na tela inicial sem navegação por páginas adicionais.
- **RNF02 — Responsividade:** A interface deve poder ser utilizada em telas de celular e de computador sem exigir rolagem horizontal.
- **RNF03 — Compatibilidade:** A aplicação deve funcionar nas versões atuais dos navegadores Google Chrome, Microsoft Edge e Mozilla Firefox.
- **RNF04 — Persistência local:** Os dados devem permanecer disponíveis após recarregar ou reabrir a aplicação no mesmo navegador e dispositivo.
- **RNF05 — Desempenho:** Em condições normais, as ações de cadastro, edição, exclusão e marcação devem atualizar a interface em até 1 segundo.

## 4. Caso de Uso Principal e Tratamento de Erros

### Caso de uso: registrar um dia de estudo

1. **Ação do usuário:** O estudante abre a aplicação e seleciona a opção para marcar como concluído um hábito na lista.
2. **Processamento do sistema:** O sistema registra a conclusão para o hábito e a data atual, atualiza o progresso semanal e salva os dados no armazenamento local.
3. **Retorno na tela:** A interface indica visualmente que o hábito foi concluído e exibe o progresso semanal atualizado.

### Fluxo de exceção

- **Nome vazio ou frequência inválida:** O sistema não salva o hábito, mantém o formulário aberto e apresenta uma mensagem explicando quais campos precisam ser corrigidos.
- **Falha ao salvar no navegador:** O sistema informa que não foi possível salvar os dados e orienta o usuário a verificar o armazenamento disponível no navegador. A interface não deve apresentar a operação como concluída.
- **Hábito removido ou não encontrado:** O sistema atualiza a lista e informa que o item não está mais disponível, sem interromper o uso da aplicação.

## 5. Arquitetura e Escolha da Stack Tecnológica

- **Interface / Frontend:** HTML, CSS e JavaScript.
- **Lógica / Backend:** JavaScript executado no navegador; esta versão não terá um backend separado.
- **Armazenamento:** `localStorage` do navegador.

Essa combinação mantém o projeto pequeno e permite desenvolver a experiência completa sem configurar servidor ou banco de dados. HTML, CSS e JavaScript são suficientes para criar uma interface responsiva, validar os dados e persistir as informações localmente.

## 6. Critérios de Aceite e Definição de Pronto (Definition of Done)

O projeto será considerado pronto quando:

- For possível cadastrar um hábito válido e vê-lo na lista.
- Campos obrigatórios vazios e frequências fora do intervalo permitido forem rejeitados com mensagens claras.
- For possível editar e excluir um hábito.
- Marcar e desmarcar uma conclusão atualizar corretamente o progresso semanal.
- Hábitos e marcações permanecerem salvos após recarregar a página no mesmo navegador.
- A aplicação puder ser utilizada em telas de celular e computador sem rolagem horizontal.
- As ações principais funcionarem nos navegadores definidos no RNF03, sem erros que impeçam o uso.
