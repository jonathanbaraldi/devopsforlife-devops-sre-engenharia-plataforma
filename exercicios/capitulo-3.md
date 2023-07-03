# Capítulo 3: Infraestrutura como Código (IaC) e Gerenciamento de Configuração

## Aula 7: Introdução à Infraestrutura como Código (IaC)

Exercícios práticos:

- Comece a explorar uma ferramenta de IaC como CloudFormation ou Ansible. Acostume-se com a interface e os conceitos básicos.

- Pesquise e discuta os benefícios da IaC. Como isso pode ajudar as empresas a melhorar a eficiência e a confiabilidade?

- Examine um exemplo de script de IaC (pode ser um arquivo de configuração do 
CloudFormation ou playbook do Ansible) e discuta o que ele está configurando.

**Dicas:**
A infraestrutura como código pode ajudar a minimizar o erro humano na configuração de sistemas.

A IaC também facilita a escalabilidade, pois as novas instâncias podem ser facilmente configuradas com os mesmos parâmetros.


## Aula 8: CloudFormation: Provisionamento e Gerenciamento de Infraestrutura

Exercícios práticos:

- Familiarize-se com o AWS Management Console e encontre o CloudFormation.
- Crie uma pilha CloudFormation simples, como um Amazon S3 bucket, usando um modelo de exemplo do AWS.
- Verifique a criação do recurso no AWS Management Console.

```yaml

AWSTemplateFormatVersion: "2010-09-09"
Description: Simple cloud formation for bucket creation and configuration

Parameters:
  BucketName: { Type: String, Default: "devopsforlife-demo-iac" }

Resources:  
  AccessLogBucket:
    Type: "AWS::S3::Bucket"
    Properties:
      AccessControl: LogDeliveryWrite
            
  MainBucket:
    Type: "AWS::S3::Bucket"
    Properties:
      BucketName: !Ref BucketName
      BucketEncryption:
        ServerSideEncryptionConfiguration:
          - ServerSideEncryptionByDefault:
              SSEAlgorithm: AES256
      LoggingConfiguration:
        DestinationBucketName: !Ref AccessLogBucket


Outputs:
  MainBucketName:
    Description: Name of the main bucket
    Value: !Ref MainBucket
  LogBucketName:
    Description: Name of the access log bucket
    Value: !Ref AccessLogBucket

```



## Aula 9: Gerenciamento de Configuração com Ansible
- Como usar o Ansible para gerenciar a configuração de servidores e aplicativos.

### Objetivos da Aula:

- Entender o que é Ansible e como ele desempenha um papel crucial no gerenciamento de configuração.
- Aprender a usar o Ansible para gerenciar a configuração de servidores e aplicativos.

### Introdução ao Ansible

- O Ansible é uma ferramenta de gerenciamento de configuração de código aberto.
- Ele usa o formato YAML, que é fácil de ler e escrever, para definir configurações de servidores e aplicativos.
- O Ansible é baseado em um modelo "push", onde as configurações são enviadas dos sistemas de controle para os nós de destino.
- Ele utiliza SSH para a comunicação, o que significa que não requer um agente especial rodando no nó de destino.

### Conceitos Principais do Ansible

- Inventário: A lista de nós que serão gerenciados pelo Ansible. Este inventário pode ser estático (um arquivo) ou dinâmico (um script).
- Playbooks: Estes são os scripts do Ansible, escritos em YAML. Eles definem uma série de "plays" a serem executadas nos nós do inventário.
- Tasks (Tarefas): São as unidades individuais de trabalho, tais como instalar um pacote ou iniciar um serviço.
- Roles (Funções): São maneiras de organizar tarefas e recursos relacionados, para facilitar a reutilização e compartilhamento.

### Exemplo Prático: Usando Ansible para Configurar um Servidor Web em uma Instância EC2

Nesta seção, vamos criar um servidor web básico usando o Ansible para configurar uma instância Amazon EC2.

Configuração Inicial

1. Instalação do Ansible: Instale o Ansible em sua máquina local. Dependendo do seu sistema operacional, isso pode ser feito com um gerenciador de pacotes como apt ou yum, ou com pip, o gerenciador de pacotes Python.

2. Definindo o Inventário: Defina o inventário, incluindo o endereço IP da instância EC2. Esta informação deve ser colocada em um arquivo de inventário, que é um arquivo de texto simples.

3. Teste de Conexão: Teste a conexão SSH com a instância EC2 usando o comando ansible all -m ping. Isso deve retornar um resultado positivo, indicando que o Ansible pode se comunicar com a instância EC2.

### Criando o Playbook do Ansible

1. Definição do Playbook: Crie um novo playbook chamado webserver.yml. Este playbook definirá as tarefas que o Ansible deve executar na instância EC2.

2. Instalação do Docker: Adicione uma tarefa para instalar o Docker na instância EC2. O Ansible tem um módulo chamado apt que pode ser usado para instalar pacotes no Ubuntu.

3. Download da Imagem do Servidor Web: Adicione uma tarefa para baixar a imagem do servidor web. Neste caso, vamos usar o nginx. O Ansible tem um módulo chamado docker_image que pode ser usado para isso.

4. Inicialização do Contêiner Docker: Adicione uma tarefa para iniciar o contêiner Docker com a imagem baixada. O Ansible tem um módulo chamado docker_container para isso.

### Executando o Playbook

1. Execução do Playbook: Execute o playbook com o comando ansible-playbook webserver.yml. Isso fará com que o Ansible execute todas as tarefas definidas no playbook na instância EC2.

2. Verificação: Verifique se o contêiner Docker está rodando na instância EC2. Você pode fazer isso com o comando docker ps na instância EC2.

### Conclusão

O Ansible é uma ferramenta poderosa e flexível para o gerenciamento de configuração. Ele pode simplificar e automatizar muitas das tarefas comuns de administração de sistemas, tornando a vida dos profissionais de DevOps muito mais fácil.

