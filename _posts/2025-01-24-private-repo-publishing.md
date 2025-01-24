---
title: How to publish private repo to public github pages
---

## Step 1: Create github public repository for publishing.

* Create a new public repository in the github.
* The repository name will be the path.

## Step 2: Prepare private repository to make static web page.

For example, if you are using next js project:

* next.config.ts

```javascript
import type { NextConfig } from "next";
const isProd = process.env.NODE_ENV === "production";

const nextConfig: NextConfig = {
  /* config options here */
  output: "export",
  basePath: isProd ? '/{your path}' : '',
  assetPrefix: isProd ? "/{your path}" : '',
  images:{
      unoptimized: true,
  },
};

export default nextConfig;
```

* package.json

```json
{
    ...
    "homepage": "https://{your github id}.github.io/{your path}",
    ...

}

```

* Test by running build command

```bash
$ npm run build
```


## Step 3: Define github actions in the private repository.

* .github/workflows/deploy.yml

```
name: github pages

on:
  push:
    branches:
      - main  # Set a branch to deploy
  pull_request:

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v3

      - name: Install and Build
        run: |
          yarn install
          yarn build && touch ./out/.nojekyll
        env: 
          NEXT_PUBLIC_BASE_PATH: '/{your path}'

      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        with:
          deploy_key: ${{ secrets.PRIVATE_KEY }}
          external_repository: {your github id}/{your path}
          publish_branch: main
          publish_dir: ./out
```

## Step 4: Add Deploy key in the public repository.

* Check the existing keys and create one.

```bash
$ ls -al ~/.ssh/
$ ssh-keygen -t rsa -b 2048 -f ~/.ssh/{your key name}
```

* Settings -> Deploy keys

* Copy the content of "{your key name}.pub" and check "Allow write access"

## Step 5: Add Variable in the private repository.

* Settings -> Secrets and variables -> Actions -> New repository secret

* Create PRIVATE_KEY and paste the content of "{your key name}"

## Step 6: Rerun the action in the private repository.