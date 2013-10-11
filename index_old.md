---

layout: bright

style: |

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
    #Picture h2 {
        color:#FFF;
        }
    #SeeMore h2 {
        font-size:100px
        }
    #SeeMore img {
        width:0.72em;
        height:0.72em;
        }
---

# Composer {#Cover}

*Dependency management for PHP*

![](pictures/dj-headphones-wallpaperakg-dj-headphones-wallpaper-wallpapers-f8paiy2d.jpg)
<!-- photo by John Carey, fiftyfootshadows.net -->

## ¿Qué es Composer?

<figure markdown="1">

> Es una herramienta que nos permite declarar cuáles son las librerías de las que depende nuestro proyecto y las instala por nosotros

</figure>

## ¿Es un concepto nuevo?

- En **python** existe `pip`
- …En **javascript** existe `npm`
- …En **ruby** existe `bundler`
- …En **php** existe... ¿`PEAR`/`Pyrus`?

## ¿Alternativas en PHP?

|                   |PEAR      |Pyrus          |Composer    |
+-------------------|----------|---------------|------------+
|* Instalación *    |Global    |Global/Local   |Local       |
|* Package types *  |Dist      |Dist           |Dist/Source |
|* PEAR support *   |Yes       |Yes            |Yes         |
|* VCS support *    |No        |No             |Yes         |

## **Instalación**

## Instalación

    curl -S <mark>http://getcomposer.org/installer</mark> | php

## Primeros pasos: Instalando dependencias

    ./composer.phar <mark class="important">require</mark> twig/twig

## composer.json

    {
        "require": {
            "twig/twig": "1.0.0"
        }
    }

## Shower Key Features

1. Built on HTML, CSS and vanilla JavaScript
2. All modern browsers are supported
3. Slide themes are separated from engine
4. Fully keyboard accessible
5. Printable to PDF

{:.note}
Shower ['ʃəuə] noun. A person or thing that shows.


## Plain Text on Your Slides

Lorem ipsum dolor sit amet, consectetur [adipisicing](#all-kind-of-lists) elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, *quis nostrud* exercitation ullamco laboris **nisi ut aliquip** ex ea commodo consequat. Duis aute irure <i>dolor</i> in reprehenderit in voluptate velit esse cillum <b>dolore</b> eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in `<culpa>` qui officia deserunt mollit anim id est laborum.

## All Kind of Lists

1. Simple lists are marked with bullets
2. Ordered lists begin with a number
3. You can even nest lists one inside another
    - Or mix their types
    - But do not go too far
    - Otherwise audience will be bored
4. Look, seven rows exactly!

## Serious Citations

<figure markdown="1">

> Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia.

<figcaption>Marcus Tullius Cicero</figcaption>
</figure>

## Code Samples

    <!DOCTYPE html>
    <html lang="en">
    <mark><head></mark> <mark class="comment"><!--Comment--></mark>
        <title>Shower</title>
        <meta charset="<mark class="important">UTF-8</mark>">
        <link rel="stylesheet" href="screen.css">
    <mark></head></mark>

## Even Tables

|  Locavore      | Umami       | Helvetica | Vegan     |
+----------------|-------------|-----------|-----------+
|* Fingerstache *| Kale        | Chips     | Keytar    |
|* Sriracha     *| Gluten-free | Ennui     | Keffiyeh  |
|* Thundercats  *| Jean        | Shorts    | Biodiesel |
|* Terry        *| Richardson  | Swag      | Blog      |

It’s good to have information organized.

## Pictures
{:.cover #Picture}

![](pictures/picture.jpg)
<!-- photo by John Carey, fiftyfootshadows.net -->

## **You can even shout this way**

## Inner Navigation

1. Lets you reveal list items one by one
2. …To keep some key points
3. …In secret from audience
4. …But it will work only once
5. …Nobody wants to see the same joke twice

## ![](http://shwr.me/pictures/logo.svg) [See more on GitHub](https://github.com/shower/shower/)
{:.shout #SeeMore}
