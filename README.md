# Node & Express
0. Create Project structures
- src/
    - config/
    - controllers/
    - database/
        - migrations/
    - models/
    - routes/
    - index.js
- .env
- .env.example
- .gitignore

1. Initiate Project

```
npm init -y
```
Langkah ini akan menghasilkan package.json dan package-lock.json

2. Install Dependecies
```
npm i express dotenv
npm i -D nodemon
```

3. Edit package.json
tambahkan:
```
"scripts": {
    "dev": "nodemon src/index.js --watch src/ --watch package.json --watch .env",
    "start": "node src/index.js"
  },
```

4. Edit .env.example dan .env:
```
SERVER_PORT=3000
```