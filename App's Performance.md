# App's Performance

## Angular Deployment

- Minification: remove spaces

- Uglification: short names

- Bundling: bundle a lot of .js in one .js

- Dead code elimation

- Ahead of time complitaion

  

  ```shell
  ng build --prod
  ```

  

### github Pages

```
//in package.json
"deploy:gh":"ng build --prod --base-href='https://username.github.io/repoName/' && ngh"
```

