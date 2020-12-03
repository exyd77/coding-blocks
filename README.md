# coding-blocks
Notebook markdown and code blocks


📒
docker




Moodle
Devoir 7
Main


## Code blocks
### bash

```bash
#!/bin/bash


```

## Dockerfile

```Dockerfile

```

## shell
- NEW

```shell
#!/bin/sh

```

#!/bin/sh
#repository par defaut
repository="C://Users/kevin/Desktop/repository/TP2/"
#chemin du Dockerfile
pathfile="`pwd`/203-tp2/the-littlest-jupyterhub/integration-tests/"
# code permanent
codepermanent="couk09028908"
#nom de l'image
imgname="couk09028908:tp"
#nom container
contname="couk09028908tp"
# dossier donner dans le container (mount point)
datadir="/inf1070"
#dossier donnees sur machine locale
datasrc=`pwd`/../

[ -d $repository ] && cd "$repository" && \
[ -d $pathfile ] && cd "$pathfile" && \
echo "Le chemin actuel: `pwd`"
#!/bin/sh
# script de creation et demarrage de container
# specialement conçu pour les lab du cours INF1070
# nom image
imgname="couk08028908:tp"
#nom container
contname="couk08028908"
# dossier donner dans le container (mount point)
datadir="/inf1070"
#dossier donnees sur machine locale
datasrc=`pwd`/../

codepermanent="couk08028908"

# Créer image si elle n'existe pas

if [[ "$(docker images -q $imgname 2> /dev/null)" == "" ]]; then
  # Image n'existe pas
  echo "Création image inf1070 ..." && \
  echo "Nécessite une connexion Internet" && \
  cp "203-tp2\the-littlest-jupyterhub\integration-tests\Dockerfile" "203-tp2\the-littlest-jupyterhub\integration-tests\Dockerfilecouk08028908" && \
  docker build -t "$imgname" -f Dockerfilecouk08028908 . && \
  echo "Image $imgname cree avec succes"
fi

# Créer container si n'existe pas

if [[ "$(docker ps -aq -f name=$contname$ 2>/dev/null)" == "" ]]; then
  #
  # container n'existe pas
  echo "creation container .. " && \
  docker create -it --mount src="$datasrc",target="$datadir",type=bind \
    -p 127.0.0.1:8069:8069 --name "$contname" "$imgname" && \
  echo "contenaire $contname créé"
else
  echo "container $contname est déjà demarré ..."
fi

# démarrage du container

if [[ "$(docker ps -q -f name=$contname$ 2>/dev/null)" == "" ]]; then
    #
    echo "démarrage du container ..." &&\
    docker container start  "$contname" && \
    echo "container $contname  démarré"
fi

# connexion sur le contenair

if [[ "$(docker ps -q -f name=$contname$ 2>/dev/null)" != "" ]]; then
    echo "connexion au contenair ..." &&\
    echo " le dossier $datasrc sera accessible " &&\
    echo "dans le dossier $datadir du container " && \
    echo "pour se deconnecter, tapez la commande: exit"&& \
    #docker exec -it "$contname" /bin/bash
    docker container  exec -it -u "$codepermanent" "$contname" /bin/bash
else
   echo "Impossible de se connecter"
   echo "Vérifier que le container $contname est démarré"
fi


# docker run -it --mount src=`pwd`/../,target=/inf1070,type=bind \
# -p 127.0.0.1:8069:8069 --name inf1070lab inf1070:lab

# docker inspect -f {{.State.Running}} $CONTAINER_ID
#!/bin/sh
#chemin du Dockerfile
pathfile="`pwd`/203-tp2/the-littlest-jupyterhub/integration-tests/"
# code permanent
codepermanent="couk09028908"
#nom de l'image
imgname="couk09028908:tp"
#nom container
contname="couk09028908"
# dossier donner dans le container (mount point)
datadir="/inf1070"
#dossier donnees sur machine locale
datasrc=`pwd`/../

[ -d $pathfile ] && cd "$pathfile"

Dockerfile$codepermanent
#directory
directory="C:\Users\kevin\Desktop\repository\TP2"
#chemin du Dockerfile
pathfile="`pwd`/203-tp2/the-littlest-jupyterhub/integration-tests/"
# code permanent
codepermanent="couk09028908"
#nom de l'image
imgname="couk09028908:tp"
#nom container
contname="couk09028908"
# dossier donner dans le container (mount point)
datadir="/inf1070"
#dossier donnees sur machine locale
datasrc=`pwd`/../

[ -d $directory ] && cd "$directory" && \
[ -d $pathfile ] && cd "$pathfile" && \
echo "`pwd`"
#!/bin/sh
#repository par defaut
repository="C://Users/kevin/Desktop/repository/TP2"
#chemin du Dockerfile
pathfile="`pwd`/203-tp2/the-littlest-jupyterhub/integration-tests/"
# code permanent
codepermanent="couk09028908"
#nom de l'image
imgname="couk09028908:tp"
#nom container
contname="couk09028908tp"
# dossier donner dans le container (mount point)
datadir="/inf1070"
#dossier donnees sur machine locale
datasrc=`pwd`/../

[ -d $repository ] && cd "$repository" && \
[ -d $pathfile ] && cd "$pathfile"

echo "Le chemin actuel: `pwd`"

# Créer image si elle n'existe pas

if [[ "$(docker images -q $imgname 2> /dev/null)" == "" ]]; then
  # Image n'existe pas
  [ -d $repository ] && cd "$repository" && \
[ -d $pathfile ] && cd "$pathfile"

echo "Le chemin actuel: `pwd`"
  echo "Création image couk09028908 ..." && \
  echo "Nécessite une connexion Internet" &&\
  docker build -t "$imgname" -f "Dockerfilecouk09028908" . && \
  echo "Image $imgname cree avec succes"
fi

# Créer container si n'existe pas

if [[ "$(docker ps -aq -f name=$contname$ 2>/dev/null)" == "" ]]; then
  #
  # container n'existe pas
  echo "creation container .. " && \
  docker create -it --mount src="$datasrc",target="$datadir",type=bind \
    -p 127.0.0.1:8069:8069 --name "$contname" "$imgname" && \
  echo "contenaire $contname créé"
else
  echo "container $contname est déjà demarré ..."
fi

# démarrage du container

if [[ "$(docker ps -q -f name=$contname$ 2>/dev/null)" == "" ]]; then
    #
    echo "démarrage du container ..." &&\
    docker container start  "$contname" && \
    echo "container $contname  démarré"
fi

# connexion sur le contenair

if [[ "$(docker ps -q -f name=$contname$ 2>/dev/null)" != "" ]]; then
    echo "connexion au contenair ..." &&\
    echo " le dossier $datasrc sera accessible " &&\
    echo "dans le dossier $datadir du container " && \
    echo "pour se deconnecter, tapez la commande: exit"&& \
    #docker exec -it "$contname" /bin/bash
    docker container  exec -it -u kevin "$contname" /bin/bash
else
   echo "Impossible de se connecter"
   echo "Vérifier que le container $contname est démarré"
fi

# docker run -it --mount src=`pwd`/../,target=/inf1070,type=bind \
# -p 127.0.0.1:8069:8069 --name inf1070lab inf1070:lab

# docker inspect -f {{.State.Running}} $CONTAINER_ID
#!/bin/sh
#repository par defaut
repository="C://Users/kevin/Desktop/repository/TP2/"
#chemin du Dockerfile
pathfile="`pwd`/203-tp2/the-littlest-jupyterhub/integration-tests/"
# code permanent
codepermanent="couk09028908"
#nom de l'image
imgname="couk09028908:tp"
#nom container
contname="couk09028908tp"
# dossier donner dans le container (mount point)
datadir="/inf1070"
#dossier donnees sur machine locale
datasrc=`pwd`/../

[ -d $repository ] && cd "$repository" && \
[ -d $pathfile ] && cd "$pathfile" && \
echo "Le chemin actuel: `pwd`"
#!/bin/sh
# script de creation et demarrage de container
# specialement conçu pour les lab du cours INF1070
# nom image
imgname="couk08028908:tp"
#nom container
contname="couk08028908"
# dossier donner dans le container (mount point)
datadir="/inf1070"
#dossier donnees sur machine locale
datasrc=`pwd`/../

codepermanent="couk08028908"

# Créer image si elle n'existe pas

if [[ "$(docker images -q $imgname 2> /dev/null)" == "" ]]; then
  # Image n'existe pas
  echo "Création image inf1070 ..." && \
  echo "Nécessite une connexion Internet" && \
  cp "203-tp2\the-littlest-jupyterhub\integration-tests\Dockerfile" "203-tp2\the-littlest-jupyterhub\integration-tests\Dockerfilecouk08028908" && \
  docker build -t "$imgname" -f Dockerfilecouk08028908 . && \
  echo "Image $imgname cree avec succes"
fi

# Créer container si n'existe pas

if [[ "$(docker ps -aq -f name=$contname$ 2>/dev/null)" == "" ]]; then
  #
  # container n'existe pas
  echo "creation container .. " && \
  docker create -it --mount src="$datasrc",target="$datadir",type=bind \
    -p 127.0.0.1:8069:8069 --name "$contname" "$imgname" && \
  echo "contenaire $contname créé"
else
  echo "container $contname est déjà demarré ..."
fi

# démarrage du container

if [[ "$(docker ps -q -f name=$contname$ 2>/dev/null)" == "" ]]; then
    #
    echo "démarrage du container ..." &&\
    docker container start  "$contname" && \
    echo "container $contname  démarré"
fi

# connexion sur le contenair

if [[ "$(docker ps -q -f name=$contname$ 2>/dev/null)" != "" ]]; then
    echo "connexion au contenair ..." &&\
    echo " le dossier $datasrc sera accessible " &&\
    echo "dans le dossier $datadir du container " && \
    echo "pour se deconnecter, tapez la commande: exit"&& \
    #docker exec -it "$contname" /bin/bash
    docker container  exec -it -u "$codepermanent" "$contname" /bin/bash
else
   echo "Impossible de se connecter"
   echo "Vérifier que le container $contname est démarré"
fi


# docker run -it --mount src=`pwd`/../,target=/inf1070,type=bind \
# -p 127.0.0.1:8069:8069 --name inf1070lab inf1070:lab

# docker inspect -f {{.State.Running}} $CONTAINER_ID
#!/bin/sh
#chemin du Dockerfile
pathfile="`pwd`/203-tp2/the-littlest-jupyterhub/integration-tests/"
# code permanent
codepermanent="couk09028908"
#nom de l'image
imgname="couk09028908:tp"
#nom container
contname="couk09028908"
# dossier donner dans le container (mount point)
datadir="/inf1070"
#dossier donnees sur machine locale
datasrc=`pwd`/../

[ -d $pathfile ] && cd "$pathfile"

Dockerfile$codepermanent
#directory
directory="C:\Users\kevin\Desktop\repository\TP2"
#chemin du Dockerfile
pathfile="`pwd`/203-tp2/the-littlest-jupyterhub/integration-tests/"
# code permanent
codepermanent="couk09028908"
#nom de l'image
imgname="couk09028908:tp"
#nom container
contname="couk09028908"
# dossier donner dans le container (mount point)
datadir="/inf1070"
#dossier donnees sur machine locale
datasrc=`pwd`/../

[ -d $directory ] && cd "$directory" && \
[ -d $pathfile ] && cd "$pathfile" && \
echo "`pwd`"
#!/bin/sh
#repository par defaut
repository="C://Users/kevin/Desktop/repository/TP2"
#chemin du Dockerfile
pathfile="`pwd`/203-tp2/the-littlest-jupyterhub/integration-tests/"
# code permanent
codepermanent="couk09028908"
#nom de l'image
imgname="couk09028908:tp"
#nom container
contname="couk09028908tp"
# dossier donner dans le container (mount point)
datadir="/inf1070"
#dossier donnees sur machine locale
datasrc=`pwd`/../

[ -d $repository ] && cd "$repository" && \
[ -d $pathfile ] && cd "$pathfile"

echo "Le chemin actuel: `pwd`"

# Créer image si elle n'existe pas

if [[ "$(docker images -q $imgname 2> /dev/null)" == "" ]]; then
  # Image n'existe pas
  [ -d $repository ] && cd "$repository" && \
[ -d $pathfile ] && cd "$pathfile"

echo "Le chemin actuel: `pwd`"
  echo "Création image couk09028908 ..." && \
  echo "Nécessite une connexion Internet" &&\
  docker build -t "$imgname" -f "Dockerfilecouk09028908" . && \
  echo "Image $imgname cree avec succes"
fi

# Créer container si n'existe pas

if [[ "$(docker ps -aq -f name=$contname$ 2>/dev/null)" == "" ]]; then
  #
  # container n'existe pas
  echo "creation container .. " && \
  docker create -it --mount src="$datasrc",target="$datadir",type=bind \
    -p 127.0.0.1:8069:8069 --name "$contname" "$imgname" && \
  echo "contenaire $contname créé"
else
  echo "container $contname est déjà demarré ..."
fi

# démarrage du container

if [[ "$(docker ps -q -f name=$contname$ 2>/dev/null)" == "" ]]; then
    #
    echo "démarrage du container ..." &&\
    docker container start  "$contname" && \
    echo "container $contname  démarré"
fi

# connexion sur le contenair

if [[ "$(docker ps -q -f name=$contname$ 2>/dev/null)" != "" ]]; then
    echo "connexion au contenair ..." &&\
    echo " le dossier $datasrc sera accessible " &&\
    echo "dans le dossier $datadir du container " && \
    echo "pour se deconnecter, tapez la commande: exit"&& \
    #docker exec -it "$contname" /bin/bash
    docker container  exec -it -u kevin "$contname" /bin/bash
else
   echo "Impossible de se connecter"
   echo "Vérifier que le container $contname est démarré"
fi

# docker run -it --mount src=`pwd`/../,target=/inf1070,type=bind \
# -p 127.0.0.1:8069:8069 --name inf1070lab inf1070:lab

# docker inspect -f {{.State.Running}} $CONTAINER_ID

code
#!/bin/sh
#repository par defaut
repository="C://Users/kevin/Desktop/repository/TP2/"
#chemin du Dockerfile
pathfile="`pwd`/203-tp2/the-littlest-jupyterhub/integration-tests/"
# code permanent
codepermanent="couk09028908"
#nom de l'image
imgname="couk09028908:tp"
#nom container
contname="couk09028908tp"
# dossier donner dans le container (mount point)
datadir="/inf1070"
#dossier donnees sur machine locale
datasrc=`pwd`/../

[ -d $repository ] && cd "$repository" && \
[ -d $pathfile ] && cd "$pathfile" && \
echo "Le chemin actuel: `pwd`"
#!/bin/sh
# script de creation et demarrage de container
# specialement conçu pour les lab du cours INF1070
# nom image
imgname="couk08028908:tp"
#nom container
contname="couk08028908"
# dossier donner dans le container (mount point)
datadir="/inf1070"
#dossier donnees sur machine locale
datasrc=`pwd`/../

codepermanent="couk08028908"

# Créer image si elle n'existe pas

if [[ "$(docker images -q $imgname 2> /dev/null)" == "" ]]; then
  # Image n'existe pas
  echo "Création image inf1070 ..." && \
  echo "Nécessite une connexion Internet" && \
  cp "203-tp2\the-littlest-jupyterhub\integration-tests\Dockerfile" "203-tp2\the-littlest-jupyterhub\integration-tests\Dockerfilecouk08028908" && \
  docker build -t "$imgname" -f Dockerfilecouk08028908 . && \
  echo "Image $imgname cree avec succes"
fi

# Créer container si n'existe pas

if [[ "$(docker ps -aq -f name=$contname$ 2>/dev/null)" == "" ]]; then
  #
  # container n'existe pas
  echo "creation container .. " && \
  docker create -it --mount src="$datasrc",target="$datadir",type=bind \
    -p 127.0.0.1:8069:8069 --name "$contname" "$imgname" && \
  echo "contenaire $contname créé"
else
  echo "container $contname est déjà demarré ..."
fi

# démarrage du container

if [[ "$(docker ps -q -f name=$contname$ 2>/dev/null)" == "" ]]; then
    #
    echo "démarrage du container ..." &&\
    docker container start  "$contname" && \
    echo "container $contname  démarré"
fi

# connexion sur le contenair

if [[ "$(docker ps -q -f name=$contname$ 2>/dev/null)" != "" ]]; then
    echo "connexion au contenair ..." &&\
    echo " le dossier $datasrc sera accessible " &&\
    echo "dans le dossier $datadir du container " && \
    echo "pour se deconnecter, tapez la commande: exit"&& \
    #docker exec -it "$contname" /bin/bash
    docker container  exec -it -u "$codepermanent" "$contname" /bin/bash
else
   echo "Impossible de se connecter"
   echo "Vérifier que le container $contname est démarré"
fi


# docker run -it --mount src=`pwd`/../,target=/inf1070,type=bind \
# -p 127.0.0.1:8069:8069 --name inf1070lab inf1070:lab

# docker inspect -f {{.State.Running}} $CONTAINER_ID
#!/bin/sh
#chemin du Dockerfile
pathfile="`pwd`/203-tp2/the-littlest-jupyterhub/integration-tests/"
# code permanent
codepermanent="couk09028908"
#nom de l'image
imgname="couk09028908:tp"
#nom container
contname="couk09028908"
# dossier donner dans le container (mount point)
datadir="/inf1070"
#dossier donnees sur machine locale
datasrc=`pwd`/../

[ -d $pathfile ] && cd "$pathfile"

Dockerfile$codepermanent
#directory
directory="C:\Users\kevin\Desktop\repository\TP2"
#chemin du Dockerfile
pathfile="`pwd`/203-tp2/the-littlest-jupyterhub/integration-tests/"
# code permanent
codepermanent="couk09028908"
#nom de l'image
imgname="couk09028908:tp"
#nom container
contname="couk09028908"
# dossier donner dans le container (mount point)
datadir="/inf1070"
#dossier donnees sur machine locale
datasrc=`pwd`/../

[ -d $directory ] && cd "$directory" && \
[ -d $pathfile ] && cd "$pathfile" && \
echo "`pwd`"
#!/bin/sh
#repository par defaut
repository="C://Users/kevin/Desktop/repository/TP2"
#chemin du Dockerfile
pathfile="`pwd`/203-tp2/the-littlest-jupyterhub/integration-tests/"
# code permanent
codepermanent="couk09028908"
#nom de l'image
imgname="couk09028908:tp"
#nom container
contname="couk09028908tp"
# dossier donner dans le container (mount point)
datadir="/inf1070"
#dossier donnees sur machine locale
datasrc=`pwd`/../

[ -d $repository ] && cd "$repository" && \
[ -d $pathfile ] && cd "$pathfile"

echo "Le chemin actuel: `pwd`"

# Créer image si elle n'existe pas

if [[ "$(docker images -q $imgname 2> /dev/null)" == "" ]]; then
  # Image n'existe pas
  [ -d $repository ] && cd "$repository" && \
[ -d $pathfile ] && cd "$pathfile"

echo "Le chemin actuel: `pwd`"
  echo "Création image couk09028908 ..." && \
  echo "Nécessite une connexion Internet" &&\
  docker build -t "$imgname" -f "Dockerfilecouk09028908" . && \
  echo "Image $imgname cree avec succes"
fi

# Créer container si n'existe pas

if [[ "$(docker ps -aq -f name=$contname$ 2>/dev/null)" == "" ]]; then
  #
  # container n'existe pas
  echo "creation container .. " && \
  docker create -it --mount src="$datasrc",target="$datadir",type=bind \
    -p 127.0.0.1:8069:8069 --name "$contname" "$imgname" && \
  echo "contenaire $contname créé"
else
  echo "container $contname est déjà demarré ..."
fi

# démarrage du container

if [[ "$(docker ps -q -f name=$contname$ 2>/dev/null)" == "" ]]; then
    #
    echo "démarrage du container ..." &&\
    docker container start  "$contname" && \
    echo "container $contname  démarré"
fi

# connexion sur le contenair

if [[ "$(docker ps -q -f name=$contname$ 2>/dev/null)" != "" ]]; then
    echo "connexion au contenair ..." &&\
    echo " le dossier $datasrc sera accessible " &&\
    echo "dans le dossier $datadir du container " && \
    echo "pour se deconnecter, tapez la commande: exit"&& \
    #docker exec -it "$contname" /bin/bash
    docker container  exec -it -u kevin "$contname" /bin/bash
else
   echo "Impossible de se connecter"
   echo "Vérifier que le container $contname est démarré"
fi

# docker run -it --mount src=`pwd`/../,target=/inf1070,type=bind \
# -p 127.0.0.1:8069:8069 --name inf1070lab inf1070:lab

# docker inspect -f {{.State.Running}} $CONTAINER_ID
unnamed_dlvfsklhq.md

Create
#!/bin/sh
#chemin du Dockerfile
pathfile="`pwd`/203-tp2/the-littlest-jupyterhub/integration-tests"

[ -d 203-tp2 ] || git clone https://gitlab.info.uqam.ca/inf1070/203-tp2.git

if [[ "(ls -R $pathfile | grep 'Dockerfilecouk09028908' == "")" ]]; then
    cp "$pathfile\Dockerfile" "$pathfile\Dockerfilecouk09028908" && \
    echo "Le Dockerfilecouk08028908 a ete creer" || \
	echo "existe deja"
else 
    echo "existe deja"
fi


Create
#!/bin/sh
#chemin du Dockerfile
pathfile="`pwd`/203-tp2/the-littlest-jupyterhub/integration-tests"

[ -d 203-tp2 ] || git clone https://gitlab.info.uqam.ca/inf1070/203-tp2.git

if [[ "(ls -R $pathfile | grep 'Dockerfilecouk09028908' == "")" ]]; then
    cp "$pathfile\Dockerfile" "$pathfile\Dockerfilecouk09028908" && \
    echo "Le Dockerfilecouk08028908 a ete creer" || \
	echo "existe deja"
else 
    echo "existe deja"
fi
