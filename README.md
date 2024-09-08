# Repositório para testes e interações com o GitHub

## O que é Git?

https://git-scm.com/

### Comandos mais usados:

- `git clone url_repositório_remoto <nome_pasta_local>` --> usado pra clonar um repositório para uma pasta local, o nome da pasta local é opcional, caso não seja passado o git vai salvar o nome da pasta com o mesmo do repositório remoto
	- `git clone url_repositorio_remoto --branch nome_branch_remota --single-branch` --> usada para clonar uma branch em específico, caso não seja passada o nome da branch que se deseja clonar ela vai fazer o clone da main/master
- `git init` --> inicializa um repositório git no diretório local
- `git config` --> mostra as configurações do git
- `git commit -m "mensagem do commit"` --> grava uma nova versão do repositório localmente
	- `git commit --amend -m "nova mensagem do commit"` --> Altera a mensagem do commit anterior, caso seja utilizado só o amend sem a mensagem, é aberto o editor padrão configurado para editar a mensagem.
- `git pull` --> puxa as alterações do repositório remoto para o seu local (busca novas alterações e mescla na sua branch atual --> fetch + merge)
- `git fetch <remote> <branch>` --> puxa as alterações da branch especificada, mas não mescla automaticamente, para verificar as diferenças podemos usar o git diff ou se quisermos aceitar as alterações podemos usar o git merge após o fetch 
- `git push` --> envia as alterações do seu repositório local para o repositório remoto
- `git remote` --> configurações do repositório remoto 
	- `git remote -v` --> mostra qual repositório remoto o seu repositório local está linkado
	- `git remote add origin url_repositório_git` --> adiciona o link de do repositório local com o repositório remoto do github
- `git stauts` --> mostra o status da sua branch atual. O git ignora pastas que estejam vazias para que ela apareça no git status é necessário que exista algum arquivo dentro dela ou o que pode acontecer é encontrar em alguns repositórios um arquivo vazio nomeado como `.gitkeep`
- `git add .` --> adiciona todos os arquivos para a staging área para serem commitados.
- `git restore <file>` --> remove as alterações no arquivo que não foram commitadas.
	- `git restore --staged <file>` --> remove o arquivo da staging area, sem apagar as alterações
- `git log` --> mostra os logs dos commits feitos no repositório
- `git restore <file>` --> recupera um arquivo apagado antes de ir para a staging area
- `git branch -v` --> lista o ultimo commit de cada branch
- `git reset <flag> hash_commit_alterar` --> ele move o ponteiro do HEAD para o commit especificado e remove oss arquivos dos commits posteriores de acordo com a flag em específicada:
	- `--soft` --> o mais seguro de todos, ele move o HEAD para o hash apontado, remove os commits posteriores e deixa adicionado os arquivos com as alterações na área de staging prontos para um novo commit (assim não perde nada caso seja feito por engano)
	- `--mixed` --> comportamento padrão do git reset, ele move o HEAD para o hash indicado, remove os commits posteriores, mas diferente do soft, o mixed não deixa os arquivos prontos para ser commitado, precisando usar o git add para inserir eles novamente na staging area e após isso serem commitados novamente
	- `--hard` --> ele move o HEAD para o hash especificado e remove os arquivos e commits posteriores, deletando os arquivos
- `git checkout -b nova_branch` --> cria uma nova branch e já muda pra ela
- `git merge outra_branch` --> Mescla a outra branch na sua branch atual
- `git branch` --> Lista as branchs
- `git branch -d nome_branch` --> deleta uma branch
- `git diff branch outra_branch` --> compara as diferenças entre as duas branchs
- `git stash` --> arquiva as alterações feitas na branch atual
	- `git stash list` --> lista as modificações arquivadas
	- `git stash pop` --> recupera a alteração removendo ela da lista de stash
	- `git stash apply` --> recupera a alteração mas mantem ela na lista do stash

