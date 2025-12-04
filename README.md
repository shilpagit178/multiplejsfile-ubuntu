# JavaScript Project (Multiple Files)

This project demonstrates a simple multi-file JavaScript setup using Node.js and npm in Ubuntu.

## Requirements

Check if Node.js and npm are installed:

```bash
node -v
npm -v
```

If not installed:

```bash
sudo apt update
sudo apt install -y nodejs npm
```

## Project Structure

```
myjsproject/
├── src/
│   ├── main.js
│   └── input.js
├── package.json
├── .gitignore
└── README.md
```

## Steps to Create the Project

### Create folder

```bash
mkdir myjsproject
cd myjsproject
```

### Create source folder

```bash
mkdir src
```

### Create input.js

```bash
nano src/input.js
```

Paste:

```js
function add(a, b) {
    return a + b;
}

module.exports = { add };
```

### Create main.js

```bash
nano src/main.js
```

Paste:

```js
const { add } = require("./input.js");

function main() {
    const result = add(10, 20);
    console.log("Result =", result);
}

main();
```

### Test program

```bash
node src/main.js
```

## Initialize npm

```bash
npm init -y
```

## Add npm scripts

Edit package.json and replace scripts section:

```json
"scripts": {
  "start": "node src/main.js",
  "build": "mkdir -p build && cp src/*.js build/",
  "run": "node build/main.js",
  "clean": "rm -rf build"
}
```

## Usage

Run:

```bash
npm start
```

Build:

```bash
npm run build
```

Run built version:

```bash
npm run run
```

Clean:

```bash
npm run clean
```

## .gitignore

```
build/
node_modules/
```

## Git Setup (Optional)

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/<username>/<repo>.git
git push -u origin main
```
