[Uploading MIPAGINA.html…]()
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Proyecto Completo</title>
  <style>
    * { box-sizing: border-box; }
    body {
      font-family: 'Poppins', sans-serif;
      margin: 0;
      background: linear-gradient(135deg, #fcd5ce, #faedcd, #d8f3dc);
      color: #444;
    }

    /* NAV */
    nav {
      background: #a2d2ff;
      padding: 15px;
      text-align: center;
    }
    nav a {
      margin: 0 15px;
      text-decoration: none;
      color: #fff;
      font-weight: bold;
      cursor: pointer;
    }
    nav a:hover {
      color: #ffb5a7;
    }

    section {
      display: none;
      padding: 40px 20px;
      min-height: 90vh;
      text-align: center;
    }
    section.active {
      display: block;
    }

    /* FORMULARIO */
    .formulario {
      background: #ffffffcc;
      padding: 30px;
      border-radius: 20px;
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
      width: 300px;
      margin: auto;
    }
    .formulario input {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border-radius: 10px;
      border: 1px solid #ccc;
    }
    .formulario button {
      padding: 10px 20px;
      border: none;
      border-radius: 10px;
      background: #a2d2ff;
      color: white;
      font-weight: bold;
      cursor: pointer;
    }
    .formulario button:hover {
      background: #89c2d9;
    }

    /* JUEGO */
    #sopa {
      display: grid;
      grid-template-columns: repeat(10, 40px);
      gap: 5px;
      justify-content: center;
      user-select: none;
      margin: 20px auto;
    }
    .cell {
      width: 40px;
      height: 40px;
      background: #fff;
      border-radius: 6px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: bold;
      cursor: pointer;
      border: 1px solid #ccc;
    }
    .cell.selected {
      background: #a0d8ef;
      color: white;
    }

    .word-list {
      margin-top: 20px;
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 10px;
    }
    .word {
      background: #f6d6d6;
      padding: 5px 10px;
      border-radius: 10px;
    }
    .word.found {
      background: #77c9d4;
      color: white;
      text-decoration: line-through;
    }

    /* CATALOGO */
    #catalogo {
      background-image: url('https://image.slidesdocs.com/responsive-images/background/sky-white-clouds-powerpoint-background_cba050973b__960_540.jpg');
      background-size: cover;
      background-position: center;
      background-attachment: fixed;
      color: #333;
    }
    #catalogo h1 {
      color: #0066cc;
    }
    #catalogo img {
      max-width: 90%;
      border-radius: 10px;
      margin: 15px auto;
      display: block;
    }
    #catalogo table {
      margin: auto;
      background: white;
      border-collapse: collapse;
    }
    #catalogo th, #catalogo td {
      padding: 10px;
      border: 1px solid #ccc;
    }
  </style>
</head>
<body>

  <!-- NAV -->
  <nav>
    <a onclick="mostrar('inicio')">Inicio</a>
    <a onclick="mostrar('juegos')">Juegos</a>
    <a onclick="mostrar('formulario')">Formulario</a>
    <a onclick="mostrar('catalogo')">Catálogo</a>
  </nav>

  <!-- INICIO -->
  <section id="inicio" class="active">
    <h1>Bienvenido 🎉</h1>
    <p>Explora juegos, completa el formulario o visita nuestro catálogo de motos.</p>
  </section>

  <!-- JUEGOS -->
  <section id="juegos">
    <h2>Sopa de Letras</h2>
    <div id="sopa"></div>
    <div class="word-list" id="palabras"></div>
  </section>

  <!-- FORMULARIO -->
  <section id="formulario">
    <h2>Formulario de contacto</h2>
    <div class="formulario">
      <input type="text" placeholder="Tu nombre" id="nombre" required>
      <input type="email" placeholder="tuemail@gmail.com" id="correo" required>
      <button onclick="enviarFormulario()">Enviar</button>
    </div>
  </section>

  <!-- CATALOGO -->
  <section id="catalogo">
    <h1>THUNDERSWIFT</h1>
    <p>En nuestra página puedes descubrir diferentes tipos de moto con excelente calidad.  
       Estas motos pueden correr hasta <b>280km/h</b> y tienen un precio razonable para su calidad.</p>

    <img src="https://cdn.leonardo.ai/users/cd9df3f6-62c2-4bf8-b018-137d45dfc035/generations/87371892-b680-4516-8dc0-a1e8843d2fa0/Leonardo_Phoenix_10_imagen_de_motos_de_alto_cc_en_un_entorno_u_3.jpg" alt="Moto de alto cilindraje">
    <ul>
      <li>
        <img src="https://cdn.leonardo.ai/users/cd9df3f6-62c2-4bf8-b018-137d45dfc035/generations/87371892-b680-4516-8dc0-a1e8843d2fa0/Leonardo_Phoenix_10_imagen_de_motos_de_alto_cc_en_un_entorno_u_0.jpg" alt="Moto deportiva">
      </li>
    </ul>
    <img src="https://img.freepik.com/fotos-premium/moto-superdeportiva-azul-3d-sobre-fondo-blanco-aislado-ilustracion-3d_101266-3874.jpg" width="1200" height="650" alt="moto deportiva">
    <table>
      <tr>
        <th>Modelos 2024</th>
        <th>Velocidad Máxima</th>
        <th>Precio</th>
      </tr>
      <tr>
        <td>Thunders317</td>
        <td>280 km/h</td>
        <td>$15,000</td>
      </tr>
    </table>
  </section>

  <!-- JS FUNCIONAL -->
  <script>
    // Cambiar de sección
    function mostrar(id) {
      document.querySelectorAll("section").forEach(sec => sec.classList.remove("active"));
      document.getElementById(id).classList.add("active");
    }

    // Formulario
    function enviarFormulario() {
      const nombre = document.getElementById("nombre").value;
      const correo = document.getElementById("correo").value;
      if (nombre && correo) {
        alert(`Gracias, ${nombre}. Hemos recibido tu correo: ${correo}`);
      } else {
        alert("Por favor, completa todos los campos.");
      }
    }

    // Juego: sopa de letras
    const palabras = ["SOL", "LUNA", "MAR", "CIELO", "NUBE"];
    const gridSize = 10;
    const letras = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
    const grid = Array.from({ length: gridSize }, () => Array(gridSize).fill(""));

    // Insertar palabras horizontalmente
    palabras.forEach(palabra => {
      let placed = false;
      while (!placed) {
        const row = Math.floor(Math.random() * gridSize);
        const col = Math.floor(Math.random() * (gridSize - palabra.length));
        let canPlace = true;
        for (let i = 0; i < palabra.length; i++) {
          if (grid[row][col + i] !== "" && grid[row][col + i] !== palabra[i]) {
            canPlace = false;
            break;
          }
        }
        if (canPlace) {
          for (let i = 0; i < palabra.length; i++) {
            grid[row][col + i] = palabra[i];
          }
          placed = true;
        }
      }
    });

    // Rellenar celdas vacías con letras aleatorias
    for (let r = 0; r < gridSize; r++) {
      for (let c = 0; c < gridSize; c++) {
        if (grid[r][c] === "") {
          grid[r][c] = letras[Math.floor(Math.random() * letras.length)];
        }
      }
    }

    const sopa = document.getElementById("sopa");
    const listaPalabras = document.getElementById("palabras");
    let seleccion = [];

    // Mostrar palabras
    palabras.forEach(p => {
      const w = document.createElement("div");
      w.textContent = p;
      w.className = "word";
      listaPalabras.appendChild(w);
    });

    // Mostrar grilla
    for (let r = 0; r < gridSize; r++) {
      for (let c = 0; c < gridSize; c++) {
        const cell = document.createElement("div");
        cell.className = "cell";
        cell.textContent = grid[r][c];
        cell.dataset.row = r;
        cell.dataset.col = c;
        cell.addEventListener("click", () => seleccionarCelda(cell));
        sopa.appendChild(cell);
      }
    }

    function seleccionarCelda(cell) {
      if (!cell.classList.contains("selected")) {
        cell.classList.add("selected");
        seleccion.push(cell);
      } else {
        cell.classList.remove("selected");
        seleccion = seleccion.filter(c => c !== cell);
      }

      const palabra = seleccion.map(c => c.textContent).join("");
      const invertida = palabra.split("").reverse().join("");

      if (palabras.includes(palabra) || palabras.includes(invertida)) {
        seleccion.forEach(c => {
          c.style.background = "#77c9d4";
          c.style.color = "white";
        });

        document.querySelectorAll(".word").forEach(w => {
          if (w.textContent === palabra || w.textContent === invertida) {
            w.classList.add("found");
          }
        });

        seleccion = [];
      }
    }
  </script>
</body>
</html>

<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Nombres</title>
</head>
<body>
    <h1>Hillary Cepeda y Durango Juan</h1>
</body>
</html>



