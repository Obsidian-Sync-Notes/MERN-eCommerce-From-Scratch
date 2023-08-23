#frontend 

Now we are going to integrate backend with frontend.

In `constants ` folder create new file `userConstants.js` 

![[Pasted image 20230816102455.png]]

Now lets create `userReducers.js` inside `reducers` folder.

![[Pasted image 20230816102841.png]]
Now in `store.js`
![[Pasted image 20230816102941.png]]

Lets add our action now, inside `actions` folder create a file `userActions.js`
![[Pasted image 20230816103358.png]]
![[Pasted image 20230816103529.png]]

![[Pasted image 20230816103718.png]]

Now lets load, already stored (if any) `userInfo` from localStorage.
Go into `store.js`

![[Pasted image 20230816103932.png]]

Next we will be working on [[40 User Login Screen & Functionality]]


