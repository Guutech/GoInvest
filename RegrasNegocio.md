# 📊 Simulador de Investimentos

---

## 📌 1. Parâmetros de Entrada

O usuário deverá informar os seguintes dados:

| Parâmetro      | Obrigatório | Regra de Validação        |
|---------------|------------|---------------------------|
| nomeCliente   | Sim        | Não pode estar vazio      |
| valorInicial  | Sim        | ≥ 0                       |
| aporteMensal  | Sim        | ≥ 0                       |
| taxaJuros     | Sim        | > 0                       |
| periodoMeses  | Sim        | > 0                       |

---

## 📐 2. Fórmula Utilizada

O cálculo será realizado utilizando **juros compostos com aportes mensais**:

```
M = P(1 + i)^t + A [((1 + i)^t - 1) / i]
```

Onde:

- **P** = Valor inicial
- **A** = Aporte mensal
- **i** = Taxa de juros mensal
- **t** = Período em meses
- **M** = Montante final

---

## 💰 3. Cálculos Derivados

Após calcular o valor final (**M**), o sistema deverá calcular:

### 3.1 Valor Total Investido

```
valorInvestido = valorInicial + (aporteMensal * periodoMeses)
```

### 3.2 Lucro Obtido

```
lucro = valorFinal - valorInvestido
```

### 3.3 Rentabilidade Percentual

```
rentabilidade = (lucro / valorInvestido) * 100
```

---

## 🛑 4. Regras de Validação

A simulação deve ser impedida quando:

- valorInicial < 0
- aporteMensal < 0
- taxaJuros ≤ 0
- periodoMeses ≤ 0
- nomeCliente estiver vazio

Caso inválido, retornar:

```
HTTP 400 - Bad Request
```

---

## 🗄 5. Persistência

Após o cálculo, o sistema deverá armazenar:

- Dados informados pelo usuário
- Valor total investido
- Valor final
- Lucro obtido
- Rentabilidade percentual
- Data da simulação

---

## 📈 6. Arredondamento

- Todos os valores monetários devem ser arredondados para **2 casas decimais**
- A rentabilidade deve ser arredondada para **2 casas decimais**

---

## 🔁 7. Evoluções Futuras (Backlog)

- Simulação com taxa anual convertida para mensal
- Gráfico de crescimento mensal
- Histórico de simulações por cliente
- Simulação com aporte variável
- Simulação considerando inflação  