Network Monitoring and Attack Prediction System 🛡️🌐
Este projeto é uma solução integrada para monitoramento de rede, previsão de ataques cibernéticos e coleta de dados em tempo real. Utiliza várias bibliotecas e ferramentas para capturar, analisar e prever possíveis ameaças em um ambiente de rede, garantindo maior segurança e eficiência no monitoramento de sistemas.

🔧 Funcionalidades
1. Monitoramento de Rede 📡
Captura e analisa pacotes de rede em tempo real, identificando potenciais intrusões, como:

Pacotes ICMP grandes (⚠️).

Pacotes TCP em portas não padrão 🔓.

2. Previsão de Ataques 🔮
Utiliza dados históricos de ataques para treinar um modelo ARIMA, que prevê a probabilidade de futuros ataques cibernéticos.

3. Coleta de Dados em Tempo Real ⏱️
Faz requisições a APIs externas para coletar dados em tempo real, que são analisados e registrados para futuras previsões.

4. Métricas de Monitoramento 📊
Expõe métricas personalizadas ao Prometheus (📈), como:

Contadores de requisições HTTP 🔢.

Duração das respostas ⏳. Permite o monitoramento contínuo do sistema.

5. Logging Centralizado 📝
Envia logs detalhados para um servidor Syslog (📡), facilitando o monitoramento centralizado de eventos e possíveis problemas.

🛠️ Tecnologias Utilizadas
Python 🐍: Linguagem principal do projeto.

scapy 🦊: Biblioteca para captura e análise de pacotes de rede.

requests 🌐: Biblioteca para fazer requisições HTTP.

pandas 📊: Biblioteca para manipulação e análise de dados.

prometheus_client 📈: Biblioteca para exposição de métricas ao Prometheus.

statsmodels (ARIMA) 📉: Usado para modelagem e previsão de séries temporais.

Syslog 📜: Para centralização de logs de eventos.

⚙️ Como Funciona
1. Captura de Pacotes 🎯
A função packet_callback utiliza scapy para capturar pacotes de rede. Pacotes ICMP grandes e pacotes TCP com portas não padrão são identificados e registrados nos logs e nas métricas do Prometheus.

2. Coleta de Dados Históricos 📅
A função collect_historical_data faz requisições a uma API para coletar dados históricos de ataques. Esses dados são processados e analisados com a ajuda da biblioteca pandas.

3. Previsão de Ataques 🔮
A função analyze_and_predict utiliza um modelo ARIMA para prever futuros ataques, com base nos dados históricos coletados. Caso a previsão indique um aumento significativo no número de ataques, um alerta é registrado.

4. Monitoramento de APIs Externas 🌍
A função fetch_external_data faz requisições periódicas a uma API externa para coletar dados em tempo real, que são analisados e registrados tanto nos logs quanto nas métricas do Prometheus.

5. Métricas e Logging 🖥️
As métricas são expostas em um servidor Prometheus rodando na porta 8000 📡.

Logs detalhados são enviados a um servidor Syslog para monitoramento centralizado 📜.

⚡ Configuração e Uso
Pré-requisitos 📝
Python 3.x 🐍

Bibliotecas Python:

scapy 🦊

requests 🌐

pandas 📊

prometheus_client 📈

statsmodels 📉

logging 📝

Servidor Syslog para receber os logs 📜.

Servidor Prometheus para coletar as métricas 📡.

Ferramenta de visualização: Grafana 📊 (para visualização de métricas no Prometheus).
