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
```bash

Initial a gitbook:
npm init
vi package.json
vi .gitignore

npm install --save gh-pages
mkdir scripts

vi scripts/deploy-gh-pages.js 

npm run publish


