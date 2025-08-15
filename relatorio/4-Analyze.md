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
