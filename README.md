# curso_test_git
Repositório para curso de Desenvolvimento de Sistemas 
1. Conceitos importantes
   
1.1. O que é controle de versão? 

Um técnica que ajuda  a gerenciar o código-fonte de um plicação;
Registrando todas as modificações de código, podendo também reverter as mesmas; 
Criar versões de um software em diferentes estágios, podendo alterar facilmente entre elas; 
Cada membro da equipe pode trabalhar em uma versão diferente; 
Há ferramentas para trabalhar o controle de versão com: git e SVN;

1.2. O que é git?

O sistema de controle de versão mais utilizado do mundo atualmente; 
O git é baseado em repositório, que contém todas as versões do código e também as cópias de cada desenvolvedor; 
Todas as operações do git são otimista por ter alto desempen
ho;
Todos os objetos do git são protegidos com criptografia para evitar alterações indesejadas e maliciosas; 
O git é um projeto de código aberto; 

1.3. O que é repositório?

É onde o código será armazenado; 
Na maioria das vezes cada projeto tem um repositório; 
Quando criamos um repositórios estamos iniciando um projeto; 
O repositório pode ir para servidores que são especializados em gerenciar repos, com GitHub e Bitbucket; 
Cada um dos desenvolvedores do time pode baixar o repositório e criar versões diferentes em sua máquina; 

Criando repositório

Para criar um repositório utilizamos o comando : git init; 
Desta maneira o git vai criar os arquivos necessários para inicializar-lo; 
Que estão na pasta oculta .git; 
Após este comando o diretório atual será reconhecido pelo git como um projeto e responderá aos seus demais comandos; 

O que é  o GitHub?

É um serviço para gerenciar repositórios , gratuito e amplamente utilizado; 
Podemos enviar nossos projetos para o GitHub e disponibilizá-lo para outros devs;
O gitHub é gratuito tanto para projetos públicos com privados; 
vamos criar uma conta em: https://github.com 







Comando para saber se existe repositório (Branch e Comint)
 git status  


Enviando repositório para o GH

Podemos facilmente enviar nossos repositórios para o Github;
Precisa criar o projeto no GitHub, inicializar o mesmo no git em nossa máquina, sincronizar com o GH e enviar; 
E esta sequência que parece ser complexa é facilmente executada por poucos comandos;
Vale lembrar que só fazemos uma vez por projeto este fluxo;
Porém alguns dos comandos utilizados vão ser úteis ao longo do curso;

Códigos para criar repositório

git init 
git add primeiro_arquivo // em vermelho é o nome do arquivo
git commit -m "primeiro commit"
git branch -m main
git remote add origin https://github.com/EmillySSilva/curso_git_gitHub.git
git push -u origin main  

OBS1.: CASO DE ERRO DE PERMISSÃO 
git remote -v // mostra a origem
git remote rm origin  // retira a origem atual
git remote -v 
git remote add origin git@github.com:EmillySSilva/curso_git_gitHub.git // adicionando origem

0BS.: AINDA DANDO ERRO
<> TERMINAL Powershell
dir $env:USERPROFILE\.ssh 
ssh-keygen -t ed25519 -C "aluno@gmail.com"
(ENTER)
(ENTER)
(ENTER)


Cadastrar no GitHub
Entre na sua conta do GitHub e vá em:
Foto do perfil → Settings → SSH and GPG keys → New SSH key
Preencha:
Title:
Computador da escola
Key type:
Authentication Key
Key:
Cole a linha que você acabou de copiar.
Depois clique em Add SSH key.
ssh -T git@github.com
se tiver a mensagem: 
Hi EmillySSilva! You've successfully authenticated, but GitHub does not provide shell access.
git add .


# modificando arquivo no repositório 

git add test_criando_arquivo // preparando o arquivo para ir para o repositório
git commit -m "Atualiza o conteúdo do test_criando_arquivo" //escrevendo comentário de qual parte foi atualizada/acrescentada de forma resumida
git push origin main // subindo para o repositório main


# Adicionando arquivo ao projeto 
Para adicionar arquivos novos a um projeto utilizamos: git add ;
Podemos adicionar um arquivo específico como também diversos de uma vez só;
Somente adicionando arquivos eles serão modificados pelo git;
Ou seja, se não adicionar ele não estará no controle de versão;
É interessante utilizar este comando de tempos em tempos para não perder algo por descuido;

🟩 Arquivos Novos
U (Untracked / Não monitorado): O arquivo é totalmente novo na pasta. O Git sabe que ele existe, mas ele ainda não foi adicionado ao histórico (falta rodar git add).
A (Added / Adicionado): Você acabou de criar o arquivo e já rodou o git add. Ele está pronto na "fase de preparação" (stage) esperando o commit.
🟨 Arquivos Modificados
M (Modified / Modificado): O arquivo já existia em commits anteriores, mas você alterou alguma linha de código ou texto nele e ainda não salvou a nova versão.
Staged Modified (Modificado no Stage): No VS Code, se o M mudar de cor (ficar verde ou ir para a aba "Alterações Salvas"), significa que você rodou git add nele após modificá-lo.
🟥 Arquivos Deletados ou com Problemas
D (Deleted / Deletado): O arquivo existia no último commit, mas você o deletou da pasta. O Git avisa que essa remoção precisa ser commitada para sumir do histórico definitivo.
C (Conflict / Conflito): Duas pessoas (ou você e o GitHub) alteraram a mesma linha do mesmo arquivo ao mesmo tempo. Você precisa abrir o arquivo e escolher qual versão manter.
🟦 Outros Status Menos Comuns
R (Renamed / Renomeado): Você mudaram o nome do arquivo ou o moveram de pasta.
?? (Sinal de interrogação duplo): É como o terminal do Git (git status) exibe arquivos com status U (Untracked) quando listados de forma simplificada.

adicionar  a# rquivo no repositório 

git add test_criando_arquivo 
git commit -m "Atualiza o conteudo do test_criando_arquivo" 
git push origin main 


# adicionar mais de um arquivo 

git add .


# Salvando alterações do projeto 
As alterações salvas do projeto são realizadas por: git commit;
Podemos commitar arquivos específicos ou vários de uma vez com a flag -a.
É uma boa prática enviar uma mensagem a cada commit, com as alterações que foi feitas;
A mensagem pode ser adicionada com a flag -m 

git commit test_criando_arquivo  -m "Atualizando o conteúdo do test_criando_arquivo" 
git push origin main 

# Para comitar mais de um arquivo para o servidor

git commit -a -m "Enviando a funcionalidade nova"
git push origin main 
_________________________________________________________________________________

Recebendo as Mudanças 

É comum também ter de sincronizar o local com mudanças do remoto;
Essa ação é feita pelo git pull;
Após o comando serão buscada atualizações, se encontradas elas serão unidas ao código atual existente na nossa máquina; 

Quando o arquivo no main está com arquivos novos no repositório remoto o  comando <git pull> atualiza a pasta local 

________________________________________________________________________________




Clonando repositórios

O ato de baixar um repositório de um servidor remoto é chamado de clonar repositório de um servidor remoto é chamado de clonar repositório; 
Para esta ação utilizamos git clone;
passando a referência do repositório remoto;
Este comando é utilizado quando entramos em um novo projeto , por exemplo;


clicar no botão verde <> code, irá abrir uma nova janela ou será copiado o endereço de localização do arquivo a ser clonado.
comando: git clone https://…. 
git pull (atualizar a pasta)

Removendo arquivos do repositório


Os arquivos podem ser deletados da monitoração do git 
O comando para deletar é git rm
após deletar um arquivo do git ele não terá mais suas atualizações consideradas pelo git; 
Apenas quando for direcionado novamente pelo git add

código: 
git rm …(nome do arquivo)
git status (para saber se precisa de alguma ação, o git status irá dizer que precisa commitar o exclusão do arquivo)
git commit -a -m “Deletando arquivo desnecessário”
git push 
git pull

Histórico de alterações 

Podemos acessar um log de modificações feitas no projeto;
O comando para este recurso é git log
Você receberá uma informação dos commits realizados no projeto até então;

Removendo arquivos

Com o comando git mv podemos renomear um arquivo; 
O mesmo também pode ser movido para outra pasta; 
E isso fará com que este arquivo seja monitorado pelo git; 
O arquivo anterior é excluído; 

Desfazendo alterações 

O arquivo modificado pode ser retornado ao estado original;
O comando utilizado é o git checkout
Após a utilização do mesmo o arquivo sai do staging;
Caso seja feita uma próxima alteração, ele entra em staging novamente; 

Ignorando arquivos no projeto

Uma técnica muito utilizada é ignorar arquivos do projeto;
Devemos inserir um arquivo chamado .gitignore na raiz do projeto;
Nele podemos inserir todos os arquivos que não devem entrar no versionamento;
Isso é útil para arquivos gerados automaticamente ou arquivos que contêm informações sensíveis

