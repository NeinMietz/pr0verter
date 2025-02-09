# pr0verter

<div align="center">
  <p align="center">
    <br />
    <img height="150" width="auto" src="https://raw.githubusercontent.com/pr0-dev/pr0verter/master/public/images/pr0verter-260x260.png" />
    <br /><br />
    pr0verter! Video converter for pr0gramm.com
    <br />
    <a href="https://dev.pr0verter.de/"><strong>LIVE URL: dev.pr0verter.de</strong></a>
    <br />
  </p>
</div>


## Dependencies:
* PHP 8.1
* NodeJS and NPM
* Composer
* yt-dl|yt-dlp
* ffmpeg
* any kind of database

## Development
pr0verter comes with Laravel Sail development environment, that does mean for development and testing you can ignore above requirements for dependencies and just use Laravel Sail instead as long as you have Docker installed on your system.

Since [Laravel Sail](https://laravel.com/docs/8.x/sail) is being installed using [Composer](https://getcomposer.org/) it is required that you do install all dependencies before using [Laravel Sail](https://laravel.com/docs/8.x/sail) to run the development environment. Since [Laravel Sail](https://laravel.com/docs/8.x/sail) does require [Docker](https://www.docker.com/) to be installed we can use an intermediade container to do so as [described in the documentation on how to install dependencies for existing projects](https://laravel.com/docs/8.x/sail#installing-composer-dependencies-for-existing-projects) - this will install all dependencies using [Composer](https://getcomposer.org/) and [NPM](https://www.npmjs.com/).
```
docker run --rm \
    -u "$(id -u):$(id -g)" \
    -v $(pwd):/var/www/html \
    -w /var/www/html \
    laravelsail/php80-composer:latest \
    composer install --ignore-platform-reqs
```

## Installation:
* Clone the Project
* `composer install --no-dev`
* `npm install`
* `npm run prod`
* `cp .env.example .env`
* Adjust .env to your needs
* `php artisan key:generate`
* `php artisan migrate`
* Setup Supervisor or any other tool to work on the queue.
* Setup crontab or windows Taskscheduler to run `php artisan schedule:run` every minute

Unter der Domain https://dev.pr0verter.de ist die neue Version des pr0verters verfügbar.

Die neuen Features umfassen:

- Untertitel Support für Youtube - Beim Download könnt ihr, sofern Untertitel verfügbar sind, diese direkt ins Video einbrennen lassen

- PornHub, TikTok, MyVideo oder was auch immer - der "Downloader" vom prOverter beherrscht es & im FAQ ist eine Liste von unterstützten Seiten aufgelistet

- Limit für Uploads wurde auf 2GB gesetzt - Konvertierungslimit wurde auf 200 MB angehoben

- Interpolation - Ihr könnt ein Video mit beliebiger FPS auf 60 FPS "verlustlos" hochscalen lassen - dieser Vorgang braucht allerdings mehr Zeit

Es gibt noch weitere geplante Features - das Wichtigste ist wohl das WASM Feature, anstatt ein Video auf dem Server zu prOvertieren wird es direkt auf eurem Endgerät konvertiert - und benutzt natürlich die Leistung eures Endgerätes, das soll euch Bandbreite sparen. Solltet ihr den Wunsch haben euch am prOverter zu beteiligen, könnt ihr das direkt auf https://github.com/pr0-dev/pr0verter tun, einfach PR erstellen und ab dafür.

Ein DICKES FETTES DANKE an @jonas32 für seinen Teil im Frontend - schaut mal vorbei und lasst ein bisschen Blussium da!
