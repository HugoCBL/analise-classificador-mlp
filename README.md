# 🧠 Análise e Otimização de um Classificador MLP com Scikit-learn

## 📌 Descrição do Projeto

Este projeto consiste na implementação, análise e otimização de uma rede neural artificial do tipo **Multilayer Perceptron (MLP)** para um problema de **classificação binária**.

> Utilizando um conjunto de dados sintético gerado pela função `make_classification` do Scikit-learn, o objetivo foi explorar como diferentes hiperparâmetros afetam o desempenho do modelo e, ao final, encontrar uma **arquitetura otimizada** que superasse o modelo base em acurácia, mas com menor complexidade.

---

## 📁 Conteúdo do Repositório

- `Analise e Otimizaçao de um Classificador MLP com Scikit-learn.ipynb`: Notebook Jupyter/Colab com código para geração de dados, construção, treinamento e avaliação dos modelos, além do relatório final com a análise detalhada.
- `README.md`: Este arquivo, com a documentação do projeto.

---

## 🛠️ Tecnologias Utilizadas

- **Python 3**
- **Scikit-learn**
- **NumPy**
- **Matplotlib**
- **Seaborn**

---

## 📊 Resumo do Projeto e Análises

O projeto foi dividido em **fases de experimentação** para avaliar o impacto de cada hiperparâmetro de forma isolada.

### 🔹 Modelo Base

Configuração inicial da MLP:

- 1 camada escondida com **5 neurônios**
- Função de ativação: **ReLU**
- Otimizador: **Adam**
- Épocas: **100**
- **Acurácia de Referência:** 🟢 **86.67%**

---

### 🔍 Análise de Hiperparâmetros

- **Número de Neurônios:**  
  Aumentar para 64 neurônios **não melhorou** a performance, indicando que o modelo base já era adequado.

- **Número de Épocas:**  
  - 200 épocas: acurácia aumentou para **88.33%**  
  - 50 épocas: causou **underfitting**, com acurácia de **83.33%**

- **Otimizador:**  
  Troca de `adam` por `sgd` levou a pior performance (**81.67%**) e uma fronteira de decisão quase linear.

- **Profundidade da Rede:**  
  Adição de uma 2ª camada (`(5, 64)`) tornou o modelo **desnecessariamente complexo**, reduzindo a acurácia para **85.00%**

- **Função de Ativação:**  
  `tanh` superou `relu`, alcançando **88.33%**

- **Quantidade de Dados:**  
  Aumento de 200 para 1000 amostras teve o **melhor impacto**, com acurácia de **89.00%**

---

### 🧪 Desafio de Otimização: Modelo Final

Objetivo: **Superar o modelo base com menos de 5 neurônios.**

🔧 Estratégia de **ajuste fino**:

- **Arquitetura Final:** 4 neurônios, ativação `tanh`
- **Ajustes:** taxa de aprendizado = `0.001`, épocas = `1500`
- ✅ **Resultado Final:** **88.33% de acurácia**

> ✨ **Conclusão:** Um modelo mais simples pode ser mais eficaz se for treinado com mais precisão e paciência.

---
