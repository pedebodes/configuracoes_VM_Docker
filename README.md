## Comandos para configurar ambiente de desenvolvimento Docker utilizando virtualBox - Ubuntu 

### Instalando Docker CE

```python

sudo apt-get install docker.io
sudo apt-get update
sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo apt-get update
sudo apt-get install docker-ce
sudo apt install docker.io
sudo docker run hello-world
```


### Instalando Docker Compose

#### URL <br>
https://linuxize.com/post/how-to-install-and-use-docker-compose-on-ubuntu-18-04/

```python
sudo curl -L "https://github.com/docker/compose/releases/download/1.23.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version
```

### Instalando WordPress via Docker-Compose

```python
mkdir my_app
cd my_app
vim docker-compose.yml

colar o script abaixo 
##################################################
version: '3.3'

services:
  db:
    image: mysql:5.7
    restart: always
    volumes:
      - db_data:/var/lib/mysql
    environment:
      MYSQL_ROOT_PASSWORD: password
      MYSQL_DATABASE: wordpress

  wordpress:
    image: wordpress
    restart: always
    volumes:
      - ./wp_data:/var/www/html
    ports:
      - "8080:80"
    environment:
      WORDPRESS_DB_HOST: db:3306
      WORDPRESS_DB_NAME: wordpress
      WORDPRESS_DB_USER: root
      WORDPRESS_DB_PASSWORD: password
    depends_on:
       - db

volumes:
    db_data:
    wp_data:
##################################################

# iniciar aplicação
docker-compose up -d

# checkar os container em execução
docker-compose ps

#para o container
docker-compose stop

# remove o container
docker-compose down

# remove o container e os volumes
docker-compose down --volumes
```


