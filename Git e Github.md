## informações importantes:
# Para configurar o nome de usuário:

git config --global user.name "NomeUsuario"

# Para configurar o e-mail:

git config --global user.email "emailUsuario@email.com"


# Para definir o editor a ser utilizado (Nunca usei)

git config -- global core.editor nomeEditor


# Para saber qual o userName configurado 
git config user.name

# Para saber qual o e-mail configurado 
git config user.email


# Para saber tudo 

git config --list


# Inicializando o repositório

git init


# Verificando o status do repositório no momento

git status


# Adicionando os arquivos para serem rastreados pelo git

git add nomeArquivo.txt ou git add * 


# Criando o commit (Imagem ou snapshot do estado do arquivo atual)

git commit -m "Adicionando arquivos"


# Mostra informações sobre os commits realizados

git log


# Mostra informações sobre os commits realizados e se mudaram de branch 


git log -- decorate


# Mostra informações sobre os commits realizados pelo autor

git log --author="NomeAutor"


# Mostra informações sobre os commits realizados pelo autor em ordem alfabética


git shortlog

# Mostra informações sobre os commits realizados de forma gráfica

git log --graph


# mostra o que foi alterado na hash 

git show 46897j546546k6546op546546p456465k6456


# verificando as mudanças do repositório antes de enviar

git diff


# mostrar o nome apenas do arquivo que foi modificado antes de enviar

git diff --name-only


# salva o arquivo e já comitta

git commit -am "nome do commit"


# Reseta o arquivo a versão anterior antes da modificação

git checkout "nomeArquivo"


# Se adicionar o arquivo com alteração errada para o staged (git add arquivo) e quiser voltar utilizar o comando, desta forma ele vai ficar com o status modified

git reset HEAD "nomeArquivo"

# Subi o commit errado, não deveria subir, como fazer
## Existem 3 comandos 
* git log para saber quais hashs existem 

### Vai excluir o commit mas vai manter o arquivo no staged, pronto para realizar um novo commit
git reset --soft 345343y5435jm5435b435b34n435k435(nome da hash) 

** Tem que ser o nome da hash que você quer que a versão esteja, não pode ser a útima, senão, não terá alteração no commit
* Por exemplo

git log 

hash 3
hash 2 
hash 1

* A hash 3 ta errada, e eu quero voltar para a hash 2, então vou utilizar 

git reset --soft hash 2

* O mesmo se aplica aos exemplos abaixo

### Vai excluir o commit e vai voltar o arquivo para o estado antes do staged (modified)
git reset --mixed 345343y5435jm5435b435b34n435k435(nome da hash) 

** Tem que ser o nome da hash que você quer que a versão esteja, não pode ser a útima, senão, não terá alteração no commit

### Vai excluir o commit e tudo o que foi feito nele
git reset --hard 345343y5435jm5435b435b34n435k435(nome da hash) 

** Tem que ser o nome da hash que você quer que a versão esteja, não pode ser a útima, senão, não terá alteração no commit



# Após a criação do repositório remoto, para conectar o repositório local ao remoto 
## origin é o nome usado para determinar a origem do repositório remoto (pode ser qualquer nome, o mais utilizado é o origin)... é como se fosse um apelido para o link do repositório remoto
git remote add origin https://github.com/felipeSantosf/Aprendendo-Git-e-GitHub.git (Substituir pelo link do repositório)


# Renomear o nome da sua branch local para main (Nesse caso é o nome da branch do repositório remoto)

git branch -M main

# Realizar o envio da branch para o repositório remoto

git push -u origin main

# Verificar se existe algum repositório remoto conectado

git remote


# Verificar se existe algum repositório remoto conectado com mais informações

git remote -v


# Tentei realizar o git push mas deu erro que dizia que meu repositório local estava desatualizado em relação ao repo remoto, usei os seguintes comandos e deu certo
git pull origin master --allow-unrelated-histories
git push origin master


# Para clonar o repositório

git clone  https://github.com/felipeSantosf/Aprendendo-Git-e-GitHub



# Para fazer uma cópia de um projeto que não é seu, realizar as modificações e enviar para o usuário posteriormente

Deve-se clilcar em Fork no github onde está o projeto e este projeto será forkado para o seu github


# O que é uma Branch... É um ponteiro móvel que leva a um commit
* Vantagens:
    - Poder modificar sem alterar o local principal(master ou no caso main que estou utilizando)
    - Facilmente "desligável"
    - Múltiplas pessoas trabalhando
    - Evita conflitos

# Verificar as branch's criadas

git branch

# Para criar e entrar em um branch

git checkout -b nomeDaBranch

# Para selecionar a branch

git checkout nomeDaBranch

# Para apagar um branch

git branch -D nomeDaBranch

# Para unir branches
## Fazendo o Merge:  Cria um novo commit com juntando os commits anteriores (forma diamante)
 * Prós:
        - Operação não destrutiva (Não exclui os commits anteriores)
 * Contra: 
        - Commit extra
        - Histórico poluído

gir merge nomeDaBranch

## Utilizando o Rebase: Pega o commit que estava separado e coloca a frente
 * Prós:S
        - Evita commits extras
        - Histórico linear
 * Contra: 
        - Perde a ordem cronológica
       S
git rebase nomeDaBranch

# É melhor utilizar o rebase sempre que puder



