# monorepo-boilerplate
This project serves as a boilerplate for setting up a monorepo using Yarn Workspaces and Lerna.

## Usage
Run 'client' package which uses 'shared' package:
```
$ node packages/client/index.js
```

Run 'server' package which uses 'shared' package:
```
$ node packages/server/index.js
```

Run 'test' script in all packages with one command from root:
```
$ yarn test
```

## How was this created?

* Create package.json with ```"private": true``` and ```"workspaces": ["packages/*"]```.
* Create folder 'packages' with the subfolders: 'client', 'server', and 'shared'.
* Run ```yarn init -y``` in all packages subfolders.
* Add 'shared' as a dependency in package.json in 'client' and 'server' folders.
* Run ```yarn install```.
* Create an index.js file with a function in 'shared' folder.
* Create an index.js file in both 'client' and 'server' folders which requires 'shared'.
* Run ```yarn add -D -W lerna``` from root to add Lerna.
* Run ```npx lerna init``` to setup Lerna.
* Add ```"npmClient": "yarn"``` and ```"useWorkspaces": true``` to lerna.json.
* Add test script that runs lerna to package.json in root.
* Add test script to package.json in all packages folders.
