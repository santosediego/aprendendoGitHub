# Guia Prático de Comandos Git

## Sumário
- [Comandos Básicos](#comandos-básicos)
- [Ignorar Arquivos](#ignorar-arquivos)
- [Editor Padrão e Ferramenta de Merge](#editor-padrão-e-ferramenta-de-merge)
- [Servidores Remotos](#servidores-remotos)
- [Adicionando Arquivos](#adicionando-arquivos)
- [Verificando Alterações](#verificando-alterações)
- [Commit](#commit)
- [Branches](#branches)
- [Apagar, Mover ou Renomear](#apagar-mover-ou-renomear)
- [Revertendo Alterações](#revertendo-alterações)
- [Histórico (log)](#histórico-log)
- [Tags](#tags)
- [Stash](#stash)
- [Referências](#referências)

## Comandos Básicos

Configurações locais:
```bash
git config --list
```

Visualizar e alterar usuário/email:
```bash
git config --global user.name
# ou para alterar
git config --global user.name "Seu Nome"

git config --global user.email
# ou para alterar
git config --global user.email "seu@email.com"
```

Iniciar/clonar/atualizar repositório:
```bash
git init
git clone <url>
git pull
```

## Ignorar Arquivos

Criar um arquivo `.gitignore` com os nomes ou padrões de arquivos a serem ignorados.

## Editor Padrão e Ferramenta de Merge

```bash
git config --global core.editor vim
git config --global merge.tool vimdiff
```

## Servidores Remotos

```bash
git remote -v                            # listar

git remote add origin <url>             # adicionar

git remote set-url origin <nova_url>    # atualizar
```

## Adicionando Arquivos

```bash
git add <arquivo>        # arquivo específico
git add .                # todos os arquivos modificados
git commit -am "msg"     # add + commit de arquivos modificados
```

## Verificando Alterações

```bash
git status
git diff                 # compara área de trabalho x stage
git diff <arquivo>
```

## Commit

```bash
git commit -m "Mensagem do commit"
```

## Branches

```bash
git branch                       # listar

git branch <nome>               # criar nova

git checkout -b <nome>          # criar e mudar para a nova

git branch -d <nome>            # deletar

git checkout <nome>             # trocar de branch

git push origin <nome>          # enviar para o servidor

git push --all origin           # enviar todas as branches

git push origin :<nome>         # deletar branch remota

git checkout main
git merge <branch>              # juntar branch na main

git push origin main            # enviar alterações da main
```

## Apagar, Mover ou Renomear

```bash
git mv <origem> <destino>       # mover/renomear

git rm <arquivo>                # remover arquivo

git rm -r <pasta>               # remover pasta com arquivos
```

## Revertendo Alterações

```bash
git reset <arquivo>             # tira do stage

git reset HEAD .                # limpa todo o stage

git checkout <arquivo>          # volta arquivo para último commit

git checkout .                  # volta tudo

git reset --soft HEAD~1         # volta commit, mantém stage

git reset --hard HEAD~1         # volta commit e limpa stage

git revert <hash>               # desfaz commit sem perder histórico

git reset --hard HEAD~1 && git push -f origin main  # desfaz push
```

## Histórico (log)

```bash
git log                         # histórico completo

git log -p -2                   # mostra 2 últimos com diff

git log --pretty=oneline        # uma linha por commit

git log --pretty=format:"%h = %an, %ar - %s"   # personalizado

git log --author="autor"        # filtrando por autor
```

## Tags

```bash
git tag <nome>                  # criar

git tag                         # listar

git tag -a <nome> -m "msg"      # com mensagem

git tag -a <nome> <hash>        # referenciando commit

git push origin <nome>          # enviar uma

git push origin --tags          # enviar todas
```

## Stash

```bash
git stash                       # salva estado

git stash save -u "mensagem"    # com untracked e mensagem

git stash list                  # listar

git stash pop                   # aplicar e remover

git stash apply                 # aplicar e manter

git stash apply stash@{n}       # aplicar stash específico
```

## Referências

- [Comandos mais utilizados no Git (William Oliveira)](https://woliveiras.com.br/posts/comandos-mais-utilizados-no-git/)
- [Guia de README bonitão - Raul Esteves](https://medium.com/@raullesteves/github-como-fazer-um-readme-md-bonit%C3%A3o-c85c8f154f8/)
- [Template em Português - dbader](https://github.com/dbader/readme-template/tree/master/portuguese)

