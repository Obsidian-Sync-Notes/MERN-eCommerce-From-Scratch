#frontend 

Quantity is going to be a component level state, so we will start by creating a state
```js
const [qty,setQty] = useState(0)
```

Go to the third row in `ProductScreen`, where we have checkout options and just after `Status`, where `In Stock` or `Out of Stock` is shown

![[Pasted image 20230809184309.png]]

![[Pasted image 20230809184332.png]]

Add an `onClick` to the "Add to Cart" button 
```js
onClick={addToCartHandler}
```

in `ProductScreen` components also destructure `history`

```js
const ProductScreen = ({history,match})=>{}
```

`history.push("/cart")` will redirect to that page.

so, our `addToCartHandler` will look like
![[Pasted image 20230809184909.png]]

```js
  const addToCartHandler = () => {
    naviagte(`/cart/${id}?qty=${qty}`)
  }
```


Now we need to create `cartScreen` so create a file `cartScreen.js` inside `screen` folder and create a `route` in frontend for that.


![[Pasted image 20230809185211.png]]

Here the `?` just after `/:id?` will make it an optional field, so that when we go to cart page, without any product id, it will show us the cart page.

Next  [[28 Cart Reducer & Add to Cart Action]].