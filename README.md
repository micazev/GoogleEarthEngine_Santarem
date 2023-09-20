# Santarém IC - Análise Temporal de Dados Landsat e Sentinel na Região de Santarém

## Descrição

Este repositório contém códigos para análise temporal de imagens Landsat e Sentinel na região de Santarém. Os scripts foram escritos usando a API do Google Earth Engine e incluem funcionalidades para:

- Importar shapefiles contendo as áreas de estudo.
- Filtro e classificação de imagens Landsat e Sentinel para múltiplos anos.
- Cálculo de índices de vegetação (NDVI) e água (NDWI).
- Classificação de uso do solo utilizando Random Forest.

## Pré-requisitos

- Conta no Google Earth Engine
- API do Google Earth Engine instalada

## Estrutura do Repositório

- `loop-landsat-indices`: Script para a análise usando dados do Landsat.
- `loop-sentinel-indices`: Script para a análise usando dados do Sentinel.
- `selecaoImagemSemNuvem`: Script com o rascunho de como foi feita a seleção manual das imagens sem nuvem

## Como Usar

1. **Acesse o Google Earth Engine e Cole o Código** de cada arquivo loop em files distintas

   Abra o Editor de Scripts do Google Earth Engine e cole o código.

2. **Faça o download dos polígonos** para a pasta de Assets do seu projeto GEE

   Renomeie o caminho dos arquivos corretamente em:
   - var shapefile = ee.FeatureCollection("...");
   - var geometryCollection = ee.FeatureCollection("...");

4. **Execute o Script**

   Clique no botão 'Run' para executar o script.

## Características dos Scripts

- **Importação de Shapefiles**: Importa shapefiles que definem a área de estudo em Santarém.
- **Loop Temporal**: Loop para filtrar e coletar imagens para múltiplos anos.

- **Cálculo de Índices**: Funções para calcular NDVI e NDWI dependendo do sensor do Landsat.

- **Random Forest Classifier**: Implementação da classificação Random Forest.
  
Cada imagem é categorizada (classificada) individualmente usando os polígonos de treinamento. Cada imagem é primeiro recortada para o polígono da área de estudo (shapefile). Em seguida, os índices NDVI e NDWI são calculados para cada imagem. Os dados de treinamento são coletados dos polígonos de interesse (geometryCollection), e um classificador Random Forest é treinado com esses dados. Por fim, cada imagem é classificada usando o classificador treinado e adicionada ao mapa.
