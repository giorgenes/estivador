# Estivador

Estivador is meant to be yet another "orchestrator" to run on top of docker
(similar to tools like docker-compose).
It is meant to give a "heroku"-like feel in managing containers inside a
serve.

Things it does for you:
* register and configure containers
* runs, stops, restart and upgrade containers
* setup monitoring in the host for the containers (monit support so far)

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'estivador'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install estivador

## Usage

simply registers an empty container

    $ estivador add <container>

configure variables for the container

    $ estivador config <container> environment.db_passoword abcd1234

configure container ports

    $ estivador config <container> ports 3000:3000

runs the container as a service and adds monitoring for it

    $ estivador start <container>

restarts the container going instance by instance
and restarting them one by one

    $ estivador phased-restart <container>

pulls new version of the container and does a phased-restart

    $ estivador phased-update <container>

runs the container a single time

    $ estivador run <container> params ...

gets the status of managed containers

    $ estivador status

## Contributing

1. Fork it ( https://github.com/giorgenes/estivador/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
