## Comandos para configurar ambiente de desenvolvimento Docker utilizando virtualBox - Ubuntu 

### Instalando Docker Compose

####URL
https://linuxize.com/post/how-to-install-and-use-docker-compose-on-ubuntu-18-04/

```python
sudo curl -L "https://github.com/docker/compose/releases/download/1.23.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version


