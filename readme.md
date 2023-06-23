<!-- antes de enviar a versão final, solicitamos que todos os comentários, colocados para orientação ao aluno, sejam removidos do arquivo -->
# Previsão de Séries Temporais de Vendas no Varejo usando Random Forest e RNN: Um Estudo de Caso

#### Aluno: [Mariana Coy](https://github.com/marianacoy)
#### Orientadora: [Manoela Kohler](https://github.com/manoelakohler).

---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

<!-- para os links a seguir, caso os arquivos estejam no mesmo repositório que este README, não há necessidade de incluir o link completo: basta incluir o nome do arquivo, com extensão, que o GitHub completa o link corretamente -->
- [Link para o código](https://github.com/link_do_repositorio). <!-- caso não aplicável, remover esta linha -->

---

### Resumo

Este estudo realiza uma análise comparativa de diferentes abordagens para a previsão de vendas no varejo. Utilizando uma base de dados de vendas de uma categoria específica de produtos em um varejista, exploramos técnicas como a Random Forest e Redes Neurais Recorrentes (RNN) para melhorar a precisão das previsões.
Ao longo da análise, exploramos diferentes técnicas e estratégias para melhorar a precisão das previsões. Consideramos diferentes janelamentos de dados, incluindo informações do mês do ano anterior, e tratamos os dados referentes ao período impactado pela pandemia de COVID-19.
Por meio de experimentos, ajustes de parâmetros e comparações entre os modelos, obtivemos melhorias progressivas nos resultados de previsão de vendas. Essas descobertas têm implicações importantes para varejistas, pois podem ajudar a otimizar o planejamento e a tomada de decisões relacionadas à gestão de estoque, promoções e estratégias de vendas.


### 1. Introdução

A previsão de vendas no varejo desempenha um papel fundamental na tomada de decisões estratégicas, planejamento de demanda e otimização de estoques. A capacidade de antecipar com precisão a demanda futura permite que os varejistas ajustem seus recursos, estoques e estratégias de marketing de maneira eficaz, visando atender às necessidades dos clientes e maximizar os lucros. Com o objetivo de melhorar a precisão das previsões de vendas no varejo, este estudo realiza uma análise comparativa de diferentes abordagens e técnicas.
Utilizando uma base de dados abrangente de vendas de uma categoria específica de produtos em um varejista, com início a partir de 2015, exploramos duas técnicas de modelagem. 
Iniciamos a análise com a Random Forest, um modelo de aprendizado de máquina amplamente utilizado pois combina a força de várias árvores de decisão para realizar previsões mais precisas. Ele é capaz de capturar relações não lineares entre as variáveis e lidar com características complexas dos dados, como sazonalidade e tendências.
Também exploramos o uso de Redes Neurais Recorrentes (RNN), um tipo de modelo de aprendizado profundo que têm se mostrado eficazes na modelagem de sequências temporais, devido à sua capacidade de capturar dependências temporais de longo prazo. As RNNs são compostas por neurônios recorrentes que possuem uma conexão de retroalimentação, permitindo que a informação seja propagada ao longo do tempo. Essa arquitetura é adequada para lidar com a natureza sequencial dos dados de vendas no varejo.


### 2. Modelagem

Iniciamos a modelagem utilizando a técnica Random Forest. Implementamos diferentes configurações, explorando o impacto do janelamento de dados de 12 meses versus janelamento de 3 meses adicionando o mesmo mês do ano anterior como uma variável adicional, buscando capturar padrões sazonais e tendências recorrentes.
Reconhecendo o impacto significativo da pandemia de COVID-19 nas vendas do varejo, adotamos estratégias especiais para tratar esse período desafiador. Utilizamos técnicas de normalização baseadas na média do valor do mesmo mês do ano anterior e do mesmo mês do ano seguinte. Essa abordagem permitiu atenuar os efeitos negativos da pandemia nos dados e fornecer uma base de comparação mais consistente para a modelagem.
Por fim, ainda na modelagem usando Random Forest, realizamos a otimização dos parâmetros do modelo, como o número de estimadores (n_estimators), a quantidade mínima de amostras necessárias para dividir um nó interno (min_samples_split) e a profundidade máxima da árvore (max_depth). Através desse processo, buscamos maximizar a precisão das previsões e evitar problemas de overfitting ou underfitting.
Além da Random Forest, também exploramos o uso de Redes Neurais Recorrentes (RNN). Utilizamos o mesmo janelamento de dados de três meses anteriores e, adicionalmente, incorporamos o mês do ano anterior como uma entrada adicional para capturar sazonalidades.
Realizamos ajustes nos parâmetros da rede neural, como o número de unidades (neurônios) na primeira camada Dense, a quantidade de épocas e o batch size. Esses ajustes nos permitiram encontrar uma configuração que melhor se adapta ao nosso conjunto de dados e maximiza a precisão das previsões.
Ao longo do estudo das duas abordagens, realizamos ajustes de parâmetros, comparações e avaliações de desempenho, utilizando métricas como o Erro Médio Percentual Absoluto (MAPE) e o coeficiente de determinação (R²). Além disso, considerando o impacto da pandemia de COVID-19, implementamos estratégias de tratamento especial para o período afetado, a fim de garantir uma análise mais precisa.

### 3. Resultados

1) Random Forest com janelamento de 12 meses: MAPE: 20,7% e R²: 0,66
2) Random Forest com janelamento de 3 meses + mês do ano anterior: MAPE: 14,9% e R²: 0,75
3) Random Forest com janelamento de 3 meses + mês do ano anterior + tratamento de dados para o período forte do COVID-19: MAPE: 10,7% e R²: 0,88
4) Random Forest com janelamento de 3 meses + mês do ano anterior + tratamento de dados para o COVID-19 + ajuste de parâmetros: MAPE: 9,7% e R²: 0,90
5) RNN com janelamento de 3 meses + mês do ano anterior + tratamento de dados para o COVID-19: MAPE: 10,1% e R²: 0,89
6) RNN com janelamento de 3 meses + mês do ano anterior + tratamento de dados para o COVID-19 + ajuste de parâmetros da primeira camada Dense: MAPE: 7,4% e R²: 0,93

### 4. Conclusões

Neste estudo, exploramos diferentes abordagens de modelagem para previsão de vendas no varejo, utilizando dados de uma categoria específica de produtos de um varejista. Através da aplicação de Random Forest e Redes Neurais Recorrentes (RNN), investigamos a influência do janelamento de dados, o tratamento dos dados do período de COVID-19 e ajuste de parâmetros.
Nossos resultados indicam que a redução do janelamento para 3 meses com a  inclusão do mês do ano anterior como uma variável adicional melhoraram significativamente a precisão das previsões. Essas técnicas permitiram capturar padrões sazonais e tendências temporais, fornecendo informações valiosas para planejamento de demanda e tomada de decisões no varejo.
Além disso, o tratamento especial dos dados do período de COVID-19, por meio da normalização baseada em médias dos valores do mesmo mês do ano anterior e do mesmo mês do ano seguinte, ajudou a mitigar os efeitos negativos da pandemia nas previsões de vendas.
Ao ajustar os parâmetros dos modelos, como o número de estimadores na Random Forest e a configuração da camada Dense na RNN, conseguimos melhorar ainda mais a precisão das previsões. Esses ajustes permitiram que os modelos se adaptassem melhor ao conjunto de dados e capturassem relações mais complexas entre as variáveis.
Nessa análise, pudemos concluir que a melhor opção para esse caso foi usar Redes Neurais Recorrentes, com o set de parâmetros definidos. Ela teve um resultado mais aderente à realidade do que os demais testes de Random Forest.
As descobertas e insights obtidos neste estudo têm o potencial de fornecer orientações valiosas para varejistas, permitindo uma melhor compreensão das tendências de vendas e o desenvolvimento de estratégias mais eficazes. Ao compartilhar esses resultados, esperamos contribuir para o avanço do campo da previsão de vendas no varejo, promovendo uma tomada de decisão mais embasada e um planejamento mais eficiente no setor varejista em constante evolução.
---

Matrícula: 211.101.165

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
