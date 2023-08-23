#backend 

Check your node version `node --verson` if it is above 14 then ES6 import syntax will work.

For that we have to add
```json
"type": "module",
```

in `package.json` and then we will be able to use import statements in our files.

Difference in import statements between frontend and backend is that, in backend we will have to use file extensions as well.

>For example:
> we cannot write `from "data/product"` , we will have to write `from "data/product.js"`.


Now remove require and use import statements.


Also, change products export to normal export `export default products`


Next we will be starting with setting up our Database [[13 MongoDB Atlas & Compass Setup]]