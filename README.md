<!-- @format -->

# An NPM package for React

Exports two components from consumption in your React Project

Thanks for the [write up](https://levelup.gitconnected.com/publish-react-components-as-an-npm-package-7a671a2fb7f)!

- Badge
- Button

## Steps

- Create new project for React
- Define components we want to import from other projects
- Install Babel

```sh
npm install --save-dev @babel/core @babel/cli @babel/preset-env
npm install -save @babel/polyfill
```

- Configure babel

```json
{
  "presets": [
    [
      "@babel/env",
      {
        "targets": {
          "edge": "17",
          "firefox": "60",
          "chrome": "67",
          "safari": "11.1"
        },
        "useBuiltIns": "usage",
        "corejs": "3.6.5"
      }
    ],
    "@babel/preset-react"
  ]
}
```

- Define build command

```json
"build": "rm -rf dist && NODE_ENV=production babel src/lib --out-dir dist --copy-files"
```

- `npm run build`

- Name package and version

```json
"name": "primetimetran-npm-counter",
"version": "0.1.0",
```

- Define path for modules

```json
"main": "dist/index.js",
"module": "dist/index.js",
"files": [ "dist", "README.md" ],
"repository": {
    "type": "git",
    "url": "git+https://github.com/PrimeTimeTran/npm-counter"
},
```

- `npm publish`

Should not be available on NPM

https://www.npmjs.com/package/primetimetran-npm-counter
