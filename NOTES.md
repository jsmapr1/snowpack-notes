9/10/20

## Step 1: Clone the Repository
- Make a fork first
- Clone and look at package.json

- Look for a `main` or `module` field.

`main` is the standard one. This points often at the entry file and is a short
hand for `require(...)`.

`module` is not official, but is used as a standard by rollup and webpack.

More info from
[rollup](https://github.com/rollup/rollup/wiki/pkg.module)

and [another
article](https://medium.com/webpack/webpack-and-rollup-the-same-but-different-a41ad427058c)

and also this
[SO](https://stackoverflow.com/questions/42708484/what-is-the-module-package-json-field-for)


Start of the package.json

```
{
  "name": "root",
  "private": true,
  "scripts": {
    "bootstrap": "lerna bootstrap",
    "build": "lerna run build --scope=snowpack",
    "publish": "lerna publish --no-private",
    "format": "prettier --write \"snowpack/src/**/*.ts\"",
    "test": "jest --test-timeout=30000"
  },
  "workspaces": [
    "create-snowpack-app/*",
    "plugins/*",
    "snowpack",
    "test/build/*",
    "test/integration/*"
  ],
  "devDependencies": {
    ...
  }
}
```

Two things to note here. The scripts reference something called `lerna` and
there is a `workspaces` field.

Sometimes there's `bin` field
```
A lot of packages have one or more executable files that they’d like to install into the PATH. npm makes this pretty easy (in fact, it uses this feature to install the “npm” executable.)
```

You can also cheat by looking for `index.js` or `src/index.js`
