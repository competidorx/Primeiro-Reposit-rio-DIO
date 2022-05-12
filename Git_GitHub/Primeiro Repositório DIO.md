1.	Navegação via command line interface e instalação

1.1.	Comandos básicos para um bom desempenho no terminal
	•Mundar de pasta
	•Listar as Pastas
	•Criar Pastas / Arquivos
	•Deletar Pastas / Arquivos

1.1.1.	Listar “dir”
	Listar todas as pastas

1.1.2.	Acessar uma pasta “cd”
	Para acessar a pasta digite cd + nome da pasta
	Tecla tab + complementa o nome da pasta

1.1.3.	Voltar uma pasta “cd ..”
	Para retrocedar uma pasta basta digitar somente cd ..

1.1.4.	Limpar o Termna “cls”
	Comando para limpar a telad do prompt comando

1.1.5.	Criar uma pasta “mkdir”
	Criar uma pasta mkdir + nome da pasta 
	Ex: mkdir workspace

1.1.6.	Criar um arquovo dentro da pasta “echo”
	Cria um arquivo dentro da pasta
	Ex: echo hello > hello.txt

1.1.7.	Deletar todos arquivos dentro da pasta “del“
	Deleta todos os arquivos dentro da pasta mas mantem a pasta
	Ex: del workspace

1.1.8.	Deletar a pasta com todos os aquivos “rmdir”
	Deleta a pasta informada e todoas os aquivos contidos dentro.
	Ex: rmdir workspace /S /Q
	•S e Q são chamadas de flags

2.	Entendendo como o Git funciona por baixo dos panos

2.1.	Tópicos fundamentais para entender o funcionamento do Git
	•SHA1
	•Objetos fundamentais
	•Sistema distribuído
	•Segurança

2.1.1.	SHA1
	A sigla SHA significa Secure Hash Algorithm (Algoritmo de Hash Seguro), é um conjunto de função hash criptográficas projetadas pela NSA (Agância de Segurança Nacional dos EUA).
	A encritaçao gera conjunto de characteres indentificador de 40 dígitos.
	Ex:
	1 echo “ola mundo” | openssl sha1
	2 > (stdin)= f9c85e559b9b950175f2b7cd7dad61facbe58eb (Chave)
	2.2.	Objetos internos do Git
	•Blobs
	•Trees
	•Commits

2.2.1.	Blobs
 	Quando passamso a string ‘conteudo’ para a função do Git hash-obect –stdin, é gerado um código sha1.
	Se criamos a msm string usando o openssl sha1, esperavamos receber o msm sha1, porem o resultado foi diferente. Isso ocorre porque ao criar com o Git e armasenado dentro do obejto chamado bos, que contem meta dados dentro deles:
 
	Recriando acrecentando o meta dado ‘blob 9/0conteudo’ é gerado o mesmo código sha1, ou seja, os dois tem o mesmo conteudo.
 
2.2.2.	Tree “árvores”
	As tree armazenam bobs, sendo uma crecente o blobs sendo o bloco básico de composição, a Tree armazeando e apontando para tipos de blobs diferentes e para outras Tree.
 
2.2.3.	Commit
  
2.3.	Login GitHub
 
2.4.	Primeiros comandos com Git

2.4.1.	Iniciando o Git e criando um commit
	•Iniciar o GIT – git init
	•Iniciar o versionamento – git add
	•Criar um commit – git commit
	•Monitorar situação dos arquivos – git status
	•Mover aruivo – mv + nome do arquivo a mover + ./ pasta de destino
	•Criar aquivo – mkdir + nome do arquivo
	•Entrar em uma pasta – cd + nome da pasta
	•Voltar uma pasta – cd ..
	•Listar aquivos na pasta – ls
	•Mudar status de untraked para staged - git add + nome do aquivo untracked
	Obs: git add * (executa para todos os arquivos untraked
	•Commitar arquivos – git commit -m “descrição das alterações”
	•Criar um arqui md – echo > + nome.estensão do arquivo

2.5.	Ciclo de vida dos arquivos no Git

2.5.1.	Tranked Untraked
 
	Untraked: arquivos que o Git não tem ciênca da existencia do arquivo
	•Ao criar um arquivo o Git não tem conhecimento da existencia dele 
	Traked: arquivos que o Git tem ciência da sua existencia
	•Unmodified: arquivo que ainda não foi modificado
	É um arquivo dentro do Git que ainda não sofreu modificação
	Se o arquivo unmodified for removido ele volta a ser untraked
	•Modified: é o arquivo unmodified que sofreu alterações
	Ao mudar um arquivo unmodified ele se torna um arquivo modified, sha1 diferente
	•Staged: 
	Ao commitar os aquivos staged, eles retoram ao estágio unmodified
	Arquivos aguardando para o commit
	Ao usar o git add, no arquivo untraked, ele é movido direto para staged
	Ao rodar o git add no aruivo modified, ele é movido para o staged

2.5.2.	Repositório
 
	•Servidor
		oRemote Repositóry
	•Ambiente de Desenvolvimento
		oWorking Directory
		oStaging Area
		oLocal Repository – todos os arquivos tem que estar commitados, senão não sera possivel enviar para o Servidor

2.6.	Unsando Git e GitHub

2.6.1.	Criando um arquivo Git
	1º - Denro da pasta
	mkdir + nome do arquivo
 
	2º Mover aquivo para outra pasta
	mv + nome do arquivo + ./ + nome da pasta destino/
 
	3º Verificando situação dos arquivos
	git status
 
	Verifica que o arquivo strofonoff.md foi dado como deletado pois foi movido para uma pasta untracked, da pasta e acusa a existencia de um aruivo untracked “receitas/” solicitando add para staged
	4º Mover os aquivos untracked para staged
	git add + nome do aquivo untracked + outros aquivos untracked
 
	5º Verificando situação dos arquivos
	git + status 
	Verifica que os aquivos que estavam untracked agora estão staged e podem ser commitados

	6º Commitando os arquivos
	git commit -m “descrição das alterações”
 
	7º Verificando situação dos arquivos
	git + status
 
	Verifica que os aquivos que estavam staged agora estão  commitados
	8º Criando um arquivo md
	echo > nome do arquivo + extensão
 
	9º Verificando situação dos arquivos
	git + status
 
	Verifica que existe um arquivo untraked

	10º Mover o arquiv par staged
	git add *  obs: * executa para todos os arquivos untracked
 

2.7.	Empurrando arquivos do Git para GitHub

2.7.1.	Primeira configuraçã do Git
	•git config global --user.name “nickname”
	•git config global --user.email “email”

2.7.2.	Alterando e-mail e name
	•git config –global --unset user.name
	•git config --global --unset user.email

2.7.3.	Criando repositório do GitHub

	1º Selecione meus repositórios
 
	2º Clicar em new
 
	3º Informar nome e decrição do repositorio e clique em create
	Obs: defina privado ou publico
 
	4º Gera gerado um link – copie
 
	5º Acesse o Git novamente para informar pra onde o Git ira Uppar os arquivos no GitHub
	git remote add origin + link gerado no GitHub
 
	6º Conferindo – Listando repositórios cadastrados 
 
	7º Upando aruivos do Git par GitHub
	git push origen master
 
	Irá pedir as credenciais
 
	Processo finalizado, aquivos enviados do Git par GitHub






 

 

 

















