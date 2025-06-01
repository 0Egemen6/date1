<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <title>dateteklifi</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      padding-top: 50px;
      background-color: #f5f5f5;
    }
    h1 {
      margin-bottom: 30px;
    }
    .button {
      display: block;
      margin: 10px auto;
      padding: 15px 30px;
      font-size: 18px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      transition: all 0.3s ease;
    }
    #yesBtn {
      background-color: green;
      color: white;
    }
    #noBtn {
      background-color: red;
      color: white;
    }
    #message {
      margin-top: 40px;
      font-size: 24px;
    }
    .heart {
      color: red;
      font-size: 60px;
      margin-bottom: 10px;
    }
  </style>
</head>
<body>

  <h1><a href="#">dateteklifi</a></h1>

  <button class="button" id="yesBtn">Evet</button>
  <button class="button" id="noBtn">Hayır</button>

  <div id="message"></div>

  <script>
    const yesBtn = document.getElementById("yesBtn");
    const noBtn = document.getElementById("noBtn");
    const message = document.getElementById("message");
    let noClickCount = 0;

    yesBtn.addEventListener("click", () => {
      message.innerHTML = `<div class="heart">❤️</div><div>bana yaz</div>`;
    });

    noBtn.addEventListener("click", () => {
      noClickCount++;
      if (noClickCount === 1) {
        message.innerText = "Emin misin?";
      } else if (noClickCount === 2) {
        message.innerText = "Bir daha düşün.";
      } else if (noClickCount === 3) {
        message.innerText = "Son kararın mı?";
      } else if (noClickCount === 4) {
        noBtn.style.display = "none";
        yesBtn.style.fontSize = "28px";
        yesBtn.style.padding = "20px 40px";
        message.innerText = "";
      }
    });
  </script>

</body>
</html>
