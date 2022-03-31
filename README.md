# heroku-buildpack-forge

- Installs a `FORGE_PRO_PRIVATE_KEY` if found in the environment.
- Creates an `app/manage.py` file if there isn't one (so Heroku collectstatic works like usual)

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
