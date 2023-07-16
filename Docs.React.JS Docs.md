---
id: ln9f16cxfut61rbiqirlozg
title: JS Docs
desc: ""
updated: 1689472103382
created: 1689472071660
---

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
