# Questão 1 – Ray Tracing

## Prompt Utilizado
Como o algoritmo de Ray Tracing calcula a cor de um pixel em uma imagem renderizada?

## Técnica Usada
**Zero-Shot Prompting**

## IA Utilizada
  <img align="inline_block" alt="chat gpt" src="https://img.shields.io/badge/chatGPT-74aa9c?style=for-the-badge&logo=openai&logoColor=white"/>

## Justificativa
Optou-se pela técnica de Zero-Shot, pois a pergunta é objetiva, clara e o tema (Ray Tracing) é amplamente documentado. A IA é capaz de gerar uma resposta completa com base no seu conhecimento prévio, sem necessidade de exemplos.

## Resposta da IA

    O algoritmo de Ray Tracing calcula a cor de um pixel simulando o caminho que um raio de luz percorre a partir da câmera até os objetos na cena. O processo segue os seguintes passos:

    Geração de Raios: Para cada pixel da imagem, é disparado um raio a partir da câmera.

    Interseção: O algoritmo calcula se esse raio colide com algum objeto na cena.

    Cálculo de Iluminação: Se houver interseção, o algoritmo calcula como a luz (direta e indireta) incide sobre o ponto de colisão.

    Sombreamento e Reflexões: São aplicados efeitos como sombras, reflexos, refrações e transparências. Para isso, novos raios secundários podem ser disparados.

    Cor Final: A cor resultante é determinada combinando os efeitos de luz, materiais e reflexos, e atribuída ao pixel correspondente na imagem final.

## Avaliação

A resposta da IA foi clara, objetiva e tecnicamente correta. A técnica de Zero-Shot foi eficaz para esta questão, pois forneceu uma explicação concisa e didática sem necessidade de ajustes ou reenvio do prompt.