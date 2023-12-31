#frontend 

Go to `ProductScreen.js` file.
![[Pasted image 20230806220311.png]]

use this to find the product we will be showing

![[Pasted image 20230806220545.png]]

![[Pasted image 20230806221649.png]]

![[Pasted image 20230806221722.png]]

![[Pasted image 20230806221755.png]]

 ![[Pasted image 20230806221840.png]]

```jsx

import React from 'react'
import { Link } from 'react-router-dom'
import { Row, Col, Image, ListGroup, Card, Button } from 'react-bootstrap'
import Rating from '../components/Rating'
import products from '../utils/products'
import { useParams } from "react-router-dom";


const ProductScreen = () => {
  const { id } = useParams();
  const product = products.find((p) => p._id === id)
  return (
    <>
      <Link className='btn btn-light my-3' to='/'>
        Go Back
      </Link>
      <Row>
        <Col md={6}>
          <Image src={product.image} alt={product.name} />
        </Col>
        <Col md={3}>
          <ListGroup variant='flush'>
            <ListGroup.Item>
              <h3>{product.name}</h3>
            </ListGroup.Item>
            <ListGroup.Item>
              <Rating
                value={product.rating}
                text={`${product.numReviews} reviews`}
              />
            </ListGroup.Item>
            <ListGroup.Item>
              <strong>Price :</strong> ${product.price}
            </ListGroup.Item>
            <ListGroup.Item>
              <strong>Description :</strong> ${product.description}
            </ListGroup.Item>
          </ListGroup>
        </Col>
        <Col md={3}>
          <Card>
            <ListGroup variant='flush'>
              <ListGroup.Item>
                <Row>
                  <Col>Price :</Col>
                  <Col>
                    <strong>${product.price}</strong>
                  </Col>
                </Row>
              </ListGroup.Item>
              <ListGroup.Item>
                <Row>
                  <Col>Status :</Col>
                  <Col>
                    {product.countInStock > 0 ? 'In Stock' : 'Out Of Stock'}
                  </Col>
                </Row>
              </ListGroup.Item>
              <ListGroup.Item>
                <Button
                  className='btn-block'
                  type='button'
                  disabled={product.countInStock === 0}
                >
                  Add to Cart
                </Button>
              </ListGroup.Item>
            </ListGroup>
          </Card>
        </Col>
      </Row>

    </>
  )
}

export default ProductScreen

```


Next step is to create a backend server. [[07 Frontend Backend Workflow]]