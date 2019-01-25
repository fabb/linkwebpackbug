# Demonstrates a bug with webpack and npm link

## Bug reproduction

- In folder `myClient` run `npm run demonstrate_bug`
- Open http://localhost:3000
- The following warning is displayed:

```
 warning  in ./pages/index.js
"export 'SomeComponent' was not found in '@myorg/mylib'
```

- Interestingly the component `SomeComponent` still renders correctly, but experiences from a bigger real project show that some functionality will be broken

## Weird Addition

- Abort the running app
- Delete the file `myLib/package.json`
- Run the application again with `npm run dev`
- The warning from above is not displayed, and the app runs fine, even if later the package.json is restored, HMR also works fine
