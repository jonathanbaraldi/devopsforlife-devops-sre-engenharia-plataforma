# Capítulo 5: Monitoramento e Registro

## Aula 17: Fundamentos e Melhores Práticas de Monitoramento

Conceitos básicos de monitoramento:

- Definição: Monitoramento de sistemas é a prática de coletar, analisar e usar dados para verificar e garantir a funcionalidade e a performance de aplicações e infraestrutura de TI. É uma estratégia essencial para detectar problemas precocemente, antes que eles afetem a experiência do usuário ou os negócios.

- Importância: O monitoramento é crucial para garantir a disponibilidade, a performance e a segurança dos sistemas e aplicações. Ele permite detectar problemas antes que causem interrupções ou perda de desempenho, além de ajudar na otimização dos recursos de TI.

### Monitoramento ativo x passivo:

- Monitoramento ativo: é uma abordagem em que se realizam checagens regulares nos sistemas para verificar se eles estão funcionando corretamente. Geralmente envolve enviar solicitações ou dados para o sistema e verificar as respostas.

- Monitoramento passivo: é uma abordagem em que se coletam e analisam os dados gerados pelo sistema durante seu funcionamento normal. Por exemplo, registros de logs, tráfego de rede, uso da CPU, entre outros.

### Melhores práticas de monitoramento:

- Abordagem proativa: A abordagem proativa envolve a identificação e resolução de problemas antes que eles causem interrupções ou impactem negativamente a experiência do usuário. Por exemplo, em vez de esperar por um sistema sair do ar, os administradores podem monitorar a utilização de recursos e tomar medidas preventivas quando os limites estiverem sendo alcançados.

- Monitoramento contínuo: O monitoramento contínuo significa que o estado dos sistemas e aplicações está sendo constantemente verificado. Isso permite que problemas sejam identificados e corrigidos o mais rápido possível.

- Definição de métricas relevantes: As métricas relevantes variam dependendo do sistema e do objetivo do negócio. Elas podem incluir métricas de desempenho, como tempo de resposta e utilização de recursos; métricas de negócios, como número de transações ou usuários ativos; e métricas de qualidade, como taxa de erros ou falhas.

- Discussão sobre ferramentas de monitoramento comuns, incluindo Prometheus e Grafana.




## Aula 18: Introdução ao Prometheus: Métricas e Alertas

Definição: Prometheus é um sistema de monitoramento e alerta de código aberto que foi originalmente construído no SoundCloud. Desde sua criação, se tornou uma escolha popular para monitoramento em ambientes de nuvem e microserviços.

Importância: Prometheus fornece uma solução robusta e escalável para coletar e armazenar métricas de tempo de execução de aplicativos e infraestrutura. Isso permite às equipes de DevOps entender melhor o comportamento de seus sistemas, detectar problemas antecipadamente e responder prontamente a qualquer incidente.

### Principais características do Prometheus:

- Modelo de dados multidimensional com séries de tempo identificadas por pares de chave/valor métrico.

- Poderosa linguagem de consulta (PromQL) para exploração de dados.

- Não depende de armazenamento distribuído; os nós do servidor são autônomos.

- Coleta de métricas acontece por meio de um processo de raspagem (scraping) de pontos de exposição HTTP.

- Suporta várias formas de gráficos e painéis, incluindo a integração com o Grafana.

### Configuração do Prometheus para coleta de métricas:

Os alunos aprenderão como instalar o Prometheus, como configurá-lo para coletar métricas dos serviços e como explorar essas métricas usando a linguagem de consulta PromQL. Isso incluirá a definição de "jobs" e "scrape configs" no arquivo de configuração do Prometheus para determinar de onde as métricas são coletadas.

### Criação de alertas usando o Alertmanager:

O Alertmanager lida com alertas enviados pelo servidor Prometheus e é responsável por agrupá-los, silenciá-los, se necessário, e enviar notificações por meio de métodos como e-mail, PagerDuty e OpsGenie. Os alunos aprenderão a configurar e definir regras de alerta no Prometheus e a gerenciar alertas no Alertmanager.

### Exercícios práticos para coleta de métricas e configuração de alertas:

Os alunos terão a oportunidade de aplicar o que aprenderam em um ambiente prático. Isso pode incluir a instalação e configuração do Prometheus em um ambiente de teste, a coleta de métricas de um ou mais serviços, a consulta dessas métricas através da interface de usuário do Prometheus e a configuração de alertas com base em condições definidas.
