#backend 


Lets create a Postman request to test the middleware.

![[Pasted image 20230814034840.png]]

Lets go and create this route, go into `userController.js`

After making the middleware, we will be able to access `user.id` which we will use inside our private routes.
But for now, lets create a simple api
![[Pasted image 20230814035226.png]]

Also import this inside our user routes.

![[Pasted image 20230814035339.png]]

Now lets create the middleware
in `middleware` folder create a file `authMiddleware.js` 

![[Pasted image 20230814035604.png]]

For now, send the token in header from postman, in the profile routes.

![[Pasted image 20230814035659.png]]

For now lets see what we are getting as the request.

![[Pasted image 20230814035759.png]]
Edit: it should be `req.headers.authorisation`



Export this and now lets see how we can protect specific routes.
It can be protected like this.
![[Pasted image 20230814035934.png]]

Now if we make request, we will be able to see the console log with the token.
![[Pasted image 20230814040221.png]]

Here also to handle exception, we will be using `express async handler`
![[Pasted image 20230814040424.png]]

![[Pasted image 20230814040604.png]]

Lets see what we get as console log
After this `console.log()` we will call  `next()`


Now if we will send the postman request without token we will get error, but if we will send it with token, we will be able to access the route.

And in the console, we will see the payload.

So we can set user in the request and we do not to get password, so we will remove that as
![[Pasted image 20230814041134.png]]

![[Pasted image 20230814041242.png]]

Now lets send profile data from
![[Pasted image 20230814041505.png]]

Now lets check this if it is working with different users or not.




Next we will be [[37 Saving the token in Postman]]