#frontend 

When we fetch, we will get CORS (Cross origin resource sharing) error and to resolve that 2 things can be done.

## Installing an extension which will bypass the CORS error.

Extension name is `CORS Unblock` and can be found over here https://addons.mozilla.org/en-US/firefox/addon/cors-unblock/ for firefox/

## Using Proxy to resolve CORS

Go to frontend `package.json` and add these lines in the file.

```json
"proxy": "http://127.0.0.1:5000"
```

because we are using port 5000 for our backend services.

Restart the server.