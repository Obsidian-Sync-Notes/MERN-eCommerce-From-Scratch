#frontend 

Lets go into `frontend`
start with constants

inside `userConstants.js`
![[Pasted image 20230816185628.png]]
Then inside `userReducers.js`
![[Pasted image 20230816185847.png]]

Now inside `store.js`

![[Pasted image 20230816185936.png]]
 Go to `userActions.js` 
 ![[Pasted image 20230816190344.png]]
 ![[Pasted image 20230816190430.png]]
 
 ![[Pasted image 20230816190622.png]]
![[Pasted image 20230816190649.png]]


Now lets go to `screens` and create a file named `ProfileScreen.js`

![[Pasted image 20230816190932.png]]
![[Pasted image 20230816191005.png]]
![[Pasted image 20230816191058.png]]
![[Pasted image 20230816191240.png]]
![[Pasted image 20230816191350.png]]
also put `dispatch` in dependency array.
![[Pasted image 20230816191451.png]]
most of the thing in this file are copied from `RegisterScreen.js` and modified.
![[Pasted image 20230816192123.png]]
Paste form thing from `RegisterScreen` to `Col md={3}` part
![[Pasted image 20230816192247.png]]

![[Pasted image 20230816192344.png]]

Now go and add `ProfileScreen.js` to `App.js` as routes.
![[Pasted image 20230816192616.png]]
Here we have to add `user` as dependency in the `useEffect`
![[Pasted image 20230816192836.png]]

Next we will be [[45 Update User Profile]]