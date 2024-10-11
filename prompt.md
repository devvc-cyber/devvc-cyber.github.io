Você é um engenheiro de software e deverá criar uma solução otimizada de acordo com o contexto e as regras 
especificadas a seguir.

""" Contexto """

- Considere uma clínica médica especializada que realiza procedimentos de checkup onde são realizadas consultas e exames de 
diversas especialidades de forma sequencial no mesmo dia.

- A clínica atende em média 40 pacientes por dia, com a seguinte média de distribuição:
  
  - F1 - 6 mulheres de até 40 anos
  - F2 - 12 mulheres com mais de 40 anos
  - M1 - 2 homens com menos de 40 anos
  - M2 - 20 homens com mais de 40 anos
  - E - 5 pessoas homens ou mulheres acima de 65 anos

""" Regras """

A. A chegada dos pacientes deve ocorrer entre 6h20 e 8h

B. A sequência de etapas, tempo médio (TM), grupo alvo (GA) e capacidade (C): 

  1. Admissão via totem, TM=5min, GA=TODOS, C=4 TOTENS
  2. Vestiário, TM=10min, GA=TODOS, C=ILIMITADA
  3. Triagem ou coleta (o que estiver livre), TM=10min, GA=TODOS, C=3 TRIAGENS  
  4. Clínico, TM=40min, GA=TODOS, C=7 CLÍNICOS 
  5. Ultrassom, TM=20min, GA=TODOS, C=4 SALAS 
  6. Pausa para lanche, TM=20min, GA=TODOS 
  7. Ginecologia, TM=20min, GA=F1 e F2, C=2 GINECOLOGISTAS
  8. Urologia, TM=20min, GA=M2, C=2 UROLOGISTAS 
  9. Teste ergométrico, TM=40min, GA=TODOS, C=3 SALAS DE TESTE  
  10. Oftalmologia, TM=20min, GA=TODOS, C=3 OFTALMOLOGISTAS
  11. Dermatologia, TM=20min, GA=TODOS, C=3 DERMATOLOGISTAS
  12. Fonaudiólogo, TM=20min, GA=M2 e F2, C=2 FONAUDIÓLOGOS
  13. Mamografia, TM=20min, GA=F2, C=1 MÁQUINA 
  14. Avaliação funcional do Idoso, TM=20min, GA=E, C=1 PROFISSIONAL 

C. A sequência de atividades pode ser dinâmica mas deve seguir algumas regras: 
  1. A pausa para o lanche não pode ocorrer antes do ultrassom
  2. O Ultrassom deve ser uma das etapas iniciais
  3. Idealmente a Ginecologia deve ocorrer antes de Mamografia
D. A execução de todas as etapas devem ocorrer em no máximo 6 horas
E. Após o término de uma etapa os pacientes devem se deslocar para a etapa "Sala de Espera', onde o tempo médio de espera é de 5min, e após esse tempo o paciente deve se deslocar para a próxima etapa
F. O número de pacientes em uma etapa não pode ultrapassar a capacidade total da etapa
G. Quando uma etapa estiver na capacidade máxima, os pacientes devem ficar aguardando na etapa "Sala de Espera"
H. Os pacientes devem aguardar o menor tempo possível entre as etapas
I. As regras de grupo por etapa devem ser seguidas criteriosamente, não sendo possível pular uma etapa 

""" Sua tarefa """

** Criar um simulador em estilo de jogo que mostre a dinámica da clínica **
 1. Criar espaços para as etapas conforme especificado. 
 2. Nas etapas, indicar a capacidade total (CT) e a capacidada ocupada no momento (CM), conforme número de pacientes na etapa
 3. Criar os pacientes de acordo com os grupos especificados e diferenciados por cor
 4. Atribuir um indicador para o paciente, que deve ser o Id do grupo, seguindo por um número sequencial (ex. F1-1)
 3. Adicionar legenda indicando os grupos e cores
 4. Simular o deslocamento dos pacientes na clínica de acordo com as etapas, tempos e regras estabelecidas
 5. Criar uma estrutura de dados que registre: o paciente, etapa, tempo inicial do paciente na etapa (TI), tempo final do paciente na etapa (TI), tempo total do paciente na etapa (TT), incluindo a etapa "Sala de Espera"  
 7. Após a execução da simulação, fazer uma análise dos dados e indicar bootlenecks
 8. O jogo deve permitir ao usuário informar o número de pacientes, que não pode ser maior que 40
 9. Após o usuário informar o número de pacientes, os pacientes devem ser movidos para etapa de inicial seguindo um modelo de distribuição normal, onde os pacientes iniciam o processo  entre 6am e 8am.
 11. O simulador / jogo deve rodar em um navegador web (HTML / Javascript / CSS)
 10. O simulador de jogo da dinâmica da clínica deve ficar fixado na parte superior da página, e os logs de todas as transições devem ser exibidoe em formato de tabela logo abaixo do simulador. 
 11. Adicionar gráficos análiticos indicando a relação paciente e tempo de espera (tempo total do paciente na etapa "Sala de Espera")
 12. Gerar o código completo do simulador / jogo em Phaser.js

-----------------------

*** Sua tarefa *** 

- Modifique o código para que "Sala de Espera" seja considerada uma etapa, que deve ser logada como as demais. 
- Separe as etapas de triagem e coleta, mantendo a mesma capacidade para cada uma
- A simulação sempre deve sempre iniciar as 6h00 da manhã.
- Revise as transições para garantir que os grupos passem por todas as etapas obrigatórias
  
-----------------------

O simulador está sendo executado por tempo indeterminado.

- Revise o simulador para seguir o tempo ocupado em cada etapa
- Adicione uma etapa chamada "Saída do Checkup", que é a etapa final do processo. 
- Otimize o processo para que as etapas possam ser paralelizadas seguindo os critérios de regras pré-definidas

-----------------------

Vamos fazer mais um refinamento no simulador. 

- Adicione um timer na parte superior da página ao lado do form, para indicar como o tempo está correndo. 
- O gráfico final deve ser gráfico de paciente x tempo total na clínica para percorrer todas as etapas necessárias
- Após a etapa final (12, 13, ou 14), o paciente deve ir diretamente para "Saída Checkup"
- A etapa "Saída Checkup" só deve ocorrer após as etapas 12, 13, ou 14 

--------------------

O gráfico não foi gerado. Remova a etapa "Conferência Final"


--------------------

Crie um arquivo em markdown com a documentação do projeto (para nossa página no github)
