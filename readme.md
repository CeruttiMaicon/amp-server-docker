# AMP server para desenvolvimentos locais em Linux (Linux Mint/Ubuntu)

Ele instala as maquinas locais contendo o PHP(uma imagem com a versão 5.6 e outra com a 7.2), Apache, Mysql and PHPMyadmin usando o Docker Composer.

## Etapa 1:

Execute (este comando baixa apenas o container com o portainer)
```
docker run -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock portainer/portainer
```
ou (executa todos os comandos necessários que estão descritos dentro do projeto)
```
/bin/bash portainer.sh
```
you'll be able to access localhost:9000 to acess [Portainer](https://www.portainer.io/) <<< nice tool >>>

### Etapa 2:

Acesse a pasta ./php_7_2 fe execute (as portas 80, 5080, 6080 serão utilizadas a partir de agora no computador local):

```
docker-compose up -d
```

Você pode executar os mesmos comandos na pasta ./php_5_6 para obter a outra versão do PHP

### Etapa 3:

Resultados:

- http://localhost/ usando php 7.2
- http://localhost:5080/ usando php 5.6
- http://localhost:6080/ usando PHPMyadmin
- http://localhost:9000/ para acessar a ferramenta Portainer e gerenciar contêineres
- Para acessar o mysql use o container MYSQL ip, user: root e password: teste123

Tudo em sua máquina local:

- seus bancos de dados serão salvos em sua pasta local ./data
- sua configuração do php.ini pode ser adicionada na pasta ./php-ini
- seus arquivos php podem ser adicionados na pasta ./www
