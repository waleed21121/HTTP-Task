```js
const http = require("node:http");

//console.log(http);

const server = http.createServer((req, res)=>{
    const str = req.url;
    let arr = str.match(/\d+/g);
    let a = +arr[0];
    let b = +arr[1];
    let result = 0;
    if(str.match(/add/)){
        result = a + b;
    }
    else if(str.match(/subtract/)){
        result = a - b;
    }
    else if(str.match(/multiply/)){
        result = a * b;
    }
    else{
        result = a / b;
    }
    res.end(`Response => ${result}`);
});

server.listen(3000, ()=>{
    console.log("listen to 3000");
});
```
