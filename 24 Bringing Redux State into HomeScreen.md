#frontend 

Now we will dipatching the action.


![[Pasted image 20230809133142.png]]

![[Pasted image 20230809133202.png]]


![[Pasted image 20230809133221.png]]


Here is the implementation

```js

import React, { useEffect } from 'react'
import { useDispatch, useSelector } from 'react-redux'
import { Row, Col } from 'react-bootstrap'
import Product from '../components/Product'
import { listProducts } from '../redux/productSlice'

const HomeScreen = () => {
  const dispatch = useDispatch()
  const product = useSelector((state) => state.product)
  const { loading, error, products } = product


  useEffect(() => {
    dispatch(listProducts())
  }, [dispatch])

  return (
    <>
      <h1>Latest Products</h1>
      {loading ? (<p>Loading... </p>) : error ? <p>{error}</p> : (
        <Row>
          {products.map(product => (
            <Col key={product._id} sm={12} md={6} lg={4} xl={3}>
              <Product product={product} />
            </Col>
          ))}
        </Row>
      )}


    </>
  )
}

export default HomeScreen


```

Next we will be creating [[25 Message & Loader Components]].
