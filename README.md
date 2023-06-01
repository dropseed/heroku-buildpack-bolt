# heroku-buildpack-bolt

- Adds a `bin/post_compile` script that the Python buildpack will use to compile Tailwind *after* the Forge packages have been installed (which contain Tailwind templates themselves)
- Uses a default `Procfile` if one isn't present


## Usage

Install the buildpack:

```sh
heroku buildpacks:add https://github.com/dropseed/heroku-buildpack-bolt --index 1
```
