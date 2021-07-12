# docker-shipit-engine

Docker image for https://github.com/Shopify/shipit-engine

## Running via Docker Compose

* Create `config/secrets.yml` based off of `config/secrets.example.yml` and fill in your GitHub App's info
* Create `shipit.yml` based off of `shipit.example.yml` and make the desired changes/configurations
*
* Copy your controled secrets.yml and shipit.yml to the server hosting the application (currently set to be readonly on a docker image from the machine hosting the image)
*
* Run `make start` to start an instance. To stop it, run: `make stop`.

## Database Management

On first run, you'll need to create the database. Do so by running `make setup`.

After upgrades, you may need to run database migrations. Do so by running `make upgrade`.

## Teams

You can limit your Shipit instance to just members of your GitHub team. After adding your team(s) to your `secrets.yml`, run `bundle exec rake teams:fetch` to add your team members.

