## 📊 Previsão de Estoque Inteligente na AWS com SageMaker Canvas

## 📋 Descrição do Projeto
Este projeto demonstra a criação de um modelo de machine learning para previsão de estoque utilizando o Amazon SageMaker Canvas, uma ferramenta de ML sem código da AWS.

## 🛠️ Ferramentas Utilizadas
Amazon SageMaker Canvas

Claude-3.5-Sonnet (para gerar o script Phyton do dataset)

Google Colab (para execução do script Python que gera o CSV e faz dowload)

## 📋 Pré-requisitos
## Conta Poe (para acessar o Claude-3.5-Sonnet)
  [Criar uma conta no Poe](https://poe.com/login)
  
  [Acessar o Claude-3.5-Sonnet no Poe](https://poe.com/Claude-3-Sonnet)
 
## Conta no Google (para acessar o Google Colab)
   [Criar uma conta Google](https://accounts.google.com/signup)
   
   [Acessar o Google Colab](https://colab.research.google.com/)

## Conta AWS ativa( para acessar o SageMaker Canva)
   [Criar uma conta AWS](https://portal.aws.amazon.com/billing/signup)
   
   [Acessar o Amazon SageMaker Canvas](https://aws.amazon.com/sagemaker/canvas/)
   
   [Guia de introdução ao SageMaker Canvas](https://docs.aws.amazon.com/sagemaker/latest/dg/canvas-getting-started.html)
     
## 🎯 Objetivos Deste Desafio de Projeto (Lab)
Aprender a utilizar dados com o Amazon SageMaker Canvas com o objetivo de prever o estoque de produtos com base em várias características e dados históricos.

## 🚀 Passo a Passo

###  SELECIONAR DATASET
O dataset utilizado neste projeto foi gerado através de um script Python executado no Google Colab. Embora o arquivo resultante (estoque_vendas_dataset.csv) esteja disponível na pasta 'datasets', você tem a opção de criar seu próprio dataset personalizado utilizando o script fornecido abaixo.

[Gerador de Dataset ](https://colab.research.google.com/drive/1x-nokxllBSdfPPB55PRLMjQzgfR5EBkj?usp=sharing)

## Passo 1: Login na AWS

![image](https://github.com/user-attachments/assets/e667b9dd-48dd-4794-8414-d0e74d9fb558)

## Passo 2: Pesquisa e Escolha do Serviço SageMaker
 
![77257494-1001-413c-a2be-ca3cdbb91bd2](https://github.com/user-attachments/assets/79e34b7a-eadf-4ae3-9b3d-37ff86d4f3d3)

## Passo 3: Escolha do Aplicativo Canvas

![a2dd08b4-30bd-44d9-9b28-91f61e1f573f](https://github.com/user-attachments/assets/59bf989e-a44a-411c-88b4-6b619a92dc9f)

## Passo 4: Abrir Aplicativo Canvas

![d07c21fc-02ef-4518-86c9-8ad3720ad802](https://github.com/user-attachments/assets/609665f6-ef0e-4955-a785-d565e36127da)

## Passo 5: Importar Dataset

![c0214dcb-7d07-4bb8-8eea-285feabb9538](https://github.com/user-attachments/assets/47802565-482c-4005-8f5f-9ee5a4c281e5)

## Passo Final - Selecionar Dataset 

![b2749700-7793-4ad7-a008-1feda5573e7e](https://github.com/user-attachments/assets/1c5f0fe0-c4bb-49de-b7e6-105724d0fde8)

### CONSTRUIR/TREINAR

## Passo 1: Criar Modelo Utilizando o DataSet Escolhido 

![b2593b1b-2de7-4802-a423-6c089bbf4568](https://github.com/user-attachments/assets/527c07bb-50b4-420f-81dd-ab2e0d9343bc)

## Passo 2: Faça a configuração de Treinamento do Modelo 

Fiz a Configuração utilizando Estoque como Target Column(1), o ID_Produto como Item ID(2), a Data_Registro como Time Stamps(3) e fiz a utilização de holiday schedule(4) com a seleção do País Brazil(5) para previsao utilizando os feriados.

![06c793a5-6523-4a4c-95f0-cf543754dc5d](https://github.com/user-attachments/assets/28066da2-b9bb-438c-83cb-69845a1c2ca4)

## Passo 3: Faça a escolha do método de treinamento

![ef8ac814-867c-4006-bb5b-2f123a5a57fe](https://github.com/user-attachments/assets/df02e6d4-e75e-4f27-a723-6e60c375d730)

Existem dois métodos de treinamentos Quick build e Standard build e cada um tem um tempo diferente de treinamento.
O Quick build geralmente leva de 2 a 15 minutos para criar o modelo, enquanto o Standard build geralmente leva de 2 a 4 horas.
para treinar meu modelo utilizei o metodo Quick build.


### ANALISAR

![Screenshot_19](https://github.com/user-attachments/assets/96ab8864-b8b3-4c83-9709-8141e5221cac)

## Métricas de Performance:

## Avg. wQL (Weighted Quantile Loss) de 0.078: 
Indica uma boa precisão geral do modelo, com erros de previsão relativamente baixos.

## MAPE (Mean Absolute Percentage Error) de 0.189: 
Sugere que, em média, as previsões têm um erro de cerca de 18.9% em relação aos valores reais.

## WAPE (Weighted Absolute Percentage Error) de 0.141:
Mostra um erro médio ponderado de 14.1%, ligeiramente melhor que o MAPE.

## RMSE (Root Mean Square Error) de 16.765: 
Representa o desvio padrão dos resíduos de previsão.

## MASE (Mean Absolute Scaled Error) de 0.973: 
Sendo menor que 1, indica que o modelo está performando melhor que um modelo naive de previsão.

## Fatores de Impacto:

![Screenshot_20](https://github.com/user-attachments/assets/e5cf53c4-f7ea-448e-902c-5c3083722f97)

![Screenshot_21](https://github.com/user-attachments/assets/50331ae7-1d0b-4c8c-a137-1d7c46ee98c3)


## Receita (9.75):
É o fator mais influente, sugerindo uma forte correlação entre a receita e os níveis de estoque necessários.

## Dia da Semana (5.77): 
Indica variações significativas na demanda de estoque dependendo do dia da semana.

## Preço do Produto (4.61): 
Mostra que alterações de preço têm um impacto considerável nas necessidades de estoque.

## Demanda (3.7):
Como esperado, a demanda direta tem um impacto significativo, embora menor que fatores como receita e dia da semana.

## Categoria do Produto (2.88): 
Diferentes categorias de produtos têm necessidades de estoque variadas.

## Feriados (0.84) e Vendas (0.36):
Têm impactos menores, mas ainda relevantes na previsão de estoque.

### PREVER

Utilizei o Método Single Prediction para analisar quatro itens diferentes (3, 13, 22 e 8), obtendo para cada um deles três cenários de previsão: P10 (cenário pessimista), P50 (cenário neutro) e P90 (cenário otimista).

O Single Prediction (Predição Única) é uma funcionalidade do Amazon SageMaker Canvas que permite aos usuários fazer previsões individuais baseadas em um conjunto específico de inputs.Esse método fornece previsões para diferentes cenários (P10, P50, P90), permitindo uma compreensão mais nuançada dos possíveis resultados.
## Legenda Linhas

P10 LINHA ROSA
P50 LINHA VERDE
P90 LINHA AMARELO

## Item 3

![single_prediction_results](https://github.com/user-attachments/assets/5652931b-b3de-41f1-94c3-33e73c43a5f7)

Demanda Histórica: 72
P10 (Pessimista): 63.119
P50 (Neutro): 64.238
P90 (Otimista): 65.231


## Item 13

![single_prediction_results (2)](https://github.com/user-attachments/assets/eacc78e9-fd2d-4845-ad1d-31f8a30f9d94)


Demanda Histórica: 74
P10 (Pessimista): 63.031
P50 (Neutro): 68.529
P90 (Otimista): 73.486


## Item 22

![single_prediction_results (1)](https://github.com/user-attachments/assets/2e193d1f-60b9-4395-8120-85560781c64c)

Demanda Histórica: 21
P10 (Pessimista): 16.488
P50 (Neutro): 50.625
P90 (Otimista): 105.073


## Item 8

![single_prediction_results](https://github.com/user-attachments/assets/9acd033f-ca2c-498d-bac8-911971fe3192)

Demanda Histórica: 78
P10 (Pessimista): 67.487
P50 (Neutro): 69.842
P90 (Otimista): 73.855

