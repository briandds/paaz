# paaz

Super mini platform as a service.

## Current features:

* Continuous deployment
* Review apps
* Support for travis integration (via HTTP POST after a build)
* Support for deploying from rackspace containers
* Support for running Mojolicious apps
* That's it

## Dependencies

* recommended: [perlbrew](https://perlbrew.pl/), [cpanminus](https://github.com/miyagawa/cpanminus)
* required: [Mojolicious](http://mojolicio.us/), [rack-cli](https://developer.rackspace.com/docs/rack-cli/)

## Installation

* Install perlbrew, cpanm and Mojolicious
```
curl -L https://install.perlbrew.pl | bash
perlbrew install perl-5.26.1
perlbrew install-cpanm
cpanm Mojolicious
```

* Download
```
git clone https://github.com/briandds/paaz
cd paaz
```

* Configure
```
cp paaz.conf.sample paaz.conf # see below
rack configure
```

* Run
```
hypnotoad ./paaz
```
(or `./paaz daemon` for development mode)

## Configuration

`paaz.conf` should looks something like this:
```
{
    app_name => 'app.pl',         # Script that starts the app
    container_name => 'builds',   # The container
    server_mode => 'development', # development/production
    log_path => 'paaz.log'        # Where to write the log
}
```
