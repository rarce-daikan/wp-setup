# Wordpress setup
Wordpress development enviroment docker setup

First off clone the repository with the stack information

```shell
git clone https://github.com/rarce-daikan/wp-setup.git wp-setup
```

Download a theme to the directory

```shell
git clone https://github.com/nilovelez/intentionally-blank.git wp-setup/intentionally-blank
```

To start the stack

```shell
sudo docker-compose wp-setup/wordpress-stack.yml up
```
The previous command will generate 2 containers, each with a specific name/id, you could find the container id/name with the command 'sudo docker ps'

Copy the downloaded theme to the wordpress container

```shell
sudo docker cp wp-setup/intentionally-blank  [container name/id]:/var/www/html/wp-content/themes/
```

Once finished, you may dispose of the containers with the following command

```shell
sudo docker-compose -f wp-setup/wordpress-stack.yml down
```

Using [Intentionally blank theme](https://github.com/nilovelez/intentionally-blank) for testing

[More infomation](https://hub.docker.com/_/wordpress) regarding wordpress container
