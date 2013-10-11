---

layout: bright

author:
    name: Adán Lobato
    company:
        name: SocialPoint

style: |

    .code-small code {
        font-size: 60%;
        line-height: 1.2 !important;
    }

    .code-medium code {
        font-size: 70%;
        line-height: 1.5 !important;
    }

    #Cover h2 {
        margin:30% 0 0;
        color:#FFF;
        text-align:right;
        font-size:100px;
        text-shadow: 2px 2px 2px #000;
    }

    #Cover p {
        margin:10px 0 0;
        text-align:right;
        color:#FFF;
        font-style:italic;
        font-size:50px;
        text-shadow: 1px 1px 5px #000;
    }

    p.semantic-versioning {
        text-align: center;
        font-size: 90px;
        margin-bottom: 0;
    }

    p.centered {
        text-align: center;
    }

    #instaladores-oficiales ul {
        margin-bottom: 0;
    }

    #bottlenecks {
        background-color: #dd3333;
    }

    #pictureslogo-composer-transparentpng {
        text-align: center;
    }
---

# Composer {#Cover}

*Dependency management for PHP*

![](pictures/dj-headphones-wallpaperakg-dj-headphones-wallpaper-wallpapers-f8paiy2d.jpg)

## What's up!

- Soy `Adán Lobato`
- Soy `de Barcelona`
- Soy `software developer`
- Trabajo `en SocialPoint`
- Mi twitter es `@adanlobato`

…**¡Interrumpidme cuando queráis!**

## Agenda

- Composer Basics
- Mastering Composer
- Bottlenecks
- Enlaces de interés
- ¿Preguntas?

## **Composer Basics**

## ¿Qué es Composer?

<figure markdown="1">

Es una herramienta que nos permite definir cuáles son las librerías de las que depende nuestro proyecto y las instala por nosotros.

<figcaption>Jordi Boggiano (@seldaek)</figcaption>
</figure>

## ¿Es un concepto nuevo?

- En **python** existe `pip`
- …En **javascript** existe `npm`
- …En **ruby** existe `bundler`
- …En **php** existe... ¿`PEAR`/`Pyrus`?

## ![](pictures/logo-composer-transparent.png)

## ¿Alternativas en PHP?

|                   |PEAR      |Pyrus          |Composer    |
+-------------------|----------|---------------|------------+
|* Instalación *    |Global    |Global/Local   |Global*/Local|
|* Package types *  |Dist      |Dist           |Dist/Source |
|* PEAR support *   |Yes       |Yes            |Yes         |
|* VCS support *    |No        |No             |Yes         |

(*) Only CLI applications

## **Instalación**

## Instalación

    curl -S <mark>http://getcomposer.org/installer</mark> | php

## Instalación

    $ php composer.phar
    <mark>   ______</mark>
    <mark>  / ____/___  ____ ___  ____  ____  ________  _____</mark>
    <mark> / /   / __ \/ __ `__ \/ __ \/ __ \/ ___/ _ \/ ___/</mark>
    <mark>/ /___/ /_/ / / / / / / /_/ / /_/ (__  )  __/ /</mark>
    <mark>\____/\____/_/ /_/ /_/ .___/\____/____/\___/_/</mark>
    <mark>                    /_/</mark>
    Composer version 3da05c68f9561fa822c522b1815435ff990493ff 2013-10-02 14:25:06

    <mark class="important">Usage:</mark>
      [options] command [arguments]

    <mark class="important">Available commands:</mark>
    <mark>  init</mark>             Creates a basic composer.json file in current directory.
    <mark>  install</mark>          Installs the project dependencies from the composer.lock file...
    <mark>  require</mark>          Adds required packages to your composer.json and installs them
    <mark>  search</mark>           Search for packages
    <mark>  self-update</mark>      Updates composer.phar to the latest version.
    <mark>  show</mark>             Show information about packages
    <mark>  status</mark>           Show a list of locally modified packages
    <mark>  update</mark>           Updates your dependencies to the latest version according to...
    <mark>  validate</mark>         Validates a composer.json
{:.code-small}

## Instalación {#installation-3}

    $ sudo mv composer.phar /usr/local/bin/composer
    …$ sudo chmod +x /usr/local/bin
    …$ sudo composer self-update

## **Primeros pasos**

## Instalando dependencias

    $ composer <mark>require</mark> <mark class="important">twig/twig</mark> <mark class="important">"1.*"</mark>

## Instalando dependencias

{:.semantic-versioning}
2.0.1

## Instalando dependencias

{:.semantic-versioning}
2.0.*

## Instalando dependencias

{:.semantic-versioning}
\>=2.1,<3.0

## Instalando dependencias

{:.semantic-versioning}
~2.1

## Analizando el resultado

    $ tree -L 3
    ├── composer.json
    ├── composer.lock
    └── <mark>vendor</mark>
        ├── autoload.php
        ├── <mark>composer</mark>
        │   ├── ClassLoader.php
        │   ├── autoload_classmap.php
        │   ├── autoload_namespaces.php
        │   ├── autoload_real.php
        │   └── installed.json
        └── <mark>twig</mark>
            └── <mark>twig</mark>
{:.code-medium}

## composer.json

    {
        <mark>"require"</mark>: {
            <mark class="important">"twig/twig"</mark>: <mark class="important">"1.*"</mark>
        }
    }

## composer.lock

- Si existe, reemplaza a composer.json
- …*Congela* nuestras dependencias a una versión concreta
- …Permite que todo el equipo trabaje/testee sobre las mismas versiones
- …Imprescindible para deployments
- …**Debe** estar commiteado en el VCS de nuestro proyecto
- …Para actualizarlo: `composer update`

## Autoloading

    <?php
    require_once __DIR__.'/vendor/autoload.php';




    <mark class="comment">// Your code</mark>

## Autoloading

    <?php
    $loader = require_once __DIR__.'/vendor/autoload.php';
    …$loader->add('My\\Namespace', array('src'));
    …$loader->add('My_Namespace', array('src', 'lib'));
    …$loader->addClassmap($classmap);

    <mark class="comment">// Your code</mark>

## **Repositorios**

## Packagist

- Repositorio central de paquetes de Composer
- …Actúa como proxy entre los repositorios VCS y los usuarios de Composer
- …Puede almacenar cualquier tipo de librería PHP: components, bundles, plugins, módulos...
- …Todo proyecto Open Source debería estar en Packagist
- …Buen lugar dónde encontrar librerías para tu aplicación

## VCS: git, svn, hg...

    {
        "repositories": [
            {
                "type": "vcs",
                "url": "https://github.com/symfony/Yaml"
            }
        ],
        "require": {
            "symfony/yaml": "2.3.*"
        }
    }
{:.code-medium}

## PEAR

    {
        "repositories": [
            {
                "type": "pear",
                "url": "http://pear2.php.net"
            }
        ],
        "require": {
            "pear-pear2.php.net/PEAR2_Text_Markdown": "*",
            "pear-pear2/PEAR2_HTTP_Request": "*"
        }
    }
{:.code-medium}

## Repositorios sin composer.json

    {
        "repositories": [
            {
                "type": "package",
                "package": {
                    "name": "smarty/smarty",
                    "version": "3.1.7",
                    "dist": {
                        "url": "http://www.smarty.net/files/Smarty-3.1.7.zip",
                        "type": "zip"
                    },
                    "source": {
                        "url": "http://smarty-php.googlecode.com/svn/",
                        "type": "svn",
                        "reference": "tags/Smarty_3_1_7/distribution/"
                    },
                    "autoload": {
                        "classmap": ["libs/"]
                    }
                }
            }
        ],
        "require": {
            "smarty/smarty": "3.1.*"
        }
    }
{:.code-small}

## **Creando un paquete**

## Creando un paquete

    {
        "name": "trovit/foo",
        "description": "Super cool library for foo stuff",
        "homepage": "http://foo.trovit.es",
        "license": "MIT",
        "authors": [
            { "name": "Trovit backend team", "email": "backend@trovit.es"}
        ],
        "autoload": {
            "psr-0": { "Trovit\\Foo": "src/" }
        },
        "require": {
            "php": ">=5.3.2",
            "ext-curl": "*",
            "symfony/console": "2.3.~"
        }
    }
{:.code-small}

## Creando un paquete: *Autoloading*

    "autoload": {
        "psr-0": {
            "Trovit\\Foo": "src/"
        }
    }

## Creando un paquete: *Autoloading*

    "autoload": {
        "psr-0": {
            "Trovit_": "src/"
        }
    }

## Creando un paquete: *Autoloading*

    "autoload": {
        "classmap": ["src/", "lib/"]
    }

## Creando un paquete: *Autoloading*

    "autoload": {
        "files": ["src/Trovit/functions.php"]
    }

## **Scripts**

## Scripts

Permiten ejecutar acciones ante determinados eventos de Composer.

- pre\|post-install-cmd
- pre\|post-update-cmd
- pre\|post-package-install
- pre\|post-package-update

## Scripts

    {
        "scripts": {
            "post-install-cmd": [
                "My\\Namescape\\ScriptHandler::buildBootstrap"
            ],
            "post-update-cmd": [
                "rm -rf app/cache/*"
            ]
        }
    }
{:.code-medium}

## **Instaladores**

## Instaladores oficiales

- Wordpress
- Drupal
- CakePHP
- CodeIgniter
- Laravel
- ¡Y muchos más!

{:.centered}
[http://github.com/composer/installers](http://github.com/composer/installers)

## Instaladores propios

{:.centered}
[http://getcomposer.org/doc/articles/custom-installers.md](http://getcomposer.org/doc/articles/custom-installers.md)

## **Mastering Composer**

## Semantic versioning

{:.semantic-versioning}
X.Y.Z

{:.centered}
[http://semver.org/spec/v2.0.0.html](http://semver.org/spec/v2.0.0.html)

## Branch aliases

    "extra": {
        "branch-alias": {
            "dev-master": "1.0.x-dev"
        }
    }

## Trabajando con forks

    {
        "repositories": [
            {
                "type": "vcs",
                "url": "https://github.com/adanlobato/Yaml"
            }
        ],
        "require": {
            "symfony/yaml": "dev-hotfix"
        }
    }
{:.code-medium}

## Trabajando con forks

    {
        "repositories": [
            {
                "type": "vcs",
                "url": "https://github.com/adanlobato/Yaml"
            }
        ],
        "require": {
            "symfony/yaml": "dev-hotfix as 1.0.x-dev"
        }
    }
{:.code-medium}

## Minimum stability

    {
        "minimum-stability": "stable",
        "require": {
            "symfony/config": "2.3",
            "symfony/yaml": "2.3.*@dev",
            "symfony/console": "2.3.*@beta"
        }
    }
{:.code-medium}

## Autoloading optimizado

    $ composer dump-autoload <mark>--optimize</mark>

## Repositorios privados: *Satis*

- Es una versión reducida de Packagist
- Se instala y se configura **muy** rápido
- Es ideal para repositorios privados

## Repositorios privados: *Satis*

    $ composer create-project composer/satis

## Repositorios privados: *Satis*

    <mark class="comment">// config.json</mark>
    {
        "name": "Trovit Repository",
        "homepage": "http://packages.trovit.es",
        "require-all": true,
        "repositories": [
            {
                "type": "git",
                "url": "https://github.com/trovit/super-cool-library"
            }
        ]
    }
{:.code-medium}

## Repositorios privados: *Satis*

    $ php bin/satis build config.json web/

## Repositorios privados: *Satis*

Para protegerlo del exterior:

- Basic HTTP Authentication
- SSH
- Red privada

## Repositorios privados: *Packagist*

- Packagist es Open Source
- Puedes instalarte tu propio packagist
- Soporta Github Webhooks

## **Bottlenecks**

## Bottlenecks

- Dependency Solver
- …Github
- …Github post-receive hooks
- …Repositorios privados

## Enlaces de interés

- [getcomposer.org](http://getcomposer.org)
- [packagist.org](http://packagist.org)
- [github.com/composer](http://github.com/composer)

## **¿Preguntas?**