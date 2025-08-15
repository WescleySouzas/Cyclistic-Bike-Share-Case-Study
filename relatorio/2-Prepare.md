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
