# Sito-per-vestiti-personalizate-
🌱Crediamo nella moda sostenibile e creativa. Ogni capo viene prodotto solo dopo l’ordine, per evitare sprechi e offrirti un prodotto davvero personalizzato, fatto con cura e passione.🌱
<!DOCTYPE html>
<html lang="it">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Il tuo stile personalizzato | MyWear</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>
    <h1>👕 MyWear</h1>
    <nav>
      <a href="index.html">Home</a>
      <a href="prodotto.html">Personalizza</a>
      <a href="#">Chi siamo</a>
    </nav>
  </header>

  <main class="hero">
    <h2>Crea il tuo stile unico</h2>
    <p>Su <strong>MyWear</strong> puoi creare vestiti personalizzati in pochi click: scegli colore, taglia e aggiungi il tuo testo o logo.</p>
    <a href="prodotto.html" class="btn">Inizia ora</a>
  </main>

  <footer>
    <p>© 2025 MyWear – Moda personalizzata con passione</p>
  </footer>
</body>
</html>
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
      <img id="productImage" src="tshirt-base.jpg" alt="T-shirt personalizzabile" style="max-width:100%;">
    </div>
    <div class="customizer">
      <div class="preview">
        <img id="previewImage" src="tshirt-base.jpg" alt="Anteprima" style="max-width:100%;">
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
      // Cambia immagine in base al colore (esempio semplice)
      preview.src = 'tshirt-' + color + '.jpg';
      const text = document.getElementById('text').value;
      if(text){
        // per semplicità, aggiungo testo come overlay (meglio usare canvas)
        preview.alt = 'T-shirt ' + color + ' con testo: ' + text;
      } else {
        preview.alt = 'T-shirt ' + color;
      }
    }

    document.getElementById('customForm').onsubmit = function(e){
      e.preventDefault();
      alert('Prodotto aggiunto al carrello con le opzioni selezionate!');
      // Qui invii al backend: colore, taglia, testo, prezzo, etc.
    }
  </script>
</body>
</html>
