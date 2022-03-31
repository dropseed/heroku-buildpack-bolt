# heroku-buildpack-forge

- Installs a `FORGE_PRO_PRIVATE_KEY` if found in the environment.
- Creates an `app/manage.py` file if there isn't one (so Heroku collectstatic works like usual)
- Adds a `bin/post_compile` script that the Python buildpack will use to re-compile Tailwind *after* the Forge packages have been installed (which contain Tailwind templates themselves)

Forked and modified from [heroku/heroku-buildpack-ssh-key](https://github.com/heroku/heroku-buildpack-ssh-key).


## Usage

Install the buildpack:

```sh
heroku buildpacks:add https://github.com/django-forge/heroku-buildpack-forge.git --index 1
```

Add a `FORGE_PRO_PRIVATE_KEY` (optional):

```sh
heroku config:set FORGE_PRO_PRIVATE_KEY="$(cat forge_pro_private_key)"
```
