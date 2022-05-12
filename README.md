This website is built using [Eleventy](https://www.11ty.dev/).

# Building

You'll need [nodejs](https://nodejs.org/en/) installed in order to build it.

Then inside the website repo run:

```
npm install
```

then to build the site:

```
npx @11ty/eleventy
```

It will output to `_site/`.

To start a dev server that watches for changes:

```
npx @11ty/eleventy --serve
```


# Deploying

The site is deployed automatically whenever code is pushed to the master
branch.
