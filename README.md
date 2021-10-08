# Example Plumber App on Heroku

This is an example [Plumber][plumber] application, which uses [heroku-buildpack-r][buildpack] for Heroku.

> Plumber allows you to create a web API by merely decorating your existing R source code
> with roxygen2-like comments.

## Usage

[![Deploy][button]][deployapp]

You can use this project as a template for creating Plumber applications on Heroku.

Execute these commands to get started:

```bash
# get the sources
git clone https://github.com/virtualstaticvoid/heroku-plumber-app.git
cd heroku-plumber-app

# optionally, reinitialize git
rm -rf .git
git init -b main
git add --all
git commit -m "initial"

# create a new heroku application, set the buildpack and deploy
heroku create --stack=heroku-20 --buildpack vsv/heroku-buildpack-r

# deploy
git push heroku main

# view the application
heroku open /__docs__/
```

The following paths are provided:

* [`/echo?msg=MSG`](plumber.R#L14)
* [`/plot`](plumber.R#L21)
* [`/sum?x=X&y=Y`](plumber.R#L30)

The OpenAPI (Swagger) user-interface is available via the [`/__docs__/`](app.R#L10) path.

## License

MIT License. Copyright (c) 2020 Chris Stefano. See [LICENSE](LICENSE) for details.

<!-- Links -->
[buildpack]: https://github.com/virtualstaticvoid/heroku-buildpack-r
[button]: https://www.herokucdn.com/deploy/button.svg
[deployapp]: https://heroku.com/deploy?template=https://github.com/virtualstaticvoid/heroku-plumber-app/tree/main
[plumber]: https://www.rplumber.io
