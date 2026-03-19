## UC01 — Realizar Login (UC EXEMPLO - FAZER DESSA FORMA PARA TODOS OS CASOS DE USO, NESSE MESMO DOCUMENTO)

@startuml
|Aluno|
start
:Acessa o menu "Minha Evolução";

|Sistema|
:Busca avaliações físicas registradas;

if (Existem avaliações registradas?) then (sim)
  :Recupera dados de peso, IMC e gordura;
  :Gera comparativo gráfico de evolução;
  
  |Aluno|
  :Visualiza os dados e gráficos na tela;
  stop
  
|Sistema|
else (não)
  :Exibe mensagem "Nenhuma avaliação encontrada";
  stop
endif
@enduml

<img width="431" height="469" alt="Screenshot 2026-03-18 221500" src="https://github.com/user-attachments/assets/d3f205fc-c79b-49c1-9f6f-dc89f643265c" />

### Caso de Uso 2
@startuml Caso02
|Aluno|
start
:Entra no Sistema;

|Sistema|
:Valida credenciais;

|Aluno|
:Entra na pagina de pagamentos;
:Realiza o pagamentos;
if (Válidas?) then (sim)
  |Sistema|
  :Pagamento realizado com sucesso;
else (não)
  |Sistema|
  :Exibe pagamento nao realizado;
endif
stop
@enduml

<img width="737" height="537" alt="Screenshot 2026-03-18 221615" src="https://github.com/user-attachments/assets/40e45ace-e5e0-47e3-ae05-17c8af0379c8" />

### Caso de Uso 3 
@startuml Caso02

|Aluno|
start
:Agenda a aula com antecedencia;
|Instrutor|
:Verificaca se o aluno esta presente na sala;

if (Presente?) then (sim)
  |Instrutor|
  :Aluno esta presente;     
else (não)
  |Instrutor|
  :Aluno faltou;
  |Sistema|
  :Negativa a presença do aluno;
endif

stop
@enduml
<img width="752" height="493" alt="Screenshot 2026-03-18 221711" src="https://github.com/user-attachments/assets/a588b40b-e5a8-4b51-ab79-a53f8a7c0fc2" />

### Caso de Uso 4
@startuml caso04
 |Gerente|
 start
:Gerente faz login no sistema;
:Acessar o menu de configurações de planos da Academia;
:O Gerente edita as configurações do plano;

|Sistema|
if(Verifica se as informações estão válidas) then (sim)
:Informações alteradas;
else (não)
:Dados inválidos;
endif

stop

@enduml

<img width="740" height="616" alt="Screenshot 2026-03-18 221828" src="https://github.com/user-attachments/assets/812c11d5-9f3e-420e-ac56-7ce0aedb9e48" />

### Caso de uso 05

@startuml Caso05

|Aluno|
Start
:Reserva uma vaga em uma aula específica;
|sistema|
if(Mensalidade em dia) then(sim)
:Pode realizar o agendamento;

else (não)
:Informa a mensalidade atrasada;
:Orienta o aluno a realizar o pagamento para poder agendar aula;
stop
endif
start
|Aluno|
:O Aluno visualiza a grade de horários disponível;
:O Aluno seleciona a aula desejada;
|sistema|
:O sistema verifica a disponibilidade de vagas;
if(Disponivel?) then(sim)
|Aluno|
:Aula confirmada!;
stop
else(não)
|sistema|
:Aula lotada;
:Tente outro horário!;
stop
endif

@enduml

<img width="757" height="307" alt="Screenshot 2026-03-18 221918" src="https://github.com/user-attachments/assets/f73108b1-9010-4d54-b228-6bd0e60b78b3" />

### Caso de Uso 06
@startuml Caso06

|Aluno|
start
:O aluno acessa seus agendamentos de aula;
:O aluno solicita o cancelamento da aula;

|Sistema|
:O sistema valida se é permitido o cancelamento;

if(validado?) then (sim)
:O sistema realiza o cancelamento da aula;
|Aluno|
:Aula cancelada com sucesso!;
stop
|Sistema|
else(não)
:O sistema verificou que o cancelamento foi solicitado em menos de 1h da aula;
:E informa o aluno que só é possível realizar o cancelamento com 1h de antecedência;
stop
endif
@enduml

<img width="734" height="291" alt="image" src="https://github.com/user-attachments/assets/b2bc1f90-4947-4d24-9dce-f70e5f9edc69" />

### Caso de uso 07
@startuml
|Gerente|
start
:Verifica no sistema os alunos que estão com pagamentos pendente;

|sistema|
if(Alunos pendentes?) then(sim)
:Os alunos que estão pendentes do pagamentos são: ...;
:Gera um relatório(PDF) sobre os alunos pendentes;

|Gerente|
:Relatório PDF dos alunos pendentes;
:Irá notificar os alunos para realizar o pagamento;
stop
|sistema|
else(não)
:Não há alunos pendentes para pagar a mensalidade!;
stop
endif
@enduml

<img width="750" height="458" alt="Screenshot 2026-03-18 222033" src="https://github.com/user-attachments/assets/3bd28f90-034f-4d4c-bbc4-c8bdf6813fcc" />

### Caso de uso 08

@startuml
|Sistema|
start
:Verifica datas de vencimento de todos os alunos ativos;

if (Alunos com atraso > 5 dias?) then (sim)
  :Identifica lista de alunos inadimplentes;
  :Altera a permissão de entrada no perfil do aluno;
  :Status de acesso atualizado para bloqueado;
  stop
else (não)
  :Nenhum aluno atende aos critérios de bloqueio;
  stop
endif
@enduml

<img width="716" height="508" alt="Screenshot 2026-03-18 222104" src="https://github.com/user-attachments/assets/f813d0db-eace-42ce-95e5-33c01f7147a3" />




