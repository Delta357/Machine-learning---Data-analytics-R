## Big data analytics R

[![MIT License](https://img.shields.io/apm/l/atomic-design-ui.svg?)](https://github.com/tterb/atomic-design-ui/blob/master/LICENSEs)
[![GPLv3 License](https://img.shields.io/badge/License-GPL%20v3-yellow.svg)](https://opensource.org/licenses/)
[![AGPL License](https://img.shields.io/badge/license-AGPL-blue.svg)](http://www.gnu.org/licenses/agpl-3.0)
[![author](https://img.shields.io/badge/author-RafaelGallo-red.svg)](https://github.com/RafaelGallo?tab=repositories) 
[![](https://img.shields.io/badge/R-3.6.0-red.svg)](https://www.r-project.org/)
[![](https://img.shields.io/badge/ggplot2-white.svg)](https://ggplot2.tidyverse.org/)
[![](https://img.shields.io/badge/dplyr-blue.svg)](https://dplyr.tidyverse.org/)
[![](https://img.shields.io/badge/readr-green.svg)](https://readr.tidyverse.org/)
[![](https://img.shields.io/badge/ggvis-black.svg)](https://ggvis.tidyverse.org/)
[![](https://img.shields.io/badge/Shiny-red.svg)](https://shiny.tidyverse.org/)
[![](https://img.shields.io/badge/plotly-green.svg)](https://plotly.com/)
[![](https://img.shields.io/badge/Caret-orange.svg)](https://caret.tidyverse.org/)


![App Screenshot](https://image.freepik.com/vetores-gratis/fundo-de-diagrama-de-circuito-de-rosto-de-tecnologia_1017-18300.jpg)


## Autores

- [@RafaelGallo](https://github.com/RafaelGallo)


## Projetos realizado nesse projeto

- Data analytics - Análise Descritiva IBGE
- Machine learning - Sistema de recomendação de filmes
- Machine learning aprendizagem não supervisionada - Sistema de recomendação de filmes~com K-Means
- Machine learning modelo de classificação - Classificação casos de dengue
- Machine learning modelo de regressão linear - Previsão de vendas
- Mapa de dados vendas
- Calculo de matriz
- Calculo de vetor


## Exemplo - Machine learning em R

```
- Definindo o diretório de trabalho
setwd()
getwd()

# Carregando as bibliotecas
library(plyr)
library(corrplot)
library(ggplot2)
library(gridExtra)
library(ggthemes)
library(caret)
library(MASS)
library(randomForest)
library(party)

library(readr)
data <- read_csv("nome_do_dataset")
data 

# Visualizando as 5 primeiras linhas
head(data)

# Visualizando linhas e colunas
str(data)

# Separando em treino e teste
intrain <- createDataPartition(data$Churn,p=0.7,list=FALSE)
set.seed(2017)

# Dados de treino
training <- data[intrain,]

# Dados de teste
testing <- data[-intrain,]

# Visualizando linhas e colunas dos dados de treino
dim(training); 

# Visualizando linhas e colunas dos dados de teste
dim(testing)

# Árvore de Decisão
tree <- ctree(data ~ Contract+tenure_group+PaperlessBilling, training)
tree

# Plot da árvore de Decisão
plot(tree, type='simple')

# Precisão da árvore de decisão
p1 <- predict(tree, training)
tab1 <- table(Predicted = p1, Actual = training$Churn)
tab2 <- table(Predicted = pred_tree, Actual = testing$Churn)
print(paste('Decision Tree Accuracy',sum(diag(tab2))/sum(tab2)))

# Confusion Matrix
print("Confusion Matrix Para Random Forest"); table(testing$Churn, pred_rf)

```

