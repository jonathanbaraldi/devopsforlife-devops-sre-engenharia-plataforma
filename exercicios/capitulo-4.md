# Capítulo 4: Integração Contínua e Implantação Contínua (CI/CD)

## Aula 10: Conceitos e Melhores Práticas de CI/CD

Exercícios práticos:

- Pesquise e discuta os benefícios da CI/CD. Como ela pode ajudar as empresas a melhorar a eficiência e a confiabilidade?
- Analise um pipeline de CI/CD e discuta os diferentes estágios e o que cada um faz.


### Integração Contínua (CI):

- Integração frequente de código: Os desenvolvedores devem integrar seu código várias vezes ao dia. Isso permite que as equipes detectem erros de integração cedo e os corrijam rapidamente.
- Automatize os testes: Sempre que o código é integrado, ele deve ser automaticamente compilado e testado. Isso ajuda a detectar e corrigir bugs rapidamente, mantendo a qualidade do código.
- Feedback rápido: Se ocorrer um problema durante a integração ou os testes, a equipe deve ser notificada imediatamente para que possa corrigir o problema rapidamente.
- Mantenha um código base limpo: As equipes devem trabalhar em um código base limpo e atualizado. Se uma build falhar, a correção da falha deve ter prioridade sobre outras atividades de desenvolvimento.

### Entrega Contínua (CD):

- Automatize a entrega: A entrega do código aos ambientes de teste e produção deve ser automatizada, reduzindo a chance de erros e acelerando o processo de entrega.
- Ambientes de produção-like: O ambiente de teste deve ser o mais parecido possível com o ambiente de produção para garantir que os testes sejam precisos.
- Implantação baseada em feature toggles: Os feature toggles permitem que você controle quais recursos estão disponíveis para os usuários. Isso permite que você implemente novos recursos em produção, mas os mantenha ocultos até que estejam prontos.
- Monitoramento e registro contínuos: Monitorar o desempenho da aplicação e manter registros detalhados pode ajudar a identificar e resolver problemas rapidamente.

Dicas:

- CI/CD é uma prática de desenvolvimento de software que envolve a integração contínua de mudanças de código e a implantação contínua dessas mudanças em produção.
- A CI/CD permite que as empresas detectem e corrijam erros mais rapidamente, além de acelerar o tempo de lançamento de novos recursos.





## Aula 11: Configurando um Pipeline CI/CD com Github Actions

Exercícios práticos:

- Configure um repositório no GitHub para usar o Github Actions.
Escreva um arquivo de workflow básico do Github Actions para executar testes sempre que o código for enviado ao repositório.

- Execute o workflow e verifique se os testes foram concluídos com sucesso.

Dicas:

Os workflows do Github Actions são configurados usando arquivos YAML no diretório .github/workflows do seu repositório.
Você pode configurar o Github Actions para executar em várias plataformas e com várias versões de linguagens de programação.

Referências

https://docs.github.com/en/actions/quickstart#creating-your-first-workflow


### Creating your first workflow

1. Create a **.github/workflows** directory in your repository on GitHub if this directory does not already exist.

2. In the **.github/workflows** directory, create a file named **github-actions-demo.yml.** For more information, see "Creating new files."

3. Copy the following YAML contents into the **github-actions-demo.yml** file:

```yml
name: GitHub Actions Demo
run-name: ${{ github.actor }} is testing out GitHub Actions 🚀
on: [push]
jobs:
  Explore-GitHub-Actions:
    runs-on: ubuntu-latest
    steps:
      - run: echo "🎉 The job was automatically triggered by a ${{ github.event_name }} event."
      - run: echo "🐧 This job is now running on a ${{ runner.os }} server hosted by GitHub!"
      - run: echo "🔎 The name of your branch is ${{ github.ref }} and your repository is ${{ github.repository }}."
      - name: Check out repository code
        uses: actions/checkout@v3
      - run: echo "💡 The ${{ github.repository }} repository has been cloned to the runner."
      - run: echo "🖥️ The workflow is now ready to test your code on the runner."
      - name: List files in the repository
        run: |
          ls ${{ github.workspace }}
      - run: echo "🍏 This job's status is ${{ job.status }}."
```

## Aula 12: GitLab CI/CD: Configuração e Fluxo de Trabalho

Exercícios práticos:

Configure um repositório no GitLab para usar o GitLab CI/CD.
Escreva um arquivo .gitlab-ci.yml para executar testes sempre que o código for enviado ao repositório.
Execute o pipeline e verifique se os testes foram concluídos com sucesso.
Dicas:

O GitLab CI/CD também usa arquivos YAML para configurar pipelines, mas o formato é um pouco diferente do Github Actions.
O GitLab CI/CD permite que você defina variáveis de ambiente que podem ser usadas em seus pipelines.

criar um arquivo .gitlab-ci.yml na raiz do repositório. 


```yaml
build-job:
  stage: build
  script:
    - echo "Hello, $GITLAB_USER_LOGIN!"

test-job1:
  stage: test
  script:
    - echo "This job tests something"

test-job2:
  stage: test
  script:
    - echo "This job tests something, but takes more time than test-job1."
    - echo "After the echo commands complete, it runs the sleep command for 20 seconds"
    - echo "which simulates a test that runs 20 seconds longer than test-job1"
    - sleep 20

deploy-prod:
  stage: deploy
  script:
    - echo "This job deploys something from the $CI_COMMIT_BRANCH branch."
  environment: production
```






