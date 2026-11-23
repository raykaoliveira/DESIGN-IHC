<div align="center">

# Diagramas de Decomposição de Tarefas (HTA)
<img src="https://img.shields.io/badge/TP2-DESIGN_THINKING-167D72?style=for-the-badge">
<img src="https://img.shields.io/badge/ARTEFATO-HTA-70CDB5?style=for-the-badge">
<img src="https://img.shields.io/badge/DISCIPLINA-IHC-E8B7C8?style=for-the-badge">

**Análise hierárquica das tarefas e operações dos usuários.**

Representação dos caminhos necessários para alcançar os objetivos identificados nos mapas de objetivos do aplicativo GAPI.

</div>

<table>
<tr>
<td align="center" width="33%">
<h1>10</h1>
<strong>HTAs</strong><br/>
<sub>Diagramas elaborados</sub>
</td>
<td align="center" width="33%">
<h1>10</h1>
<strong>OBJETIVOS</strong><br/>
<sub>Processos analisados</sub>
</td>
</tr>
</table>
  
## HTA 1 – Acessar o aplicativo de acordo com o perfil do usuário

<div align="center">

Mapa de ojetivo | Autenticação e controle de acesso

<img width="439" height="292" alt="image" src="https://github.com/user-attachments/assets/187c44a6-9b60-4c64-ac41-6bc96f3dab8a" />

HTA 1 

<img width="8760" height="1855" alt="HTA 1 DESIGN drawio" src="https://github.com/user-attachments/assets/fc4f09e8-8537-4cf2-8d8b-2828ad8cc8dd" />

</div>

**Plano 0:** 1 > 2 / 3 > 4

| Nº | Subobjetivo | Tarefas |
|----|-------------|---------|
| 1 | Identificar o perfil | 1.1 Visualizar as opções de acesso · 1.2 Selecionar acesso público ou acesso de voluntário |
| 2 | Acessar a área pública | 2.1 Selecionar a opção de acesso público · 2.2 Entrar na área de consulta dos animais disponíveis |
| 3 | Acessar a área restrita do GAPI | 3.1 Selecionar a opção de acesso de voluntário · 3.2 Informar a matrícula · 3.3 Informar a senha · 3.4 Confirmar os dados de acesso · 3.5 Acessar o ambiente restrito do GAPI |
| 4 | Tratar falhas de autenticação | 4.1 Visualizar mensagem de erro quando as credenciais forem inválidas · 4.2 Corrigir os dados informados · 4.3 Tentar realizar o acesso novamente |

> **Descrição:** Essa funcionalidade permite que os usuários acessem o aplicativo de acordo com seus respectivos perfis. Inicialmente, o sistema identifica o tipo de usuário e disponibiliza as opções de acesso correspondentes. Para usuários comuns, é possível acessar a área pública do aplicativo. Já os usuários autorizados podem realizar login utilizando matrícula e senha para acessar funcionalidades restritas.
>
>Após a identificação do perfil, o sistema direciona o usuário para a área correspondente, permitindo a utilização das funcionalidades disponíveis conforme suas permissões. Dessa forma, o processo de autenticação organiza o acesso ao aplicativo e contribui para a segurança das informações.


## HTA 2 – Consultar animais disponíveis para adoção

<div align="center">

Mapa de ojetivo | Consulta e gerenciamento de animais

<img width="436" height="291" alt="image" src="https://github.com/user-attachments/assets/004e2202-9a6b-44e5-a486-7a323fb29580" />


HTA 2  

<img width="1526" height="462" alt="hta2 drawio" src="https://github.com/user-attachments/assets/a747ced7-a9af-470d-a9fb-4e7549e9f0d7" />


</div>


**Plano 0:** 1 > 2 > 3 > 4

| Nº | Subobjetivo | Tarefas |
|:--:|---|---|
| 1 | Acessar o catálogo de animais | 1.1 Abrir o aplicativo · 1.2 Acessar a área pública · 1.3 Selecionar a opção de animais para adoção |
| 2 | Visualizar os animais disponíveis | 2.1 Consultar a lista de animais disponíveis para adoção · 2.2 Visualizar fotografias dos animais · 2.3 Consultar características e informações dos pets |
| 3 | Consultar informações de um animal específico | 3.1 Selecionar o animal desejado · 3.2 Visualizar as informações individuais · 3.3 Verificar sua situação de disponibilidade |
| 4 | Iniciar contato com o GAPI | 4.1 Selecionar a opção de interesse na adoção · 4.2 Acessar o link de direcionamento para o WhatsApp · 4.3 Iniciar uma conversa com os voluntários |

>**Descrição:** Essa funcionalidade permite que os usuários visualizem os animais disponíveis para adoção no aplicativo. Inicialmente, o usuário acessa o catálogo de animais, podendo visualizar os pets cadastrados e suas respectivas informações. Caso tenha interesse em algum animal, poderá consultar detalhes específicos, como suas características e condições.
>
>Após identificar um animal de interesse, o usuário pode iniciar contato com o GAPI para obter informações sobre o processo de adoção. Dessa forma, a funcionalidade facilita a busca por animais disponíveis e aproxima os interessados do processo de adoção.

## HTA 3 – Gerenciar o cadastro dos animais

<div align="center">

Mapa de ojetivo | Processo de adoção e registro

<img width="435" height="297" alt="image" src="https://github.com/user-attachments/assets/e4b1dc6f-b238-4fc7-acd7-c95b67bc3e4f" />

HTA 3  

<img width="2136" height="462" alt="HTA 3 drawio" src="https://github.com/user-attachments/assets/e3903030-3cb2-4b4a-b0d5-7c9fe68b9793" />

</div>

**Plano 0:** 1 > 2 / 3 / 4

| Nº | Subobjetivo | Tarefas |
|:--:|---|---|
| 1 | Acessar o gerenciamento de animais | 1.1 Realizar login com matrícula e senha · 1.2 Acessar a área restrita · 1.3 Selecionar a funcionalidade de gerenciamento de animais |
| 2 | Cadastrar um novo animal | 2.1 Selecionar a opção de novo cadastro · 2.2 Informar o nome do animal · 2.3 Inserir suas características e informações · 2.4 Anexar fotografias · 2.5 Salvar o cadastro |
| 3 | Atualizar informações de um animal | 3.1 Consultar os animais cadastrados · 3.2 Selecionar o animal desejado · 3.3 Editar as informações necessárias · 3.4 Anexar ou substituir fotografias · 3.5 Salvar as alterações |
| 4 | Atualizar a disponibilidade do animal | 4.1 Selecionar a situação atual do animal · 4.2 Informar se está disponível para adoção · 4.3 Confirmar a alteração · 4.4 Atualizar a situação no catálogo público |

>**Descrição:** Essa funcionalidade permite que os responsáveis pelo sistema realizem o gerenciamento das informações dos animais cadastrados. Inicialmente, é necessário acessar a área de gerenciamento, onde estão disponíveis as opções para cadastrar novos animais e administrar os registros existentes.
>
>Durante o processo, os responsáveis podem inserir informações dos animais, atualizar seus dados, anexar fotografias e modificar sua disponibilidade para adoção. Essas atividades garantem que as informações apresentadas no catálogo permaneçam organizadas e atualizadas, facilitando a consulta pelos usuários interessados.

## HTA 4 – Registrar e formalizar uma adoção

<div align="center">

Mapa de ojetivo | Acompanhamento pós- adoção

<img width="504" height="343" alt="image" src="https://github.com/user-attachments/assets/7181417a-8a9a-422e-80a1-5603c5a4eede" />


HTA 4  

<img width="1770" height="462" alt="HTA 4 drawio" src="https://github.com/user-attachments/assets/c9d97751-af8e-4fd9-af98-7f8c563823ab" />

</div>

**Plano 0:** 1 > 2 > 3 > 4
| Nº | Subobjetivo | Tarefas |
|:--:|---|---|
| 1 | Iniciar o registro da adoção | 1.1 Realizar login na área restrita · 1.2 Acessar a funcionalidade de registro de adoção · 1.3 Selecionar o animal adotado |
| 2 | Registrar os dados do adotante | 2.1 Informar os dados pessoais do adotante · 2.2 Associar o adotante ao animal selecionado · 2.3 Conferir as informações cadastradas |
| 3 | Registrar o termo de adoção | 3.1 Disponibilizar o termo de adoção · 3.2 Realizar a assinatura do adotante · 3.3 Registrar a assinatura no sistema · 3.4 Confirmar a formalização da adoção |
| 4 | Gerar a carteirinha digital | 4.1 Atualizar a situação do animal para adotado · 4.2 Gerar a identificação digital do pet · 4.3 Associar a carteirinha ao cadastro do tutor · 4.4 Disponibilizar a carteirinha para acesso do tutor |


>**Descrição:** Essa funcionalidade permite que os responsáveis registrem e formalizem as adoções realizadas por meio do sistema. Inicialmente, é necessário iniciar o registro da adoção e identificar o animal envolvido no processo. Em seguida, são inseridos os dados do adotante, permitindo documentar as informações necessárias para a formalização.
>
>Após o preenchimento dos dados, o responsável realiza o registro do termo de adoção e acompanha sua formalização. Ao concluir as etapas, o sistema permite gerar a carteirinha digital do animal adotado, reunindo informações importantes para o acompanhamento posterior. Dessa forma, a funcionalidade organiza o processo de adoção e mantém os registros correspondentes.

## HTA 5 – Acompanhar o animal após a adoção

<div align="center">

Mapa de ojetivo | Gestão financeira das feiras

<img width="496" height="334" alt="image" src="https://github.com/user-attachments/assets/ff6b159a-8e79-42c9-89b6-b6456e111777" />

HTA 5  

<img width="2014" height="462" alt="HTA 5 drawio" src="https://github.com/user-attachments/assets/83dfe6dd-8f17-4151-9a9b-60ab379f473a" />

</div>



**Plano 0:** 1 > 2 + 3 + 4
| Nº | Subobjetivo | Tarefas |
|:--:|---|---|
| 1 | Consultar a carteirinha digital | 1.1 Acessar o aplicativo · 1.2 Entrar na área do tutor · 1.3 Selecionar o animal adotado · 1.4 Visualizar a carteirinha digital |
| 2 | Acompanhar a vacinação | 2.1 Acessar a área de vacinação · 2.2 Consultar as vacinas registradas · 2.3 Identificar as vacinas pendentes · 2.4 Selecionar uma vacina já realizada · 2.5 Marcar a vacina como realizada · 2.6 Salvar a atualização |
| 3 | Registrar e consultar visitas | 3.1 Combinar uma visita externamente com o voluntário do GAPI · 3.2 Acessar a área de acompanhamento de visitas · 3.3 Consultar a data da visita no aplicativo |
| 4 | Consultar informações de acompanhamento | 4.1 Visualizar os registros de vacinação · 4.2 Consultar as informações da carteirinha · 4.3 Verificar as datas de visitas registradas |

>**Descrição:** Essa funcionalidade permite que os tutores acompanhem a saúde e o bem-estar dos animais após a adoção. Inicialmente, o usuário pode acessar a carteirinha digital do animal, consultar seu histórico de vacinação e verificar quais vacinas já foram realizadas ou ainda estão pendentes.
>
>Além disso, o sistema permite consultar datas de visitas agendadas e registrar informações sobre atendimentos combinados externamente. A funcionalidade também contempla o acompanhamento das informações relacionadas à saúde do animal, possibilitando que os tutores recebam notificações sobre visitas e atualizações importantes. Dessa forma, o sistema facilita o acompanhamento pós-adoção e contribui para a organização dos cuidados com os animais.


## HTA 6 – Realizar levantamento financeiro das feiras

<div align="center">

Mapa de ojetivo | Comunicação e notificações

<img width="492" height="328" alt="image" src="https://github.com/user-attachments/assets/2bca9d7e-7dc7-49b9-9d01-b4871934fa29" />

HTA 6  

<img width="1916" height="462" alt="HTA 6 drawio" src="https://github.com/user-attachments/assets/f4379b12-5ce8-4421-b93c-c0e8ed8af4b2" />

</div>

**Plano 0:** 1 > 2 > 3 > 4 / 5
| Nº | Subobjetivo | Tarefas |
|:--:|---|---|
| 1 | Acessar a gestão financeira | 1.1 Realizar login com matrícula e senha · 1.2 Acessar a área restrita · 1.3 Selecionar a funcionalidade financeira |
| 2 | Identificar a feira ou evento | 2.1 Consultar os eventos cadastrados · 2.2 Selecionar a feira desejada · 2.3 Iniciar o levantamento financeiro |
| 3 | Registrar as movimentações financeiras | 3.1 Informar os valores arrecadados · 3.2 Informar as despesas realizadas · 3.3 Conferir os valores registrados |
| 4 | Finalizar o levantamento financeiro | 4.1 Confirmar as informações registradas · 4.2 Salvar o levantamento · 4.3 Consultar o resultado financeiro do evento |
| 5 | Consultar levantamentos anteriores | 5.1 Acessar o histórico financeiro · 5.2 Selecionar um evento anterior · 5.3 Visualizar os registros financeiros |

>**Descrição:** Essa funcionalidade permite que os responsáveis realizem o controle e a consulta das informações financeiras das feiras organizadas pelo projeto. Inicialmente, é necessário acessar a área de gestão financeira e identificar a feira ou o evento cujas movimentações serão registradas.
>
>Durante o processo, os responsáveis podem registrar os valores arrecadados, inserir as despesas realizadas e organizar as informações financeiras de cada evento. Após o registro, é possível conferir os valores e finalizar o levantamento financeiro. Por fim, o sistema permite consultar levantamentos anteriores, facilitando a comparação e o acompanhamento dos resultados financeiros.

## HTA 7 – Acessibilidade e personalização da experiência

<div align="center">

Mapa de ojetivo | Acessar configurações de acessibilidade

<img width="428" height="284" alt="image" src="https://github.com/user-attachments/assets/be65fc1b-b7f2-4007-8e18-c19f918c34ac" />

HTA 7  

<img width="6856" height="1016" alt="HTA7" src="https://github.com/user-attachments/assets/9de9632f-2ae3-4463-a06f-b467af6df3d9" />

</div>

**Plano 0:** 1 > 2 > 3 > 4 > 5 > 6
| Nº | Subobjetivo | Tarefas |
|:--:|---|---|
| 1 | Acessar as configurações de acessibilidade | 1.1 Localizar a opção de acessibilidade no aplicativo · 1.2 Abrir as configurações de acessibilidade · 1.3 Visualizar as opções de personalização disponíveis |
| 2 | Ajustar a aparência visual | 2.1 Aumentar ou diminuir o tamanho dos textos · 2.2 Ajustar o espaçamento entre textos · 2.3 Ativar o modo de alto contraste · 2.4 Selecionar opções de cores e fundos |
| 3 | Personalizar os estímulos sensoriais | 3.1 Reduzir ou desativar animações e movimentos · 3.2 Desativar sons e efeitos sonoros · 3.3 Evitar elementos visuais piscantes · 3.4 Selecionar uma interface com menos estímulos visuais |
| 4 | Configurar notificações e alertas | 4.1 Selecionar os tipos de notificações desejadas · 4.2 Desativar notificações não essenciais · 4.3 Controlar sons e alertas visuais · 4.4 Definir períodos sem notificações |
| 5 | Personalizar a comunicação | 5.1 Ativar linguagem simples e objetiva · 5.2 Consultar instruções passo a passo · 5.3 Utilizar ícones acompanhados de textos · 5.4 Visualizar mensagens de confirmação das ações |
| 6 | Salvar preferências de acessibilidade | 6.1 Salvar as configurações selecionadas · 6.2 Manter as preferências nas próximas utilizações · 6.3 Alterar as configurações quando necessário |

> **Descrição:** Essa funcionalidade permite que os usuários personalizem a experiência de utilização do aplicativo conforme suas preferências e necessidades de acessibilidade. Inicialmente, o usuário acessa as configurações específicas, onde poderá ativar recursos de acessibilidade e modificar diferentes aspectos da interface.
>
>Entre as possibilidades disponíveis estão os ajustes de tamanho e espaçamento dos textos, a ativação de alto contraste, a personalização de cores, a redução de animações e a configuração das notificações. Também são contempladas opções de preferências sensoriais, interface simplificada e orientações com linguagem clara. Dessa forma, o aplicativo oferece alternativas para tornar a navegação mais acessível e confortável para diferentes usuários.

## HTA 8 - Organizar eventos e relatórios financeiros

<div align="center">

Mapa de ojetivo | Gerenciamento de eventos

<img width="435" height="286" alt="image" src="https://github.com/user-attachments/assets/7635dbeb-0563-477e-9ef1-830ab9eaa637" />

HTA 8  

<img width="1864" height="492" alt="HTA 8 drawio" src="https://github.com/user-attachments/assets/03279ba4-7ee5-447b-ba51-85b0659e4d4c" />

</div>

**Plano 0:** 
| Nº | Subobjetivo | Tarefas |
|:--:|---|---|
| 1 | Criar e configurar evento de arrecadação | 1.1 Acessar a área de gerenciamento de eventos · 1.2 Informar nome, data e meta de arrecadação do evento · 1.3 Salvar a configuração do evento |
| 2 | Selecionar os voluntários participantes | 2.1 Consultar a lista de voluntários disponíveis · 2.2 Selecionar os voluntários para o evento · 2.3 Confirmar a participação dos voluntários |
| 3 | Solicitar e acompanhar os relatórios individuais | 3.1 Solicitar o relatório a cada voluntário · 3.2 Acompanhar o recebimento dos relatórios · 3.3 Conferir os valores informados |
| 4 | Consolidar e compartilhar o relatório financeiro final | 4.1 Consolidar os relatórios individuais · 4.2 Gerar o relatório financeiro final · 4.3 Compartilhar o relatório com os envolvidos |

>**Descrição:** Essa funcionalidade permite que os responsáveis organizem eventos de arrecadação e acompanhem os resultados financeiros de cada atividade. Inicialmente, é necessário acessar a área de gerenciamento de eventos, informar o nome, a data e a meta de arrecadação, além de salvar a configuração do evento.
>
>Após essa etapa, o responsável pode consultar a lista de voluntários disponíveis, selecionar os participantes e confirmar suas participações. Durante a realização do evento, também é possível solicitar relatórios financeiros individuais aos voluntários, acompanhar o recebimento dessas informações e conferir os valores apresentados. Por fim, os relatórios individuais são consolidados para gerar um relatório financeiro final, que poderá ser compartilhado com os envolvidos. Dessa forma, a funcionalidade contribui para a organização dos eventos e para o controle das informações financeiras.

##HTA 9 - Organizar registros e assinaturas

<div align="center">

Mapa de ojetivo | Gerenciamento de registros de adoção

<img width="461" height="292" alt="image" src="https://github.com/user-attachments/assets/8b6f0d36-193d-4fa3-8c3d-dcfb29e2b0c9" />

HTA 9  

<img width="1390" height="492" alt="HTA 9 drawio" src="https://github.com/user-attachments/assets/7605f274-6704-4c91-8c2c-551a22ce5734" />

</div>


**Plano 0:** 1 > 2 > 3
| Nº | Subobjetivo | Tarefas |
|:--:|---|---|
| 1 | Personalizar o modelo do registro de adoção | 1.1 Acessar o modelo do registro de adoção · 1.2 Editar os campos e o texto do modelo · 1.3 Salvar o modelo personalizado |
| 2 | Consultar os registros de adoção cadastrados | 2.1 Acessar a lista de registros de adoção · 2.2 Buscar ou filtrar os registros · 2.3 Visualizar os detalhes do registro |
| 3 | Consultar o status de preenchimento e assinatura | 3.1 Selecionar o registro de adoção · 3.2 Verificar o status de preenchimento · 3.3 Verificar o status da assinatura |

>**Descrição:** Essa funcionalidade permite que os responsáveis organizem os documentos relacionados aos processos de adoção. Inicialmente, é possível acessar e personalizar o modelo do registro de adoção, realizando alterações nos campos e no texto do documento antes de salvar o modelo personalizado.
>
>Além disso, o sistema permite consultar os registros de adoção cadastrados, acessar uma lista de documentos e utilizar opções de busca ou filtragem para localizar registros específicos. Após selecionar um documento, o responsável pode visualizar seus detalhes e verificar o status de preenchimento e assinatura. Dessa forma, a funcionalidade facilita o gerenciamento dos documentos, permitindo acompanhar a situação dos registros de adoção.

## HTA 10 - Carteirinha digital 

<div align="center">

Mapa de ojetivo | Gerenciamento de carteirinha digital

<img width="449" height="294" alt="image" src="https://github.com/user-attachments/assets/df78e0fc-d799-464c-b0be-21430bedc4f0" />

HTA 10  

<img width="1390" height="492" alt="HTA 10 drawio" src="https://github.com/user-attachments/assets/2fc474ff-b26f-4e6f-a5b8-e6030d3623bd" />

</div>

**Plano 0:** 1 > 2 > 3
| Nº | Subobjetivo | Tarefas |
|:--:|---|---|
| 1 | Personalizar o modelo da carteirinha digital de animais | 1.1 Acessar o modelo da carteirinha · 1.2 Editar os campos do modelo · 1.3 Salvar o modelo personalizado |
| 2 | Consultar as carteirinhas cadastradas | 2.1 Acessar a lista de carteirinhas · 2.2 Buscar a carteirinha do animal · 2.3 Visualizar as informações da carteirinha |
| 3 | Preencher a carteirinha do animal adotado | 3.1 Selecionar o animal adotado · 3.2 Preencher os dados do animal · 3.3 Salvar a carteirinha preenchida |

>**Descrição:** Essa funcionalidade permite que os responsáveis organizem e atualizem as carteirinhas digitais dos animais adotados. Inicialmente, é possível acessar o modelo da carteirinha, editar seus campos e salvar uma versão personalizada conforme as informações que deverão ser apresentadas.
>
>Após a configuração do modelo, o sistema permite consultar a lista de carteirinhas cadastradas, buscar a carteirinha de um animal específico e visualizar suas informações. Também é possível selecionar um animal adotado, preencher seus dados e salvar a carteirinha preenchida. Dessa forma, a funcionalidade contribui para a organização das informações dos animais e facilita o acesso aos seus dados por meio de um documento digital.

---

<div align="center">

  **DESIGN IHC | SISTEMAS DE INFORMAÇÃO & ENGENHARIA DE SOFTWARE**

</div>
