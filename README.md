# heroku-buildpack-bolt

- Installs `FORGEPACKAGES_AUTH` for private packages if found in the environment
- Creates an `app/manage.py` file if there isn't one (so Heroku collectstatic works like usual)
- Adds a `bin/post_compile` script that the Python buildpack will use to compile Tailwind *after* the Forge packages have been installed (which contain Tailwind templates themselves)
- Uses a default `Procfile` if one isn't present


## Usage

Install the buildpack:

```sh
heroku buildpacks:add https://github.com/dropseed/heroku-buildpack-bolt --index 1
```

Add `FORGEPACKAGES_AUTH` (optional):

```sh
heroku config:set FORGEPACKAGES_AUTH="<project_name>:<project_token>"
```
