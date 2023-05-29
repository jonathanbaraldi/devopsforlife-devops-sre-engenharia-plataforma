
# Capítulo 2: Controle de Versão e Colaboração

## Aula 4 :
4. Git e GitHub: Fundamentos e Melhores Práticas
    
Visão geral dos sistemas de controle de versão.

Introdução ao Git: instalação, configuração e comandos (init, add, commit, status, log).

Introdução ao GitHub: criar uma conta, criar e gerenciar repositórios, enviar para repositórios remotos.

Modelo de ramificação do Git: criando e alternando ramificações, mesclando ramificações.

Noções básicas sobre arquivos .gitignore.

Melhores práticas: Escrever boas mensagens de commit, manter um repositório limpo e organizado.

### Exercícios

- Instale o Git no seu computador e configure seu nome de usuário e email.

- Criar repositório no Github e clonar ele localmente para executar os exercícios.

```sh 
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@exemplo.com"
```
- Crie uma conta no GitHub e crie um novo repositório. Inicialize o repositório com um README, .gitignore ou licença.
- Clone o repositório que você acabou de criar no GitHub para o seu computador local.
```sh
git clone https://github.com/seuUsuario/seuRepositorio.git
cd seuRepositorio
```
- Faça alterações nos seus arquivos, faça commit dessas alterações e faça push delas para o GitHub.
```sh
echo "Olá, mundo!" > arquivo.txt
git add arquivo.txt
git commit -m "Adiciona arquivo.txt"
git push
```
- Crie um arquivo .gitignore e exclua arquivos específicos de serem rastreados.
```sh
touch logs.txt
echo "*.log" > .gitignore
git add .gitignore
git commit -m "Adiciona .gitignore"
git push
```
- Crie uma nova branch, faça algumas alterações, faça commit delas e então faça o merge da branch de volta para a main.
```sh
git checkout -b nova-branch
echo "Alguma alteração" > novo_arquivo.txt
git add novo_arquivo.txt
git commit -m "Adiciona novo_arquivo.txt"
git checkout main
git merge nova-branch
git push

```


## Aula 5 : 
5. Estratégias e Fluxos de Trabalho de Branching do Git
    Descrição: Diferentes estratégias de branching do Git e como aplicá-las em projetos.

O papel das ramificações no Git.
Diferentes estratégias de ramificação: Ramificação de recursos, Gitflow, Bifurcação.
Entendendo os conflitos de mesclagem e como resolvê-los.
Usando tags para marcar pontos específicos na história.
Rebase e a diferença entre merge e rebase.
Práticas recomendadas para um fluxo de trabalho eficiente: quando ramificar, quando mesclar, etc.

Melhores práticas: Escrever boas mensagens de commit, manter um repositório limpo e organizado.

### Exercícios

Crie uma nova branch no seu repositório, faça alterações, faça commit delas e depois faça merge da branch de volta para a main.
```sh
git checkout -b nova-branch
echo "Alguma alteração" > arquivo.txt
git commit -am "Altera arquivo.txt"
git checkout main
git merge nova-branch
```
Simule um conflito de merge fazendo alterações conflitantes em duas branches e depois tente fazer merge delas. Pratique a resolução do conflito.
```sh
git checkout -b branch1
echo "Alteração na branch1" > arquivo.txt
git commit -am "Altera arquivo na branch1"
git checkout main
git checkout -b branch2
echo "Alteração na branch2" > arquivo.txt
git commit -am "Altera arquivo na branch2"
git checkout main
git merge branch1
git merge branch2
# Resolver conflito no arquivo.txt, depois:
git commit -am "Resolve conflito de merge"
```
Use tags para marcar um commit específico como um lançamento de versão.
```sh
git tag v1.0.0
git push --tags
```


## Aula 6 :
6. Colaborando com Git: Pull Requests e Revisão de Código
Descrição: Como colaborar com colegas de equipe usando pull requests e revisão de código.

O conceito de Pull Request (PR).
Criando, revisando e mesclando uma solicitação pull no GitHub.
A importância das revisões de código e como fazê-las de forma eficaz.
Fluxos de trabalho colaborativos com Git e GitHub: fork & pull, modelo de repositório compartilhado.
Resolução de conflitos de merge durante pull requests.
Ferramentas para revisão de código no GitHub: comentários embutidos, revisões, rascunhos de PRs.


### Exercícios

- Colabore com um parceiro. Peça para eles fazerem um fork do seu repositório, fazerem alterações e, em seguida, enviarem um pull request. Revise e faça merge das alterações deles.
Este exercício envolve mais interação com a interface do GitHub, mas o parceiro pode usar comandos semelhantes aos acima para fazer alterações no repositório forkado.
- Faça uma alteração em uma branch e envie um pull request para o seu próprio repositório. Reveja as alterações, deixe comentários e faça merge do request.
```sh 
git checkout -b nova-branch
echo "Alguma alteração" > arquivo.txt
git commit -am "Altera arquivo.txt"
git push origin nova-branch
```
- Depois disso, vá para o GitHub e crie um novo pull request a partir da "nova-branch" para a "main".
- Faça alterações em uma branch e intencionalmente crie um conflito de merge quando enviar um pull request. Pratique a resolução do conflito no GitHub.
- Este exercício é uma extensão do exercício de conflito de merge acima, mas envolve a criação de um pull request no GitHub.






