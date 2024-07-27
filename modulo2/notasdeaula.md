## Notas de aula do Módulo 2: Prática - Criando um Repositório do 0 e aprendendo os comandos mais utilizados

### Roteiro para criar um Repositório Local

- **Primeiro Passo**: *Criar uma pasta* para comportar o repositório do GitHub.
- **Segundo Passo**: Entrar na pasta e abrir o terminal ou o VSCode.
- **Terceiro Passo**: Verificar se as suas configurações da conta do GitHub estão corretas, pelo comando:
    - *git config --list*
    - Se não estiver correto o username e o email, configurar usando:
        - *git config --global user.email "seuemail@email.com"*
        - *git config --global user.name "seunomedeusuário"*
- **Quarto Passo**: Inicializar o repositório na pasta local usando o comando:
    - *git init*
- **Quinto Passo**: Criar arquivos e pastas dentro da pasta/repositório que você criou.

### Roteiro para configuração do acesso ao repositório por SSH

No terminal de comando do computador:
- *cd ~/.ssh* --> entrar nesse diretório
- *ls* --> vê as chaves no diretório
- *ssh -keygen -o* --> adiciona nova chave ssh
- *cat ~/.ssh/id-XXX.pub* --> abre a chave no terminal
- Copiar a chave que aparece no seu terminal

No site do GitHub:
- entrar na parte de SSH e chaves e colar o código da chave que você copiou.

### Roteiro para conectar o repositório local com um repositório remoto no GitHub

- **Criar repositório no site do GitHub**: Navegar para o seu usuário no GitHub, Clicar no botão "+" no canto superior direito da tela e depois "New repository".
- **Copiar chave SSH ou HTTPS**: Dentro do repositório criado, clicar no botão verde escrito "Code" e copiar a chave HTTPS ou SSH.
- **Fazendo a ligação dos dois**: 
    - Voltar para terminal na pasta onde se encontra o seu repositório que você criou.
    - Usar a seguinte sequencia de comandos no terminal:
        - *git remote -v* --> verifica se o repositório tem alguma origem remota
        - Se não tiver:
            - *git remote add origin chave_HTTPS*
            - OU
            - *git remote add origin chave_SSH*
        - *git remote -v* --> para ver se deu certo a conexão

### Comandos mais utilizados:

#### Git status
Verifica o estatus dos arquivos e pastas dentro do repositório

#### Git add
- *Git add caminho_do_arquivo* --> adiciona aquele arquivo específico para a esteira de commit
- *Git add .* --> adiciona todos arquivos e pastas daquele repositório na esteira de commit

#### Git Commit
Sintaxe: *git commit -m "comentário"*

Objetivo: registrar estado da aplicação/arquivo/código - registra alterações realizadas, quem realizou e quando.

#### Roteiro - quando adicionar arquivo ou modificação: 
- *git status* 
- *git add .*
- *git commit -m "comentário"*
- *git status*

#### Git Push
Função: envia arquivos commitados para o GitHub, dentro do repositório especificado.

Comandos: 
- Para a primeira vez que usa o comando, logo após criar um repositório:
    - *git push --set-upstream origin master* (OU main, dependendo da versão)
    - OU
    - *git push -u origin master*
- Se você ja conectou a origem remota da branch no GitHub (*--set-upstream origin*) com o seu repositório local (*main* ou *master*), pode usar somente o comando:
    - *git push*

#### Git Pull

Sintaxe: *git pull*

Objetivo: Trazer alterações presentes no repositório remoto (no site do GitHub) para sua pasta local

#### Roteiro - atualizar repositório no site logo após ele ser criado: 
- *git status* 
- *git push --set-upstream origin master*

#### Roteiro - fazer atualizações ao repositório e trazer as atualizações do repositório para sua máquina: 
- *git status* 
- *git pull*
- *git push*



