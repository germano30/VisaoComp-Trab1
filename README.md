# Detecção de Óculos em Imagem com OpenCV

## Descrição

Este projeto foi desenvolvido como parte do trabalho para a disciplina de **Visão Computacional**. O objetivo é detectar a presença de óculos em uma imagem facial utilizando técnicas de processamento de imagens e visão computacional com a biblioteca **OpenCV**. A abordagem inclui detecção de faces, manipulação de imagem para focar nas regiões de interesse, e aplicação de filtros para identificar possíveis características que indicam a presença de óculos.

## Estrutura do Código

O código é estruturado da seguinte forma:

1. **Leitura e Visualização da Imagem:**
   O código tenta abrir a imagem do arquivo em dois formatos possíveis (.png ou .jpg). Caso a imagem seja carregada corretamente, ela é exibida utilizando `matplotlib`.

2. **Detecção de Faces:**
   Utilizamos o classificador Haar Cascade (`haarcascade_frontalface_default.xml`) para identificar a região da face na imagem. A partir disso, desenha-se um retângulo em torno da face detectada.

3. **Corte e Manipulação da Imagem:**
   A região da face detectada é cortada e processada. Uma subseção da parte superior da face (área onde os óculos normalmente se posicionam) é extraída para um tratamento mais detalhado.

4. **Conversão para Tons de Cinza:**
   A parte superior da face cortada é convertida para escala de cinza, facilitando o uso de operações de filtro para detecção de bordas.

5. **Aplicação de Filtros:**
   Utilizamos o filtro de Sobel com um kernel personalizado para detectar bordas verticais e horizontais, o que nos ajuda a identificar a estrutura dos óculos.

6. **Criação da Imagem Binária:**
   A imagem resultante dos filtros é binarizada, facilitando a segmentação de regiões com fortes bordas que podem indicar a presença de óculos.

7. **Verificação da Presença de Óculos:**
   A região abaixo da metade da imagem binarizada é verificada para identificar a presença de bordas intensas, que podem sugerir a existência de armações de óculos.

## Requisitos

- **Python 3.x**
- **Bibliotecas**:
  - `opencv-python`
  - `numpy`
  - `matplotlib`

Para instalar as dependências, execute:

```bash
pip install opencv-python numpy matplotlib
