# mkdocs-iaw

## Creación

Para comenzar vamos a crear una maquina en AWS con "docker" y "docker-compose" para crear nuestra practica en MKdocs, dicha instancia es la siguiente:

![imagen](https://github.com/user-attachments/assets/b2b6fdc7-0dd1-4106-bdec-3d3badab9498)

Una vez tenemos instalado los modulos necesarios vamos a crear una carpeta llamada proyecto donde lanzaremos el comando: ```docker run --rm -it -p 8000:8000 -u $(id -u):$(id -g) -v "$PWD":/docs squidfunk/mkdocs-material new .```. Con él vamos a crear la imagen "material".

Ahora vamos a añadir el archivo "about.md" a la carpeta que se ha creado al lanzar el comando anterior y por ultimo vamos a usar el comando ```docker run --rm -it -p 8000:8000 -u $(id -u):$(id -g) -v "$PWD":/docs squidfunk/mkdocs-material```. Con este pondremos el marcha el contenedor y podremos entrar a la siguiente página:

![imagen](https://github.com/user-attachments/assets/ff89ce6b-a957-4bf3-9dfc-8c18de62ba78)

## Editar

Ahora vamos a editar el archivo para personalizarlo y añadir algunas practicas anteriores.

![imagen](https://github.com/user-attachments/assets/4ef4d5e7-5673-48cd-b63e-6411eb83819e)

![imagen](https://github.com/user-attachments/assets/a669793b-4c57-4967-9c4f-a51c23a63213)

## Documentación y GitHub Pages

Debemos lanzar el comando ```docker run --rm -it -u $(id -u):$(id -g) -v "$PWD":/docs squidfunk/mkdocs-material build``` el cual nos creara el "site"
Y el comando ```docker run --rm -it -v ~/.ssh:/root/.ssh -v "$PWD":/docs squidfunk/mkdocs-material gh-deploy``` para el "gh_deploy"

## Git Actions

Vamos a configurar un archivo "git-push-mkdocs.yml" para que se realicen unas operaciones al hacer un commit de nuestro repositorio.

Debemos entrar en ```Setting/Actions/General``` para permitir que realice cambios nuestro "build-push-mkdocs.yaml", y una vez hecho eso ya podemos comprobar si funciona en "Actions"

![imagen](https://github.com/user-attachments/assets/6f065c75-95a0-48ec-91ad-1da500bf1aa8)
