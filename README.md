# 📊 Clinical Evaluation Dataset – Leprosy

This repository provides supporting materials and example code for working with a structured dataset for the clinical evaluation of patients with leprosy. The dataset includes demographic, clinical, and functional information organized across multiple relational tables.

The dataset files are publicly available through Mendeley Data:

**Dataset:**  
https://data.mendeley.com/datasets/hjgfjkj3tv/1

This repository also includes an example pipeline demonstrating how to read and integrate the relational tables into a denormalized tabular format suitable for analysis, visualization, and machine learning.

---

## 📦 Dataset Availability

The dataset itself is hosted on **Mendeley Data** and can be accessed at:

https://data.mendeley.com/datasets/hjgfjkj3tv/1

After downloading the dataset, the CSV files can be organized inside a local `dataset/` directory to run the examples provided in this repository.

---

## 📁 Dataset Structure

The dataset available through Mendeley Data contains the following relational tables:

```text
dataset/
    ├── Avaliação sensitiva pé.csv
    ├── Face.csv
    ├── Ficha.csv
    ├── Membro inferior.csv
    ├── Membro superior.csv
    ├── Paciente.csv
    ├── Pontuação.csv
    └── Queixas.csv
```

The repository contains the supporting documentation and example code:

```text
modelagem/
    ├── data_dictionary.pdf
    └── data modeling.png

example_reading.ipynb
example_reading.py
README.md
```

---

## 🧠 Data Modeling

* The dataset follows a **normalized relational model**
* The central table is **Ficha (clinical record)**, linked to other entities
* Clinical evaluations are recorded over time via `data_avaliacao`
* Some tables may include an additional dimension related to the evaluated side, such as right or left

For more details about the data structure and relationships:

* 📘 `modelagem/data_dictionary.pdf`
* 🧩 `modelagem/data modeling.png`

The complete dataset can be downloaded from:

https://data.mendeley.com/datasets/hjgfjkj3tv/1

---

## 🚀 How to Use the Dataset

This repository provides example scripts for reading and integrating the dataset:

* `example_reading.py`
* `example_reading.ipynb`

### ✔️ Goal of the example

Transform multiple relational tables into a single DataFrame where:

> **Each row represents one clinical follow-up (`id_ficha + data_avaliacao`)**

---

## ▶️ Quick Start

### 1. Clone the repository

```bash
git clone <repository-url>
cd <repository-name>
```

---

### 2. Download the dataset

Download the dataset from Mendeley Data:

https://data.mendeley.com/datasets/hjgfjkj3tv/1

Place the downloaded CSV files inside a local directory named:

```text
dataset/
```

The expected structure is:

```text
dataset/
    ├── Avaliação sensitiva pé.csv
    ├── Face.csv
    ├── Ficha.csv
    ├── Membro inferior.csv
    ├── Membro superior.csv
    ├── Paciente.csv
    ├── Pontuação.csv
    └── Queixas.csv
```

---

### 3. Install dependencies

```bash
pip install pandas
```

---

### 4. Run the example

```bash
python example_reading.py
```

Or open the notebook:

```bash
jupyter notebook example_reading.ipynb
```

---

## 📌 What the Code Does

The example pipeline performs the following steps:

### 🔹 1. Load CSV files

Reads the relational tables downloaded from Mendeley Data and stored in the local `dataset/` directory.

---

### 🔹 2. Date normalization

* Converts `data_avaliacao` to datetime format
* Handles common formatting inconsistencies

---

### 🔹 3. Side based feature transformation

Tables containing variables related to body side can be transformed into separate features for right and left evaluations.

Example:

```text
face_nariz_ressecamento_direita
face_nariz_ressecamento_esquerda
```

---

### 🔹 4. Data integration

The relational tables are merged using:

```text
id_ficha + data_avaliacao
```

This preserves the correct temporal granularity for each clinical follow-up.

---

### 🔹 5. Enrichment with patient data

The resulting dataset is enriched with attributes from:

* `Paciente`
* `Ficha`

---

## 📦 Output

The pipeline generates a final DataFrame with a structure similar to:

```text
id_ficha | data_avaliacao | sexo | ... | face_* | ms_* | mi_* | pe_* | ...
```

The resulting tabular dataset can be used for:

* 📊 Exploratory Data Analysis
* 📈 Dashboards using Power BI, Looker, and similar tools
* 🤖 Machine Learning

---

# 📊 Dataset de Avaliação Clínica – Hanseníase

Este repositório disponibiliza materiais de apoio e códigos de exemplo para utilização de um conjunto de dados estruturados voltado à avaliação clínica de pacientes com hanseníase. O dataset contém informações demográficas, clínicas e funcionais organizadas em múltiplas tabelas relacionais.

Os arquivos do dataset estão disponíveis publicamente através do **Mendeley Data**:

**Dataset:**  
https://data.mendeley.com/datasets/hjgfjkj3tv/1

O repositório também disponibiliza exemplos de leitura e integração das tabelas relacionais em um formato tabular denormalizado, adequado para análises, visualizações e desenvolvimento de modelos de machine learning.

---

## 📦 Disponibilidade do Dataset

O conjunto de dados está hospedado no **Mendeley Data** e pode ser acessado através do endereço:

https://data.mendeley.com/datasets/hjgfjkj3tv/1

Após realizar o download, os arquivos CSV podem ser organizados localmente em uma pasta chamada `dataset/` para utilização dos exemplos disponibilizados neste repositório.

---

## 📁 Estrutura do Dataset

O conjunto de dados disponibilizado através do Mendeley Data contém as seguintes tabelas relacionais:

```text
dataset/
    ├── Avaliação sensitiva pé.csv
    ├── Face.csv
    ├── Ficha.csv
    ├── Membro inferior.csv
    ├── Membro superior.csv
    ├── Paciente.csv
    ├── Pontuação.csv
    └── Queixas.csv
```

O repositório contém a documentação de apoio e os exemplos de utilização:

```text
modelagem/
    ├── data_dictionary.pdf
    └── data modeling.png

example_reading.ipynb
example_reading.py
README.md
```

---

## 🧠 Modelagem dos Dados

* O dataset segue um **modelo relacional normalizado**
* A tabela central é a **Ficha**, que se conecta às demais entidades
* As avaliações clínicas são registradas ao longo do tempo através de `data_avaliacao`
* Algumas tabelas podem possuir granularidade adicional relacionada ao lado avaliado, como direito ou esquerdo

Para mais detalhes sobre a estrutura e os relacionamentos dos dados:

* 📘 `modelagem/data_dictionary.pdf`
* 🧩 `modelagem/data modeling.png`

O conjunto de dados completo pode ser obtido em:

https://data.mendeley.com/datasets/hjgfjkj3tv/1

---

## 🚀 Como Utilizar o Dataset

Este repositório inclui exemplos para leitura e integração das tabelas:

* `example_reading.py`
* `example_reading.ipynb`

### ✔️ Objetivo do exemplo

Transformar os dados das múltiplas tabelas relacionais em um único DataFrame onde:

> **Cada linha representa um acompanhamento clínico (`id_ficha + data_avaliacao`)**

---

## ▶️ Execução Rápida

### 1. Clone o repositório

```bash
git clone <url-do-repositorio>
cd <nome-do-repo>
```

---

### 2. Baixe o dataset

Realize o download do conjunto de dados através do Mendeley Data:

https://data.mendeley.com/datasets/hjgfjkj3tv/1

Após o download, coloque os arquivos CSV dentro de uma pasta local chamada:

```text
dataset/
```

A estrutura esperada é:

```text
dataset/
    ├── Avaliação sensitiva pé.csv
    ├── Face.csv
    ├── Ficha.csv
    ├── Membro inferior.csv
    ├── Membro superior.csv
    ├── Paciente.csv
    ├── Pontuação.csv
    └── Queixas.csv
```

---

### 3. Instale as dependências

```bash
pip install pandas
```

---

### 4. Execute o exemplo

```bash
python example_reading.py
```

Ou utilize o notebook:

```bash
jupyter notebook example_reading.ipynb
```

---

## 📌 O que o Código Faz

O pipeline implementado no exemplo realiza as seguintes etapas:

### 🔹 1. Leitura dos arquivos CSV

Carrega as tabelas relacionais baixadas do Mendeley Data e armazenadas localmente na pasta `dataset/`.

---

### 🔹 2. Normalização de datas

* Converte `data_avaliacao` para o formato datetime
* Trata inconsistências comuns de formatação

---

### 🔹 3. Transformação de variáveis por lado

As tabelas que possuem variáveis relacionadas ao lado corporal podem ser convertidas em colunas separadas para avaliações do lado direito e esquerdo.

Exemplo:

```text
face_nariz_ressecamento_direita
face_nariz_ressecamento_esquerda
```

---

### 🔹 4. Integração dos dados

As tabelas relacionais são integradas utilizando:

```text
id_ficha + data_avaliacao
```

Esse procedimento preserva a granularidade temporal correta de cada acompanhamento clínico.

---

### 🔹 5. Enriquecimento com dados do paciente

O conjunto resultante é complementado com informações das tabelas:

* `Paciente`
* `Ficha`

---

## 📦 Resultado

O pipeline gera um DataFrame final com estrutura semelhante a:

```text
id_ficha | data_avaliacao | sexo | ... | face_* | ms_* | mi_* | pe_* | ...
```

O conjunto tabular resultante pode ser utilizado para:

* 📊 Análise Exploratória de Dados
* 📈 Dashboards utilizando Power BI, Looker e ferramentas similares
* 🤖 Machine Learning

---
