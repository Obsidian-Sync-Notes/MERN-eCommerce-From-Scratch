#frontend 

Here is what is shown in tutorial and later i will mention how i implemented it.

Firstly create a `reducers` folder inside `src` folder.
Create a file `productReducers.js`

  ![[Pasted image 20230809092320.png]]
then in `store.js`
![[Pasted image 20230809092415.png]]

In `productReducers.js` we have few strings as case in  switch case, we can move all those files into a different file.

Create a `constants` folder inside `src` folder and create a file `productConstants.js` .

![[Pasted image 20230809092749.png]]

and make these modifications inside `productReducers.js`
![[Pasted image 20230809092854.png]]

Now lets create actions, for that create a folder `action` inside `src` folder.
Create a file `productActions.js` inside that folder.

So, what we did in `homeScreen.js` for fetching the product, now we will fetch the product inside actions.

![[Pasted image 20230809093652.png]]

![[Pasted image 20230809093716.png]]

Here is my implementation for the above code in `redux-toolkit` [[23.1 Product List Reducer and Action]].



Next is [[24 Bringing Redux State into HomeScreen]]