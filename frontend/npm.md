# NPM Cheatsheet

## Command line
### npx
serve a static html
```
npx serve
```

### Package Management
```
npm i
npm install
npm install lodash
npm install --save-dev lodash
npm install --save-exact lodash
```

### Updating
```
pm update
npm update --dev
npm update -g
npm update lodash
```

# Install Names
```
npm i sax
npm i sax@latest	                    // Specify tag latest
npm i sax@3.0.0	                        // Specify version 3.0.0
npm i sax@">=1 <2.0"	                // Specify version range
npm i @org/sax                          // Scoped NPM package
npm i user/repo//                       // GitHub
npm i user/repo#master	                // GitHub
npm i github:user/repo                  // GitHub
npm i gitlab:user/repo/                 / GitLab
npm i /path/to/repo                     // Absolute path
npm i ./archive.tgz                     // Tarball
npm i https://site.com/archive.tgz         // Tarball via HTTP
```

### Scripts
```
npm run <script>
```

### Credits
credit https://devhints.io/npm
