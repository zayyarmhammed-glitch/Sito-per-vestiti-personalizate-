# Sito-per-vestiti-personalizate-
🌱Crediamo nella moda sostenibile e creativa. Ogni capo viene prodotto solo dopo l’ordine, per evitare sprechi e offrirti un prodotto davvero personalizzato, fatto con cura e passione.🌱
<!DOCTYPE html>
<html lang="it">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Personalizza la tua T-shirt</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 20px;
      background-color: #f5f5f5;
    }

    h1 {
      text-align: center;
      margin-bottom: 30px;
    }

    .product-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      background: #fff;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 2px 6px rgba(0,0,0,0.1);
      max-width: 900px;
      margin: 0 auto;
    }

    .image, .customizer {
      flex: 1 1 300px;
      padding: 15px;
    }

    .preview {
      border: 1px solid #ccc;
      padding: 10px;
      text-align: center;
      background: #fafafa;
      border-radius: 10px;
      margin-bottom: 12px;
    }

    label {
      display: block;
      margin: 8px 0 4px;
      font-weight: bold;
    }

    select, input[type=text] {
      width: 100%;
      padding: 8px;
      margin-bottom: 12px;
      border-radius: 5px;
      border: 1px solid #ccc;
    }

    button {
      padding: 10px 20px;
      background: #007BFF;
      color: #fff;
      border: none;
      cursor: pointer;
      border-radius: 5px;
      margin-right: 10px;
    }

    button:hover {
      background: #0056b3;
    }

    footer {
      text-align: center;
      margin-top: 40px;
      font-size: 14px;
      color: #777;
    }

    /* Testo sopra immagine */
    .preview-container {
      position: relative;
      display: inline-block;
    }

    #overlayText {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      color: black;
      font-size: 22px;
      font-weight: bold;
      text-shadow: 0 0 4px white;
    }
  </style>
</head>
<body>

  <h1>👕 Personalizza la tua T-shirt</h1>

  <div class="product-container">
    <div class="image">
      <div class="preview">
        <div class="preview-container">
          <img id="previewImage" 
               src="https://upload.wikimedia.org/wikipedia/commons/2/24/White_Tshirt.jpg" 
               alt="T-shirt bianca" 
               style="max-width:100%; border-radius:10px;">
          <div id="overlayText"></div>
        </div>
      </div>
    </div>

    <div class="customizer">
      <form id="customForm">
        <label for="color">Colore:</label>
        <select id="color" name="color">
          <option value="bianco">Bianco</option>
          <option value="nero">Nero</option>
          <option value="rosso">Rosso</option>
        </select>

        <label for="size">Taglia:</label>
        <select id="size" name="size">
          <option value="S">S</option>
          <option value="M">M</option>
          <option value="L">L</option>
          <option value="XL">XL</option>
        </select>

        <label for="text">Testo da stampare (opzionale):</label>
        <input type="text" id="text" name="text" placeholder="Es: IL MIO NOME">

        <button type="button" onclick="updatePreview()">Aggiorna Anteprima</button>
        <button type="submit">Aggiungi al carrello</button>
      </form>
    </div>
  </div>

  <footer>
    © 2025 MyWear - Crea il tuo stile unico
  </footer>

  <script>
    function updatePreview() {
      const color = document.getElementById('color').value;
      const text = document.getElementById('text').value;
      const img = document.getElementById('previewImage');
      const overlay = document.getElementById('overlayText');

      // Cambia immagine in base al colore
      if (color === 'bianco') {
        img.src = 'https://upload.wikimedia.org/wikipedia/commons/2/24/White_Tshirt.jpg';
      } else if (color === 'nero') {
        img.src = 'https://upload.wikimedia.org/wikipedia/commons/8/88/Black_Tshirt.jpg';
      } else if (color === 'rosso') {
        img.src = 'https://upload.wikimedia.org/wikipedia/commons/4/4d/Red_Tshirt.jpg';
      }

      // Mostra testo sull'immagine
      overlay.textContent = text;
      overlay.style.color = (color === 'nero') ? 'white' : 'black';
    }

    document.getElementById('customForm').onsubmit = function(e) {
      e.preventDefault();
      const color = document.getElementById('color').value;
      const size = document.getElementById('size').value;
      const text = document.getElementById('text').value;
      alert(`Hai aggiunto al carrello una T-shirt ${color} taglia ${size} con testo: "${text}"`);
    };
  </script>

</body>
</html>
    }

