#frontend 

Install `Redux DevTools` extensions.

Go to `frontend` folder and 
```console
npm i redux react-redux redux-thunk redux-devtools-extension
```

After installing create redux store files.
so, go into `src` inside frontend create `store.js`


![[Pasted image 20230808164656.png]]
>  Remove squre brackets around middleware spread around line 14


Now to implement this in our application is via a Provider
Go to `index.js` 

![[Pasted image 20230808164852.png]]


Above method is deprecated so we will be using `redux-toolkit`
Here is how [[22.1 Creating a Redux Store]]




Next we will be creating [[23 Product List Reducers & Action]]

