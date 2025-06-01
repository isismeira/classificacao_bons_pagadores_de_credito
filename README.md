# Modelo classificador de potenciais bons pagadores de crédito: um comparativo entre Naive Bayes, Máquinas de Vetores de Suporte, Árvores de Decisão e Florestas Aleatórias

## Descrição do Projeto

Este projeto tem como objetivo desenvolver e comparar modelos de Machine Learning para classificar potenciais clientes de crédito como "bons pagadores" ou "maus pagadores". A análise é realizada com base em um conjunto de dados de clientes de um banco alemão, explorando diferentes algoritmos de classificação: Naive Bayes, Máquinas de Vetores de Suporte (SVM), Árvores de Decisão e Florestas Aleatórias (Random Forests). O projeto inclui etapas de análise exploratória, pré-processamento de dados, treinamento e avaliação dos modelos, além da aplicação de um dos modelos treinados para prever a classificação de um novo cliente.

## Objetivo

O principal objetivo é criar um modelo preditivo que, a partir de características específicas de um novo cliente, possa indicar sua propensão a ser um bom pagador de crédito. Além disso, o projeto busca comparar a performance de diferentes algoritmos de classificação para identificar qual deles apresenta os melhores resultados para este problema.

## Dataset

O dataset utilizado neste projeto contém dados de vários clientes de um banco alemão que solicitaram crédito. Cada cliente é descrito por um conjunto de características e, por fim, classificado como bom ou mau pagador de crédito. O dataset original (`Credit.csv`) possui 1000 instâncias e 21 atributos. Um arquivo adicional (`NovoCliente.csv`) contendo os dados de um único novo cliente (sem a classe de pagamento) é utilizado para demonstração de previsão.

## Tecnologias e Bibliotecas Utilizadas

*   **Python:** Linguagem de programação principal.
*   **Pandas:** Para manipulação e análise de dados.
*   **Scikit-learn:** Biblioteca para Machine Learning, incluindo:
    *   `train_test_split`: Para dividir o dataset em conjuntos de treino e teste.
    *   `GaussianNB`: Implementação do classificador Naive Bayes Gaussiano.
    *   `DecisionTreeClassifier`: Implementação da Árvore de Decisão.
    *   `export_graphviz`: Para exportar a estrutura da Árvore de Decisão.
    *   `SVC`: Implementação da Máquina de Vetor de Suporte.
    *   `ExtraTreesClassifier`: Para seleção de atributos (embora não totalmente implementado no snippet fornecido, a importação indica a intenção).
    *   `RandomForestClassifier`: Implementação da Floresta Aleatória.
    *   `LabelEncoder`: Para converter atributos categóricos em valores numéricos.
    *   `confusion_matrix`: Para gerar a matriz de confusão.
    *   `accuracy_score`: Para calcular a acurácia do modelo.
*   **Graphviz:** Para visualização gráfica da Árvore de Decisão.
*   **Yellowbrick:** Para visualização gráfica da matriz de confusão.

## Estrutura do Código

O código está organizado nas seguintes seções:

1.  **Importações das bibliotecas necessárias:** Carrega todas as bibliotecas a serem utilizadas.
2.  **Análise e tratamento de dados:**
    *   **Conhecendo o dataset:** Carrega o dataset e exibe suas dimensões e as primeiras linhas.
    *   **Transformação de atributos:** Converte atributos categóricos em numéricos utilizando `LabelEncoder`. É crucial notar que objetos `LabelEncoder` separados são criados para cada coluna categórica para garantir a consistência ao transformar novos dados.
    *   **Divisão entre treino e teste:** Divide o dataset em conjuntos para treinamento (70%) e teste (30%).
3.  **Classificação com Naive Bayes:**
    *   **Treinamento e acurácia do modelo:** Treina o modelo Naive Bayes e realiza previsões no conjunto de teste. Calcula e exibe a matriz de confusão.
    *   **Como o modelo classificaria um novo cliente?:** Carrega dados de um novo cliente, aplica as mesmas transformações de atributos do dataset de treinamento e utiliza o modelo Naive Bayes treinado para prever a classificação.
4.  **Classificação com Árvores de Decisão:**
    *   **Treinamento e acurácia do modelo:** Treina o modelo Árvore de Decisão.
    *   Gera um arquivo `.dot` para visualização da árvore completa (com sugestão de ferramenta online para visualização).

## Como Executar o Projeto

1.  Certifique-se de ter o Python instalado em seu ambiente.
2.  Instale as bibliotecas necessárias:
   `bash pip install pandas scikit-learn yellowbrick graphviz`
(Talvez seja necessário instalar o executável do Graphviz separadamente dependendo do seu sistema operacional. Consulte a documentação oficial do Graphviz para instruções detalhadas.)
3.  Baixe o arquivo do notebook (`.ipynb`).
4.  Certifique-se de que os arquivos `Credit.csv` e `NovoCliente.csv` estejam no mesmo diretório do notebook, ou ajuste os caminhos de leitura dos arquivos no código.
5.  Execute o notebook em um ambiente compatível, como Google Colab ou Jupyter Notebook. As células de código podem ser executadas sequencialmente para reproduzir a análise.
