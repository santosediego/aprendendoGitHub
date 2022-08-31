# Comandos mais utilizados no Git

## Sumário
- [`Comandos básicos`](https://www.google.com.br);
- [`Ingnorar arquivos`](https://www.google.com.br);
- [`Servidores`](https://www.google.com.br);
- [`Adicionando arquivo`](https://www.google.com.br);
- [`Verificando alterações`](https://www.google.com.br);
- [`Commit`](https://www.google.com.br);
- [`Branches`](https://www.google.com.br);
- [`Apagar, mover ou renomear`](https://www.google.com.br);
- [`Revertendo alterações`](https://www.google.com.br);
- [`Histórico (log)`](https://www.google.com.br);
- [`Tags`](https://www.google.com.br);
- [`Stash`](https://www.google.com.br);
- [`Referência`](https://www.google.com.br);

## Comandos básicos

Configurações locais

```bash

git config --list
```

Visualizar o nome de usuário

```bash
git config --global user.name
```

Alterar o nome de usuário

```bash
git config --global user.name <nome do usuário>
```

Visualizar o e-mail

```bash
git config --global user.email
```

Alterar o e-mail

```bash
git config --global user.email <email do usuário>
```

Iniciar um repositório

```bash
git init
```

Clonar repositório

```bash

git clone <link>
```
 Atualizar repositório

```bash

git pull
```

## Ignorar arquivos

Criar um arquivo chamado `.gitignore` e adicionamos os nomes dos arquivos nele.

## Alterando o editor de textos usados para commit e diffs

```bash
git config --global core.editor vim
```

```bash
git config --global merge.tool vimdiff
```

## Servidores

Listando caminhos de servidores

```bash
git remote -v
```

Adicionando o caminho do servidor

```bash
git remote add origin <url>
```

Atualizando o caminho do servidor

```bash
git remote set-url origin <url>
```

## Adicionando arquivos

Arquivo especifico

```bash
git add <nome do arquivo>
```
Todos os arquivos criados e ou alterados

```bash
git add .
```
Adiciona e commita diretamente

```bash
git commit -am <Mensagem do commit>
```

## Verificando alterações

Verifica as alterações de forma geral

```bash
git status
```

Verifica todas as alterações do arquivo

```bash
git diff <nome do arquivo>
```
Verifica todas as alterações dos arquivos

```bash
git diff
```

## Commit

Realiza o commit

```bash
git commit -m <mensagem>
```
## Branches

Lista as branches

```bash
git branch
```

Cria uma nova branch

```bash
git branch <nome da branch>
```
Cria uma nova branch

```bash
git branch <nome da branch>
```
Cria uma nova branch já a setando para utilização

```bash
git checkout -b <nome da branch>
```
Deleta uma branch

```bash
git branch -d <nome da branch>
```
Troca de brach

```bash
git checkout <nome da branch>
```
Envia a branch para o servidor

```bash
git push origin <nome da branch>
```
Envia todas as branchs para o servidor

```bash
git push --all origin
```
Deleta uma branch remota

```bash
git push origin :<nome da branch>
```

Junta branches

```bash
git checkout main
```

```bash
git merge <nome da branch>
```

Enviando alterações para o servidor

```bash
git checkout main
```

```bash
git push origin main
```

## Apagando, movendo ou renomeando arquivos ou pastas sem "estragar" histórico Git

Mover arquivos ou pastas

```bash
git mv <options> <args>
```

Deletando pasta ou arquivo, no caso de pasta, a mesma deve estar vazia

```bash
git rm <nome do arquivo ou pasta>
```

Deletando pasta que não esta vazia

```bash
git rm -r <nome da pasta>
```

Renomeando pasta ou arquivo

```bash
git mv <nome da pasta ou arquivo>
```

## Revertendo alterações

Desfazendo inclusões ou alterações no stage

```bash
git reset <nome do arquivo>
```

Desfazendo todas inclusões ou alterações no stage

```bash
git reset HEAD .
```

Desfazendo todas inclusões ou alterações no stage

```bash
git reset HEAD .
```

Desfazendo um arquivo para o ultimo commit

```bash
git checkout <nome do arquivo>
```

Desfazendo tudo para o ultimo commit

```bash
git checkout .
```

Desfazendo uma alteração mas colocando em stage

```bash
git reset --soft HEAD~1
```

Desfazendo alteração sem colocar em stage

```bash
git reset --hard HEAD~1
```

Desfazendo para um commit especifico

```bash
git revert <hash>
```

Desfazendo para o último push

```bash
git reset --hard HEAD~1 && git push -f origin main
```

## Analisando o histórico (log)

Lista todo o log

```bash
git log
```

Lista de acordo com a quantidade informada

```bash
git log -p -<2>
```

Apresenta o log resumido

```bash
git log --pretty=oneline
```

Formantando o log
- Onde
  - %h: abreviação do hash;
  - %an: nome do autor;
  - %ar: data;
  - %s: comentário

```bash
git log --pretty=format:"%h = %an, %ar - %s"
```

Exibindo o log por autor

```bash
git log --author=<nome do autor ou usuário>
```

## Utilizando tags

Criando uma tag

```bash
git tag <nomeDaTag>
```

Listando tags

```bash
git tag
```
Criar tag com mensagem

```bash
git tag -a <nome> -m "<mensagem>"
```

Criar tag referencia commit

```bash
git tag -a <nome> <hash>
```

Enviando tag para o servidor

```bash
git push origin <nome>
```

Enviando todas as tags para o servidor

```bash
git push origin --tags
```


## Stash

Stash, resumindo, é uma área temporária onde se guarda um histórico sem adicionar na brach.

Salvar tudo no stash

```bash
git stash
```

Salvando stash com descrição

```bash
git stash  save -u "<mensagem>"
```

Listando o que existe em stash

```bash
git stash list
```


Revertendo para o stash e removendo da lista. Removendo a última entrada na lista.

```bash
git stash pop
```

Revertendo para o stash em remover do stash

```bash
git stash apply
```

Revertendo para o stash em remover do stash para um item especifico

```bash
git stash apply stash@{<numero>}
```

## Referências
[Comandos mais utilizados no Git](https://woliveiras.com.br/posts/comandos-mais-utilizados-no-git/), Autor: William Oliveira, Data de publiação: 26/Dez/2018

Abaixo segue alguns links com exemplos para a edição do README.md.

[Exemplo escrito por Raul Esteves](https://medium.com/@raullesteves/github-como-fazer-um-readme-md-bonit%C3%A3o-c85c8f154f8/)

[Template em Português](https://github.com/dbader/readme-template/tree/master/portuguese)
