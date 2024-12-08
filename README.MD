#  Projeto da Disciplina Ciclo 3

## Apresentação

Este projeto foi desenvolvido no contexto da disciplina do ciclo 3, cujo objetivo foi analisar dados de uso e cobertura do solo no território brasileiro a partir de uma imagem de satélite. Por meio de um código em Python, é possível extrair a quantidade total de pixels da imagem, bem como pixels relacionados a categorias específicas de uso da terra, e a partir desses resultados, estimar a área ocupada por determinados usos do solo em hectares.

### Objetivos

1. **Quantificar pixels da imagem**:  
   - Obter a quantidade total de pixels.
   - Quantificar pixels sem dados (código 0).
   - Quantificar pixels referentes a plantio de soja (código 39).
   - Quantificar pixels referentes a pastagem (código 15).

2. **Calcular áreas a partir dos pixels**:  
   Após identificar a proporção de pixels correspondentes a cada categoria (soja e pastagem) em relação à área útil (total de pixels subtraindo os sem dados), calcula-se a área real em hectares. Para isso, utiliza-se a área total do Brasil em hectares (valor obtido junto ao IBGE) e aplica-se a proporção dos pixels sobre a área total, resultando na área ocupada por soja e pastagem em hectares.

### Dados Utilizados

- **Imagem de Satélite**:  
  A imagem utilizada no projeto é acessível por meio do link: [Imagem de Uso e Cobertura do Brasil](https://drive.google.com/file/d/1BrtGByxXu5xqBGOvSBmPWkb_YGZagHav/view?usp=sharing).

- **Códigos de Uso e Cobertura**:  
  - 0: Pixels sem dados
  - 15: Pixels com cobertura de pastagem
  - 39: Pixels com cobertura de plantio de soja

- **Área do Brasil**:  
  Dados do IBGE: Área do Brasil em hectares: 851.576.742 ha (valor exemplo fornecido).

### Metodologia

1. **Leitura da Imagem**:  
   O código utiliza a biblioteca Pillow (PIL) para carregar e processar a imagem. A imagem é convertida para um array NumPy, facilitando a contagem de pixels por valor.

2. **Contagem de Pixels por Código**:  
   Por meio do NumPy, conta-se quantos pixels possuem o código 0, 15 e 39.

3. **Cálculo de Percentuais e Áreas**:  
   A partir do total de pixels e do número de pixels sem dados, obtém-se o número de pixels com dados válidos (pixels úteis). Em seguida, calcula-se a fração de pixels de soja e pastagem em relação a esses pixels úteis.  
   Multiplicando as frações pelo valor total da área do Brasil (851.576.742 ha), obtém-se a área equivalente a essas classes de uso do solo em hectares.

### Resultado Esperado

O código retornará no terminal:

- Quantidade total de pixels da imagem.
- Quantidade de pixels sem dados (0).
- Quantidade de pixels para soja (39).
- Quantidade de pixels para pastagem (15).
- A área de plantio de soja em hectares e sua contagem de pixels.
- A área de cobertura de pastagem em hectares e sua contagem de pixels.

### Ferramentas Utilizadas

- Python 3.x
- Bibliotecas:  
  - `Pillow (PIL)` para tratamento da imagem
  - `NumPy` para manipulação de arrays
  - `gdown` para download da imagem de exemplo

### Instruções de Execução

1. Certifique-se de ter o Python 3 instalado.
2. Instale as dependências:  
   ```bash
   pip install gdown pillow numpy
   ```
3. Baixe a imagem (opcional, o código já faz o download automaticamente se o link estiver configurado).
4. Execute o código Python:  
   ```bash
   python script.py
   ```
   
   (Substitua `script.py` pelo nome do arquivo que contém o código.)

### Equipe

- **Alunos**:  
  - Edwin Nichollas Rocha Medina
  - João Victor Guimarães Santos
  - João Vitor Luiz Soares Silva
  - João Marcus Fleury Siqueira

- **Disciplina**:  
  - Processamento Digital

- **Docente Responsável**:  
  - Fabio Botelho
