# Diário de Desenvolvimento — Classificador de Doenças em Plantas

## Sobre este diário
Registro do progresso do projeto de Visão Computacional
para classificação de doenças em plantas com I.A.

---

## Dia 1 — Configuração do ambiente

**O que foi feito:**
- Ambiente de desenvolvimento configurado (Google Colab, GitHub, Kaggle)
- Repositório criado no GitHub com estrutura de pastas organizada
- Dataset selecionado: New Plant Diseases Dataset (Kaggle)
- Primeiros commits realizados

**Decisões tomadas:**
- Escolha do Google Colab por não exigir instalação local e ter GPU gratuita
- Dataset escolhido por ter mais de 87.000 imagens, sendo robusto para treino

**Próximos passos:**
- Configurar o notebook no Colab
- Fazer análise exploratória das imagens
- Iniciar o pré-processamento dos dados
---

## Dia 2 — Coleta e Análise dos Dados

**O que foi feito:**
- Dataset baixado direto do Kaggle para o servidor do Google Colab
- Confirmadas 38 categorias de doenças em plantas
- Total de 70.295 imagens de treino disponíveis
- Visualização das imagens realizada com sucesso
- Análise da distribuição das categorias — dados bem balanceados

**Decisões tomadas:**
- Uso do kagglehub para download direto no servidor, evitando downloads lentos
- Dataset com distribuição balanceada dispensou técnicas de correção de dados

**Próximos passos:**
- Pré-processar as imagens para o formato que a I.A. espera
- Construir o modelo com Transfer Learning usando MobileNetV2
- Iniciar o treinamento
