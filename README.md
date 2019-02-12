# NODE + TYPESCRIPT = ♥
## FROM BASIC TO MASTER IN 5 MIN :p

### NODE

Install node from here: https://nodejs.org/it/download/

Node è una applicazione che prendendo in pasto un file js ne esegue le istruzioni in esso contenute. Facile!!

```
Hello_world.js

Console.log("Hello World!!");
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
 
### NPM

Oltre ai moduli standard e i file che ci scriviamo noi a mano c'è una folta comunità di persone che crea moduli e li distribuisce al mondo!!! il canale di distribuzione pricipare è https://www.npmjs.com/.

**NPM** è un tool che viene installato assieme a node e ne è il package manager. Tramite lui è possibile gestire package per il nostro progetto, creare script di build etc.. la documentazione completa è qui https://docs.npmjs.com/

Quello che interessa a noi è una piccola percentuale delle sue funzionalità.

per iniziare un nuovo progetto da console lanciare `npm init` e seuire le istruzioni. Alla fine si avrà nella folder di lavoro un file **package.json**. In esso è contenuto tutto ciò che riguarda il progetto!!

```
{
  "name": "examplejs",
  "version": "1.0.0",
  "description": "package.json example",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "me",
  "license": "ISC",
  "dependencies": {}
}
```

Di questo file ci interessa il campo **dependencies** e **dev-dependecies** in cui vengono specificati i package necessari per il nostro progetto. 

per aggiungere un nuovo package `npm install <nome_package>` e aspettare. Lanciando solo `npm install` npm scorre tutte le dependencies, verifica la presensa quindi installa le mancanti.

Alcuni package intervengono solo nella fase di coding o building ma non a runtime. Tali package possono esser installati come `--save-dev` in questo modo non verranno rilasciati in "realese".

Giusto per citarne alcuni:
 - expressjs
 - edgejs
 - gruntjs
 - loadash
 - jquery
 - bootstrap
 - react
 - ...

L'altra cosa figa che ci interessa è **scripts**! al sui interno possiamo specifica una serie di shell command che npm lancierà per noi invocando `npm run <nome_script>`. Possiamo farne quanti ne vogliamo e sono tendenzialmente utili per metter in piedi una pipeline di build.
