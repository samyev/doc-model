# Deploy Junt Club

### 1. Verificar quais branches já foram criadas na sua máquina:
~~~ shell
git branch
~~~

Se só houverem **dev, stagin e master**, criar uma branch para trabalhar no projeto atual, utilize:
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

dica: não devem ser nem **dev, stagin nem master**

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