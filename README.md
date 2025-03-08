# mkdocs-iaw

## Creación

Para comenzar vamos a crear una maquina en AWS con "docker" y "docker-compose" para crear nuestra practica en MKdocs, dicha instancia es la siguiente:

![imagen](https://github.com/user-attachments/assets/12eb667d-4d20-4a25-8235-4bfa75ddb8a2)

Una vez tenemos instalado los modulos necesarios vamos a crear una carpeta llamada proyecto donde lanzaremos el comando: ```docker run --rm -it -p 8000:8000 -u $(id -u):$(id -g) -v "$PWD":/docs squidfunk/mkdocs-material new .```. Con él vamos a crear la imagen "material".

Ahora vamos a añadir el archivo "about.md" a la carpeta que se ha creado al lanzar el comando anterior y por ultimo vamos a usar el comando ```docker run --rm -it -p 8000:8000 -u $(id -u):$(id -g) -v "$PWD":/docs squidfunk/mkdocs-material```. Con este pondremos el marcha el contenedor y podremos entrar a la siguiente página:

![imagen](https://github.com/user-attachments/assets/3b55a445-6cc5-4376-b0d1-4f1083d47ff0)
(Ya esta editada porque necesité hacer de nuevo las capturas por un error)

## Editar

Ahora vamos a editar el archivo para personalizarlo y añadir algunas practicas anteriores.

![imagen](https://github.com/user-attachments/assets/eab9380b-046a-4bff-b05d-f7266b2cd87c)

![imagen](https://github.com/user-attachments/assets/7db26073-11ff-4a03-b585-e3508bf38e74)

## Documentación y GitHub Pages

Debemos lanzar el comando ```docker run --rm -it -u $(id -u):$(id -g) -v "$PWD":/docs squidfunk/mkdocs-material build``` el cual nos creara el "site"
Y el comando ```docker run --rm -it -v ~/.ssh:/root/.ssh -v "$PWD":/docs squidfunk/mkdocs-material gh-deploy``` para el "gh_deploy"

## Git Actions

Vamos a configurar un archivo "git-push-mkdocs.yml" para que se realicen unas operaciones al hacer un commit de nuestro repositorio.

Debemos entrar en ```Setting/Actions/General``` para permitir que realice cambios nuestro "build-push-mkdocs.yaml", y una vez hecho eso ya podemos comprobar si funciona en "Actions"

![imagen](https://github.com/user-attachments/assets/6f065c75-95a0-48ec-91ad-1da500bf1aa8)
