#backend 

Authentication and Authorisation are two different things.

Getting verified from data base is called authentication.
e've already implemented authentication where we take an email and a password. We authenticate it against the database.




Now, authorization is having that user access.ertain parts are certain protected routes in the API. And we do that by sending `json web token`.

So essentially when we log in, it's going to create and it's going to sign a `json web token` with a secret key. That way the server can tell if it's been tampered with and then that token gets sent back to the client.
And we can use that. We can store it in the client/browser.

So when we have to access any protected routes, we can send that token in the header.

So there's a header which consists of the type of the token, which is going to be JWT and then the algorithm that was used to sign the token. Now the payload data is what we actually choose.
So typically we'd send a user I.D. or session ID something to identify the user we would put in the payload.


You want to be sure not to put secure data like passwords or, you know, bank account numbers and stuff like that.

So typically we'll just send a user ID. That way the server can receive it and we can do a database call or we can get that user. And then the last part is the signature. And the signature is used to verify that nothing has changed along the way.

And it verifies that the sender is who they say they are.

Now, if we just hop over to Postman right now, when we hit this log and route, it authenticates us. But we're only getting some basic user data. We're not getting a token that we can use to send to a protected row. So next we are going to make it so we can send a token back.

And the way that will work is once we get it, then we will be able to access protected routes.

We will create our own middleware for that to protect routes.
So that we need to send token in headers to access the routes.


So, this JWT token is the token that we are bearing, so typical conventio is to use bearer and then whatever the token is

![[Pasted image 20230814033437.png]]

For signing the token we will be using `jsonwebtoken`
to install we can use

```console
npm install jsonwebtoken
```

Next we will be [[35 Generate a JSON web token]]