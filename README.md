# Docker-compose based Multi-Juicer
This repo fits the need for spawning multiple juice-shop instances, without the need for a kubernetes kluster.

The base setup is bare-bones and would require the user to customize the docker images. Additionally, this was thrown together rather quickly and as such does not allow spawning beyond 10, uses static files, and killing the containers just loops over all 10 of them.

## Setup
The js-up, js-down and js-restart require the execution bit, as such:

> chmod +x js-*

## js-up
This requires a number, which can be between 1 and 10.
Starts up this amount of juice-shop instances, using port 8001 to 8010 corrosponding with their number.

The containers are set to automatically restart unless stopped manually.

If you somehow rename the containers, you can always kill them with

> docker ps
> docker kill <uid>

## js-down
Loops through all instances and stops them

## js-restart
This requires a number, which can be between 1 and 10.
Restarts the specified numbered container.
