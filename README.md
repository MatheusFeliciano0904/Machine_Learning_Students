# 📊 Análise de Performance de Estudantes com K-Means

Projeto de Machine Learning Não Supervisionado focado na identificação de padrões acadêmicos e comportamentais entre estudantes utilizando **K-Means Clustering**, **PCA** e técnicas de análise exploratória de dados.


## 📌 Objetivo

O projeto busca identificar grupos de estudantes com características semelhantes relacionadas a:

- desempenho acadêmico;
- hábitos de estudo;
- frequência escolar;
- apoio familiar;
- atividades extracurriculares.

## 🧠 Técnicas Utilizadas

- K-Means Clustering
- PCA (Principal Component Analysis)
- One-Hot Encoding
- Padronização de Dados
- Análise Exploratória de Dados (EDA)
- Silhouette Score

## ⚙️ Tecnologias

### Linguagem
- Python

### Bibliotecas
```python
pandas
numpy
matplotlib
seaborn
plotly
scikit-learn
```
## 📂 Dataset

O dataset contém informações acadêmicas, demográficas e comportamentais dos estudantes.

### Principais Variáveis

| Variável        | Descrição                                    |
| --------------- | -------------------------------------------- |
| Age             | Idade do estudante                           |
| Gender          | Gênero                                       |
| Ethnicity       | Etnia                                        |
| StudyTimeWeekly | Horas de estudo semanais                     |
| Absences        | Número de faltas                             |
| GPA             | Média geral do estudante                     |
| ParentalSupport | Nível de apoio familiar                      |
| Extracurricular | Participação em atividades extracurriculares |
| Sports          | Participação em esportes                     |
| Music           | Participação em música                       |
| Volunteering    | Participação em voluntariado                 |

### 🔗 Fonte do Dataset

Dataset obtido no Kaggle:

* [Students Performance Dataset - Kaggle](https://www.kaggle.com/datasets/rabieelkharoua/students-performance-dataset/data?utm_source=chatgpt.com)

Autor do dataset: Rabie El Kharoua.

## 🔄 Pipeline do Projeto

1. Pré-processamento dos dados;
2. Análise exploratória;
3. Engenharia de features;
4. Padronização dos dados;
5. Clusterização com K-Means;
6. Visualização com PCA;
7. Avaliação dos clusters.


## 📉 Resultados

Os clusters apresentaram diferenças comportamentais e acadêmicas entre os estudantes, porém com certa sobreposição entre os grupos.

O projeto demonstrou que datasets educacionais frequentemente possuem padrões parcialmente misturados, algo confirmado pelo **Silhouette Score** obtido.


## 🚀 Como Executar

### Clonar o repositório

```bash
git clone https://github.com/seu-usuario/seu-repositorio.git


### Instalar dependências

```bash
pip install -r requirements.txt
```

### Executar o notebook

```bash
jupyter notebook
```

Abrir:

```bash
K_means_Students.ipynb
```

## 📁 Estrutura do Projeto

```bash
Aprendizado_Nao_Supervisionado_Students/
│
├── data/
│   └── students/
│       └── K_means_Students.ipynb
│
├── notbooks/
│   ├── Metadados do Dataset.docx
│   └── Student_performance_data_.csv
│
└── .gitattributes
```


## 👨‍💻 Autor

* Matheus Victor Feliciano Jupi

* Gabriella Santos Mendes
