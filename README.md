# Deploy Junt Club

> Dica: Leia tudo com calma antes de realizar as operações a baixo

### 1. Verificar quais branches já foram criadas na sua máquina:
~~~ shell
git branch
~~~

Se só houverem **dev, staging e master**, criar uma branch para trabalhar no projeto atual, utilize:
~~~ shell
git checkout -b [nome da branch]
~~~

dica: ao utilizar **git checkout -b** você cria e modifica a branch do seu projeto automáticamente,
se a sua branch já está criada, utilize **git checkout [branch]**.

dica: para as suas branches, utilize o padrão JUNT-número-nome-especificando-a-atividade.


### 2. Verificar se a branch atual do projeto é mesmo a correta
~~~ shell
git status
~~~ 

dica: não devem ser nem **dev, staging nem master**

dica: verifique se as mudanças feitas são somente as que você precisa para a atividade atual,
caso hajam alterações que não deviam estar ali, utilize:

~~~ shell
git restore [nome do arquivo]
~~~


### 3. Já tendo certeza de que está na branch do projeto correto, adicione as mudanças:
~~~ shell
git add .
~~~ 

dica: o ponto especifica que você irá adicionar **todas** as mudanças realizadas naquela branch.


### 4. Crie o commit

~~~ shell
git commit -m "especifique a mudança feita"
~~~

dica: escreva frases no modo imperativo.

dica: utilize o padrão "[JUNT-numero] frase imperativa"


### 5. Faça o push dos arquivos para o repositório remoto
~~~ shell
git push orgin [nome da branch]
~~~


## Realizando a solicitação pull

Dentro do projeto, vá na aba **Branches**, ao localizar a sua, clique em **create**, você será 
direcionado para a página de pull request. 

<p align="center">
  <img src="img/pullrequest.png" alt="Aba pull request bitbucket">
</p>

Ao carregar a página, observe que ela lhe mostrará duas branches, a branch atual da sua máquina, 
e a branch atual do repositório para abrir o pull, você escolherá a branch **dev**. Em seguida,
escreva uma descrição para o seu pull, descreva qual ação ele fará se aceito.

dica: escreva a frase em modo imperativo

**OBS: Você deverá deletar a sua branch local criada para o projeto, para isso marque a opção**
**"Delete feature/add-api after the pull request is merged", mas preste atenção, você não irá**
**fazer isto para as outras branches, somente para sua branch local.**

>Nota: Quando aprovado, realize novamente os passos a cima para a branch staging.


## Realizando o deploy para o Heroku

Primeiramente você vai realizar todos os passo a cima novamente para atualizar o repositório
de produção do projeto no bitbucket.

### 1. Verifique se você já possui a url do repositório do projeto no heroku
~~~ shell
git remote -v 
~~~

Caso não possua, log em sua conta heroku, vá no projeto, no caso primeiramente em staging,
abra a aba **settings** e procure a url que encontra-se em **Heroku git URL** copie, abra 
o terminal na pasta do projeto junt-club e insira o seguinte comando para adicionar:
~~~ shell
git remote add [nome repositório heroku] [url]
~~~

> Faça o mesmo procedimento para o repositório de produção caso altorizado a isto.

### 2. Suba o projeto para o heroku em staging
~~~ shell
make push_staging
~~~

### 3. Caso altorizado suba o projeto para o heroku em production
~~~ shell
make push_production
~~~

Finalizado o deploy!!!