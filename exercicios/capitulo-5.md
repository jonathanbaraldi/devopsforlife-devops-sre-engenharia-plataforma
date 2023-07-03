# Capítulo 5: Containers e Orquestração

## Aula 13: Introdução ao Docker: Conceitos Básicos de Containerização


Objetivos da Aula:

- Compreender o que é Docker e a importância da containerização.
- Aprender a criar e gerenciar containers Docker.

### Introdução ao Docker

- Docker é uma plataforma open-source que permite desenvolver, empacotar e executar aplicações dentro de containers.

- Um container Docker é um pacote independente que contém tudo o que uma aplicação precisa para ser executada: código, bibliotecas, variáveis de ambiente e arquivos de configuração.

- Os containers Docker são leves e portáveis. Eles podem ser executados em qualquer máquina que tenha Docker instalado, independentemente do sistema operacional.

### Conceitos Básicos do Docker

- Imagem Docker: Uma imagem Docker é um modelo read-only usado para criar containers. Uma imagem inclui tudo o que um aplicativo precisa para ser executado.

- Container Docker: Um container é uma instância em execução de uma imagem Docker. Você pode criar, iniciar, parar, mover ou excluir um container usando o Docker API ou CLI.

- Dockerfile: Um Dockerfile é um script que contém uma série de instruções para criar uma imagem Docker.

- Docker Compose: Docker Compose é uma ferramenta para definir e gerenciar aplicações multi-container com Docker. Ele usa arquivos YAML para configurar os serviços da aplicação.

### Exemplo Prático: Criando e Gerenciando Containers Docker

Nesta seção, vamos usar o Docker para criar um servidor web simples.

### Configuração Inicial
- Instalação do Docker: Instale o Docker em sua máquina local. A instalação varia dependendo do sistema operacional.

### Criando um Dockerfile

1. Crie um Dockerfile: O Dockerfile define o que vai dentro do seu container. Aqui está um exemplo básico para um servidor web Nginx.

```sh
# Use a imagem oficial do Nginx
FROM nginx

# Copie o arquivo de configuração do Nginx
COPY nginx.conf /etc/nginx/nginx.conf
```

Construindo a Imagem Docker

1. Construa a Imagem Docker: Use o comando docker build para construir sua imagem Docker.
bash
```sh
docker build -t my-nginx-image .
```

Criando e Gerenciando Containers Docker

1. Crie um Container Docker: Use o comando docker run para criar um novo container a partir da 
imagem do Nginx que você acabou de construir.
```sh
docker run --name my-nginx-container -d -p 8080:80 my-nginx-image
```

2. Gerencie seus Containers Docker: Use os comandos docker ps, docker stop, e docker start para ver, parar e iniciar seus containers, respectivamente.

### Conclusão

Docker é uma ferramenta poderosa para a criação e gerenciamento de containers, permitindo que os desenvolvedores criem aplicações portáteis e consistentes. Conhecê-lo é fundamental para qualquer desenvolvedor ou profissional de DevOps.


## Aula 14:  Docker Compose: Aplicações Multi-Container
    Descrição: Como usar o Docker Compose para gerenciar aplicações multi-container.


## Aula 15: Kubernetes: Introdução e Arquitetura
    Descrição: Conceitos básicos do Kubernetes e sua arquitetura subjacente.


## Aula 16: Kubernetes: Implantação e Gerenciamento de Aplicações
    Descrição: Como implantar e gerenciar aplicativos no Kubernetes, incluindo configuração e ajuste de recursos.



