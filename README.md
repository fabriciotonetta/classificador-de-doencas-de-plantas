# 🌿 Classificador de Doenças em Plantas com I.A.

Modelo de Visão Computacional capaz de identificar 38 tipos diferentes de doenças em folhas de plantas a partir de uma imagem, utilizando Transfer Learning com a arquitetura MobileNetV2.

![Status](https://img.shields.io/badge/status-concluído-brightgreen)
![Python](https://img.shields.io/badge/Python-3.10-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)

---

## 📌 Sobre o Projeto

Doenças em plantações causam perdas enormes na agricultura todos os anos. O diagnóstico tradicional depende de um especialista olhar a folha pessoalmente — um processo lento e nem sempre acessível para pequenos produtores.

Este projeto demonstra como a Visão Computacional pode automatizar esse diagnóstico: basta uma foto da folha para o modelo indicar qual doença (ou se a planta está saudável) com alta precisão.

## 🎯 Resultados

- **Acurácia de validação: 95,4%**
- Modelo testado em mais de 17.000 imagens nunca vistas durante o treino
- 38 categorias de doenças/plantas diferentes reconhecidas

![Evolução do treinamento](notebook/evolucao_treinamento.png)

## 🧠 Como funciona (Transfer Learning)

Em vez de treinar uma rede neural do zero — o que exigiria milhões de imagens e dias de processamento — este projeto utiliza a técnica de **Transfer Learning**: 

1. Parte-se do modelo **MobileNetV2**, já treinado pelo Google com mais de 1 milhão de imagens (dataset ImageNet)
2. Esse modelo já sabe reconhecer formas, bordas, texturas e padrões visuais gerais
3. Adicionamos novas camadas no topo dele, treinadas especificamente para reconhecer as 38 categorias de doenças em plantas
4. O resultado: um treinamento muito mais rápido e com excelente precisão

## 🗂️ Dataset

- **Fonte:** [New Plant Diseases Dataset (Kaggle)](https://www.kaggle.com/datasets/vipoooool/new-plant-diseases-dataset)
- **Total de imagens:** ~87.000
- **Categorias:** 38 (incluindo plantas saudáveis e diferentes doenças)
- **Divisão:** 70.295 imagens de treino / 17.572 imagens de validação

## 🛠️ Tecnologias Utilizadas

| Tecnologia | Uso no projeto |
|---|---|
| Python | Linguagem principal |
| TensorFlow / Keras | Construção e treinamento do modelo |
| MobileNetV2 | Modelo base de Transfer Learning |
| Matplotlib | Visualização de imagens e gráficos |
| Google Colab | Ambiente de desenvolvimento com GPU gratuita |
| Kaggle | Fonte do dataset |

## 📁 Estrutura do Repositório

classificador_de_doencas_de_plantas/

│
├── notebook/
│  ├── classificador_doencas_plantas.ipynb   ← código completo
│  └── evolucao_treinamento.png              ← gráfico de resultados
│
├── data/                                      ← instruções de acesso aos dados
├── README.md
└── diario-de-desenvolvimento.md               ← histórico do processo de criação

## 🚀 Como Executar Este Projeto

1. Acesse o notebook na pasta `notebook/`
2. Abra com o [Google Colab](https://colab.research.google.com)
3. Ative a GPU em: `Ambiente de execução > Alterar o tipo de ambiente de execução > T4 GPU`
4. Execute as células em ordem, de cima para baixo

## 📓 Processo de Desenvolvimento

Todo o raciocínio, decisões técnicas e desafios enfrentados durante a construção deste projeto estão documentados no [Diário de Desenvolvimento](diario-de-desenvolvimento.md).

## 👤 Autor

**Fabricio Tonetta**
[LinkedIn](https://www.linkedin.com/in/fabricio-tonetta-33a2462a0) · [GitHub](https://github.com/fabriciotonetta)
