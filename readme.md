# Demonstrates a bug with webpack and npm link

## Bug reproduction

- In folder `myClient` run `npm run demonstrate_bug`
- http://localhost:3000 is opened in the browser
- The following warning is displayed in the browser:

```
Failed to compile
./src/App.js
Attempted import error: 'SomeComponent' is not exported from '@myorg/mylib'.
```

## Weird "Fix"

- Abort the running app
- Delete the file `myLib/package.json`
- Run the application again with `npm run start`
- The warning from above is not displayed, and the app runs fine, even if later the package.json is restored, HMR also works fine
