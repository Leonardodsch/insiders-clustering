Link para o notebook através do nbviewer (Recomendado para uma melhor visualização): 

[![image](https://img.shields.io/badge/Jupyter-F37626.svg?&style=for-the-badge&logo=Jupyter&logoColor=white)](https://nbviewer.org/github/Leonardodsch/insiders-clustering/blob/main/notebooks/c09_insiders_clustering-model-results.ipynb)

# Insiders Clustering

Disclaimer: O Contexto a seguir, é completamente fictício, a empresa, o contexto, as perguntas de negócio foram criadas apenas para o desenvolvimento do projeto, e se baseiam em um projeto do site https://sejaumdatascientist.com/.

<p align="center">
  <img width="900" height="450" src="https://sejaumdatascientist.com/wp-content/uploads/2021/03/premium.png"/>
</p>


## Contexto de negócio

A empresa All in One Place é uma empresa Outlet Multimarcas, ou seja, ela comercializa produtos de segunda linha de várias marcas a um preço menor, através de um e-commerce.

Em pouco mais de 1 anos de operação, o time de marketing percebeu que alguns clientes da sua base, compram produtos mais caros, com alta frequência e acabam contribuindo com uma parcela significativa do faturamento da empresa.

Baseado nessa percepção, o time de marketing vai lançar um programa de fidelidade para os melhores clientes da base, chamado Insiders. Mas o time não tem um conhecimento avançado em análise de dados para eleger os participantes do programa.

Por esse motivo, o time de marketing requisitou ao time de dados uma seleção de clientes elegíveis ao programa, usando técnicas avançadas de manipulação de dados.

## O Desafio

Você faz parte do time de cientistas de dados da empresa All In One Place, que precisa determinar quem são os clientes elegíveis para participar do Insiders. Em posse dessa lista, o time de Marketing fará uma sequência de ações personalizadas e exclusivas ao grupo, de modo a aumentar o faturamento e a frequência de compra.

Como resultado para esse projeto, é esperado que você entregue uma lista de pessoas elegíveis a participar do programa Insiders, junto com um relatório respondendo às seguintes perguntas:

1. Quem são as pessoas elegíveis para participar do programa de Insiders ?
2. Quantos clientes farão parte do grupo?
3. Quais as principais características desses clientes ?
4. Qual a porcentagem de contribuição do faturamento, vinda do Insiders ?
5. Qual a expectativa de faturamento desse grupo para os próximos meses ?
6. Quais as condições para uma pessoa ser elegível ao Insiders ?
7. Quais as condições para uma pessoa ser removida do Insiders ?
8. Qual a garantia que o programa Insiders é melhor que o restante da base ?
9. Quais ações o time de marketing pode realizar para aumentar o faturamento?

## Dados

O conjunto de dados está disponível na plataforma do Kaggle, através desse link: https://www.kaggle.com/vik2012kvs/high-value-customers-identification 

Cada linha representa uma transação de venda, que ocorreu entre o período de Novembro de 2016 e Dezembro de 2017.

O conjunto de dados inclui as seguintes informações:

- Invoice Number: identificador único de cada transação.
- Stock Code Product: código do item.
- Description Product: nome do item
- Quantity: A quantidade de cada item comprado por transação.
- Invoice Date: O dia em que a transação ocorreu
- Unit Price: Preço do produto por unidade
- Customer ID: identificador único do cliente
- Country: O nome do país que o cliente reside

## Planejamento da solução

**1. Entendimento do negócio e problemas e serem resolvidos** - Buscar entender os reais motivos da necessidade da criação do programa insiders e como o probelma pode ser resolvido através de machine learning, quais aspectos serão considerados na hora da predição e quão melhor a solução proposta pode ser considerando os modelos de predição utilizados atualmente na empresa.    

**2. Coleta de dados** - Acesso a plataforma do Kaggle para download dos arquivos que serão usados.

**3. Limpeza dos dados** - Os dados são analisados usando diferentes técnicas para verificar a existência de dados faltantes, outliers (valor discrepantes) , ou qualquer tipo de inconsistências para que assim possam ser tratados devidamente e não impactar nas análises futuras. 

**4. Exploração dos dados** - Busca um melhor entendimento do negócio através da geração de insights e das variáveis mais importantes na modelagem do modelo de Machine Learning. Diversas hipóteses foram levantadas e validadas para obtenção de um conhecimento de negócio mais profundo, verificando também a correlação entre os atributos para que se possa ter uma ideia da importância de cada um para o modelo de machine learning. 

**5. Preparação dos dados** - Os dados foram transformados, balanceados e regularizados para que atendam as premissas de funcionamento dos algoritmos de machine learning, nesta etapa é importante deixar os dados preparados para que os algoritmos possam ter o melhor desempenho possível, e possíveis inconsistencias no dataset não interfiram no resultado final.

**6. Seleção de features** - Após a preparação dos dados, nesta seção as melhores features para o modelo serão selecionadas. Elas serão analisadas e selecionadas de acordo com descobertas feitas na análise exploratória e levando em conta o contexto de nagócio.

**7. Aplicação dos algoritmos de machine learning** - Nesta etapa foram escolhidos os algoritmos de machine learning que seriam usados e então os mesmos foram treinados com os dados já preparados e prontos, cada algoritmo foi testado usando seus devidos parâmetros, bem como tecnicas de hyperparameter fine tunning para encontrar os melhores parâmetros para o modelo escolhido. 

**8. Avaliação do algoritmo** - O algoritmo e os clusters criados são avaliados com base em algumas métricas e nesse ponto verifica-se ou não a necessidade de realizar mais um ciclo para melhorar o desempenho final.

**9. Utilização do cluster final para responder as perguntas de negócio** - Com o melhor modelo escolhido e o cluster final montado é possível atacar o probelma inicial e responder as perguntas de negócio a partir de um entendimento melhor dos dados e de como o modelo irá impactar no negócio. 

**10. Deploy do modelo em produção** - O modelo foi colocado em produção no ambiente cloud AWS para que execute de tempos em tempos e assim possa gerar uma nova clusterização de clientes e esses resultados possam ser acessados através de ferramentas de visulização como o Metabase ou PowerBI

O projeto utiliza a metodologia CRISP-DM, que consiste desenvolver o projeto de forma ciclica entendendo todos os passos do projeto e buscando entregar valor ao negócio o mais rápido possível e aperfeiçoar a solução a cada ciclo.

<p align="center">
  <img width="500" height="400" src="https://user-images.githubusercontent.com/76128123/129281894-1a9389f5-e953-4c7d-ad6a-cadbc62e9abc.png"/>
</p>

## Melhores Insights

- **735 pessoas farão parte do grupo Insiders**
- **Principais caracteristicas desse grupo:**
  - Número de customers: 735 (13% do customers )
  - Faturamento médio: $5621
  - Recência média: 8 dias
  - Média de Produtos comprados: 232 produtos
  - Frequência de Produtos comprados: 0.438 produtos/dia
- **A porcentagem de contribuição do faturamento vinda do grupo Insiders é de 40,98%**


## Machine Learning Models

Os algoritmos utilizados para fazer a clusterização foram:
- KMeans;
- GMM (Gaussian Mixture Model);
- Hierarchical Clustering;
- DBScan.

Após a realização de diversos testes com os modelos verificou-se um melhor desempenho do KMeans e Hierarchical Clustering, ambos possuem funcionamento parecido então um resultado próximo entre eles já era esperado. A métrica escolhida para medir o desempenho foi a **Silhouette Score**, que é calculado usando a distância média intra-cluster e a distância média mais próxima do cluster para cada amostra. O valor da métrica pode variar de -1 até 1, com 1 sendo o melhor resultado possível e valores negativos podendo indicar que o modelo classificou os dados no cluster errado. Sendo assim, os resultados encontrados foram os seguintes:

![image](https://user-images.githubusercontent.com/76128123/138116375-4fbbb904-ac93-4fe7-b22d-ccd88de1c7dc.png)

A tabela acima mostra o número de clusters testados e o desempenho dos modelos utilizando a métrica da Silhouette para cada número de clusters. Percebe-se que o melhor resultado é encontrado quando um número de clusters igual a 18 é testado, porém optou-se por escolher o número de 9 clusters para o modelo final pois também possui um resultado rezoavelmente bom. 

Essa escolha se deu pelo fato de 18 clusters ser um número grande para ser analisado mais cuidadosamente e poderia dificultar o time de negócios na tomada de decisão, fazendo com que fosse mais trabalhoso acompanhar todos eles, então de forma a simplificar questões de negócio/marketing o numero de clusters igual a 9 foi considerado mais adequado para a situação. 

## Resultados

Como resultado foi possível obter um modelo que faz o agrupamento dos clientes e torna possível gerenciar e colocar em prática diversas alavancas de negócio, como campanhas de marketing especificas para cada grupo, programa de fidelidade com brindes e promoções, incentivos para outros clientes se tornarem Insiders, calcular expectativa de faturamento do grupo Insiders para semanas futuras, entre outros. Os resultados podem ser acompanhados diretamente em ferramentas de visualização, facilitando e deixando a tomada de decisão mais rápida e assertiva.

## Conclusão
