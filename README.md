# Gestion-de-stockage_Docker_Training
Gestion de stockage avec Docker

1-Créer un volume de type volumes.
2-Créer deux conteneurs ubuntu(ubuntu1 et ubuntu2) puis monter le volume crée dans le repertoire /tmp de chacun des conteneurs ubuntu.
3-Créer un fichier toto.txt dans le repertoire /tmp de ubuntu1 et verifier qu'il est bien present dans /tmp de ubuntu2.
4-Créer un conteneur Apache dont le site internet affiché sera celui hébergé ici: https://github.com/startbootstrap/startbootstrap-sb-admin-2 (Utiliser un volume de type bind mount) et n'oublier pas de verifier que le site soit bien accessible.


982  docker volume create --name share
  983  docker run -it --name ubuntu1 -v share:/tmp -d ubuntu /bin/bash 
  984  docker run -it --name ubuntu2 -v share:/tmp -d ubuntu /bin/bash 
  985  docker exec -it ubuntu1 /bin/bash
  986  docker exec -it ubuntu2 /bin/bash
  987  git clone https://github.com/diranetafen/static-website-example.git
  988  ls
  989  docker run --name webserver -p 80:80 -d -v ${PWD}/static-website-example:/usr/local/apache2/htdocs/ httpd
  990  docker ps
  991  docker logs webserver
  992  ls
  993  cd static-website-example
  994  ls
  995  cat index.html
  996  vi index.html
