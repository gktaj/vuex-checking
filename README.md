# vuex-checking
This project was built by Vue 3.2.1.

## Local environment
```
$ git clone https://github.com/kdevsoftware/vuex-checking.git
$ cd vuex-checking
$ npm install
$ npm run serve
```
Navigate to `http://localhost:8080/`.

## Deploying to github page
```
$ npm run deploy
```
Navigate to `https://kdevsoftware.github.io/vuex-checking/`.

## Reference for deploying to github page

### 1. Create vue.config.js in the root directory and set the baseUrl.
```
module.exports = {
  baseUrl: process.env.NODE_ENV === 'production'
    ? '/vuex-checking/'
    : '/'
}
```

### 2. Create deploy.sh in the root directory with the following content.
```
#!/usr/bin/env sh

# abort on errors
set -e

# build
npm run build

# navigate into the build output directory
cd dist

# if you are deploying to a custom domain
# echo 'www.example.com' > CNAME

git init
git add -A
git commit -m 'deploy'

# if you are deploying to https://<USERNAME>.github.io
# git push -f git@github.com:<USERNAME>/<USERNAME>.github.io.git master

# if you are deploying to https://<USERNAME>.github.io/<REPO>
# git push -f git@github.com:<USERNAME>/<REPO>.git master:gh-pages

cd -
```

### 3. Add "deploy" script to package.json
```
"scripts": {
  ...
  "deploy": "bash deploy.sh"
  ...
```

### 4. Deploy to github
```
$ npm run deploy
```
Navigate to `https://kdevsoftware.github.io/vuex-checking/`.
