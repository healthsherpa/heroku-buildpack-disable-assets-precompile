# Heroku Buildpack: Disable Assets Precompile

Disable assets precompile for Rails when used before official `heroku/ruby` buildpack.

### How it works

It simply creates the `manifest-<md5 hash>.json` (Rails 4) or `.sprockets-manifest-<md5 hash>.json`
(Rails 5+) in the `public/assets/` directory, and the `heroku/ruby` buildpack will assume that the
assets were compiled locally.

## Usage

First, view the installed buildpacks:

```bash
$ heroku buildpacks [--app=...]
```

Next, add the Disable Assets Precompile buildpack _before_ the `heroku/ruby` buildpack.

```bash
$ heroku buildpacks:add --index 1 https://github.com/healthsherpa/heroku-buildpack-disable-assets-precompile
```
