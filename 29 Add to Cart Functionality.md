#frontend 

 We will have to add functionality inside `cartScreen.js` , so import these.
 ![[Pasted image 20230810223032.png]]

![[Pasted image 20230810223629.png]]

After this the product will be added inside our state.
Lets subscribe our `cartScreen` component with cart store

![[Pasted image 20230810223928.png]]


 here is my implementation which is going to be similar except for me using some hooks.

```js
import React, { useEffect } from 'react'
import { Link } from 'react-router-dom'
import { useDispatch, useSelector } from 'react-redux'
import { useParams, useLocation } from "react-router-dom";
import { Row, Col, ListGroup, Image, Form, Button, Card } from 'react-bootstrap'
import Message from '../components/Message'
import Loader from '../components/Loader'
import { cartAddItem } from '../redux/cartSlice'

const CartScreen = () => {
  const { id } = useParams();
  const qty = new URLSearchParams(useLocation().search).get('qty')
  const dispatch = useDispatch()
  const cart = useSelector(state => state.cart)
  const { cartItems } = cart

  console.log(cartItems)

  useEffect(() => {
    if (id) {
      dispatch(cartAddItem({ id, qty }))
    }
  }, [dispatch, id, qty])
  return (
    <div>cartScreen</div>
  )
}

export default CartScreen
```

Now we will work on cartScreen page UI. [[30 Cart Screen UI]]