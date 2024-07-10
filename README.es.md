# Miguel E. Navas R.
## _Excuse Generator_

Antes de empezar a corregir mi proyecto sugiero instalar los paquetes escribiendo: ```$ npm install ```

Para ejecutar mi sitio web para ver los cambios en el browser; escribe en la línea de comandos ``` $ npm run start ```

He creado este pequeño sitio web que genera una excusa cada vez que se hace click en el boton [Change Excuse].

Del archivo original, he modificado solo los archivos

> index.html

> app.js

## INDEX.html
```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta
      name="description"
      content="In this website you will find an excuse generator created as a practice on JavaScript"
    />
    <meta
      name="keywords"
      content="html, css, bootstrap, javascript, practice, 4geeksacademy"
    />
    <meta name="author" content="Miguel E. Navas R." />
    <title>Excuse Generator</title>
  </head>
  <body class="bg-dark">
    <!--Title-->
    <h4 class="text-primary ms-3 pt-3">
      Miguel E. Navas R. - Excuse Generator
    </h4>
    <!--End Title-->

    <!--Excuse Generator-->
    <div class="d-flex align-items-center vh-100">
      <div class="container text-center">
        <h1 class="mt-5 text-light">OMG! you will not bealieve me but...</h1>
        <p id="excuse" class="text-danger">My dog ate my homework</p>
        <script src="app.js"></script>

        <!--Button-->
        <button id="button" type="button" class="btn btn-danger">
          Change Excuse
        </button>
        <!--End Button-->
      </div>
    </div>
    <!--EndExcuse Generator-->
  </body>
</html>
```

<img width="1662" alt="Website" src="https://github.com/4GeeksAcademy/menr_25-excuse-generator/assets/143790463/0d4df411-675c-4cb9-9669-3d22b84aabe1">

## APP.js
```
import "bootstrap";
import "./style.css";

import "./assets/img/rigo-baby.jpg";
import "./assets/img/4geeks.ico";

window.onload = function() {
  function excuseGenerator() {
    let who = ["The dog", "My grandma", "The mailman", "My bird"];
    let action = ["ate", "peed", "crushed", "broke"];
    let what = ["my homework", "my phone", "the car"];
    let when = [
      "before the class.",
      "when I was sleeping.",
      "while I was exercising.",
      "during my lunch.",
      "while I was praying."
    ];

    function randomElement(array) {
      return array[Math.floor(Math.random() * array.length)];
    }

    let excuse = `${randomElement(who)} ${randomElement(
      action
    )} ${randomElement(what)} ${randomElement(when)}`;

    return excuse;
  }

  function changeText() {
    let paragraph = document.getElementById("excuse");
    paragraph.innerText = excuseGenerator();
  }

  document.getElementById("button").addEventListener("click", changeText);
};
```

![Alt text](../src/assets/img/Website.png?raw=true "Website")
