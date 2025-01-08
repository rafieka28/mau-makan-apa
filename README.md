<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mau Makan Apa</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f8f9fa;
      text-align: center;
    }
    header {
      background-color: #4caf50;
      color: white;
      padding: 20px;
    }
    h1 {
      margin: 0;
    }
    .container {
      padding: 20px;
    }
    .food-item {
      display: inline-block;
      margin: 10px;
      padding: 20px;
      width: 200px;
      border: 1px solid #ddd;
      border-radius: 10px;
      background-color: white;
      text-align: center;
      cursor: pointer;
      transition: transform 0.2s, box-shadow 0.2s;
    }
    .food-item:hover {
      transform: scale(1.05);
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    }
    img {
      width: 100%;
      max-width: 200px;  /* Ensuring uniform image size */
      height: auto;
      border-radius: 10px;
    }
    footer {
      margin-top: 20px;
      padding: 10px;
      background-color: #4caf50;
      color: white;
    }
    .location {
      margin-top: 20px;
      font-size: 18px;
      color: #333;
    }
    #selected-food {
      margin-top: 30px;
      display: none;
      text-align: center;
    }
    #selected-food img {
      width: 300px;
      max-width: 80%;
      border-radius: 10px;
    }
  </style>
</head>
<body>
  <header>
    <h1>Mau mam apa sayanggg</h1>
    <p>pilih makanan yang kamu mauu</p>
  </header>
  
  <div class="container">
    <div class="food-item" id="pecel" onclick="confirmChoice('Pecel Lele', 'Pecel Lele Cafe, Jalan Citarum', 'pecel', 'pecel.jpg')">
      <img src="pecel.jpg" alt="Pecel Lele">
      <h3>Pecel Lele</h3>
    </div>
    <div class="food-item" id="ramen" onclick="confirmChoice('Ramen', 'Ramen Shop, Jalan Sultan Tirtayasa No. 11a', 'ramen', 'ramen.jpg')">
      <img src="ramen.jpg" alt="Ramen">
      <h3>Ramen</h3>
    </div>
    <div class="food-item" id="baso" onclick="confirmChoice('Baso', 'Baso, Jalan Pahlawan desa kamp.cibodas ', 'baso', 'baso.jpg')">
      <img src="baso.jpg" alt="Baso">
      <h3>Baso</h3>
    </div>
    <div class="food-item" id="sate" onclick="confirmChoice('Sate', 'Sate, Jalan Pecinan Lama', 'sate', 'sate.jpg')">
      <img src="sate.jpg" alt="Sate">
      <h3>Ayam Om Hans</h3>
    </div>
    <div class="food-item" id="mie" onclick="confirmChoice('Mie Djawa', 'Mie Djawa, Di Kosan', 'mie', 'mie djawa.jpg')">
      <img src="mie djawa.jpg" alt="Mie Djawa">
      <h3>Mie Djawa</h3>
    </div>
  </div>

  <div id="location" class="location"></div>

  <div id="selected-food">
    <h2>Food yang kamu pilih:</h2>
    <img id="selected-image" src="" alt="Selected Food">
  </div>

  <footer>
    <p>© 2025 Rafi Eka Cahya Muhammad</p>
  </footer>

  <script>
    function confirmChoice(food, location, foodId, imageSrc) {
      const userConfirmed = confirm(`Yakin mau makan ${food}?`);
      if (userConfirmed) {
        alert(`Kamu pilih ${food}!`);
        // Display the location
        document.getElementById("location").innerHTML = `Tempat makan: ${location}`;
        
        // Show the selected food image
        const selectedImage = document.getElementById("selected-image");
        selectedImage.src = imageSrc;
        
        // Display the selected food image and info
        document.getElementById("selected-food").style.display = 'block';
        
        // Scroll to the selected food item
        const foodElement = document.getElementById(foodId);
        foodElement.scrollIntoView({ behavior: 'smooth', block: 'center' });
      } else {
        alert("Oke, pilih lagi!");
        document.getElementById("location").innerHTML = ''; // Clear location if user cancels
        document.getElementById("selected-food").style.display = 'none'; // Hide the selected food if cancelled
      }
    }
  </script>
</body>
</html>
