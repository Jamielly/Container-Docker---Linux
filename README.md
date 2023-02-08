# Container-Docker---Linux
Demonstre e explique a criação de um contêiner docker com uma distro linux pura, a ser escolhida no docker hub. 


Criar um video que demonstre e explique a criação de um contêiner docker com uma distro linux pura, a ser escolhida no docker hub. O conteiner deve ter um volume mapeado e, nesse volume deve ter 10 arquivos texto com conteúdo de 1 linha cada um, com nomes definidos por você e, em um comando docker exec, deve-se exibir o conteúdo do volume mapeado no contêiner. NÃO SE DEVE acessar o arquivo por dentro do contêiner. O vídeo deve ter até 10 minutos

https://www.youtube.com/watch?v=wzxG8iY2E0Q

------------------------------------------------------------------------------------------------
Artigo de minha autoria publicado na plataforma DIO( Digtal Innovation One) que pode contém mais informações:


Aqui estão os comandos básicos do Docker que são importantes para trabalhar com volumes mapeados:

docker run: Usado para iniciar uma nova instância de um container Docker. Você pode especificar a montagem do volume com o argumento -v.
docker inspect: Usado para exibir informações detalhadas sobre um container ou imagem, incluindo informações sobre volumes mapeados.
docker volume create: Usado para criar um novo volume Docker.
docker volume ls: Usado para listar todos os volumes Docker existentes.
docker volume rm: Usado para excluir um volume Docker.


Em resumo, esses são os comandos que permitem que você gerencie os volumes mapeados e interaja com eles ao iniciar, inspecionar, criar, listar e excluir volumes Docker.



🔸Comandos com maior detalhamento:

Dentro do Docker playground (link disponível no fim deste artigo) realiza-se os seguintes comandos:



docker pull ubuntu : Usado para baixar um contêiner.

docker ps -a  : Usado para verificar se o contêiner está ativo.

docker volume ls  : Indica os volumes presentes.

docker volume create ubuntu-01 : Usado para criar um volume.



docker run -dt --name ubuntu-vol -e UBUNTU_ROOT_PASSWORD=root -v ubuntu-01:/tmp/aula-volume  : Usado para mapear um volume e ativar o contêiner em um único comando.



sudo ls /var/lib/docker/volumes  : Usado para lista o caminho dos volumes. 

docker inspect ubuntu-vol : Função de identificar em que local está cada componente.



docker rm (ID) OU docker volume prune : Usado para remover/apagar o volume. 



docker exec -it ubuntu-vol /bin/bash : Usado para entrar no terminal do volume.



🔸 Comandos dentro do volume no terminal: -----------------------------------------------------

 ls  : Usado para ver os diretórios presentes.

cd  : Usado para entrar em um diretório.



cd tmp  : Local onde é possível encontrar o aula-volume.

cd aula-volume/ : Entrar na pasta aula-volume.



🔸 Dentro da pasta aula-volume: ---------------------------------------------------------------------

 echo "Testando vol" >> teste.txt : Indica que é um arquivo de texto que vai possuir a frase testando vol como conteúdo.



cat teste.txt : Informa o conteúdo do txt.

exit : Usado para sair do modo diretório do volume atual.

------------------------------------------------------------------------------------------------------------------

+ +Extra:

Para mudar o conteúdo do txt:

sudo vim /var/lib/docker/volumes/ubuntu-vol/_data/teste.txt



Clicando a tecla i do teclado é possível editar.

Para sair e salvar o conteúdo ( : ) - dois pontos e wq (salvar e sair) 

------

⭐Para mais informações:

Links importantes:

DOCKER PLAYGROUND: https://labs.play-with-docker.com/

DOCKER HUB: https://hub.docker.com/_/ubuntu


😊 Meu vídeo aula sobre o assunto:

https://www.youtube.com/watch?v=wzxG8iY2E0Q
