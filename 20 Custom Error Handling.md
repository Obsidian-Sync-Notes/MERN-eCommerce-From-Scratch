#backend 


Currently for some errors, we are getting `html` as response, but we want it to be `json`. So, we will be handling errors separately.

For this, we have to add custom `middlewares`
Middlewares are function which has access to  request, response cycle.

![[Pasted image 20230808014131.png]]

![[Pasted image 20230808014336.png]]

Lets move these middlewares into different place, for that create `middleware` folder inside `backend` folder [[Folder Structure]].

Create a file `errorMiddleware.js` inside that folder.

![[Pasted image 20230808014615.png]]

 ![[Pasted image 20230808014723.png]]

Since we are handling error differently, so we can modify `productRoutes.js` with these modifications.

![[Pasted image 20230808014921.png]]


Next we will be seting up our frontend state management tool [[21 Overview of Redux]]