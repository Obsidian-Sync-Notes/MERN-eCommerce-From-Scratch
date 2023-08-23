#frontend

First step is to make a project folder and initialise it as git repository and installing required software which are mentioned in [[Useful Links Related to Project]].

We will be using create-react-app to create boiler plate for front-end.

```console
npx create-react-app frontend
```

Clean up `src` folder and remove extra files or codes.

Remove `.git` folder and `.gitignore`  file from the front-end folder because we will be using git inside our root directory, which contains both front-end and back-end folders. 

use this command to check all files and folder
```console
ls -a
```
`-a` flag is used to show hidden folders.


use this to remove git folder
```console
rm -rf .git
```


Create `gitignore` in root folder and mention necessary items.

Push changes to git.

Moving on to next steps in [[02 Firing up project]]