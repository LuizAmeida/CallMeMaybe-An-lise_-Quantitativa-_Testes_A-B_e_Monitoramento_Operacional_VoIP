# 📞 CallMeMaybe — Análise Quantitativa, Testes A/B e Monitoramento Operacional VoIP

![Python](https://img.shields.io/badge/Python-3.10%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.0%2B-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Scipy](https://img.shields.io/badge/SciPy-1.10%2B-8CAAE6?style=for-the-badge&logo=scipy&logoColor=white)
![Tableau](https://img.shields.io/badge/Tableau-Interativo-E97627?style=for-the-badge&logo=tableau&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-Consultas-003B57?style=for-the-badge&logo=postgresql&logoColor=white)

---

## 📌 Contexto & Desafio de Negócio

A **CallMeMaybe** é uma operadora de telefonia virtual (VoIP) focada no segmento corporativo (B2B). A empresa enfrentava um desafio crítico de gestão: a falta de critérios objetivos e padronizados para identificar **operadores com baixo rendimento operacional**.

Historicamente, as avaliações eram baseadas em julgamentos subjetivos, o que gerava:
1. **Chamadas Abandonadas na Fila:** Insatisfação dos clientes corporativos.
2. **Custos Operacionais Elevados:** Mau dimensionamento de equipe e má alocação de recursos.

---

## 🛠️ As 4 Etapas do Projeto Final

O estudo foi desenvolvido seguindo **4 passos estruturados**:

### 1. Decomposição do Problema
Estruturação e planejamento de todas as etapas analíticas, definindo hipóteses testáveis, pipeline de limpeza/engenharia de recursos e plano de ação.

### 2. Análise Exploratória (EDA) & Testes de Hipóteses (A/B)
Identificação de assimetria à direita nas variáveis operacionais (exigindo métodos não paramétricos) e validação formal de **5 Hipóteses formais (H1 a H5)** com correção de Bonferroni ($p < 0.05$):
* **H1 (Tempo de Espera x Abandono):** Correlação positiva e estatisticamente significativa entre tempo na fila e taxa de queda (*Spearman, $p < 0.05$*).
* **H2 (Produtividade Outbound):** Operadores ineficientes realizam volume de saídas significativamente menor (*Mann-Whitney U, $p < 0.05$*).
* **H3 (Natureza da Chamada):** Diferença estatística relevante nos tempos de fila entre chamadas internas e externas (*Mann-Whitney U, $p < 0.05$*).
* **H4 (Segmentação por Planos):** A taxa de abandono varia entre os planos tarifários A, B e C (*Kruskal-Wallis, $p < 0.05$*).
* **H5 (Antiguidade do Cliente):** O tempo de contrato do cliente não influencia a eficiência do operador (*Sem correlação*).

### 3. Projeto SQL
Desenvolvimento de consultas e extrações em banco de dados relacional para apoio à engenharia de atributos e sumarização transacional.

### 4. Entrega do Projeto & Dashboard
Classificação automática de **Ineficiência Operacional** com base nos limites dos quartis reais:
* **Regra 1 (Perdidas):** Chamadas recebidas perdidas $> P75$.
* **Regra 2 (Espera):** Tempo médio de espera $> P75$.
* **Regra 3 (Ativa):** Volume diário de chamadas realizadas $< P25$.

---

## 📊 Dashboard Interativo no Tableau

Para apoiar a tomada de decisão em tempo real pelos supervisores, foi desenvolvido um painel interativo:

👉 **[Acessar Painel de Desempenho Operacional CallMeMaybe no Tableau Public](https://public.tableau.com/views/CallMeMaybe-PaineldeDesempenhoOperacional/Dashboard1?:language=pt-BR&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)**

---

## 🚀 Recomendações Práticas para a Gestão

1. **Monitoramento em Tempo Real:** Disponibilizar o dashboard interativo para monitoramento diário dos supervisores.
2. **Alertas Automatizados:** Disparar notificações automáticas para a liderança sempre que um atendente violar o limiar crítico do 3º quartil ($P75$) de espera.
3. **Metas Segmentadas:** Separar formalmente os indicadores de atendimento receptivo das campanhas de prospecção/ativação.
4. **Treinamento Focado:** Redirecionar o *Top 10* de operadores mais ineficientes para programas de reciclagem focados em redução do tempo de fila.

---

## 🔧 Como Executar o Projeto

1. **Clonar o repositório:**
   ````
   git clone [https://github.com/seu-usuario/callmemaybe-analise-voip.git](https://github.com/seu-usuario/callmemaybe-analise-voip.git)
   cd callmemaybe-analise-voip
   ````

- **👨 💻 Autor**
**Luiz Almeida** — Analista de Dados
- Sprint 14 — Projeto Final (TripleTen)
