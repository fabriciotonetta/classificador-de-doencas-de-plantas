# 🌱 Classificador de Doenças em Plantas com I.A.

Modelo de Visão Computacional que identifica doenças em plantas a partir de fotos de folhas, usando Transfer Learning. Meu primeiro projeto de Machine Learning — foi onde comecei a colocar em prática tudo que vinha estudando.

<p align="center">
  <img src="./assets/teste-predicao.png" width="480" alt="Teste de predição do modelo: identificação correta de Cercospora leaf spot com 100% de confiança" />
</p>

> ☝️ Print real de um teste do modelo: identificou corretamente "Corn (maize) — Cercospora leaf spot" com 100% de confiança.

## 📋 Contexto do problema

Doenças em plantas causam perdas relevantes na agricultura, e identificar o problema cedo — e corretamente — é essencial para o produtor agir a tempo. O objetivo deste projeto é automatizar esse diagnóstico: a partir de uma foto de folha, o modelo classifica se a planta está saudável e, se não estiver, qual doença apresenta.

## 🧠 Solução aplicada

- **Visão Computacional + Transfer Learning**: em vez de treinar uma rede neural do zero (o que exigiria muito mais dados e tempo), usei a arquitetura **MobileNetV2** já pré-treinada como base, "congelando" seus pesos e treinando apenas uma camada final nova para o problema específico de 38 classes.
- Isso é confirmado pela contagem de parâmetros do modelo: de **2.426.854 parâmetros totais**, apenas **168.870 são treináveis** — o restante veio pronto da base pré-treinada.
- Arquitetura da camada final: `Dense(128)` → `Dropout` → `Dense(38, softmax)`.

## 🛠️ Tecnologias utilizadas

- Python
- TensorFlow / Keras
- MobileNetV2 (Transfer Learning)
- NumPy, Matplotlib, Pillow
- Google Colab (GPU T4)

## 📊 Dataset

- **Fonte:** [New Plant Diseases Dataset (Kaggle)](https://www.kaggle.com/datasets/vipoooool/new-plant-diseases-dataset)
- **Total de imagens:** ~87.000
- **Categorias:** 38 (plantas saudáveis + diferentes doenças)
- **Divisão:** 70.295 imagens de treino / 17.572 imagens de validação

## 📈 Métricas e resultados

Treinamento por 5 épocas:

| Época | Accuracy (treino) | Loss (treino) | Accuracy (validação) | Loss (validação) |
|---|---|---|---|---|
| 1/5 | 85,83% | 0,4631 | 93,00% | 0,2127 |
| 2/5 | 92,72% | 0,2161 | 94,91% | 0,1530 |
| 3/5 | 94,09% | 0,1728 | 95,16% | 0,1492 |
| 4/5 | 94,86% | 0,1484 | 95,57% | 0,1282 |
| 5/5 | **95,50%** | 0,1269 | **95,42%** | 0,1387 |

O modelo converge de forma consistente, sem sinais de overfitting relevante (accuracy de treino e validação seguem próximas ao longo das épocas). Em um teste individual com imagem de validação, o modelo classificou corretamente a doença com **100% de confiança** (print acima).

Modelo final salvo em formato `.keras`, 11,11 MB — leve o suficiente para deploy simples.

## 🚀 Melhorias futuras

- Publicar uma demo interativa (Streamlit) onde qualquer pessoa possa subir uma foto e testar o modelo ao vivo
- Adicionar *data augmentation* (rotação, zoom, brilho) para melhorar a generalização
- Gerar matriz de confusão e métricas de precisão/recall por classe, não só accuracy geral
- Testar fine-tuning das últimas camadas da base MobileNetV2 (hoje totalmente congelada) para tentar ganhar mais alguns pontos de acurácia
- Adicionar `requirements.txt` e instruções de instalação para reprodutibilidade
