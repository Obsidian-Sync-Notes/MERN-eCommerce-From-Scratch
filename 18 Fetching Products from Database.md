#backend 

Create a `routes` folder  in `backend` folder [[Folder Structure]]

Create `productRoutes.js` inside `routes` folder.

![[Pasted image 20230808002143.png]]

and in the `server.js` we can put a middleware
```js
app.use('/api/products',productRoutes)
```

Since, we are dealing with database and will have to use try-catch in every routeHandler, we will be using `express-async-handler`
It is a middlerware for handling exceptions inside of async express routes and passing them to your express error handlers.

```console
npm i express-async-handler
```

and for use we have to wrap everyfunction with `asyncHandler`

![[Pasted image 20230808002758.png]]

![[Pasted image 20230808002958.png]]

adding description about the routes as
![[Pasted image 20230808003129.png]]

For now test it in browser. After we will be using postman for testing the API routes.

[[19 Getting Started With Postman]]