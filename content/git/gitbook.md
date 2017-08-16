Install node and npm:
```bash
wget http://nodejs.org/dist/v5.1.0/node-v5.1.0-linux-x64.tar.gz
tar -xf node-v5.1.0-linux-x64.tar.gz
sudo npm install -g gitbook-cli@2.3.0
```

Creat a gitbook folder:
```bash
mkdir XPnotes
cd XPnotes
gitbook init
mkdir contents
mv README.md SUMMARY.md content/
```

Creat a empty repository on Github and connect it with a local git repositoty 
```bash
git init
git add -A
git commit -m "first"
git remote add origin https://github.com/TIBseqlab/XPnotes.git
git push -u origin master
```

Initial a gitbook:
```bash
npm init
```

Add the following codes into package.json
```bash
"scripts": {
 "start": "gitbook serve ./content ./gh-pages",
 "build": "gitbook build ./content ./gh-pages",
 "deploy": "node ./scripts/deploy-gh-pages.js",
 "publish": "npm run build && npm run deploy",
 "port": "lsof -i :35729"
},
```

Add "gh-pages" into "./gitignore" 
```bash
echo "gh-pages" >./gitignore
```

Install a "gh-pages" package
```bash
npm install --save gh-pages
mkdir scripts
vi scripts/deploy-gh-pages.js 
```

Add the following code:
```bash
'use strict';

var ghpages = require('gh-pages');

main();

function main() {
    ghpages.publish('./gh-pages', console.error.bind(console));
}
```

Publish the gitbook after update
```bash
npm run publish
```

