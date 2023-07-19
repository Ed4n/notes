---
id: koyga7pu9kczh335zphxdoo
title: Upload gh Pages
desc: ""
updated: 1689726141188
created: 1689726135013
---

Easily upload to gh-pages

[Introducción a Vite, mas Deploy en Github Pages (Por si no lo vite)](https://youtu.be/UX4gvort2TU?t=755)

## JS Doc Implementation

To us js doc, first it's needed to install node:

```json
npm init -y
```

Now is possible to install it:

```json
npm i jsdoc
```

With jsdoc installed, now is needed to create a specific json file for js doc, this file will have the following name:
`jsdoc.json																					`

In this file add the following template:

```json
{
  "source": {
    "include": ["src"],
    "includePattern": ".js$",
    "excludePattern": "(node_modules|docs)"
  },
  "plugins": [],
  "templates": {
    "cleverLinks": true,
    "monospaceLinks": true
  },
  "opts": {
    "recurse": true,
    "destination": "./docs",
    "readme": "./README.md"
  }
}
```

Now with this done, its possible to run **jsdoc**, for that type this in the console:

```other
npx jsdoc -c jsdoc.json
```

To avoid writing all this inside the scripts in the **package.json** file

```json
"docs": "jsdoc -c jsdoc.json",
```

Now run this in the console:

```json
npm run docs
```

#### References:

[JS Doc Documentation](https://jsdoc.app/)
[Js Doc NPM](https://www.npmjs.com/package/jsdoc)
[Jsdoc cheatsheet](https://devhints.io/jsdoc)
[JS Doc Fatz](https://youtu.be/r0H-acWQS6c)
