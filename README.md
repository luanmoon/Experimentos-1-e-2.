# Experimentos 1 e 2

## Descrição

Este repositório contém os experimentos desenvolvidos para o artigo:

**"Análise comparativa da eficácia de técnicas de
aprendizado não-supervisionados no contexto de
cibersegurança datasets processados em formato
offline e simulados online com fluxo contínuo"**

O objetivo do estudo é comparar o desempenho dos algoritmos de agrupamento:

- K-Means
- Cluster Hierárquico
- DBSCAN

em dois contextos distintos:

1. **Cenário Offline** – processamento tradicional de um dataset estático.
2. **Cenário Online Simulado** – processamento do mesmo dataset utilizando a biblioteca CApyMOA para simular fluxo contínuo de dados (*data stream*).

O dataset utilizado foi o **Kitsune Network Attack Dataset**, contendo diferentes cenários de tráfego de rede e ataques cibernéticos.

---

## Estrutura do Repositório

```text
├── Experimento_1_Offline.ipynb
├── Experimento_2_Online_CapyMOA.ipynb
├── resultados/
│   ├── tabelas/
│   └── figuras/
└── README.md
```

---

## Dataset

O estudo utiliza uma amostra aleatória de 10.000 instâncias do:

**Kitsune Network Attack Dataset**

Referência:

> Mirsky, Y. et al. Kitsune: An Ensemble of Autoencoders for Online Network Intrusion Detection. NDSS 2018.

Link do dataset:

https://www.kaggle.com/datasets/ymirsky/network-attack-dataset-kitsune

---

# Experimento 1 – Cenário Offline

Neste experimento os dados são processados de forma tradicional, sem simulação de fluxo contínuo.

## Etapas

1. Carregamento do dataset
2. Remoção de atributos não numéricos
3. Tratamento de valores ausentes
4. Padronização com StandardScaler
5. Redução de dimensionalidade utilizando PCA
6. Aplicação dos algoritmos:
   - K-Means
   - Cluster Hierárquico
   - DBSCAN
7. Avaliação utilizando:
   - Silhouette Score
   - Número de clusters encontrados
   - Percentual de ruído (DBSCAN)
8. Visualização bidimensional utilizando t-SNE

---

# Experimento 2 – Cenário Online Simulado

Neste experimento o dataset é convertido para fluxo contínuo de dados utilizando a biblioteca CApyMOA.

## Etapas

1. Amostragem do dataset
2. Criação de coluna dummy para compatibilidade com o CSVStream
3. Conversão para stream utilizando CApyMOA
4. Leitura sequencial das instâncias
5. Padronização dos dados
6. Aplicação dos algoritmos:
   - K-Means
   - Cluster Hierárquico
   - DBSCAN
7. Avaliação utilizando:
   - Silhouette Score
   - Número de clusters encontrados
   - Percentual de ruído (DBSCAN)
8. Visualização bidimensional utilizando t-SNE

---

## Bibliotecas Utilizadas

```python
pandas
numpy
matplotlib
scikit-learn
capymoa
```

Instalação:

```bash
pip install pandas numpy matplotlib scikit-learn capymoa
```

---

## Métricas Avaliadas

### Silhouette Score

Avalia a qualidade dos agrupamentos encontrados pelos algoritmos.

Intervalo:

- Próximo de 1 → agrupamentos bem definidos
- Próximo de 0 → sobreposição entre clusters
- Negativo → agrupamentos inadequados

### Número de Clusters

Quantidade de agrupamentos identificados por cada método.

### Percentual de Ruído

Métrica utilizada para o DBSCAN, representando a proporção de amostras classificadas como ruído.

---

## Resultados

Os resultados completos podem ser encontrados nas tabelas e figuras geradas pelos notebooks.

As comparações incluem:

- Desempenho Offline × Online
- Número de clusters encontrados
- Silhouette Score
- Percentual de ruído
- Visualização dos agrupamentos após redução de dimensionalidade

---

## Autores

- Luan de Mendonça Soares
- Victor Lucas da Costa Lopes
- Olive Oliveira Medeiros
- José Kauã de Lima Souza
- José Carlos Oliveira de Lima

Instituto Metrópole Digital (IMD)

Universidade Federal do Rio Grande do Norte (UFRN)
