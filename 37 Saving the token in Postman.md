#backend 


Currently for accessing protected route we have to manually copy token and send it inside header.

So, what we can do is, when we login, we will set the token inside our environment variables.

for that go into `Tests` tab and
![[Pasted image 20230814223805.png]]

Now the token will be saved in the environment variable.

To use that token to access protected route,
Go into `Authorization` tab and
![[Pasted image 20230814223950.png]]



Next we will be working on [[38 User Registration & Password Encryption]]