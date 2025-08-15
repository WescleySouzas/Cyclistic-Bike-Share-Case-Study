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

