[🇺🇸 English](README.md) | [🇧🇷 Português](README-pt.md)

# Análise-GIS-para-Triagem-Locacional-de-um-Potencial-Truck-Stop-no-Arizona
### Pesquisa  da Viabilidade para a Construção de uma Truck Stop
![capa](capa.png)
---

## 1. Contextualização e Objetivo
* O estado do Arizona, localizado nos Estados Unidos, possuí alta presença de Truck Stops devido a sua alta dependência do tráfego rodoviário, tendo em vista a formação geológica e disposição geográfica dos terrenos. Isso faz com que a geolocalização para a construção de um novo posto de combustível para atender caminhões de grande porte seja realizada através de um estudo territorial, devendo ser observado não apenas a viabilidade de aquisição do terreno e capacidade em comportar a construção, mas também o fluxo de carretas e caminhões, além do risco de desastres naturais. O sul e o sudoeste do estado (onde ficam Phoenix e Tucson) são formados por vales desérticos de baixa altitude (como o Deserto de Sonora). Embora passe a maior parte do ano extremamente seco e quente, o sul sofre com enchentes repentinas severas (flash floods) em duas épocas específicas (verão e inverno), necessitando que o terreno selecionado seja categorizado como seguro de acordo com a FEMA Flood Map Service Center.
* O objetivo desse repositório foi demonstrar competências aplicáveis à função de GIS & Land Feasibility Analyst da KND Fuels por meio de um fluxo de análise espacial em escala estadual e de uma investigação local na região de Tucson.
* O trabalho combina dados de tráfego, ETL em python, imagens de satélite, camadas territoriais, localização de concorrentes e triagem de viabilidade do terreno mediante a análise de risco de eventos naturais, tais como enchentes (FEMA).
---

## 2. Área de Estudo e Dados Selecionados

* Recorte Espacial: Estado do Arizona, EUA.
* Ano de Referência: 2025/2026
* A seleção dos indicadores não foi feita pela simples disponibilidade dos dados, mas sim ao buscar fontes que forneçam informação confiável e de qualidade para auxiliar na tomada de decisão em busca de uma área para a construção de um Truck Stop. 
* Os dados foram buscados a partir de algumas necessidade:
  - Contextualização territorial: organizar camadas de situação das terras para distinguir, em nível exploratório, áreas privadas, públicas e categorias com restrições específicas à aquisição privada convencional.
  - Leitura do tráfego: comparar o volume total estimado de veículos com indicadores de tráfego comercial de longa distância e regional.
  - Mapeamento da concorrência: reunir 59 pontos obtidos por consulta automatizada à Overpass e 11 pontos complementares pesquisados manualmente (com base em fontes oficiais e pesquisa exploratória em imagens de satélite), totalizando 70 pontos identificados antes da validação final de duplicatas e atributos.
  - Análise de proximidade: construir e dissolver buffers de 20 e 30 milhas ao redor dos pontos de concorrentes.
  - Diferença espacial: destacar segmentos e áreas fora das zonas de influência geométrica definidas pelos buffers e interpretá-los em conjunto com as camadas de tráfego.
  - Priorização e inspeção local: análise das áreas fora das zonas de influência a partir do buffer para aprofundar a análise e selecionar o terreno escolhido.
  - Triagem de restrições: sobrepor as zonas de inundação da FEMA para evitar a seleção de áreas de alto risco.

* Os dados utilizados foram:
  - **Bureau of Land Management (2026):** Utilizado para o mapeamento fundiário, delimitando terras privadas, governamentais, reservas indígenas e áreas federais.
  - **AZGeo Data Hub (2025):** Fonte principal para as métricas de transporte, fornecendo os dados de Volume Médio Diário Anual (AADT) para tráfego comercial de longo curso, caminhões de unidade simples e estimativas totais de veículos.
  - **U.S. Census Bureau (2026):** Aplicado para a estruturação das malhas territoriais e limites estaduais/municipais do Arizona.
  - **OpenStreetMap contributors (2026):** Base vetorial empregada na extração da malha rodoviária, vias de acesso e geolocalização da infraestrutura de concorrentes do setor (Flying J, Love's, Petro, Pilot, TA).
  - **FEMA - National Flood Hazard Layer (2026):** Utilizado na validação ambiental do terreno, mapeando as classes de risco de inundação (como as zonas seguras X e as zonas de risco A/AE) para garantir a segurança da infraestrutura.
  - **Google Satellite Hybrid / HCMGIS (2026):** Forneceu as imagens orbitais de alta resolução para a visualização do lote proposto em Tucson e das áreas adjacentes na escala de micro-triagem.
---

## 3. Produtos Cartográficos
### 3.1 
![Estatísticas](correlacoes.jpg)

* Para resp
