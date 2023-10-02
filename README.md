## Introdução
Em soluções de sistemas conversacionais inteligentes, é importante que o sistema tenha capacidade de aprender continuamente, permitindo que os usuários tenham sempre informações atualizadas e que agreguem valor para eles, principalmente na velocidade em que as informações mudam nos dias de hoje.

## Solução Proposta
Um sistema de coleta e atualização de dados capaz de identificar quando uma busca validada no sistema conversacional não teve uma resposta adequada com base na coleta feita previamente, utilizando como base o Concept Drift. Esse sistema será responsável por identificar as necessidades de atualização dos dados e rodar um pipeline de coleta de novos dados utilizando de estratégias de web scraping.

## Fluxo da solução
![image](https://github.com/FelipeSaadi/ponderada-aprendizado-continuo/assets/54749257/03c9b48d-5cff-4cb1-90ab-c9935e76c69c)

###  Evento de falta de respostas
Evento acionado diariamente pelo backend da solução, responsável por enviar todas as palavras chaves que não houveram respostas relevantes no dia ou que não tem respostas atualizadas a muito tempo, para o orquestrador de coleta de novos dados.

### Orquestrador de coleta dados
Uma fila de execução responsável por orquestrar as coletas de dados do sistema, invoca a API de Web Scraping e encaminha os documentos recebidos para a API de NLP.

### Web Scraping
Sistema responsável por coletar novos dados e sites selecionados previamente (whitelist), ao receber novos textos, trata-os e os encaminha de volta para o osquestrador de coleta.

### Sistema de NLP
Sistema responsável por tratar os documentos e atualizar o banco de dados com eles, as palavras chaves são utilizadas para classificar os documentos.

### Banco de dados
Responsável por armazenar todos os documentos coletados, utilizado posteriormente pelo backend para treinar o modelo e para aperfeiçoar o sistema conversacional.


## Conclusão
Com esse sistema de aprendizado contínuo somos capazes de aperfeiçoar a interação do usuário com o sistema conversacional, de forma que o modelo é atualizado conforme os usuários fazem perguntas, de acordo com o avanço dos dados disponibilizados digitalmente.
Todo dia que um usuário faz uma pergunta que não há respostas, o sistema é capaz de salvar essa informação e posteriormente buscar novos dados, além disso, o sistema é capaz de identificar os dados que estão desatualizados a muitos dias, criando assim uma base de dados ainda mais robusta e atualizada. Nota-se que essa solução é capaz resolver o principal problema de sistemas conversacionais dos dias de hoje: a falta de informações atualizadas e relevantes para os usuários ao longo do tempo.
