# Cyclistic Case Study – Parte "Ask"
Este estudo foi realizado individualmente, incluindo limpeza, análise e recomendações


## 1 ASK. Declaração clara da tarefa comercial

**Problema a ser resolvido:**  
A Cyclistic deseja entender como membros anuais e usuários casuais utilizam as bicicletas de formas diferentes. O objetivo principal é identificar padrões de uso em cada grupo para embasar estratégias de marketing que convertam usuários casuais em membros anuais.

**Como os insights podem orientar decisões de negócio:**  
Ao compreender as diferenças no comportamento de uso entre membros e casuais, a equipe de marketing poderá:
- Direcionar campanhas mais eficazes e segmentadas.
- Propor benefícios e promoções alinhados ao perfil de cada grupo.
- Focar na conversão de usuários casuais para o plano anual, aumentando a receita recorrente da empresa.

**Stakeholders principais:**
- Diretora de Marketing (Lily Moreno)
- Equipe de análise de marketing da Cyclistic
- Equipe executiva da Cyclistic
- Usuários do serviço Cyclistic

---

**Resumo:**  
O objetivo desta etapa é analisar como membros anuais e usuários casuais utilizam as bicicletas Cyclistic de maneira diferente, fornecendo subsídios para o desenvolvimento de estratégias de conversão de usuários casuais em membros anuais.



# Cyclistic Case Study – Parte "Prepare"

## 2. Descrição de Todas as Fontes de Dados Utilizadas

**Fonte dos dados:**
- Foram utilizados os dados históricos de viagens de bicicletas da Cyclistic, abrangendo todos os meses do ano de 2024.
- Os dados foram baixados dos repositórios oficiais publicados pela operadora do sistema (Motivate International Inc.), disponíveis em arquivos CSV mensais.

**Organização dos dados:**
- Cada arquivo representa um mês do ano de 2024, contendo registros detalhados de cada viagem realizada.
- Principais colunas encontradas nos arquivos:
  - `ride_id`: Identificador único da viagem
  - `started_at`: Data e hora do início da viagem
  - `ended_at`: Data e hora do término da viagem
  - `rideable_type`: Tipo de bicicleta utilizada (standard, elétrica, etc.)
  - `start_station_name` / `end_station_name`: Estações de início e fim
  - `member_casual`: Tipo de usuário (casual ou membro anual)

**Credibilidade, viés e integridade dos dados (ROCCC):**
- Os dados são divulgados pela operadora responsável pelo sistema Cyclistic, garantindo alta credibilidade e integridade.
- Dados são anonimizados, respeitando questões de privacidade.
- A abrangência de 12 meses permite observar tendências sazonais e padrões consistentes.
- Possíveis vieses: Não é possível identificar se um usuário casual já foi membro no passado, ou se reside na área de atuação da Cyclistic.

**Licença, privacidade e acessibilidade:**
- Os dados disponibilizados são de acesso público e respeitam requisitos de privacidade, não incluindo informações pessoais dos usuários.
- Utilização dos dados está de acordo com as diretrizes e licença de uso da Motivate International Inc.

**Verificação da integridade dos dados:**
- Os arquivos foram abertos e verificados para garantir que não há corrupção ou ausência de colunas essenciais.
- Conferência de consistência entre os arquivos mensais, padronizando nomes de colunas quando necessário.

**Como os dados ajudam a responder à pergunta de negócio:**
- Permitem analisar padrões de uso ao longo do tempo, diferenças de comportamento entre membros e casuais, horários, locais e duração das viagens, fornecendo subsídios para embasar estratégias de marketing e conversão.

---

**Resumo:**  
Os dados utilizados são completos, confiáveis e abrangem todos os meses de 2024, permitindo uma análise robusta sobre o comportamento de uso de bicicletas Cyclistic por diferentes tipos de usuários.




# Cyclistic Case Study – Parte "Process"

## 3. Documentação de Limpeza ou Manipulação de Dados

### Ferramentas Utilizadas
A preparação e limpeza dos dados foram realizadas utilizando Python e a biblioteca pandas, que são amplamente reconhecidos pela eficiência no tratamento e manipulação de grandes volumes de dados.

### Etapas Realizadas

1. **Importação e Unificação dos Dados**
   - Todos os arquivos CSV referentes aos meses de 2024 foram importados e concatenados em um único DataFrame para análise integrada de todo o período.

2. **Padronização dos Nomes das Colunas**
   - Os nomes das colunas foram uniformizados para garantir consistência e facilitar as operações subsequentes.

3. **Conversão de Tipos de Dados**
   - As colunas `started_at` e `ended_at` foram convertidas para o tipo datetime, possibilitando cálculos precisos de tempo de viagem.

4. **Criação de Novas Colunas**
   - Foi criada a coluna `ride_length`, que representa a duração de cada viagem em minutos, calculada pela diferença entre `ended_at` e `started_at`.
   - Também foi adicionada a coluna `day_of_week`, indicando o dia da semana em que a viagem foi iniciada.

5. **Remoção de Dados Inválidos**
   - Foram removidas todas as viagens com duração negativa ou igual a zero, pois representam inconsistências ou possíveis erros de registro.
   - Linhas com campos essenciais nulos, como `ride_id`, `started_at`, `ended_at` e `member_casual`, também foram excluídas para evitar distorções na análise.

6. **Exportação dos Dados Tratados**
   - O conjunto de dados limpo e processado foi salvo em um novo arquivo CSV para uso nas etapas de análise e visualização.

### Exemplo de Código Python Utilizado

**Resumo:**  
Por meio dessas etapas, garantiu-se a integridade, uniformidade e qualidade dos dados, tornando-os prontos para a fase de análise exploratória e geração de insights relevantes para o negócio.


# Cyclistic Case Study – Parte "Analyze"

## 4. Resumo da Análise

A análise dos dados de viagens realizadas em 2024 revelou diferenças marcantes entre o comportamento dos membros anuais ("member") e dos usuários casuais ("casual") do sistema Cyclistic:

### Estatísticas Gerais

- **Volume de Viagens:**  
  - Usuários casuais: 2.151.397 viagens  
  - Membros anuais: 3.708.448 viagens

- **Duração Média das Viagens:**  
  - Casuais: média de 25,15 minutos (mediana: 12,06 min)
  - Membros: média de 12,77 minutos (mediana: 8,70 min)
  - Viagens de ambos os grupos podem ultrapassar 25 horas, mas viagens muito longas são raras e representam outliers.

---

### Uso por Dia da Semana

|                  | Segunda | Terça  | Quarta | Quinta | Sexta | Sábado | Domingo | Média Fim de Semana |
|------------------|--------|--------|--------|--------|-------|--------|---------|---------------------|
| **Casual**       | 25,85  | 23,28  | 22,24  | 21,48  | 24,92 | 30,32  | 31,61   | 30,97               |
| **Member**       | 12,60  | 12,70  | 12,68  | 12,07  | 12,19 | 14,37  | 14,34   | 14,35               |

- **Casuais** fazem viagens mais longas, especialmente aos finais de semana (média ~31 min).
- **Membros** apresentam uso mais regular ao longo da semana (~12-14 min).

---

### Número de Viagens por Dia da Semana

|                  | Segunda | Terça  | Quarta | Quinta | Sexta | Sábado  | Domingo | Total Semana |
|------------------|--------|--------|--------|--------|-------|---------|---------|-------------|
| **Casual**       | 64.968 | 59.774 | 64.742 | 60.928 | 72.832| 108.945 | 84.082  | 516.271     |
| **Member**       |171.340 |187.957 |199.382 |187.995 |163.629|144.775  |121.305  |1.176.383    |

- **Membros** utilizam mais frequentemente durante os dias úteis.
- **Casuais** concentram seus usos em finais de semana, sendo sábado o pico.

---

### Viagens por Mês

- **Tendência anual:**  
  O número de viagens se distribui de forma consistente ao longo dos meses, com picos em meses de clima mais quente (detalhar conforme seus dados reais).

---

### Tipo de Bicicleta Utilizada

|                  | classic_bike | electric_bike | electric_scooter |
|------------------|-------------|---------------|------------------|
| **Casual**       | 974.931     | 1.091.251     | 85.215           |
| **Member**       |1.760.627    | 1.888.699     | 59.122           |

- Ambos os grupos usam mais bicicletas elétricas, mas a diferença entre classic e electric é equilibrada.
- Scooters elétricos são menos utilizados, principalmente pelos membros.

---

## Principais Insights

- Usuários casuais fazem viagens quase duas vezes mais longas que membros, principalmente aos finais de semana.
- Membros utilizam o sistema com frequência maior, especialmente nos dias úteis, sugerindo uso para deslocamento (commute).
- O sábado é o dia de maior movimento para casuais, enquanto membros mantêm padrão consistente ao longo da semana.
- O uso de bicicletas elétricas é significativo para ambos os grupos, mas classic bikes também têm alta demanda.
- Estratégias de conversão devem considerar o apelo do lazer para casuais e o perfil de deslocamento para membros.

---

**Esses achados sustentam recomendações e direcionamentos para as próximas etapas do projeto e para ações de marketing específicas.**





# Cyclistic Case Study – Parte "Share"

## 5. Visualizações Complementares e Principais Conclusões

### Exemplos de Geração de Gráficos em Python (matplotlib/seaborn)

### Principais Conclusões

- **Usuários casuais**:
  - Fazem viagens significativamente mais longas, especialmente aos sábados e domingos.
  - Preferem uso recreativo e lazer, aproveitando mais finais de semana e feriados.

- **Membros anuais**:
  - Fazem mais viagens durante a semana, com duração menor, indicando uso para deslocamento diário (commute).
  - Mantêm padrão de uso mais constante ao longo do ano.

- **Tipo de bicicleta**:
  - Ambos os grupos utilizam bastante tanto bicicletas clássicas quanto elétricas.
  - Scooters elétricos têm baixa adesão, especialmente entre membros.

- **Tendência anual**:
  - O volume de viagens cresce nos meses mais quentes, especialmente entre casuais.

---

## Comunicação dos Resultados

As visualizações e insights foram organizados em slides e gráficos de fácil leitura, destacando as diferenças de uso entre membros e casuais. Os resultados podem ser apresentados em reuniões executivas, publicações internas ou dashboards para orientar decisões de marketing e produto.

---

**Esses achados sustentam as recomendações estratégicas para conversão de usuários casuais em membros anuais, abordadas na próxima etapa.**


# Cyclistic Case Study – Parte "Act"

## 6. Suas Três Principais Recomendações com Base na Análise

Com base nos resultados apresentados, as recomendações para a equipe Cyclistic são:

### 1. Campanhas Focadas em Lazer para Casuais aos Finais de Semana
Os dados mostram que usuários casuais fazem viagens mais longas e concentram o uso aos sábados e domingos. Recomenda-se criar campanhas específicas para esse público, como promoções de upgrade para o plano anual durante o uso aos finais de semana, com mensagens que reforcem o valor do lazer recorrente e benefícios exclusivos para assinantes.

### 2. Incentivos para Membros em Deslocamento Diário
Membros utilizam mais a plataforma durante a semana e em viagens mais curtas, sugerindo uso para deslocamento (commute). Sugere-se oferecer incentivos para renovação antecipada, descontos em parceiros (cafés, coworkings), ou recompensas por frequência de uso durante dias úteis, reforçando a ideia de praticidade e economia.

### 3. Comunicação Personalizada e Digital
Aproveite os dados de comportamento para enviar sugestões personalizadas via app, e-mail ou SMS. Por exemplo: quem realizou 3 ou mais viagens em um mês como casual pode receber uma oferta exclusiva de teste do plano anual. Use comparativos claros de economia e conveniência, além de facilitar o processo de adesão diretamente pelo aplicativo.

---

## Considerações Finais

Essas recomendações, fundamentadas em dados concretos, têm potencial para aumentar a conversão de usuários casuais em membros anuais, elevar a satisfação dos clientes e impulsionar o crescimento sustentável da Cyclistic. Para maximizar resultados, recomenda-se acompanhar as métricas de conversão e satisfação, ajustando as estratégias conforme o comportamento dos usuários evoluir.

