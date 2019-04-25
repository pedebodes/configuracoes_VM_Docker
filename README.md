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



### Instalando Docker Compose

#### URL <br>
https://linuxize.com/post/how-to-install-and-use-docker-compose-on-ubuntu-18-04/

```python
sudo curl -L "https://github.com/docker/compose/releases/download/1.23.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version


