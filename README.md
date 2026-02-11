# API makima 👩🏻‍💻
## nodejs index.js

```ts
touch index.js
```
```ts
chmod +x index.js
```

```ts
#!/usr/bin/env node

const https = require("https");

const url = "https://api-makima.onrender.com/makima.json";

https.get(url, (res) => {
  let data = "";

  res.on("data", (chunk) => {
    data += chunk;
  });

  res.on("end", () => {
    try {
      const json = JSON.parse(data);
      console.log(JSON.stringify(json, null, 2));
    } catch (err) {
      console.error("Erro ao converter JSON:", err.message);
    }
  });

}).on("error", (err) => {
  console.error("Erro na requisição:", err.message);
});
```
