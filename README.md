# Projeto de mineração de informações 
### Objetivo
> Minerar informações sobre livros do site http://books.toscrape.com/

> Obter as seguintes informações:
   1. Nome do livro
   2. Genero do livro
   3. Quantidade de estrelas dadas
   4. Se está disponivel em estoque
   5. Preço do livro
  
> Inserir essas informações em um banco de dados mysql
### Arquitetura
1. Foi usado o cluster proposto em: [https://github.com/Antonio-Borges-Rufino/cluster_base]
![](https://github.com/Antonio-Borges-Rufino/mineracao_livros/blob/main/Central.png)

### Parte 1 -> Coleta
1. A coleta dos dados foi realizada utilizando a biblioteca Beatiful Soap
2. Não foi necessário usar slenium pois os links tinham um padrão definido
3. A estrutura do site e da coleta é representada a baixo:
![Site](https://github.com/Antonio-Borges-Rufino/mineracao_livros/blob/main/2.PNG)

4. Primeiro, passei um coletor na janela de categorias, elas me retornariam um link e o nome da categoria
5. Depois de ter o link das categorias e seu nome, comecei a ir de link em link recuperando as informações de cada livro por categoria
6. Despois de ter as informações, construi um DF com todas as informações para serem persistidas posteriormente
7. [O código de estração pode ser encontrado aqui](https://github.com/Antonio-Borges-Rufino/mineracao_livros/blob/main/coleta_livros.ipynb)
8. [O DF pode ser encontrado aqui](https://github.com/Antonio-Borges-Rufino/mineracao_livros/blob/main/livros_data_set.csv)

### Parte 2 -> Persistencia 
1. A persistencia foi feita no banco de dados mysql, com a seguinte estrutura
![Arquitetura BD](https://github.com/Antonio-Borges-Rufino/mineracao_livros/blob/main/1.PNG)
2. [O código de estração pode ser encontrado aqui](https://github.com/Antonio-Borges-Rufino/mineracao_livros/blob/main/insercao_livros.ipynb)
