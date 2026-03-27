# Base de Conhecimento

## Dados Utilizados

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `tabela_price.csv` | CSV | Demonstrar cálculo de parcelas no sistema PRICE |
| `tabela_sac.csv` | CSV | Demonstrar cálculo de parcelas no sistema SAC |
| `conceitos_financiamento.json` | JSON | Explicar conceitos como juros, amortização e saldo devedor |
| `exemplos_financiamento.json` | JSON | Fornecer exemplos práticos para facilitar o entendimento do usuário |
| `simulacoes.csv` | CSV | Apresentar comparações entre SAC e PRICE com valores reais |

> [!TIP]
> **Observação:** Os dados foram estruturados com foco educativo, simulando cenários reais de financiamento (imobiliário, veículos, etc.).

---

## Adaptações nos Dados

Os dados mockados foram **adaptados e enriquecidos** para fins educacionais. As principais modificações incluem:

- Criação de exemplos simplificados de financiamento para facilitar o entendimento do usuário  
- Inclusão de comparações diretas entre os sistemas **SAC e PRICE**  
- Adição de explicações passo a passo dentro dos arquivos JSON  
- Padronização dos valores (parcelas, juros, saldo devedor) para facilitar a leitura  
- Inclusão de diferentes cenários (curto, médio e longo prazo)  

---

## Estratégia de Integração

### Como os dados são carregados?

Os arquivos em formato **CSV e JSON são carregados no início da sessão** e utilizados como base de conhecimento do agente.  

Eles podem ser:
- Pré-carregados no contexto do sistema  
- Ou acessados dinamicamente conforme a pergunta do usuário  

---

### Como os dados são usados no prompt?

Os dados são utilizados de duas formas:

- **System Prompt:**  
  Inclui definições base como:
  - O que é SAC  
  - O que é PRICE  
  - O que é amortização  

- **Consulta dinâmica:**  
  Quando o usuário faz perguntas específicas (ex: *"qual é melhor?"* ou *"simula pra mim"*), o agente:
  - Busca exemplos nos arquivos  
  - Monta explicações com base nos dados  
  - Apresenta comparações claras e educativas  

---

## Exemplo de Contexto Montado
```
 Dados do Cenário:
- Tipo de financiamento: Imobiliário
- Valor financiado: R$ 100.000
- Taxa de juros: 1% ao mês
- Prazo: 12 meses

Sistema SAC:
- Amortização fixa: R$ 8.333,33
- Parcela inicial: R$ 9.333,33
- Parcela final: R$ 8.416,67

Sistema PRICE:
- Parcela fixa: R$ 8.885,00
- Juros maiores no início
- Amortização cresce ao longo do tempo

Resumo:
- SAC: parcelas decrescentes, menos juros no total
- PRICE: parcelas fixas, maior custo total
```
```
