# laravel.lndo.site

O objetivo é ter um ambiente de desenvolvimento (LAMP) para projetos em Laravel utilizando Docker + Lando. Com isso não será mais necessário ter Apache, MySql e PHP instalados no desktop de desenvolvimento.

## Uso

Certifique-se de ter instalados o lando e o docker

Caso não tenha, siga os passos nos links abaixo:

Docker: https://docs.docker.com/engine/install/ubuntu/ e após a instalação: https://docs.docker.com/engine/install/linux-postinstall/

Lando: https://docs.lando.dev/basics/installation.html#linux

Reinicie

Clone o seu projeto Laravel como de costume

### Baixe os arquivos deste repositório para a raiz do seu projeto

Note que o .gitignore vai substituir o do projeto. Isso é para que os arquivos do Lando não sejam versionados em seu projeto. Você pode optar em incluir no .gitignore do seu projeto ou se preferir pode deixar que os arquivos sejam versionados.

Note que no arquivo .lando.yml você pode optar por exemplo pela versão do PHP, versão do Composer ou pelo servidor de Web utilizado, Apache ou Ngix

### Configure o .env do projeto

Para as credenciais MySQL utilize:

```bash
DB_CONNECTION=mysql
DB_HOST=database
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=laravel
DB_PASSWORD=laravel
```

### Comandos

#### Se existe o container destrói e recompila
```bash
lando destroy -y && lando rebuild -y
```

#### Composer install no projeto
```bash
lando composer install
```

#### Gera a key do projeto
```bash
lando php artisan key:generate
```

#### Roda as migrations do projeto
```bash
lando php artisan migrate
```

#### Só para testar o override de configurações php no arquivo php.ini
```bash
lando php -i | grep upload_max_filesize
```

#### Se reiniciar o pc
```bash
lando start
```

#### Informações do container
```bash
lando info
```

## Sobre o Lando

O Lando também possui outros comandos de acordo com o recipiente utilizado, Ex. LAMP, https://docs.lando.dev/config/lamp.html#tooling

O Lando possui recipientes para outros Frameworks (Symfony) e CMS's (Drupal e Wordpress), https://docs.lando.dev/config/recipes.html#supported-recipes

## Endereço do projeto
https://laravel.lndo.site

## Se usa senha única pode-se cadastrar um oauth consumidor respondendo no endereço 
https://laraval.lndo.site/callback 

Dessa forma seus projetos dev com senha única podem utilizar o mesmo oauth consumidor

