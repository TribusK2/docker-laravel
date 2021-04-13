## 1 Utilities

### Composer
This utility allow to use Composer without install it on local machine.

Run `docker-compose run --rm composer <some-command>` i the main project folder. It will run only composer container (`--rm` - to remove container after shault it down)

`<some-command>` - You can specify Composer command to build project source: `create-project laravel/laravel .` (from Laravel documentation). The 'composer' statement is not required because it was defined in the dockerfile in the 'ENTRYPOINT'. Dot at the end is path to folder where project have to be located.

### Artisan
This utility allow to use Artisan without install it on local machine.

Run `docker-compose run --rm artisan <some-command>` i the main project folder. It will run only artisan container (`--rm` - to remove container after shault it down)

`<some-command>` - You can specify Artisan command, similar to Composer utility (e.g. migrate)

### NPM
This utility allow to use NPM without install it on local machine.

Run `docker-compose run --rm npm <some-command>` i the main project folder. It will run only npm container (`--rm` - to remove container after shault it down)

`<some-command>` - You can specify NPM command, similar to Composer utility
## 2 Start project
After build the project (see #1), run: `docker-compose up -d server`. It will run only required containers (thanks to 'depend_on' flag in the docker-compose file), without utilites.

## 3 Rebuild project
Run `docker-compose up -d --build server` to run containers after source code changed. It will force rebuild images.