# Oficina de Regressão Linear - PUC-SP

Este repositório contém o material da oficina prática de Ciência de Dados, ministrada como atividade extensionista da disciplina "Consultoria Especializada em Engenharia de Software".

# 📊 Projeto Extensionista — PUC-SP

## 🧠 Tema
**Quando o Cliente Pode Comprar?**  
Previsão de Tempo de Aquisição com Regressão Linear e Correção pela Inflação (IPCA).

---

## 🎯 Objetivo Geral
Desenvolver um modelo de análise baseado em **regressão linear**, partindo de um **modelo Entidade-Relacionamento (ER)** para estimar o tempo necessário para um cliente adquirir um produto, com ou sem correção de preço pela inflação.

---

## 🔍 Etapas Realizadas

### 1. 🗃️ Modelagem Entidade-Relacionamento (ER)
Foram definidas 3 entidades principais:
- **Cliente**: ID, Nome, Saldo em poupança
- **Produto**: ID, Nome, Preço (R$)
- **Compra**: ID, Data, relação entre Cliente e Produto

Relacionamentos:
- Um Cliente pode realizar várias Compras (1:N)
- Um Produto pode estar presente em várias Compras (1:N)

---

### 2. 📥 Coleta e Preparação de Dados
- Dados simulados foram criados para clientes, produtos e compras.
- Realizado merge entre as tabelas.
- Variável `Tempo_Estimado_Semanas` foi calculada como:  
  \[
  \text{(Preço - Saldo)} \div 50
  \]
- Conversão de datas, verificação de tipos e integridade dos dados.

---

### 3. 📈 Modelagem Estatística
- Implementado modelo de **Regressão Linear Múltipla** com `scikit-learn`, considerando:
  - Entrada (X): `Preço`, `Saldo em poupança`
  - Saída (y): `Tempo Estimado de Compra (semanas)`
- Avaliação do modelo por visualização:
  - Gráfico 3D com superfície de regressão
  - Gráfico 2D com dispersão colorida por saldo

---

### 4. 📊 Correção de Preço pela Inflação (IPCA)
- Utilização da **API do Banco Central** para obter inflação mensal (série 433).
- Ajuste dos preços de cada produto no tempo estimado usando o IPCA acumulado.
- Foram adicionadas as colunas:
  - `Tempo_Estimado_IPCA`
  - `Data_Previsao_IPCA`
  - `Preco_Reajustado_IPCA`

---

## 🧪 Exemplo Aplicado
**Cliente:** Elisa Rocha  
**Produto 1:** Tablet - Preço: R$1.100  
**Produto 2:** Notebook - Preço: R$3.000  
**Saldo atual:** R$200  

| Produto    | Tempo Estimado | Preço Reajustado | Data Prevista    |
|------------|----------------|------------------|------------------|
| Tablet     | 18 semanas     | R$1118,98        | 07/10/2025       |
| Notebook   | 59 semanas     | R$3171,12        | 24/06/2026       |

---

## 🧹 Limpeza Estatística
- [ ] Verificar valores nulos com `df.isnull().sum()`
- [ ] Análise de distribuição com `.describe()`
- [ ] Identificação de outliers com boxplot

---

## 📦 Tecnologias Utilizadas
- `Python 3.x`
- `pandas`, `numpy`, `matplotlib`, `seaborn`
- `sklearn.linear_model.LinearRegression`
- API Banco Central (IPCA)

---

## 📹 Evidência de Atividade
Este notebook será convertido em vídeo de 3 minutos, com roteiro narrado e animações didáticas para o público geral.  
A apresentação busca traduzir a aplicação de Ciência de Dados e Engenharia de Software para o contexto cotidiano.

---

## 📚 Conclusão
A proposta mostra como integrar **modelagem ER**, **aprendizado de máquina** e **dados econômicos reais** para responder perguntas práticas de planejamento financeiro e marketing.

O projeto serve como ponte entre teoria e prática, com grande potencial educativo e extensionista.

---

Pontíficia universidade Católica São Paulo

👨‍🏫 Autoria
Andson Andre Ribeiro
Disciplina: 
Consultoria Especializada de Apoio  ao Projeto Integrado: 

Engenharia de Software
Curso: 
Ciência de Dados e Inteligência Artificial — PUC-SP 

Prof. Ítalo S. Vega - PUC-SP

Personagem fictícia Elisa Rocha 

![image](https://github.com/user-attachments/assets/4cec8d38-c9da-48be-a5ac-23b932e3cbe6)


[![Assista no YouTube](https://img.shields.io/badge/🎥%20Ver%20no%20YouTube-red?style=for-the-badge&logo=youtube)](https://www.youtube.com/watch?v=nlfJvUv01Zg)
