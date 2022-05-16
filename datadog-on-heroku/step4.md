# Configure Datadog

## Create a Datadog account. 
Visit https://www.datadoghq.com/ and create an account, starting a 14 days free trial.

## Add the Datadog buildpack to the app and install Datadog agent for heroku

1. Enable Heroku Labs Dyno Metadata

`heroku labs:enable runtime-dyno-metadata -a [name of your app]`

2. Add the Datadog Heroku buildpack

`heroku buildpacks:add https://github.com/DataDog/heroku-buildpack-datadog.git`

3. Set the Agent version to install

`heroku config:add DD_AGENT_MAJOR_VERSION=7`

4. Set your Datadog API key

`heroku config:add DD_API_KEY=[your Datadog API key]`

5. Set the Datadog site

`heroku config:add DD_SITE=datadoghq.eu`

6. Deploy to Heroku

`git push heroku master`