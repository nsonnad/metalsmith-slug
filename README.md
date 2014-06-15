# metalsmith slug

Add a slug property to the metadata for targeted files in your
[Metalsmith](http://www.metalsmith.io/), based on a particular property.
Useful for generating links to pages based on, say, their title.

## Installation

    npm install metalsmith-slug

## Usage

If you're not familiar with Metalsmith, check it out. It's a very versatile file
processor that can be used for static site generation, project scaffolding and
more.

### Metalsmith CLI

Add `metalsmith-slug` to your `metalsmith.json`.

```json
{
  "plugins": {
    "metalsmith-slug": {}
  }
}
```

### Metalsmith JavaScript API

Add `metalsmith-slug` to your project and `.use()` it.

```js
var slug = require('metalsmith-slug');

metalsmith.use(slug());
```

## Options

**patterns** _[array]_: Glob patters of files to match. Uses
[minimatch](https://github.com/isaacs/minimatch).

```js
metalsmith.use(slug({
  patterns: ['*.md', *.rst]
}));
```

**property** _'string'_: Property to generate the slug from. Defaults to `title`.

```js
metalsmith.use(slug({
  property: 'name' // Defaults to 'title'
}));
```

**slug options**: You can additionally use any of the options available to [node-slug](https://github.com/dodo/node-slug#options)

```js
metalsmith.use(slug({
  replacement: '_',
  symbols: false
}));
```
