# Node
1. Create
# Node & Express
0. Create Project structures
- src/
    - config/
    - controllers/
    - database/
        - migrations/
    - models/
    - routes/
        - router.js
    - index.js
- .env
- .env.example
- .gitignore

1. Initiate Project

```
npm init -y
```
Langkah ini akan menghasilkan package.json dan package-lock.json

2. Install Dependencies
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

4. modifikasi isi .gitignore
```
node_modules
.env
```

5. Modifikasi isi .env.example dan .env:
```
SERVER_PORT=3000
```

6. Modifikasi isi index.js
```
const path = require("path");

require("dotenv").config({ path: path.join(__dirname, "../.env") });

const express = require("express");
const router = require("./routes/router");

const app = express();

app.use(express.urlencoded({ extended: true }));
app.use(express.json());

app.use("/", router);

app.listen(process.env.SERVER_PORT || 3000, () => {
  console.log("Server Running");
});
```

7. Modifikasi is routes/router.js
```
const express = require("express");

const router = express.Router();

router.get("/", function (req, res) {
  res.send({
    serverMessage: "Hello World!",
    serverTime: new Date(),
  });
});

module.exports = router;
```