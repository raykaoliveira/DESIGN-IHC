# Diagramas de Decomposição de Tarefas (HTA) – GAPI

Esta seção apresenta os HTAs (Hierarchical Task Analysis) do aplicativo do GAPI, organizados por objetivo do usuário.

---

## HTA 1 – Acessar o aplicativo de acordo com o perfil do usuário

![HTA 1 – Acessar o aplicativo de acordo com o perfil do usuário](HTA1.png)

**Plano 0:** 1 > 2 / 3 > 4

| Nº | Subobjetivo | Tarefas |
|----|-------------|---------|
| 1 | Identificar o perfil | 1.1 Visualizar as opções de acesso · 1.2 Selecionar acesso público ou acesso de voluntário |
| 2 | Acessar a área pública | 2.1 Selecionar a opção de acesso público · 2.2 Entrar na área de consulta dos animais disponíveis |
| 3 | Acessar a área restrita do GAPI | 3.1 Selecionar a opção de acesso de voluntário · 3.2 Informar a matrícula · 3.3 Informar a senha · 3.4 Confirmar os dados de acesso · 3.5 Acessar o ambiente restrito do GAPI |
| 4 | Tratar falhas de autenticação | 4.1 Visualizar mensagem de erro quando as credenciais forem inválidas · 4.2 Corrigir os dados informados · 4.3 Tentar realizar o acesso novamente |

> **Observação:** *(adicionar aqui a descrição do HTA 1)*

---

## HTA 2 – Consultar animais disponíveis para adoção

![HTA 2 – Consultar animais disponíveis para adoção](HTA2.png)

**Plano 0:** 1 > 2 > 3 > 4

**1. Acessar o catálogo de animais** (1.1 > 1.2 > 1.3)
- 1.1. Abrir o aplicativo.
- 1.2. Acessar a área pública.
- 1.3. Selecionar a opção de animais para adoção.

**2. Visualizar os animais disponíveis** (2.1 > 2.2 > 2.3)
- 2.1. Consultar a lista de animais disponíveis pra adoção.
- 2.2. Visualizar fotografias dos animais.
- 2.3. Consultar características e informações dos pets.

**3. Consultar informações de um animal específico** (3.1 > 3.2 + 3.3)
- 3.1. Selecionar o animal desejado.
- 3.2. Visualizar as informações individuais.
- 3.3. Verificar sua situação de disponibilidade.

**4. Iniciar contato com o GAPI** (4.1 > 4.2 > 4.3)
- 4.1. Selecionar a opção de interesse na adoção.
- 4.2. Acessar o link de direcionamento para o WhatsApp.
- 4.3. Iniciar uma conversa com os voluntários.

**Descrição:**
Este HTA representa o processo de consulta dos animais disponíveis para adoção, desde o primeiro acesso do interessado até o início do contato com o GAPI.

O usuário deverá acessar a área pública do aplicativo e selecionar a funcionalidade de consulta de animais. O sistema apresentará os pets cadastrados, suas fotografias e informações relevantes para auxiliar na escolha.

Após selecionar um animal, o interessado poderá consultar seus dados individuais e verificar se ele continua disponível para adoção.

Caso tenha interesse, poderá utilizar um link que o direcionará para uma conversa externa pelo WhatsApp com os voluntários do GAPI.

A principal decisão está relacionada ao interesse do usuário em determinado animal. O contato e as orientações sobre a adoção acontecerão externamente ao aplicativo, permitindo que os voluntários conduzam o processo de acordo com os procedimentos do grupo.

---

## HTA 3 – Gerenciar o cadastro dos animais

![HTA 3 – Gerenciar o cadastro dos animais](HTA3.png)

**Plano 0:** 1 > 2 / 3 / 4

**1. Acessar o gerenciamento de animais** (1.1 > 1.2 > 1.3)
- 1.1. Realizar login com matrícula e senha.
- 1.2. Acessar a área restrita.
- 1.3. Selecionar a funcionalidade de gerenciamento de animais.

**2. Cadastrar um novo animal** (2.1 > 2.2 > 2.3 + 2.4 > 2.5)
- 2.1. Selecionar a opção de novo cadastro.
- 2.2. Informar o nome do animal.
- 2.3. Inserir suas características e informações.
- 2.4. Anexar fotografias.
- 2.5. Salvar o cadastro.

**3. Atualizar informações de um animal** (3.1 > 3.2 > 3.3 + 3.4 > 3.5)
- 3.1. Consultar os animais cadastrados.
- 3.2. Selecionar o animal desejado.
- 3.3. Editar as informações necessárias.
- 3.4. Anexar ou substituir fotografias.
- 3.5. Salvar as alterações.

**4. Atualizar a disponibilidade do animal** (4.1 > 4.2 > 4.3 > 4.4)
- 4.1. Selecionar a situação atual do animal.
- 4.2. Informar se está disponível para adoção.
- 4.3. Confirmar a alteração.
- 4.4. Atualizar a situação no catálogo público.

**Descrição:**
Este HTA representa as atividades administrativas relacionadas ao gerenciamento dos animais cadastrados no aplicativo.

Após realizar a autenticação, o voluntário poderá acessar a área de gerenciamento e escolher entre cadastrar um novo animal, atualizar informações existentes ou modificar a situação de disponibilidade de um pet.

No cadastro, serão inseridos os dados de identificação, características e fotografias do animal. Na atualização, o voluntário poderá modificar as informações já registradas e manter o perfil do animal atualizado.

A atualização da disponibilidade permitirá indicar se o pet continua aguardando adoção ou se sua situação foi modificada.

A principal decisão envolve a escolha entre cadastrar um novo animal e modificar um registro existente. Essas funcionalidades contribuem para manter o catálogo público atualizado e facilitar o acesso dos interessados às informações dos animais.

---

## HTA 4 – Registrar e formalizar uma adoção

![HTA 4 – Registrar e formalizar uma adoção](HTA4.png)

**Plano 0:** 1 > 2 > 3 > 4

**1. Iniciar o registro da adoção** (1.1 > 1.2 > 1.3)
- 1.1. Realizar login na área restrita.
- 1.2. Acessar a funcionalidade de registro de adoção.
- 1.3. Selecionar o animal adotado.

**2. Registrar os dados do adotante** (2.1 > 2.2 > 2.3)
- 2.1. Informar os dados pessoais do adotante.
- 2.2. Associar o adotante ao animal selecionado.
- 2.3. Conferir as informações cadastradas.

**3. Registrar o termo de adoção** (3.1 > 3.2 > 3.3 > 3.4)
- 3.1. Disponibilizar o termo de adoção.
- 3.2. Realizar a assinatura do adotante.
- 3.3. Registrar a assinatura no sistema.
- 3.4. Confirmar a formalização da adoção.

**4. Gerar a carteirinha digital** (4.1 > 4.2 > 4.3 > 4.4)
- 4.1. Atualizar a situação do animal para adotado.
- 4.2. Gerar a identificação digital do pet.
- 4.3. Associar a carteirinha ao cadastro do tutor.
- 4.4. Disponibilizar a carteirinha para acesso do tutor.

**Descrição:**
Este HTA representa o processo de formalização das adoções realizadas pelo GAPI.

Após o contato externo e a definição da adoção, o voluntário deverá acessar a área restrita do aplicativo e iniciar um novo registro. Inicialmente, será selecionado o animal adotado e serão inseridos os dados do novo tutor.

Em seguida, as informações deverão ser conferidas e o termo de adoção será disponibilizado para assinatura do adotante. Após a confirmação, o sistema registrará a adoção e atualizará a situação do animal, retirando-o do catálogo de disponíveis.

Por fim, será gerada uma carteirinha digital vinculada ao cadastro do tutor, permitindo seu acesso às informações de identificação e acompanhamento do animal.

A principal decisão ocorre durante a conferência dos dados, pois qualquer inconsistência deverá ser corrigida antes da conclusão do registro. Esse processo contribui para organizar a documentação das adoções e centralizar as informações dos animais e seus responsáveis.

---

## HTA 5 – Acompanhar o animal após a adoção

![HTA 5 – Acompanhar o animal após a adoção](HTA5.png)

**Plano 0:** 1 > 2 + 3 + 4

**1. Consultar a carteirinha digital** (1.1 > 1.2 > 1.3 > 1.4)
- 1.1. Acessar o aplicativo.
- 1.2. Entrar na área do tutor.
- 1.3. Selecionar o animal adotado.
- 1.4. Visualizar a carteirinha digital.

**2. Acompanhar a vacinação** (2.1 > 2.2 / 2.3 > 2.4 > 2.5 > 2.6)
- 2.1. Acessar a área de vacinação.
- 2.2. Consultar as vacinas registradas.
- 2.3. Identificar as vacinas pendentes.
- 2.4. Selecionar uma vacina já realizada.
- 2.5. Marcar a vacina como realizada.
- 2.6. Salvar a atualização.

**3. Registrar e consultar visitas** (3.1 > 3.2 > 3.3)
- 3.1. Combinar uma visita externamente com o voluntário do GAPI.
- 3.2. Acessar a área de acompanhamento de visitas.
- 3.3. Consultar a data da visita no aplicativo.

**4. Consultar informações de acompanhamento** (4.1 + 4.2 + 4.3)
- 4.1. Visualizar os registros de vacinação.
- 4.2. Consultar as informações da carteirinha.
- 4.3. Verificar as datas de visitas registradas.

**Descrição:**
Este HTA representa as funcionalidades destinadas ao acompanhamento dos animais após a adoção, permitindo que os tutores consultem informações importantes sobre seus pets.

O primeiro subobjetivo consiste em acessar a carteirinha digital, disponibilizada após a formalização da adoção. Por meio dela, o tutor poderá consultar a identificação do animal e acessar as funcionalidades de acompanhamento.

Na área de vacinação, será possível visualizar os registros existentes, identificar as vacinas pendentes e marcar aquelas que já foram realizadas. Dessa forma, o tutor terá um controle das informações relacionadas à vacinação do pet.

O acompanhamento das visitas ocorrerá por meio de uma combinação externa entre o tutor e os voluntários. Após a definição da data, o voluntário deverá registrá-la no aplicativo, permitindo que o sistema envie uma notificação ao tutor.

A principal decisão está relacionada à atividade que o usuário deseja realizar: consultar a carteirinha, atualizar informações de vacinação ou verificar visitas. Essas funcionalidades contribuem para facilitar o acompanhamento pós-adoção e manter os tutores informados.

---

## HTA 6 – Realizar levantamento financeiro das feiras

![HTA 6 – Realizar levantamento financeiro das feiras](HTA6.png)

**Plano 0:** 1 > 2 > 3 > 4 / 5

**1. Acessar a gestão financeira** (1.1 > 1.2 > 1.3)
- 1.1. Realizar login com matrícula e senha.
- 1.2. Acessar a área restrita.
- 1.3. Selecionar a funcionalidade financeira.

**2. Identificar a feira ou evento** (2.1 > 2.2 > 2.3)
- 2.1. Consultar os eventos cadastrados.
- 2.2. Selecionar a feira desejada.
- 2.3. Iniciar o levantamento financeiro.

**3. Registrar as movimentações financeiras** (3.1 > 3.2 > 3.3)
- 3.1. Informar os valores arrecadados.
- 3.2. Informar as despesas realizadas.
- 3.3. Conferir os valores registrados.

**4. Finalizar o levantamento financeiro** (4.1 > 4.2 > 4.3)
- 4.1. Confirmar as informações registradas.
- 4.2. Salvar o levantamento.
- 4.3. Consultar o resultado financeiro do evento.

**5. Consultar levantamentos anteriores** (5.1 > 5.2 > 5.3)
- 5.1. Acessar o histórico financeiro.
- 5.2. Selecionar um evento anterior.
- 5.3. Visualizar os registros financeiros.

**Descrição:**
Este HTA representa o processo de organização e registro das informações financeiras das feiras realizadas pelo GAPI.

O voluntário deverá acessar a área restrita do aplicativo e selecionar a funcionalidade de gestão financeira. Em seguida, deverá identificar a feira ou evento, registrado pela líder ou suporte técnico, correspondente ao levantamento.

O registro será realizado por meio da inserção dos valores arrecadados e das despesas realizadas durante o evento. Após o preenchimento, será necessário conferir as informações antes de confirmar e salvar o levantamento.

O aplicativo também permitirá consultar os registros financeiros de feiras anteriores, facilitando o acompanhamento das movimentações e a organização das informações do grupo.

A principal decisão está relacionada à conferência dos valores antes da finalização do levantamento. Essa etapa contribui para reduzir inconsistências e centralizar os registros financeiros em um único ambiente.

---

## HTA 7 – Acessibilidade e personalização da experiência

![HTA 7 – Acessibilidade e personalização da experiência](HTA7.png)

**Objetivo 0:** Utilizar o aplicativo de maneira acessível e personalizada.

**1. Acessar as configurações de acessibilidade**
- 1.1. Localizar a opção de acessibilidade no aplicativo.
- 1.2. Abrir as configurações de acessibilidade.
- 1.3. Visualizar as opções de personalização disponíveis.

**2. Ajustar a aparência visual**
- 2.1. Aumentar ou diminuir o tamanho dos textos.
- 2.2. Ajustar o espaçamento entre textos.
- 2.3. Ativar o modo de alto contraste.
- 2.4. Selecionar opções de cores e fundos.

**3. Personalizar os estímulos sensoriais**
- 3.1. Reduzir ou desativar animações e movimentos.
- 3.2. Desativar sons e efeitos sonoros.
- 3.3. Evitar elementos visuais piscantes.
- 3.4. Selecionar uma interface com menos estímulos visuais.

**4. Configurar notificações e alertas**
- 4.1. Selecionar os tipos de notificações desejadas.
- 4.2. Desativar notificações não essenciais.
- 4.3. Controlar sons e alertas visuais.
- 4.4. Definir períodos sem notificações.

**5. Personalizar a comunicação**
- 5.1. Ativar linguagem simples e objetiva.
- 5.2. Consultar instruções passo a passo.
- 5.3. Utilizar ícones acompanhados de textos.
- 5.4. Visualizar mensagens de confirmação das ações.

**6. Salvar preferências de acessibilidade**
- 6.1. Salvar as configurações selecionadas.
- 6.2. Manter as preferências nas próximas utilizações.
- 6.3. Alterar as configurações quando necessário.

> **Observação:** *(adicionar aqui a descrição do HTA 7)*
