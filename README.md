# Modelo de Detecção de Pneumonia em Radiografias de Tórax

## Objetivo

Este projeto tem como objetivo implementar um modelo de Deep Learning para a detecção de pneumonia em radiografias de tórax O modelo é treinado, validado e testado em um dataset público de radiografias de tórax

- **Link do Dataset**: [Chest X-Ray Images (Pneumonia)](https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia)

---

## Pré-Processamento

As seguintes etapas de pré-processamento foram realizadas no dataset:

- **Redimensionamento**: Todas as imagens foram ajustadas para um tamanho fixo de `128x128` pixels
- **Normalização**: Os valores dos pixels foram normalizados para o intervalo `[0, 1]`
- **Aumento de Dados (Data Augmentation)**:
  - Rotação aleatória de até 15 graus
  - Reflexão horizontal com 50% de probabilidade
  - Adição de ruído utilizando blur gaussiano com probabilidade de 20%
  - Transformação em tensores e normalização para escala de cinza

---

## Etapas do Projeto

### 1. Configuração do Dataset

- O dataset foi organizado em pastas de treinamento, validação e teste
- As categorias presentes no conjunto de dados são automaticamente detectadas no diretório `train`

### 2. Pré-Processamento das Imagens

- Conversão das imagens para escala de cinza (`8-bit grayscale`)
- Redimensionamento para `128x128 pixels`
- Normalização dos valores dos pixels para o intervalo `[0, 1]`

### 3. Implementação de Data Augmentation

Durante o treinamento, aplicamos Data Augmentation às imagens para aumentar a robustez do modelo As transformações incluem:

- **Rotação Aleatória**: Rotação de até 15 graus
- **Reflexão Horizontal**: Reflexão com 50% de probabilidade
- **Adição de Ruído**: Utilizando blur gaussiano com probabilidade de 20%
- **Normalização**: Os valores dos pixels são normalizados em torno de `mean=0.5` e `std=0.5`

As transformações foram aplicadas apenas ao conjunto de treinamento Os conjuntos de validação e teste passaram por uma normalização simples

### 4. Processamento e Análise dos Dados

- Contagem de imagens por categoria nos conjuntos de treinamento, validação e teste
- Geração de informações detalhadas, como:
  - Tamanho médio das imagens
  - Proporção de imagens por classe

### 5. Visualização dos Dados

- Exemplos de imagens com Data Augmentation foram visualizados para validação das transformações aplicadas

---

## Análise e Resultados

### Estatísticas Gerais

- **Distribuição de Imagens**:
  - As imagens foram divididas entre os conjuntos de treinamento, validação e teste
  - A distribuição das classes foi visualizada utilizando gráficos de barras

### Visualização de Exemplos

- Amostras de imagens de cada classe foram selecionadas e visualizadas para verificar as transformações de Data Augmentation
