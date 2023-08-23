For this we have to install `colors`

```console
npm i colors
```

import `colors` in `server.js`

```js
import 'colors'
```

now go into db.js and modify the console.log as follows

```js
console.log("message".cyan.underline)
```

This will make the messgaes in console appears in colors.


Here is next step [[15 Modeling our data]]