# API makima 👩🏻‍💻
<p>
 Una simple API devuelve más de 100 imágenes de cosplay de makima
  <br><br>
  Aquí está el enlace para usar en cualquier lugar 
 
**[URL-1](https://raw.githubusercontent.com/trezhywinks/API-Makima/refs/heads/main/makima.json) makima.json Github**
  
</p>

## index.js

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
