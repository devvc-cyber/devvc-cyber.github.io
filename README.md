
# Simulador da Clínica Médica

Bem-vindo ao Simulador da Clínica Médica! Este projeto é um simulador interativo desenvolvido em JavaScript, utilizando o framework Phaser.js, que modela o fluxo de pacientes em uma clínica médica fictícia. O objetivo é analisar e visualizar o processo de atendimento, identificar gargalos e otimizar o fluxo de pacientes nas diversas etapas do check-up.

## Índice
1. [Introdução](#introdução)
2. [Recursos Principais](#recursos-principais)
3. [Tecnologias Utilizadas](#tecnologias-utilizadas)
4. [Instalação e Configuração](#instalação-e-configuração)
5. [Como Utilizar o Simulador](#como-utilizar-o-simulador)
6. [Estrutura do Projeto](#estrutura-do-projeto)
7. [Etapas do Check-up](#etapas-do-check-up)
8. [Grupos de Pacientes](#grupos-de-pacientes)
9. [Regras de Negócio](#regras-de-negócio)
10. [Análise de Gargalos](#análise-de-gargalos)
11. [Contribuição](#contribuição)
12. [Licença](#licença)

## Introdução
Este simulador foi criado para modelar e visualizar o fluxo de pacientes em uma clínica médica, permitindo a análise de tempos de espera, utilização de recursos e identificação de possíveis gargalos no processo. Com base em regras de negócio pré-definidas e capacidades específicas para cada etapa, o simulador oferece uma representação visual e estatística do atendimento clínico.

## Recursos Principais
- **Simulação Interativa**: Visualize pacientes se movendo entre as etapas do check-up em tempo real.
- **Configuração Personalizada**: Escolha o número total de pacientes a serem simulados (até 40).
- **Logs Detalhados**: Acompanhe os logs de transição de cada paciente, incluindo tempos de entrada e saída de cada etapa.
- **Gráficos Estatísticos**: Analise o tempo total que cada paciente passou na clínica através de gráficos gerados automaticamente.
- **Análise de Gargalos**: Identifique etapas que consumiram mais tempo total e potencialmente são gargalos no processo.
- **Timer Simulado**: Acompanhe o tempo simulado de atendimento, começando às 6h00 da manhã.

## Tecnologias Utilizadas
- **JavaScript**
- **Phaser.js**: Framework para desenvolvimento de jogos e simulações 2D.
- **Chart.js**: Biblioteca para geração de gráficos interativos.
- **HTML5 e CSS3**

## Instalação e Configuração

### Pré-requisitos
- Navegador web moderno (recomendado: Google Chrome ou Mozilla Firefox)
- Acesso à internet para carregar as bibliotecas externas

### Passos para Executar o Simulador
1. **Clone o Repositório**

   ```bash
   git clone https://github.com/seu-usuario/seu-repositorio.git
   ```

2. **Navegue até o Diretório do Projeto**

   ```bash
   cd seu-repositorio
   ```

3. **Abra o Arquivo HTML no Navegador**

   Localize o arquivo `index.html` (ou o nome do arquivo HTML principal). Abra-o diretamente no navegador web (arraste e solte o arquivo no navegador ou utilize o menu "Abrir com").

   **Nota**: Se o simulador não funcionar ao abrir o arquivo localmente devido a restrições de segurança do navegador, é recomendável utilizar um servidor HTTP simples. Você pode usar a extensão Live Server do Visual Studio Code ou executar o seguinte comando no terminal:

   ```bash
   # Para Python 3.x
   python -m http.server 8000

   # Para Python 2.x
   python -m SimpleHTTPServer 8000
   ```

   Em seguida, acesse [http://localhost:8000](http://localhost:8000) no seu navegador.

## Como Utilizar o Simulador

### Entrada de Dados
Na parte superior da página, você encontrará um campo para inserir o número total de pacientes. O valor máximo permitido é 40. Insira o número desejado de pacientes e clique no botão "Iniciar Simulação".

### Execução da Simulação
- A simulação será iniciada imediatamente.
- Um timer simulado mostrará o tempo atual, começando às 6h00.
- Você verá círculos coloridos representando os pacientes se movendo entre as etapas do check-up.
- Cada etapa exibe sua capacidade total (CT) e a capacidade ocupada no momento (CM).

### Visualização dos Logs
Abaixo do simulador, há uma tabela que registra todos os logs de transição dos pacientes. Cada registro inclui:
- **Paciente**: Identificação do paciente (grupo e número).
- **Etapa**: Nome da etapa em que o paciente entrou.
- **Tempo Inicial**: Hora em que o paciente entrou na etapa.
- **Tempo Final**: Hora prevista para o paciente sair da etapa.
- **Tempo Total na Etapa**: Duração total da etapa para o paciente.

### Análise dos Dados
Após a conclusão da simulação (quando todos os pacientes tiverem concluído o check-up), um gráfico será gerado. O gráfico mostra o tempo total que cada paciente passou na clínica. Utilize este gráfico para analisar e comparar o tempo de permanência dos pacientes.

## Análise de Gargalos
Abra o console do navegador (pressione F12 e vá para a aba "Console") para visualizar a análise de gargalos. A análise lista as etapas ordenadas pelo tempo total gasto nelas, ajudando a identificar possíveis pontos de melhoria.

## Estrutura do Projeto
- `index.html`: Arquivo principal que contém o código HTML e JavaScript do simulador.
- `styles.css` (opcional): Arquivo de estilos CSS para personalização da aparência.
- `/assets` (opcional): Diretório para recursos adicionais, como imagens ou arquivos de dados.

## Etapas do Check-up
A clínica possui diversas etapas pelas quais os pacientes devem passar, dependendo do seu grupo. Cada etapa tem características específicas:

| ID  | Nome                           | Tempo Médio (tm) | Grupo Alvo (ga)       | Capacidade |
| --- | ------------------------------ | ---------------- | --------------------- | ---------- |
| 1   | Admissão via Totem              | 5 min            | Todos                 | 3          |
| 2   | Vestiário                      | 10 min           | Todos                 | 5          |
| 3   | Triagem                        | 15 min           | Todos                 | 2          |
| 4   | Coleta                         | 20 min           | Todos                 | 2          |
| 5   | Clínico                        | 30 min           | Todos                 | 4          |
| ... | ...                            | ...              | ...                   | ...        |

## Grupos de Pacientes
Os pacientes são divididos em grupos, cada um com características e necessidades específicas:
- **F1**: Mulheres até 40 anos
- **F2**: Mulheres com mais de 40 anos
- **M1**: Homens com menos de 40 anos
- **M2**: Homens com mais de 40 anos
- **E**: Pessoas acima de 65 anos

Cada grupo é representado por uma cor específica no simulador.

## Regras de Negócio
O simulador segue um conjunto de regras que definem como os pacientes devem avançar pelas etapas:
- **Capacidade das Etapas**: Cada etapa tem uma capacidade máxima. Se a capacidade estiver cheia, o paciente deve esperar na "Sala de Espera".
- **Dependências**: Algumas etapas só ficam disponíveis após a conclusão de outras.
- **Regras Específicas**:
  - Pausa para Lanche não pode ocorrer antes do Ultrassom.
  - Saída do Checkup só ocorre após a conclusão da última etapa específica do paciente.
  - Certas etapas são específicas para determinados grupos de pacientes.

## Contribuição
Contribuições são bem-vindas! Se você deseja melhorar o simulador, corrigir bugs ou adicionar novas funcionalidades, sinta-se à vontade para abrir uma issue ou enviar um pull request.

### Como Contribuir
1. **Faça um Fork do Repositório**
   - Clique em "Fork" no canto superior direito para criar uma cópia do repositório em sua conta.

2. **Clone o Repositório Forkado**
   ```bash
   git clone https://github.com/seu-usuario/seu-fork.git
   ```

3. **Crie uma Nova Branch**
   ```bash
   git checkout -b minha-contribuicao
   ```

4. **Faça as Alterações Desejadas**
   - Edite os arquivos, corrija bugs ou adicione novas funcionalidades.

5. **Commit e Push**
   ```bash
   git add .
   git commit -m "Descrição das minhas alterações"
   git push origin minha-contribuicao
   ```

6. **Abra um Pull Request**
   - No GitHub, navegue até o seu fork e clique em "Compare & pull request" para enviar suas alterações para revisão.

## Licença
Este projeto é licenciado sob a licença MIT. Consulte o arquivo LICENSE para obter mais detalhes.

Esperamos que este simulador seja útil para seus estudos e análises. Se você tiver alguma dúvida ou precisar de assistência, não hesite em entrar em contato.

**Divirta-se explorando o fluxo da clínica médica!**
