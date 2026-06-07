# 🎓 Machine Learning Students

Projeto desenvolvido com o objetivo de explorar diferentes abordagens de Machine Learning utilizando o mesmo conjunto de dados de desempenho acadêmico de estudantes.

O estudo foi dividido em duas etapas complementares:

1. **Aprendizado Não Supervisionado** utilizando K-Means para identificação de padrões e agrupamentos de estudantes.
2. **Aprendizado Supervisionado** utilizando Redes Neurais Artificiais para classificação do desempenho acadêmico dos estudantes.

A proposta do projeto foi compreender, na prática, as diferenças entre técnicas supervisionadas e não supervisionadas, aplicando ambas sobre o mesmo dataset e comparando seus objetivos, resultados e aplicações.


# 📂 Estrutura do Projeto

```text
Machine_Learning_Students/
│
├── data/
│   └── Student_performance_data_.csv
│
├── docs/
│   ├── Metadados do Dataset.docx
│   └── machine_learning_resumo.pdf
│
├── Aprendizado não Supervisionado/
│   └── notebooks/
│       └── K_means_Students.ipynb
│
├── Aprendizado Supervisionado- RNA/
│   └── notebooks/
│       └── Student Performance Classification Using Neural Networks.ipynb
│
├── README.md
└── .gitattributes
```


# 📊 Dataset

O projeto utiliza o dataset **Student Performance Dataset**, contendo informações acadêmicas, demográficas e comportamentais de estudantes. Os dados incluem idade, gênero, etnia, tempo semanal de estudo, faltas, apoio familiar, participação em atividades extracurriculares e desempenho acadêmico.

## Variáveis Principais

### Demográficas

- Age
- Gender
- Ethnicity
- ParentalEducation

### Hábitos de Estudo

- StudyTimeWeekly
- Absences
- Tutoring

### Apoio Familiar

- ParentalSupport

### Atividades Extracurriculares

- Extracurricular
- Sports
- Music
- Volunteering

### Desempenho Acadêmico

- GPA
- GradeClass


# 🎯 Objetivos do Projeto

Este projeto busca responder duas perguntas distintas:

## Aprendizado Não Supervisionado

> Existem grupos naturais de estudantes com características semelhantes?

## Aprendizado Supervisionado

> É possível prever a classificação acadêmica de um estudante utilizando suas características pessoais e acadêmicas?


# 🔍 Etapa 1 — Aprendizado Não Supervisionado (K-Means)

## Objetivo

Identificar padrões ocultos nos dados sem utilizar uma variável alvo.

Nesta etapa, o algoritmo K-Means foi utilizado para segmentar os estudantes em grupos com características semelhantes.


## Etapas Realizadas

### 1. Análise Exploratória dos Dados (EDA)

- Estatísticas descritivas
- Distribuição das variáveis
- Identificação de padrões iniciais

### 2. Correlação entre Variáveis

- Construção da matriz de correlação
- Identificação de relações entre hábitos de estudo e desempenho

### 3. Padronização dos Dados

Utilização do StandardScaler para normalização das variáveis.

### 4. Clusterização com K-Means

- Determinação do número ideal de clusters
- Aplicação do algoritmo K-Means

### 5. Redução de Dimensionalidade

Utilização de PCA (Principal Component Analysis) para visualização dos agrupamentos.


## Resultados Obtidos

O algoritmo foi capaz de identificar grupos de estudantes com perfis acadêmicos e comportamentais distintos, permitindo observar padrões relacionados a:

- Tempo de estudo
- Faltas
- Participação em atividades extracurriculares
- Apoio familiar

Importante destacar que, por se tratar de Aprendizado Não Supervisionado, não havia uma variável alvo a ser prevista.


# 🧠 Etapa 2 — Aprendizado Supervisionado (Redes Neurais Artificiais)

## Objetivo

Prever a variável **GradeClass**, que representa o desempenho acadêmico final do estudante.

### Classes

| Classe | Significado |
|----------|----------|
| 0 | A |
| 1 | B |
| 2 | C |
| 3 | D |
| 4 | F |

Valores maiores representam pior desempenho acadêmico. :contentReference[oaicite:1]{index=1}


## Preparação dos Dados

### Escolha da Variável Alvo

Foi escolhida a variável:

```python
GradeClass
```

por representar diretamente o desempenho acadêmico dos estudantes.


### Remoção do GPA

A variável GPA foi removida para evitar **Data Leakage**, pois a GradeClass é derivada diretamente do GPA.


### One-Hot Encoding

Transformação das variáveis categóricas em formato numérico:

- Gender
- Ethnicity
- ParentalEducation
- ParentalSupport


### Padronização

Aplicação do StandardScaler para normalização das variáveis.

### Divisão dos Dados

```text
Treino: 80%
Teste: 20%
```


# 🏗️ Arquitetura da Rede Neural

A rede neural foi construída utilizando TensorFlow/Keras.

### Estrutura

```text
Entradas (25 Features)
          ↓
Camada Oculta (32 neurônios)
          ↓
Camada Oculta (16 neurônios)
          ↓
Saída (5 classes)
```

### Funções Utilizadas

- ReLU (camadas ocultas)
- Softmax (camada de saída)

### Otimizador

```python
Adam
```

### Função de Perda

```python
Sparse Categorical Crossentropy
```

# 📈 Resultados Obtidos

## Avaliação Final

```text
Accuracy: 68,48%
Loss: 0,82
```

A Rede Neural conseguiu classificar corretamente aproximadamente 68% dos estudantes do conjunto de teste.


## Matriz de Confusão

A análise da matriz de confusão mostrou que:

✅ Excelente desempenho para identificar estudantes da classe F.

✅ A maior parte dos erros ocorreu entre classes adjacentes:

```text
B ↔ C
C ↔ D
D ↔ F
```

✅ Poucas confusões entre classes extremas:

```text
A ↔ F
```

---

## Classification Report

| Classe | Precision | Recall | F1-Score |
|----------|----------|----------|----------|
| A | 0.29 | 0.19 | 0.23 |
| B | 0.51 | 0.48 | 0.50 |
| C | 0.43 | 0.47 | 0.45 |
| D | 0.49 | 0.49 | 0.49 |
| F | 0.90 | 0.91 | 0.90 |

### Conclusões

- A classe F apresentou excelente desempenho.
- As classes intermediárias apresentaram desempenho moderado.
- A classe A foi a mais difícil de identificar.
- O dataset apresenta desbalanceamento de classes, favorecendo a classe F.


# 🛠️ Tecnologias Utilizadas

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn
- TensorFlow
- Keras


# 📚 Principais Conceitos Aplicados

## Aprendizado Não Supervisionado

- K-Means
- Clusterização
- PCA
- Segmentação de Dados

## Aprendizado Supervisionado

- Redes Neurais Artificiais
- Classificação Multiclasse
- One-Hot Encoding
- StandardScaler
- Matriz de Confusão
- Classification Report


# 👨‍💻 Autor

**Matheus Victor Feliciano Jupi**
