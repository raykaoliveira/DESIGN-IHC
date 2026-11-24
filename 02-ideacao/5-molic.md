<div align="center">
  
# Diagramas MoLIC

<img src="https://img.shields.io/badge/TP2-DESIGN THINKING-167D72?style=for-the-badge">
<img src="https://img.shields.io/badge/ARTEFATO-MOLIC-70CDB5?style=for-the-badge">
<img src="https://img.shields.io/badge/DISCIPLINA-IHC-E8B7C8?style=for-the-badge">

</div>

## 01. Introdução

Este documento apresenta a modelagem da interação entre usuários e o aplicativo do GAPI com a linguagem MoLIC (*Modeling Language for Interaction as Conversation*). O diagrama foi construído a partir das tarefas definidas nos sete HTAs e representa, em forma de conversa, o que o usuário diz ao sistema (`u:`) e como o sistema responde (`d:`) em cada funcionalidade. Primeiro é apresentada a visão geral do diagrama completo e, em seguida, cada parte é ampliada e explicada.

## 02. Notação utilizada

| Elemento | Representação | Significado |
|---|---|---|
| Ponto de abertura | círculo preto | início da interação |
| Ponto de encerramento | círculo preto dentro de um anel | fim da interação |
| Cena | retângulo arredondado | momento da conversa, com tópico e diálogos |
| Acesso ubíquo (Menu inicial) | retângulo cinza | acessível a partir de qualquer cena |
| Processo do sistema | quadrado preto | processamento interno, fora do alcance do usuário |
| `u:` / `d:` | rótulo da transição | fala do usuário / fala do designer (sistema) |
| `d+u:` | rótulo de diálogo | sistema e usuário trocam falas |
| Seta tracejada | transição | saída ou cancelamento da funcionalidade |
| `XOR` | operador | escolha exclusiva entre as opções |

## 03. Visão geral do diagrama completo

<img width="3582" height="1150" alt="image" src="https://github.com/user-attachments/assets/d577d442-02d8-413f-9ca0-a7758eeeda1d" />


O diagrama tem dez partes, uma para cada HTA. Todas seguem o mesmo padrão: partem do **Menu inicial** (acesso ubíquo, em cinza), que permite entrar em qualquer funcionalidade e sair do aplicativo com `u: Sair`. Dentro de cada parte, o usuário avança por cenas conectadas por processos do sistema: ele envia `u: Prosseguir`, o sistema processa e responde com um `d:` que leva à cena seguinte. Setas de retorno permitem corrigir uma escolha e setas tracejadas permitem sair da funcionalidade ou cancelar a operação, voltando ao Menu inicial.

| Parte | Funcionalidade | HTA relacionado |
|---|---|---|
| 1 | Acesso ao aplicativo conforme o perfil | HTA 1 |
| 2 | Consulta de animais para adoção | HTA 2 |
| 3 | Gerenciamento do cadastro dos animais | HTA 3 |
| 4 | Registro e formalização da adoção | HTA 4 |
| 5 | Acompanhamento do animal após a adoção | HTA 5 |
| 6 | Levantamento financeiro das feiras | HTA 6 |
| 7 | Acessibilidade e personalização | HTA 7 |
| 8 | Organização de eventos e relatórios | HTA 8 |
| 9 | Organização de registros e assinaturas | HTA 9 |
| 10 | Organizar a carteirinha digital | HTA 10 |

## 4. Detalhamento por partes

<div align="center">

  ### Parte 1 – Acesso ao aplicativo (HTA 1)

<img width="619" height="1550" alt="image" src="https://github.com/user-attachments/assets/f253733b-003a-4d86-979f-02e9917ec3b7" />

**Resumo da parte:** O usuário entra no aplicativo, escolhe o tipo de acesso (área pública ou área do voluntário) e, no caso do voluntário, informa suas credenciais para chegar ao ambiente do seu perfil. Atende ao objetivo de acessar o aplicativo conforme o perfil.

</div>

**Cenas**

| Cena | Diálogos | Papel no fluxo |
|---|---|---|
| Identificar perfil | `d: Opções de acesso`; o usuário seleciona o tipo de acesso (`XOR`: Área pública ou Área do voluntário) | Ponto de partida: apresenta as opções e define o perfil de uso |
| Autenticar voluntário | O usuário informa matrícula e senha (`d+u`) e confirma; se as credenciais forem inválidas, o sistema responde com `d: Mensagem de erro` e o usuário corrige os dados | Verifica quem é o voluntário antes de liberar a área restrita |
| Acesso liberado | `d: Ambiente do perfil` (`XOR`: Área pública ou Área restrita do GAPI) | Entrega o ambiente correspondente ao perfil identificado |

**Transições**

| De | Para | Fala | Condição |
|---|---|---|---|
| Menu inicial | Identificar perfil | `u: Acessar o aplicativo` | Acesso ubíquo: pode ser feito a partir do Menu inicial a qualquer momento |
| Identificar perfil | Processo do sistema | `u: Prosseguir` | O usuário concluiu os diálogos da cena |
| Processo do sistema | Autenticar voluntário | `d: Perfil identificado` | O processamento foi concluído com sucesso |
| Autenticar voluntário | Processo do sistema | `u: Prosseguir` | O usuário concluiu os diálogos da cena |
| Processo do sistema | Acesso liberado | `d: Acesso concedido` | O processamento foi concluído com sucesso |
| Autenticar voluntário | Identificar perfil | `u: Alterar perfil` | O usuário quer corrigir ou mudar uma escolha anterior |
| Identificar perfil | Menu inicial | `u: Sair da funcionalidade` (tracejada) | O usuário desiste e abandona a funcionalidade sem concluir |
| Autenticar voluntário | Menu inicial | `u: Cancelar acesso` (tracejada) | O usuário desiste e abandona a funcionalidade sem concluir |

**Processos do sistema:** Dois processos: o primeiro registra o perfil escolhido (`d: Perfil identificado`) e o segundo valida as credenciais (`d: Acesso concedido`).

**Rupturas e recuperação:** Credenciais inválidas são tratadas dentro da própria cena de autenticação: o sistema exibe a mensagem de erro e o usuário corrige os dados e confirma novamente. Em qualquer ponto, `u: Alterar perfil` volta à escolha do tipo de acesso e as setas tracejadas (`u: Sair da funcionalidade` e `u: Cancelar acesso`) levam ao Menu inicial.

**Relação com o HTA 1:** A cena *Identificar perfil* corresponde à tarefa 1 do HTA (visualizar as opções e selecionar acesso público ou de voluntário). A cena *Autenticar voluntário* cobre as tarefas 3 (acessar a área restrita, com matrícula e senha) e 4 (tratar falhas: mensagem de erro, correção dos dados e nova tentativa). A cena *Acesso liberado* corresponde às tarefas 2 e 3 (entrar na área pública ou no ambiente restrito).

---

<div align="center">
  
### Parte 2 – Consulta de animais para adoção (HTA 2)

<img width="651" height="1921" alt="image" src="https://github.com/user-attachments/assets/f8bd9629-28d9-4a1d-9185-3e66c828cd65" />

**Resumo da parte:** O interessado acessa a área pública, consulta o catálogo de animais disponíveis, vê os dados de um animal específico e, se tiver interesse, recebe o link que o leva ao WhatsApp dos voluntários do GAPI.

</div>

**Cenas**

| Cena | Diálogos | Papel no fluxo |
|---|---|---|
| Acessar catálogo | O usuário acessa a área pública e seleciona a opção de animais para adoção | Dá entrada no catálogo |
| Visualizar animais | `d: Lista de animais disponíveis`, `d: Fotografias dos animais`, `d: Características e informações dos pets`; o usuário seleciona o animal desejado | Permite comparar os animais e escolher um |
| Consultar animal | `d: Informações individuais` e `d: Situação de disponibilidade`; o usuário pode manifestar interesse (`u: Tenho interesse`) | Detalha o animal e confirma se ele continua disponível |
| Contato com o GAPI | `d: Link de direcionamento ao WhatsApp`; o usuário acessa o link para iniciar a conversa com os voluntários | Encaminha o interessado ao atendimento, que ocorre fora do aplicativo |

**Transições**

| De | Para | Fala | Condição |
|---|---|---|---|
| Menu inicial | Acessar catálogo | `u: Consultar animais` | Acesso ubíquo: pode ser feito a partir do Menu inicial a qualquer momento |
| Acessar catálogo | Processo do sistema | `u: Prosseguir` | O usuário concluiu os diálogos da cena |
| Processo do sistema | Visualizar animais | `d: Catálogo exibido` | O processamento foi concluído com sucesso |
| Visualizar animais | Processo do sistema | `u: Prosseguir` | O usuário concluiu os diálogos da cena |
| Processo do sistema | Consultar animal | `d: Animal selecionado` | O processamento foi concluído com sucesso |
| Consultar animal | Processo do sistema | `u: Prosseguir` | O usuário concluiu os diálogos da cena |
| Processo do sistema | Contato com o GAPI | `d: Link do WhatsApp disponível` | O processamento foi concluído com sucesso |
| Consultar animal | Visualizar animais | `u: Escolher outro animal` | O usuário quer corrigir ou mudar uma escolha anterior |
| Acessar catálogo | Menu inicial | `u: Sair da funcionalidade` (tracejada) | O usuário desiste e abandona a funcionalidade sem concluir |
| Consultar animal | Menu inicial | `u: Cancelar interesse` (tracejada) | O usuário desiste e abandona a funcionalidade sem concluir |

**Processos do sistema:** Três processos: exibir o catálogo (`d: Catálogo exibido`), carregar o animal escolhido (`d: Animal selecionado`) e disponibilizar o link (`d: Link do WhatsApp disponível`).

**Rupturas e recuperação:** Se o usuário quiser ver outro animal, `u: Escolher outro animal` retorna à lista. As setas tracejadas permitem sair da funcionalidade ou cancelar o interesse, voltando ao Menu inicial.

**Relação com o HTA 2:** As quatro cenas correspondem às quatro tarefas do HTA: acessar o catálogo (1), visualizar os animais (2), consultar um animal específico (3) e iniciar contato com o GAPI (4). A conversa no WhatsApp acontece externamente e por isso não aparece como cena.

---

<div align="center">
  
### Parte 3 – Gerenciamento do cadastro dos animais (HTA 3)

<img width="640" height="1925" alt="image" src="https://github.com/user-attachments/assets/678381db-932e-4813-9967-ddd112fc4c2a" />

**Resumo da parte:** O voluntário acessa a área de gerenciamento, escolhe entre cadastrar um novo animal, atualizar informações ou atualizar a disponibilidade, preenche os dados e salva, o que atualiza o catálogo público.

</div>

**Cenas**

| Cena | Diálogos | Papel no fluxo |
|---|---|---|
| Acessar gerenciamento | O voluntário realiza login (matrícula e senha) e seleciona o gerenciamento de animais | Dá acesso à funcionalidade administrativa |
| Escolher operação | Seleção da operação (`XOR`: Cadastrar novo animal, Atualizar informações ou Atualizar disponibilidade) | Define o caminho que o voluntário seguirá |
| Preencher dados do animal | O usuário informa o nome, as características e informações, anexa ou substitui fotografias e informa a situação (`XOR`: Disponível ou Indisponível) | Reúne os dados necessários para cadastro ou atualização |
| Registro salvo | `d: Confirmação da alteração` e `d: Catálogo público atualizado` | Confirma a operação e informa que o catálogo foi atualizado |

**Transições**

| De | Para | Fala | Condição |
|---|---|---|---|
| Menu inicial | Acessar gerenciamento | `u: Gerenciar animais` | Acesso ubíquo: pode ser feito a partir do Menu inicial a qualquer momento |
| Acessar gerenciamento | Processo do sistema | `u: Prosseguir` | O usuário concluiu os diálogos da cena |
| Processo do sistema | Escolher operação | `d: Área de gerenciamento` | O processamento foi concluído com sucesso |
| Escolher operação | Processo do sistema | `u: Prosseguir` | O usuário concluiu os diálogos da cena |
| Processo do sistema | Preencher dados do animal | `d: Operação selecionada` | O processamento foi concluído com sucesso |
| Preencher dados do animal | Processo do sistema | `u: Prosseguir` | O usuário concluiu os diálogos da cena |
| Processo do sistema | Registro salvo | `d: Cadastro salvo` | O processamento foi concluído com sucesso |
| Preencher dados do animal | Escolher operação | `u: Alterar operação` | O usuário quer corrigir ou mudar uma escolha anterior |
| Acessar gerenciamento | Menu inicial | `u: Sair da funcionalidade` (tracejada) | O usuário desiste e abandona a funcionalidade sem concluir |
| Preencher dados do animal | Menu inicial | `u: Cancelar alterações` (tracejada) | O usuário desiste e abandona a funcionalidade sem concluir |

**Processos do sistema:** Três processos: abrir a área de gerenciamento (`d: Área de gerenciamento`), preparar a operação escolhida (`d: Operação selecionada`) e gravar o registro (`d: Cadastro salvo`).

**Rupturas e recuperação:** Se o voluntário escolheu a operação errada, `u: Alterar operação` volta à escolha. As setas tracejadas (`u: Sair da funcionalidade` e `u: Cancelar alterações`) levam ao Menu inicial sem salvar.

**Relação com o HTA 3:** A cena *Acessar gerenciamento* corresponde à tarefa 1 do HTA. *Escolher operação* representa a decisão entre as tarefas 2 (cadastrar), 3 (atualizar informações) e 4 (atualizar disponibilidade). *Preencher dados do animal* reúne as subtarefas de edição dessas três operações, e *Registro salvo* corresponde às subtarefas de salvar e atualizar o catálogo público.

---

<div align="center">

### Parte 4 – Registro e formalização da adoção (HTA 4)

<img width="666" height="1921" alt="image" src="https://github.com/user-attachments/assets/92b23fbd-5c51-4bd2-b731-5d4394cfa310" />

**Resumo da parte:** Depois do contato externo, o voluntário seleciona o animal adotado, registra os dados do adotante, formaliza o termo de adoção e o sistema gera a carteirinha digital do pet, vinculada ao tutor.

</div>

**Cenas**

| Cena | Diálogos | Papel no fluxo |
|---|---|---|
| Iniciar registro | O voluntário realiza login, acessa o registro de adoção e seleciona o animal adotado | Identifica qual adoção será registrada |
| Registrar adotante | O usuário informa os dados pessoais do adotante; `d: Adotante associado ao animal`; `d: Dados cadastrados` para conferência | Cadastra o tutor e permite conferir as informações |
| Formalizar termo | `d: Termo de adoção`; o adotante assina (`u: Assinatura do adotante`); `d: Formalização confirmada` | Formaliza juridicamente a adoção |
| Carteirinha digital | `d: Situação do animal: adotado`, `d: Identificação digital do pet gerada` e `d: Carteirinha vinculada ao tutor e disponível` | Conclui o processo, retira o animal do catálogo e entrega a carteirinha |

**Transições**

| De | Para | Fala | Condição |
|---|---|---|---|
| Menu inicial | Iniciar registro | `u: Registrar adoção` | Acesso ubíquo: pode ser feito a partir do Menu inicial a qualquer momento |
| Iniciar registro | Processo do sistema | `u: Prosseguir` | O usuário concluiu os diálogos da cena |
| Processo do sistema | Registrar adotante | `d: Animal selecionado` | O processamento foi concluído com sucesso |
| Registrar adotante | Processo do sistema | `u: Prosseguir` | O usuário concluiu os diálogos da cena |
| Processo do sistema | Formalizar termo | `d: Dados conferidos` | O processamento foi concluído com sucesso |
| Formalizar termo | Processo do sistema | `u: Prosseguir` | O usuário concluiu os diálogos da cena |
| Processo do sistema | Carteirinha digital | `d: Adoção registrada` | O processamento foi concluído com sucesso |
| Formalizar termo | Registrar adotante | `u: Corrigir dados inconsistentes` | O usuário quer corrigir ou mudar uma escolha anterior |
| Iniciar registro | Menu inicial | `u: Sair da funcionalidade` (tracejada) | O usuário desiste e abandona a funcionalidade sem concluir |
| Registrar adotante | Menu inicial | `u: Cancelar registro` (tracejada) | O usuário desiste e abandona a funcionalidade sem concluir |

**Processos do sistema:** Três processos: confirmar o animal selecionado (`d: Animal selecionado`), validar os dados conferidos (`d: Dados conferidos`) e registrar a adoção, atualizando a situação do animal e gerando a carteirinha (`d: Adoção registrada`).

**Rupturas e recuperação:** Se houver dados inconsistentes, `u: Corrigir dados inconsistentes` leva da cena do termo de volta ao registro do adotante, antes da conclusão. As setas tracejadas permitem sair da funcionalidade ou cancelar o registro.

**Relação com o HTA 4:** As quatro cenas seguem as quatro tarefas do HTA: iniciar o registro (1), registrar os dados do adotante (2), registrar o termo de adoção (3) e gerar a carteirinha digital (4). A decisão principal do HTA, a conferência dos dados, aparece na transição de retorno para corrigir inconsistências.

---

<div align="center">
  
### Parte 5 – Acompanhamento do animal após a adoção (HTA 5)

<img width="657" height="1569" alt="image" src="https://github.com/user-attachments/assets/bd55f695-5c99-42a7-8f13-8cdfb9e008fa" />

**Resumo da parte:** O tutor entra na área do tutor, consulta a carteirinha digital do animal adotado e escolhe o que acompanhar: vacinação, visitas ou informações gerais de acompanhamento.

</div>

**Cenas**

| Cena | Diálogos | Papel no fluxo |
|---|---|---|
| Consultar carteirinha | O usuário entra na área do tutor, seleciona o animal adotado e o sistema mostra a carteirinha digital | Dá acesso às informações de identificação do pet |
| Escolher acompanhamento | Seleção da atividade (`XOR`: Vacinação, Visitas ou Informações de acompanhamento) | Direciona o tutor para a atividade desejada |
| Acompanhar animal | Vacinação: vacinas registradas e pendentes, marcar como realizada e salvar. Visitas: data registrada pelo voluntário e notificação ao tutor. Informações: registros de vacinação, carteirinha e datas de visitas | Reúne as três formas de acompanhamento do animal |

**Transições**

| De | Para | Fala | Condição |
|---|---|---|---|
| Menu inicial | Consultar carteirinha | `u: Acompanhar animal` | Acesso ubíquo: pode ser feito a partir do Menu inicial a qualquer momento |
| Consultar carteirinha | Processo do sistema | `u: Prosseguir` | O usuário concluiu os diálogos da cena |
| Processo do sistema | Escolher acompanhamento | `d: Carteirinha exibida` | O processamento foi concluído com sucesso |
| Escolher acompanhamento | Processo do sistema | `u: Prosseguir` | O usuário concluiu os diálogos da cena |
| Processo do sistema | Acompanhar animal | `d: Atividade selecionada` | O processamento foi concluído com sucesso |
| Acompanhar animal | Escolher acompanhamento | `u: Escolher outra atividade` | O usuário quer corrigir ou mudar uma escolha anterior |
| Consultar carteirinha | Menu inicial | `u: Sair da funcionalidade` (tracejada) | O usuário desiste e abandona a funcionalidade sem concluir |
| Acompanhar animal | Menu inicial | `u: Encerrar atividade` (tracejada) | O usuário desiste e abandona a funcionalidade sem concluir |

**Processos do sistema:** Dois processos: exibir a carteirinha do animal escolhido (`d: Carteirinha exibida`) e abrir a atividade selecionada (`d: Atividade selecionada`).

**Rupturas e recuperação:** O tutor pode trocar de atividade com `u: Escolher outra atividade`. As setas tracejadas (`u: Sair da funcionalidade` e `u: Encerrar atividade`) levam ao Menu inicial.

**Relação com o HTA 5:** A cena *Consultar carteirinha* corresponde à tarefa 1 do HTA. *Escolher acompanhamento* representa a escolha entre as tarefas 2 (vacinação), 3 (visitas) e 4 (informações), que no HTA são realizadas em conjunto (`2+3+4`). *Acompanhar animal* detalha o conteúdo dessas três tarefas. A combinação da visita ocorre externamente, e a data registrada pelo voluntário gera a notificação ao tutor.

---

<div align="center">

### Parte 6 – Levantamento financeiro das feiras (HTA 6)

<img width="641" height="1919" alt="image" src="https://github.com/user-attachments/assets/39a39e9c-833f-4cc0-8481-bdf588f69c4e" />

**Resumo da parte:** O voluntário acessa a gestão financeira, escolhe a feira ou o evento, registra valores arrecadados e despesas e salva o levantamento, obtendo o resultado financeiro do evento. A cena de escolha também permite consultar o histórico.

</div>

**Cenas**

| Cena | Diálogos | Papel no fluxo |
|---|---|---|
| Acessar gestão financeira | O voluntário realiza login e seleciona a funcionalidade financeira | Dá acesso à área financeira |
| Identificar feira ou evento | `d: Eventos cadastrados`; escolha (`XOR`: Novo levantamento ou Histórico financeiro) e seleção da feira | Define a qual evento o levantamento se refere ou se é uma consulta ao histórico |
| Registrar movimentações | O usuário informa valores arrecadados e despesas; `d: Resumo registrado` para conferência; confirma e salva | Registra e confere os valores antes de finalizar |
| Resultado financeiro | `d: Resultado financeiro do evento` e `d: Registro incluído no histórico` | Mostra o resultado e arquiva o levantamento |

**Transições**

| De | Para | Fala | Condição |
|---|---|---|---|
| Menu inicial | Acessar gestão financeira | `u: Gestão financeira` | Acesso ubíquo: pode ser feito a partir do Menu inicial a qualquer momento |
| Acessar gestão financeira | Processo do sistema | `u: Prosseguir` | O usuário concluiu os diálogos da cena |
| Processo do sistema | Identificar feira ou evento | `d: Área financeira` | O processamento foi concluído com sucesso |
| Identificar feira ou evento | Processo do sistema | `u: Prosseguir` | O usuário concluiu os diálogos da cena |
| Processo do sistema | Registrar movimentações | `d: Levantamento iniciado` | O processamento foi concluído com sucesso |
| Registrar movimentações | Processo do sistema | `u: Prosseguir` | O usuário concluiu os diálogos da cena |
| Processo do sistema | Resultado financeiro | `d: Levantamento salvo` | O processamento foi concluído com sucesso |
| Registrar movimentações | Identificar feira ou evento | `u: Alterar evento` | O usuário quer corrigir ou mudar uma escolha anterior |
| Acessar gestão financeira | Menu inicial | `u: Sair da funcionalidade` (tracejada) | O usuário desiste e abandona a funcionalidade sem concluir |
| Registrar movimentações | Menu inicial | `u: Cancelar levantamento` (tracejada) | O usuário desiste e abandona a funcionalidade sem concluir |

**Processos do sistema:** Três processos: abrir a área financeira (`d: Área financeira`), iniciar o levantamento do evento escolhido (`d: Levantamento iniciado`) e salvar o levantamento (`d: Levantamento salvo`).

**Rupturas e recuperação:** Se o evento escolhido estiver errado, `u: Alterar evento` retorna à seleção da feira. As setas tracejadas (`u: Sair da funcionalidade` e `u: Cancelar levantamento`) levam ao Menu inicial sem salvar.

**Relação com o HTA 6:** As cenas correspondem às tarefas 1 (acessar a gestão financeira), 2 (identificar a feira), 3 e 4 (registrar as movimentações, conferir, confirmar e salvar) e à consulta do resultado (4.3). A tarefa 5, consultar levantamentos anteriores, aparece como a opção *Histórico financeiro* na escolha da cena *Identificar feira ou evento*, conforme a escolha `4/5` do plano do HTA.

---

<div align="center">

### Parte 7 – Acessibilidade e personalização (HTA 7)

<img width="652" height="1651" alt="image" src="https://github.com/user-attachments/assets/76da5acb-5d3f-4072-a09d-fc331ea40661" />

**Resumo da parte:** O usuário abre as configurações de acessibilidade, personaliza a aparência, os estímulos sensoriais, as notificações e a comunicação, e o sistema salva e mantém as preferências nas próximas utilizações.

</div>

**Cenas**

| Cena | Diálogos | Papel no fluxo |
|---|---|---|
| Acessar configurações | O usuário localiza a opção de acessibilidade; `d: Opções de personalização disponíveis` | Dá acesso às configurações |
| Personalizar experiência | Quatro grupos de ajustes: Aparência (tamanho do texto, espaçamento, alto contraste, cores e fundos), Estímulos sensoriais (animações, sons, elementos piscantes, interface simplificada), Notificações (tipos, sons e alertas, períodos sem notificações) e Comunicação (linguagem simples, passo a passo, ícones com texto, confirmações) | Concentra a personalização da experiência |
| Preferências salvas | `d: Configurações salvas` e `d: Preferências mantidas nas próximas utilizações` | Confirma e garante a persistência das escolhas |

**Transições**

| De | Para | Fala | Condição |
|---|---|---|---|
| Menu inicial | Acessar configurações | `u: Configurar acessibilidade` | Acesso ubíquo: pode ser feito a partir do Menu inicial a qualquer momento |
| Acessar configurações | Processo do sistema | `u: Prosseguir` | O usuário concluiu os diálogos da cena |
| Processo do sistema | Personalizar experiência | `d: Configurações abertas` | O processamento foi concluído com sucesso |
| Personalizar experiência | Processo do sistema | `u: Prosseguir` | O usuário concluiu os diálogos da cena |
| Processo do sistema | Preferências salvas | `d: Preferências selecionadas` | O processamento foi concluído com sucesso |
| Preferências salvas | Personalizar experiência | `u: Alterar configurações` | O usuário quer corrigir ou mudar uma escolha anterior |
| Acessar configurações | Menu inicial | `u: Sair da funcionalidade` (tracejada) | O usuário desiste e abandona a funcionalidade sem concluir |
| Personalizar experiência | Menu inicial | `u: Cancelar alterações` (tracejada) | O usuário desiste e abandona a funcionalidade sem concluir |

**Processos do sistema:** Dois processos: abrir as configurações (`d: Configurações abertas`) e gravar as preferências escolhidas (`d: Preferências selecionadas`).

**Rupturas e recuperação:** Se o usuário quiser mudar algo depois de salvar, `u: Alterar configurações` retorna à personalização. As setas tracejadas (`u: Sair da funcionalidade` e `u: Cancelar alterações`) levam ao Menu inicial sem salvar.

**Relação com o HTA 7:** A cena *Acessar configurações* corresponde à tarefa 1 do HTA. *Personalizar experiência* reúne as tarefas 2 a 5 (aparência visual, estímulos sensoriais, notificações e comunicação) e *Preferências salvas* corresponde à tarefa 6 (salvar e manter as preferências).

---

<div align="center">

### Parte 8 – Organização de eventos e relatórios (HTA 8)

<img width="680" height="2013" alt="image" src="https://github.com/user-attachments/assets/4b3e90f6-2788-4f58-b48b-154822838069" />

**Resumo da parte:** O voluntário cria e configura um evento de arrecadação, seleciona os voluntários participantes, solicita e acompanha os relatórios individuais e, por fim, consolida e compartilha o relatório financeiro final.

</div>

**Cenas**

| Cena | Diálogos | Papel no fluxo |
|---|---|---|
| Criar evento de arrecadação |  O usuário acessa o gerenciamento de eventos, informa nome, data e meta de arrecadação (`d+u`) e salva a configuração | Define o evento a ser organizado |
| Selecionar voluntários | `d: Lista de voluntários disponíveis`; o usuário seleciona os voluntários do evento e confirma a participação | Define quem participa do evento |
| Acompanhar relatórios individuais | O usuário solicita o relatório a cada voluntário; `d: Acompanhamento do recebimento dos relatórios`; `d: Valores informados para conferência` | Garante que os valores de cada voluntário foram recebidos e conferidos |
| Relatório financeiro final | `d: Relatórios individuais consolidados` e `d: Relatório financeiro final gerado; o usuário compartilha com os envolvidos` | Conclui o ciclo e divulga o resultado |

**Transições**

| De | Para | Fala | Condição |
|---|---|---|---|
| Menu inicial | Criar evento de arrecadação | `u: Organizar evento` | Acesso ubíquo: pode ser feito a partir do Menu inicial a qualquer momento |
| Criar evento de arrecadação | Processo do sistema | `u: Prosseguir` | O usuário concluiu os diálogos da cena |
| Processo do sistema | Selecionar voluntários | `d: Evento salvo` | O processamento foi concluído com sucesso |
| Selecionar voluntários | Processo do sistema | `u: Prosseguir` | O usuário concluiu os diálogos da cena |
| Processo do sistema | Acompanhar relatórios individuais | `d: Participação confirmada` | O processamento foi concluído com sucesso |
| Acompanhar relatórios individuais | Processo do sistema | `u: Prosseguir`  | O usuário concluiu os diálogos da cena |
| Processo do sistema | Relatório financeiro final | `d: Valores conferidos` (tracejada) | O processamento foi concluído com sucesso |
| Selecionar voluntários | Criar evento de arrecadação | `u: Alterar dados do evento` (tracejada) | O usuário quer corrigir ou mudar uma escolha anterior |
| Criar evento de arrecadação | Menu inicial | `u: Sair da funcionalidade` (tracejada) | O usuário desiste e abandona a funcionalidade sem concluir |
| Acompanhar relatórios individuais | Menu inicial | `u: Cancelar acompanhamento` (tracejada) | O usuário desiste e abandona a funcionalidade sem concluir |

**Processos do sistema:** Três processos: salvar a configuração do evento (`d: Evento salvo`), registrar a participação dos voluntários (`d: Participação confirmada`) e validar os valores recebidos (`d: Valores conferidos`).

**Rupturas e recuperação:** Se os dados do evento precisarem mudar, `u: Alterar dados do evento volta à primeira cena` . As setas tracejadas (`u: Sair da funcionalidade` e `u: Cancelar acompanhamento`) levam ao Menu inicial.

**Relação com o HTA 8:** As quatro cenas correspondem aos quatro subobjetivos do HTA: criar e configurar o evento (1), selecionar os voluntários (2), solicitar e acompanhar os relatórios individuais (3) e consolidar e compartilhar o relatório final (4).

---

<div align="center">

### Parte 9 –  (HTA 9)

<img width="657" height="1646" alt="image" src="https://github.com/user-attachments/assets/5a53b583-176e-42f1-9a16-a81715b63f23" />

**Resumo da parte:** O usuário escolhe entre personalizar o modelo do registro de adoção, consultar os registros cadastrados ou consultar o status de preenchimento e de assinatura de um registro.

</div>

**Cenas**

| Cena | Diálogos | Papel no fluxo |
|---|---|---|
| Escolher atividade |  Seleção da atividade (`XOR`: Personalizar modelo do registro, Consultar registros cadastrados ou Consultar status de preenchimento e assinatura) | Define o caminho que o usuário seguirá |
| Realizar atividade | Modelo: acessar o modelo e editar campos e texto. Registros: acessar a lista, buscar ou filtrar. Status: selecionar o registro de adoção | Reúne as ações de entrada de cada atividade |
| Resultado da atividade | Modelo: d: Modelo personalizado salvo. Registros: d: Detalhes do registro. Status: `d: Status de preenchimento` e `d: Status da assinatura` | Apresenta o resultado da atividade escolhida |

**Transições**

| De | Para | Fala | Condição |
|---|---|---|---|
| Menu inicial | Escolher atividade | `u: Gerenciar registros de adoção` | Acesso ubíquo: pode ser feito a partir do Menu inicial a qualquer momento |
| Escolher atividade | Processo do sistema | `u: Prosseguir` | O usuário concluiu os diálogos da cena |
| Processo do sistema | Realizar atividade | `d: Atividade selecionada` | O processamento foi concluído com sucesso |
| Realizar atividade | Processo do sistema | `u: Prosseguir` | O usuário concluiu os diálogos da cena |
| Processo do sistema | Resultado da atividade | `d: Atividade concluída` | O processamento foi concluído com sucesso |
| Realizar atividade | Escolher atividade | `u: Escolher outra atividade`  | O usuário quer corrigir ou mudar uma escolha anterior |
| Escolher atividade | Menu inicial | `u: Sair da funcionalidade` (tracejada) | O usuário desiste e abandona a funcionalidade sem concluir |
| Realizar atividade | Menu inicial | `u: Cancelar atividade` (tracejada) | O usuário desiste e abandona a funcionalidade sem concluir |

**Processos do sistema:** Dois processos: abrir a atividade escolhida (`d: Atividade selecionada`) e concluí-la, salvando o modelo ou exibindo as informações (`d: Atividade concluída`).

**Rupturas e recuperação:** O usuário pode trocar de atividade com `u: Escolher outra atividade`. As setas tracejadas (`u: Sair da funcionalidade` e `u: Cancelar atividade`) levam ao Menu inicial.

**Relação com o HTA 9:** Relação com o HTA 9: A cena Escolher atividade representa a escolha entre os subobjetivos 1, 2 e 3 do HTA. Realizar atividade reúne as tarefas de acessar, editar, buscar e selecionar (1.1, 1.2, 2.1, 2.2 e 3.1) e Resultado da atividade reúne as de salvar, visualizar e verificar (1.3, 2.3, 3.2 e 3.3).

---

<div align="center">

### Parte 10 –  (HTA 10)

<img width="657" height="1648" alt="image" src="https://github.com/user-attachments/assets/edb53379-9e1e-46e9-88aa-7d2728bd783b" />

**Resumo da parte:** O usuário escolhe entre personalizar o modelo da carteirinha digital, consultar as carteirinhas cadastradas ou preencher a carteirinha de um animal adotado.

</div>

**Cenas**

| Cena | Diálogos | Papel no fluxo |
|---|---|---|
| Escolher atividade |  Seleção da atividade (XOR: Personalizar modelo da carteirinha, Consultar carteirinhas cadastradas ou Preencher carteirinha do animal adotado) | Define o caminho que o usuário seguirá |
| Realizar atividade |  Modelo: acessar o modelo e editar os campos. Consulta: acessar a lista e buscar a carteirinha do animal. Preenchimento: selecionar o animal adotado e preencher os dados | Reúne as ações de entrada de cada atividade |
| Resultado da atividade | Modelo: `d: Modelo personalizado salvo`. Consulta: `d: Informações da carteirinha`. Preenchimento: `d: Carteirinha preenchida salva` | Apresenta o resultado da atividade escolhida  |

**Transições**

| De | Para | Fala | Condição |
|---|---|---|---|
| Menu inicial | Escolher atividade | `u: Gerenciar carteirinhas` | Acesso ubíquo: pode ser feito a partir do Menu inicial a qualquer momento |
| Escolher atividade | Processo do sistema | `u: Prosseguir` | O usuário concluiu os diálogos da cena |
| Processo do sistema | Realizar atividade | `d: Atividade selecionada` | O processamento foi concluído com sucesso |
| Realizar atividade | Processo do sistema | `u: Prosseguir` | O usuário concluiu os diálogos da cena |
| Processo do sistema | Resultado da atividade | `d: Atividade concluída` | O processamento foi concluído com sucesso |
| Realizar atividade | Escolher atividade | `u: Escolher outra atividade`  | O usuário quer corrigir ou mudar uma escolha anterior |
| Escolher atividade | Menu inicial | `u: Sair da funcionalidade` (tracejada) | O usuário desiste e abandona a funcionalidade sem concluir |
| Realizar atividade | Menu inicial | `u: Cancelar atividade` (tracejada) | O usuário desiste e abandona a funcionalidade sem concluir |

**Processos do sistema:** Dois processos: abrir a atividade escolhida (`d: Atividade selecionada`) e concluí-la, salvando o modelo ou a carteirinha, ou exibindo as informações (`d: Atividade concluída`)

**Rupturas e recuperação:** O usuário pode trocar de atividade com `u: Escolher outra atividade`. As setas tracejadas (`u: Sair da funcionalidade` e `u: Cancelar atividade`) levam ao Menu inicial.

**Relação com o HTA 10:** A cena Escolher atividade representa a escolha entre os subobjetivos 1, 2 e 3 do HTA. Realizar atividade reúne as tarefas de acessar, editar, buscar, selecionar e preencher (1.1, 1.2, 2.1, 2.2, 3.1 e 3.2) e Resultado da atividade reúne as de salvar e visualizar (1.3, 2.3 e 3.3).

---

## 5. Observações finais

- Todas as partes partem do Menu inicial, o que permite entrar em qualquer funcionalidade a partir de qualquer ponto do aplicativo e sair com `u: Sair`.
- O padrão repetido (cena, `u: Prosseguir`, processo, `d:` e próxima cena) mantém a conversa previsível e facilita a aprendizagem do usuário.
- As funcionalidades restritas (partes 3, 4 e 6) exigem login do voluntário, e a parte 5 exige a área do tutor, liberada após a formalização da adoção.
- O contato por WhatsApp (parte 2) e a combinação de visitas (parte 5) acontecem fora do aplicativo e por isso não são modelados como cenas.
- Os pontos a validar com os usuários são a clareza das mensagens de erro, a facilidade de cancelar operações e a compreensão do Menu inicial como acesso ubíquo.

---

<div align="center">

**DESIGN IHC | SISTEMAS DE INFORMAÇÃO & ENGENHARIA DE SOFTWARE**

</div>
