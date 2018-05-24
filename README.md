# dockerks8

#Execute esse comando para criar a imagem
docker buid -t hellodocker .

#Para testar local a imagem
docker run -d -p 8080:80 --name mydocker hellodocker

#Acesse no navegado, http://192.168.99.100 é o endereço do meu docker machine(docker toolbox)
http://192.168.99.100:8080/

Depois de criado a imagem, iremos atribuir uma tag para subir para o registry do Google

docker tag hellodocker gcr.io/graceful-fact-190201/hellodocker

Feito isso, faremos o upload no registry do google

Login no google
//docker login -u oauth2accesstoken -p "$(gcloud auth application-default print-access-token)" https://gcr.io

Instalar esse componente
gcloud components install docker-credential-gcr

Execute isso
docker-credential-gcr configure-docker

Execute
docker push gcr.io/graceful-fact-190201/hellodocker

Pronto, imagem upada no registry





docker run -e 'ACCEPT_EULA=Y' -e 'MSSQL_SA_PASSWORD=teste' \
   -p 1401:1433 --name sql1 \
   -d microsoft/mssql-server-linux:2017-latest
   
   
   
   
   
   
   
docker run -e 'ACCEPT_EULA=Y' -e 'MSSQL_SA_PASSWORD=<YourStrong!Passw0rd>' -p 1401:1433 --name sql1 -d microsoft/mssql-server-linux:2017-latest


 