# Lista com os principais comandos para terminal linux

| Comando | Função | Observação |
| ------- | ------ | ---------- |
| ```pwd``` | Mostra em qual diretório está o terminal | |
| ```ls``` | Irá listar todos os itens que estão no diretório | |
|```cd [nome-diretorio] ``` | Irá entrar dentro de um diretório | No lugar de [nome-diretorio] você deve colocar o diretório que deseja acessar |
| ```cd ..``` | Irá voltar para o diretório anterior | |
| ```mkdir [nome-novo-diretório]``` | Irá criar um novo diretório dentro do diretório atual | Substituir [nome-novo-diretório] pelo nome que deseja |
| ```[diretorio-ser-excluído] rm -rf``` | Irá excluir o diretório desejado e tudo o que está dentro dele, incluindo sub-diretórios | O comando ```rm``` é para fazer a exclusão, contudo utilizar só esse comando (sem o ```-rf```) irá retornar o erro: ```rm: cannot remove [diretorio-ser-excluído]: Is a directory```.  O parâmetro ```r``` informa ao sistema que o comando deve ser recursivo e o ```f```que o sistema deve forçar a exclusão. Mas cuidado ao utilizar o ```-f``` nos seus comandos|
| ```rmdir [diretorio-ser-excluído]``` | Irá fazer a exclusão de um diretório. | Esse comando não tem a necessidade de utilizar outros parâmetros, basta rodar esse comando para fazer a exclusão do diretório e tudo o que está dentro dele |
| ```cp -r [diretorio-ser-copiado] [diretorio-destino]``` | Esse comando irá copiar um diretório para o outro. | O comando ```-r``` é para informar o sistema que o comando é recursivo, ou seja deve ser copiado tudo o que está dentro do diretório |
| ```cp -r [primeiro-diretorio-ser-copiado] [segundo-diretorio-ser-copiado] [diretorio-destino]``` | Irá copiar dois diretórios para outros diretórios | O último parâmetro do diretório, é sempre o diretório de destino |
| ```mv [diretorio-ser-movido] [diretorio-destino]``` | Esse comando irá mover o diretório de um lugar para o outro | |
| ```mv [primeiro-diretorio-ser-movido] [segundo-diretorio-ser-movido] [diretorio-destino]```| Irá mover dois diretórios para um mesmo diretório | O último parâmetro é sempre o diretório de destino |
| ```find [local-onde-procurar] [critério-busca] [o-que-buscamos]``` | Esse comando irá retornar o local onde está [o-que-buscamos]  | Exemplo prático: ```find ~/workspace -name "foto"```. Aqui estamos fazendo uma consulta na pasta workspace, que está dentro de home (~/), pelo nome do arquivo que deve chamar "foto"
| ```cat [nome].tx```| Esse comando serve para criar um arquivo tx | Não e possível criar com conteúdo dentro do arquivo|
| ```touch [nome].txt``` | Esse comando serve para criar um arquivo txt | Não é possível criar com conteúdo dentro do arquivo |
| ```touch [conteúdo] > [nome].txt``` | Esse comando serve para criar um arquivo txt com algum conteúdo dentro dele | Isso só foi possível porque utilizamos o comando de redirecionamento que é o ```>```. Exemplo: ```touch "Lucas" > my-name.txt``` |
| ```cat [nome-arquivo].txt``` | Esse comando irá ler o arquivo pelo próprio terminal | Porém deve ser informado o nome de um arquivo existente |
| ```rm [nome-arquivo].txt``` | Esse comando irá excluir o arquivo passado por parâmetro | Nesse caso não é necessário utilizar o ```-rf``` pois selecionamos apenas um único arquivo, diferente do diretório que deve excluir tudo o que tem dentro dele |
| ```rm [diretorio/arquivo].txt``` | Esse comando irá excluir um arquivo que está em outro diretório. | Também não é necessário utilizar o ```-rf``` |
| ```rm [nome-arquivo].txt [nome-arquivo-2].txt [nome-arquivo-3].txt ``` | Esse comando irá deletar vários arquivos de uma única vez | Também não é necessário utilizar o ```-rf``` |
| ```cp [nome-arquivo].txt [diretorio-destino]``` | Esse comando irá copiar um arquivo para um outro diretório. | |
| ```cp [nome-arquivo].txt [nome-arquivo-2].txt [diretorio-destino]``` | Esse comando irá fazer a cópia de vários arquivos para o diretório. | O último parâmetro é sempre do diretório de destino | 
| ```mv [nome-arquivo].txt [diretorio-destino]``` | Esse comando irá moer um arquivo para um outro diretório. | |
| ```mv [nome-arquivo].txt [nome-arquivo-2].txt [diretorio-destino]``` | Esse comando irá fmover vários arquivos para o diretório. | O último parâmetro é sempre do diretório de destino | 
| ```head -n 20 [nome-arquivo].txt``` | Esse comando irá fazer a leitura do arquivo pelo próprio terminal | O parâmetro ```-n 20``` informa ao sistema que deverá ser mostrado apenas 20 linhas. O ```head``` informa que deve ser as 20 primeiras linhas, ou seja o início do arquivo |
| ```tail -n 5 [nome-arquivo].txt``` | Esse comando irá fazer a leitura do arquivo pelo próprio terminal| o parâmetro ```-n 5``` informa ao sistema que deverá ser mostrado apenas 5 linhas. O ```tail``` informa que deve ser as 5 últimas linhas, ou seja o final do arquivo |
| ```tail -f [nome-arquivo].txt``` | Esse comando faz a leitura de um arquivo de forma dinâmica | Tudo o que é adiconado no arquivo vai sendo listado no terminal, sendo assim não é necessário rodar o comando novamente para ver o que foi incluído. Muito utilizado para arquivos de logs |
| ```tail -f nome_do_arquivo ** \| grep "busca"**``` | Esse comando irá trazer todas as linhas que contém "busca" | Esse comando também pode ser utilizado com o cat ou o head |