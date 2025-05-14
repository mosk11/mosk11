<!DOCTYPE html><html lang="ar">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>MO.NA</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(135deg, #ffd6e0, #ffe6f0);
      text-align: center;
      padding: 30px;
      direction: rtl;
    }h1 {
  font-size: 48px;
  color: #ff4081;
  text-shadow: 2px 2px 5px #ff80ab;
}

#love-btn {
  background-color: #ff4081;
  color: white;
  border: none;
  padding: 15px 30px;
  font-size: 24px;
  border-radius: 12px;
  cursor: pointer;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
}

#heart {
  font-size: 100px;
  color: red;
  opacity: 0;
  transform: scale(0.5);
  transition: all 0.6s ease-in-out;
  margin-top: 30px;
}

#heart.show {
  opacity: 1;
  transform: scale(1.5);
  animation: pulse 1s infinite;
}

@keyframes pulse {
  0%, 100% {
    transform: scale(1.5);
  }
  50% {
    transform: scale(1.8);
  }
}

textarea {
  width: 80%;
  height: 100px;
  margin-top: 30px;
  font-size: 18px;
  padding: 10px;
  border: 2px solid #ff80ab;
  border-radius: 10px;
  resize: none;
}

.decorations {
  margin-top: 30px;
  font-size: 32px;
}

  </style>
</head>
<body>  <h1>MO.NA</h1><button id="love-btn">mo.na</button>

  <div id="heart">❤️</div>  <textarea id="user-note" placeholder="اكتب رسالة جميلة..."></textarea>  <div class="decorations">
    محمد و ناهيا <br>
    ❤️ 💖 💫 ✨ 🌹 💕
  </div>  <script>
    const heart = document.getElementById('heart');
    const button = document.getElementById('love-btn');
    const textarea = document.getElementById('user-note');

    button.addEventListener('click', () => {
      heart.classList.add('show');
    });

    // Load saved message
    window.onload = () => {
      const saved = localStorage.getItem('note');
      if (saved) textarea.value = saved;
    };

    // Save message
    textarea.addEventListener('input', () => {
      localStorage.setItem('note', textarea.value);
    });
  </script></body>
</html>
