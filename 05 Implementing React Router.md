#frontend

Install these packages
```console
npm i react-router-dom react-router-bootstrap

```

We are using `react-router-bootstrap` because we will be dealing buttons and all, and `react-router-bootstrap` will help there with `CSS`

Go to `App.js` to implement the router.
```javascript
import {BrowserRouter as Router, Route} from 'react-router-dom'
```

Wrap entire app inside the `<Router></Router>`


use
```javascript
<Route path='/' component={HomeScreen} exact/>
```


Create new file `ProductScreen.js` in `screens` folder [[Folder Structure]].

Render the product screen on `/product/:id`

Replace `<a>` tags and replace it with `<Link>` from `react-router-dom`.


For `<a>` tags from navbar , we will be using `<LinkContainer>` from the `react-router-bootstrap`. Its same thing as `<Link>` tag but it allows us to wrap bootstrap components.
![[Pasted image 20230806213423.png]]

 
In next part we will be creating [[06 Creating Product Screen]].