#backend 

In `routes` create a file `userRoutes.js` and create a file `userController.js` inside controller folder.

For testing, create a folder in `Postman` `Users & Auth` 
And create a POST request 
![[Pasted image 20230814021910.png]]

![[Pasted image 20230814022023.png]]

To get request body, we need to set body parser as middleware in express, so in `server.js` add this line.

```js
app.use(express.json())
```

For now lets test this routes as
![[Pasted image 20230814022326.png]]
 And in `userRoutes.js`
![[Pasted image 20230814022426.png]]

Now we have to add this in `server.js`

![[Pasted image 20230814022538.png]]

Now lets write actual logic for auth

![[Pasted image 20230814022812.png]]

Here we also need to check for password, but the password is stored as encryption, so either we could use `bcrypt` here in controller or we can
Put a method inside model
![[Pasted image 20230814023320.png]]


![[Pasted image 20230814023450.png]]

Here we also should have added `token` but since functionality is not yet set, we are setting it as `null` for now.

Also if user is not found, this will be else part
![[Pasted image 20230814023605.png]]


Now this can be tested with postman.

Next we will looking at [[34 Explanation of JWT]]