# Major Project Diary (jrd15) #
This document is a record of my progress as I develop my project and serve as a reference point when undertaking my report.

## February 13, 2023 ##
Initial creation of the Git repository, hosted on [Github](https://github.com/jackrdavies2023/jrd15_MP_AberDock_BitTorrent)

## February 15, 2023 ##
Pushed initial project outline to the Git repository. [Link](https://github.com/jackrdavies2023/jrd15_MP_AberDock_BitTorrent/commit/96288dff7e6707e2a2f91e2731a91a153dc8a4bd)

## February 20, 2023 ##
Completed and pushed initial UI design mockups to the Git repository. Mockups were made using Google Slides. [Link](https://github.com/jackrdavies2023/jrd15_MP_AberDock_BitTorrent/commit/b350b1b129776bb710a0b39b03f90959370659eb)

## February 22, 2023 ##
Created another Git repository, which will host the main code and Docker configuration. This repository was added as a submodule to the main repository. [Link](https://github.com/jackrdavies2023/jrd15_MP_AberDock_BitTorrent_src)

## February 22, 2023 ##
Initial creation of docker-compose and Dockerfile. The docker-compsose defines how an image is set up, and the Dockerfile builds the image that will be used by the docker-compose.

![Portainer web-ui](images/feb22_portainer.png "A screenshot of Portainer, a Docker management web interface.")

![Command line interface](images/feb22_docker-compose.png "A screenshot of the docker-compose being deployed.")

Sources used to understand docker-compose:

* https://docs.docker.com/compose/compose-file/build/ 
* https://docs.docker.com/compose/compose-file/

Sources used to start NGINX from within a docker container that is built on top of Debian:

* https://stackoverflow.com/questions/24241292/dockerized-nginx-is-not-starting
* https://stackoverflow.com/questions/45371521/adding-startup-script-to-dockerfile

![cURL request to NGINX container](images/feb22_testingNGINX.png "Command line interface, using cURL to test NGINX.")

The above screenshot shows tests being performed against the NGINX container, to ensure that it is responding to requests.

I then proceeded to modifying the docker image entrypoint script to start PHP-FPM. Sources used:

* https://stackoverflow.com/questions/37313780/how-can-i-start-php-fpm-in-a-docker-container-by-default


![phpinfo() function call](images/feb22_phpinfo.png "A screenshot of the phpinfo() funciton being called, to show the PHP configuration within the client browser.")

The Dockerfile was updated to include a customised nginx configuration, which enables PHP support. A index.php was placed in /var/www/html, which contains the function call “phpinfo()”, to test that PHP is working correctly.

## Februrary 23, 2023 ##
Created a project on Github, to keep track of task progress.

![Github project tracking board](images/feb23_gitprojecttracker.png "Git project tracker, showing tasks that are needed.")

I also refactored the file structure for the Docker files, so that the Dockerfile can include the “www” directory that was previously in the parent directory.

## February 25, 2023 ##
Implemented back-end navigation code to load a different page based on the GET parameter in the URL. Pages are stored and loaded as templates, using the [Smarty template library](https://www.smarty.net/).

![Smarty 01](images/feb25_smarty01.png)
![Smarty 02](images/feb25_smarty02.png)
![Smarty 03](images/feb25_smarty03.png)

## March 1, 2023 ##
Implemented the side navigation bar, featuring navigation links and the user profile image and name.

![Navigation bar](images/mar01_navigationbar.png)

The navigation bar is stored in its own template file, called "navbar.tpl". This file is included by other template files, such as "browse.tpl", "upload.tpl" and "statistics.tpl".

![Navigation bar included in templates](images/mar01_navigationbar_code.png)

Note the line

    {include file='navbar.tpl'}

## March 2, 2023 ##
I started working on the browse page, which is the main part of the site that is used for searching and browsing for content.

"Cards" were created to list each torrent and to seperate content.

![Torrent "cards"](images/mar02_browsecards.png)

Each card consists of a custom DOM named "card". The "card" element is styled using CSS, and using a custom element rather than a DIV improves code readability.

### HTML ###
![Torrent card HTML](images/mar02_browsecardhtml.png)

### CSS ###
![Torrent card CSS](images/mar02_browsecardcss.png)

The background colour of the card is defined by a global variable, which is defined at the beginning of the stylesheet. This variable will differ based on the users browser preferences. If the browser reports that the operating system uses the dark colour scheme, the dark theme will be used. Otherwise the light colour scheme will be defaulted to.

![Dark and light theme CSS variables](images/mar02_darklightthemecss.png)

The icons used in torrent cards, are SVG files obtained from [Google fonts](https://fonts.google.com/icons)

![Using Google fonts to obtain SVG icons](images/mar02_icons.png)

The advantage to using SVG files rather than PNG or JPEG is that they are vector images, meaning that they are typically smaller in size, scale without loss of quality and they can be colourised using CSS, meaning I don't need a new icon for each colour scheme.

The icons are defined using the below CSS:

![Icon CSS](images/mar02_iconcss.png)

The "background-color" option is defined by a global variable, which is set based on the users global system theme.
