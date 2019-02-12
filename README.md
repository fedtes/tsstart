# NODE + TYPESCRIPT = ♥
## FROM BASIC TO MASTER IN 5 MIN :p

# NODE

Install node from here: https://nodejs.org/it/download/

Node è una applicazione che prendendo in pasto un file js ne esegue le istruzioni in esso contenute. Facile!!

```
Hello_world.js

Console.log("Hello Wolrd!!");
```

Aprendo cmd sulla folder contenente il file basta eseguire `node Hello_world.js`. Facile!!

Node offre una serie di strumenti per interagire con l'ambiente circostante (FileSystem, HTTP, etc...). Tali strumenti sono chiamati moduli e se ne trova la lista completa qui: https://nodejs.org/api/

Per chiedere a Node di utilizzare questi moduli basta usare il comando require:

```
const fs = require("fs");

fs.open('/open/some/file.txt', 'r', (err, fd) => {
  if (err) throw err;
  fs.close(fd, (err) => {
    if (err) throw err;
  });
});
```
 
Tramite `require` è possibile importare funzionalità anche da altri file js scritti di nostro pugno. Infatti ogni file js è considerato un modulo!!

```
Hello_world_from_Module.js

function salutation() {
  Console.log("Hello Wolrd!!");
}

module.exports={
  salutation:salutation
}
```
quindi:
```
index.js

const myMod= require("./Hello_world_from_Module.js");

myMod.salutation();
```

Tutto quello che serve (e anche oltre): https://medium.freecodecamp.org/requiring-modules-in-node-js-everything-you-need-to-know-e7fbd119be8
 
