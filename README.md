# Challenge_Sprint3
Integrantes:
Gabriel Ortiz Oliva Gil - RM: 98642 – 2TDSPK
Rafael Noboru Watanabe Nasaha - RM:99948 – 2TDSPK
João Pedro Kraide Máximo - RM:550974 – 2TDSPK
Matheus de Andrade Ferreira - RM:99375 – 2TDSPK
Larissa Pereira Biusse - RM:551062 - 2TDSPK

Challenge Sprint3 IA FUTURE:

Projeto IA Future :

Detalhamento da arquitetura de IA:
 


Etapa 1: Análise Exploratória de Dados com Power BI
Nosso cliente nos fornecerá conjuntos de dados, que serão a base para o desenvolvimento do projeto. A primeira etapa consiste em realizar uma análise detalhada desses dados utilizando o Power BI, uma ferramenta poderosa para visualização e exploração de informações. O objetivo inicial é identificar quais colunas são mais relevantes e fazem sentido em relação à coluna "target", que representa o resultado ou comportamento que queremos prever. Essa análise nos ajudará a entender melhor os dados e a definir os atributos mais significativos para o processo de modelagem.
 

Etapa 2:Construção e Treinamento do Modelo com Azure AutoML
Após a análise exploratória dos dados no Power BI, passamos para a construção do modelo preditivo usando o Azure AutoML. O AutoML (Automated Machine Learning) automatiza o processo de seleção de algoritmos e otimização de hiperparâmetros, tornando o desenvolvimento de modelos de machine learning mais eficiente e acessível.
1. Configuração do Ambiente no Azure Machine Learning
A primeira etapa envolve a configuração do ambiente no Azure ML Studio, que é onde todo o processo de AutoML será gerenciado.
•	Criação do Workspace: O workspace do Azure Machine Learning é o espaço centralizado onde todas as operações relacionadas ao machine learning serão executadas, incluindo a execução de experimentos e o armazenamento dos resultados.
•	Configuração do Compute Target: Para garantir o processamento adequado, configuramos um cluster de computação (Azure ML Compute), que o AutoML usará para testar diversos modelos em paralelo. Dependendo da complexidade dos dados, podemos escalar essa infraestrutura conforme necessário.
2. Pré-processamento Automático dos Dados
O Azure AutoML facilita o pré-processamento dos dados de forma automática. Algumas das etapas que o AutoML gerencia são:
•	Limpeza e preparação dos dados: O AutoML automaticamente detecta e trata valores ausentes, normaliza os dados e executa transformações necessárias (como encoding de variáveis categóricas).
•	Divisão dos dados: Ele divide os dados em treinamento e validação para avaliar o desempenho dos modelos em dados não vistos.
Essa automação agiliza significativamente o processo, garantindo que os dados estejam no formato adequado sem a necessidade de manipulação manual.

3. Execução do Azure AutoML
Com os dados preparados, configuramos o experimento AutoML. Nesta fase, especificamos os seguintes parâmetros:
•	Tipo de Problema: Definimos se o problema é de classificação, regressão ou previsão de séries temporais.
•	Métrica de Avaliação: Escolhemos a métrica que o AutoML usará para selecionar o melhor modelo. Por exemplo, podemos utilizar Acurácia para problemas de classificação ou Erro Quadrático Médio (MSE) para regressão.
•	Limite de Tempo: Estabelecemos um tempo máximo para que o AutoML teste diferentes combinações de algoritmos e hiperparâmetros. O AutoML então começa a experimentar diversas técnicas de aprendizado de máquina, como Random Forests, Gradient Boosting Machines, e Redes Neurais, sem que o desenvolvedor precise selecionar manualmente cada algoritmo.
4. Otimização e Seleção Automática do Modelo
O AutoML não apenas testa diferentes algoritmos, mas também ajusta automaticamente os hiperparâmetros para maximizar o desempenho do modelo. O processo envolve:
•	Teste Automático de Modelos: O AutoML executa vários experimentos em paralelo, treinando diferentes modelos e avaliando seu desempenho em tempo real com base nos dados de validação.
•	Otimização Automática: Ao longo das execuções, o AutoML ajusta os hiperparâmetros para melhorar as métricas de desempenho.
No final desse processo, o Azure AutoML escolhe o modelo com o melhor desempenho com base na métrica de avaliação definida (como acurácia ou erro). Ele também gera um ranking dos modelos testados, para que possamos visualizar como cada um performou.
5. Treinamento do Modelo Selecionado
Com o melhor modelo automaticamente selecionado pelo AutoML, ele é treinado em todo o conjunto de dados. Durante essa fase, o Azure AutoML faz ajustes finais no modelo para garantir que ele esteja bem otimizado.
Além disso, o Azure Machine Learning permite visualizar métricas detalhadas de desempenho do modelo, como confusion matrix, precisão, recall, f1-score para classificação, ou R² e Mean Absolute Error (MAE) para regressão.
6. Implantação do Modelo
Depois de escolhido e treinado o modelo ideal, ele é implantado diretamente no ambiente de produção. A plataforma oferece diversas opções de deploy:
•	Azure Kubernetes Service (AKS): Para implantações em grande escala e de alta disponibilidade.
•	Azure Container Instances (ACI): Para implantações rápidas e leves, geralmente usadas em ambientes de desenvolvimento e teste.
O AutoML facilita a exportação do modelo como uma API REST, que pode ser integrada a aplicativos e sistemas desenvolvidos em Java, C# ou Mobile. Assim, o cliente pode utilizar o modelo preditivo de forma prática e eficiente.
7. Monitoramento e Atualização do Modelo
Depois de implantado, o modelo pode ser monitorado através do Azure Application Insights, que coleta informações sobre a performance do modelo em produção, como tempo de resposta e eventuais falhas.
Além disso, o Azure ML permite monitorar drift de dados, o que ajuda a identificar quando o comportamento dos dados muda ao longo do tempo, impactando a precisão do modelo. Caso necessário, o AutoML pode ser utilizado novamente para re-treinar o modelo com dados atualizados, garantindo que ele continue performando de maneira eficaz.
Esse uso do Azure AutoML torna o processo de desenvolvimento de modelos preditivos muito mais ágil e preciso, automatizando tarefas que geralmente seriam manuais e demoradas. Com o AutoML, garantimos a criação de modelos de alta performance com menos esforço, permitindo um foco maior na análise de resultados e na comunicação com o cliente.
Etapa 3: Visualização de Insights e Previsões em Dashboards Interativos
Com o modelo treinado e pronto, voltaremos ao Power BI para criar um dashboard interativo, onde poderemos apresentar os resultados de forma visual e acessível. Esse dashboard será fundamental para que o cliente tenha um entendimento claro e completo das previsões e insights gerados pelo modelo. A ideia é tornar os dados e as previsões algo intuitivo e útil para a tomada de decisões.

Além disso, para garantir uma comunicação eficiente e contínua das informações, o dashboard será integrado às nossas APIs, que atuarão como um portal de comunicação. Esse portal permitirá que o cliente acesse as informações preditivas e relatórios diretamente, de forma prática e centralizada, seja via APIs Java, C#, ou até mesmo por meio de aplicativos mobile.
Este processo garante uma solução completa, desde a análise inicial dos dados até a criação de um modelo preditivo robusto, finalizando com uma visualização clara e acessível por meio de dashboards e APIs integradas.
