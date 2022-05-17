
## Create a Datadog account. 
Visit https://www.datadoghq.com/ and create an account, starting a 14 days free trial.

## Add the Datadog buildpack to the app and install Datadog agent for heroku

1. Add the appropriate language-specific buildpack
    `heroku buildpacks:add heroku/nodejs`

2. Enable Heroku Labs Dyno Metadata

    `heroku labs:enable runtime-dyno-metadata -a [name of your app]`

3. Add the Datadog Heroku buildpack

    `heroku buildpacks:add https://github.com/DataDog/heroku-buildpack-datadog.git`

4. Set the Agent version to install

    `heroku config:add DD_AGENT_MAJOR_VERSION=7`

5. Set your Datadog API key (Datadog API key can be found in `Integration/API` tab in the Datadog application)

    `heroku config:add DD_API_KEY=[your Datadog API key]`

6. Set the Datadog site

    `heroku config:add DD_SITE=datadoghq.eu`

7. Configure Procfile
    `echo "web: npm start" > Procfile` 

8. Deploy to Heroku

    `git add .`

    `git commit -m [commit message]`

    `git push heroku master`