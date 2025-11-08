# Sito-per-vestiti-personalizate-
🌱Crediamo nella moda sostenibile e creativa. Ogni capo viene prodotto solo dopo l’ordine, per evitare sprechi e offrirti un prodotto davvero personalizzato, fatto con cura e passione.🌱

  <!DOCTYPE html>
<html lang="it">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Personalizza il tuo capo</title>
  <style>
    body { font-family: Arial, sans-serif; margin:0; padding:20px; }
    .product-container { display: flex; flex-wrap: wrap; }
    .image { flex:1 1 300px; padding:10px; }
    .customizer { flex:1 1 300px; padding:10px; }
    label { display:block; margin:8px 0 4px; }
    select, input[type=text] { width:100%; padding:6px; margin-bottom:12px; }
    .preview { border:1px solid #ccc; padding:10px; text-align:center; margin-bottom:12px; }
    button { padding:10px 20px; background:#007BFF; color:#fff; border:none; cursor:pointer; }
    button:hover { background:#0056b3; }
  </style>
</head>
<body>
  <h1>Personalizza la tua T-shirt</h1>
  <div class="product-container">
    <div class="image">
      <!-- Maglietta bianca di default -->
      <img id="productImage" 
           src="https://upload.wikimedia.org/wikipedia/commons/2/24/White_Tshirt.jpg" 
           alt="T-shirt bianca personalizzabile" 
           style="max-width:100%; border:1px solid #ccc; border-radius:10px;">
    </div>
    <div class="customizer">
      <div class="preview">
        <!-- Anteprima iniziale -->
        <img id="previewImage" 
             src="https://upload.wikimedia.org/wikipedia/commons/2/24/White_Tshirt.jpg" 
             alt="Anteprima maglietta bianca" 
             style="max-width:100%; border-radius:10px;">
      </div>
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

  <script>
    function updatePreview(){
      const color = document.getElementById('color').value;
      const preview = document.getElementById('previewImage');
      const text = document.getElementById('text').value;

      // Cambia immagine in base al colore selezionato
      if(color === 'bianco'){
        preview.src = 'https://upload.wikimedia.org/wikipedia/commons/2/24/White_Tshirt.jpg';
      } else if(color === 'nero'){
        preview.src = 'https://upload.wikimedia.org/wikipedia/commons/8/88/Black_Tshirt.jpg';
      } else if(color === 'rosso'){
        preview.src = 'https://upload.wikimedia.org/wikipedia/commons/4/4d/Red_Tshirt.jpg';
      }

      // Aggiorna descrizione (puoi migliorarlo con overlay o canvas)
      if(text){
        preview.alt = 'T-shirt ' + color + ' con testo: ' + text;
      } else {
        preview.alt = 'T-shirt ' + color;
      }
    }

    document.getElementById('customForm').onsubmit = function(e){
      e.preventDefault();
      alert('Prodotto aggiunto al carrello con le opzioni selezionate!');
    }
  </script>
</body>
</html>
