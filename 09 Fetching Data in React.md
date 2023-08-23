#frontend 

We will be using `axios` for making API requests from front-end.
```console
npm i axios
```

Go to `HomeScreen.js` where we are displaying products, so we will make request there.

Remove `products` import, now we will be fetching from backend.

We will be storing the product in component level state (of HomeScreen).

Import `useState` and `useEffect` and also `axios`.
```jsx
const [products,setProducts] = useState([])

useEffect(()=>{
	const fetchProducts = async () =>{
		const {data} = await axios
							.get('/api/products')
		setProducts(data)
	}
	fetchProducts()
},[])
```

Since we mentioned `/api/products` it will go to `localhost:3000/api/products/`  even after this, we will get a CORS error and will not be able to fetch.
Here more details can be found [[Resolving Issues with CORS]].

Now we will also fetch single product data for `productScreen.js` page.

Here we will do almost same thing.

```jsx
const [product,setProduct] = useState({})

useEffect(()=>{
	const fetchProduct = async () =>{
		const {data} = await axios
							.get(`/api/product/${id}`)
		setProduct(data)
	}
	fetchProduct()
},[])
```

Since now everything is fetched from backend, we can delete `products.js` from frontend.

Next we will be [[10 Nodemon and Concurrently Setup]]