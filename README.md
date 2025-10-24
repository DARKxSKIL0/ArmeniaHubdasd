<!DOCTYPE html>
<html lang="hy">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>ArmeniaHub Donate Shop</title>
  <style>
    body {
      font-family: 'Poppins', sans-serif;
      background: linear-gradient(135deg, #1e1e2f, #2a2a40);
      color: white;
      text-align: center;
      margin: 0;
      padding: 0;
    }
    header {
      background: #141422;
      padding: 20px;
      font-size: 28px;
      font-weight: bold;
      color: #f0b90b;
      text-shadow: 0 0 10px #f0b90b;
    }
    .server-ip {
      background: #202035;
      color: #00ff88;
      font-size: 18px;
      padding: 10px;
      border-bottom: 2px solid #f0b90b;
      box-shadow: 0 0 15px #00000055;
      text-shadow: 0 0 5px #00ff88;
    }
    .welcome {
      margin-top: 20px;
      font-size: 22px;
      animation: fadeIn 2s ease-in-out;
    }
    @keyframes fadeIn {
      0% {opacity: 0;}
      100% {opacity: 1;}
    }
    .shop {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 20px;
      padding: 40px;
    }
    .item {
      background: #202035;
      border: 2px solid #f0b90b;
      border-radius: 12px;
      width: 250px;
      padding: 20px;
      box-shadow: 0 0 15px #00000066;
      transition: transform 0.3s, box-shadow 0.3s;
    }
    .item:hover {
      transform: scale(1.05);
      box-shadow: 0 0 25px #f0b90b99;
    }
    .item img {
      width: 100px;
      height: 100px;
    }
    .price {
      font-size: 20px;
      color: #00ff88;
      margin-top: 10px;
    }
    .buy-btn {
      background: #f0b90b;
      border: none;
      padding: 10px 20px;
      border-radius: 8px;
      color: #000;
      font-weight: bold;
      cursor: pointer;
      transition: 0.3s;
      margin-top: 10px;
      text-decoration: none;
      display: inline-block;
    }
    .buy-btn:hover {
      background: #ffe15b;
    }
    .discord-btn {
      margin: 20px 0;
      display: inline-block;
      padding: 12px 25px;
      font-size: 18px;
      font-weight: bold;
      background: #2a58ff;
      color: #fff;
      border-radius: 10px;
      text-decoration: none;
      transition: transform 0.3s, background 0.3s;
    }
    .discord-btn:hover {
      background: #5b6eae;
      transform: scale(1.05);
    }
    footer {
      background: #141422;
      padding: 20px;
      color: #aaa;
      font-size: 14px;
    }
  </style>
</head>
<body>
  <header>💎 ArmeniaHub — Donate Shop</header>
  <div class="server-ip">🌍 Server IP: <b>armeniahub.aternos.me</b></div>

  <div class="welcome">Բարի գալուստ մեր ArmeniaHub Donate Shop! 🎉</div>

  <div class="shop" id="shop"></div>

  <a href="https://discord.gg/3PUcwqNc" target="_blank" class="discord-btn">Միանալ Discord Խմբին</a>

  <footer>
    © 2025 ArmeniaHub | Created by Gor
  </footer>

  <script>
    const products = [
      {name: "Hero", price: 200, image: "https://media.discordapp.net/attachments/1430942895791407169/1431201014719185018/Screenshot_20251024_123739_CapCut.jpg?ex=68fc8d50&is=68fb3bd0&hm=bb96869ac2eba52f9e25787e2f1c9a9166dc0e16db638b9bbb16f95107858d6d&=&format=webp&width=826&height=800", desc: "Gold privileges + Tag + Bonus Cash"},
      {name: "Bomj", price: 400, image: "https://media.discordapp.net/attachments/1430942895791407169/1431201014215606323/Screenshot_20251024_123745_CapCut.jpg?ex=68fc8d50&is=68fb3bd0&hm=a4dfb2339009e6a06e927f2f77985f2c94583774c1331b6ba93ffd842912fb6a&=&format=webp&width=654&height=800", desc: "Diamond Rank + Exclusive Commands"},
      {name: "Stringer", price: 600, image: "https://media.discordapp.net/attachments/1430942895791407169/1431202320489779210/Screenshot_20251024_123749_CapCut.jpg?ex=68fc8e87&is=68fb3d07&hm=8334b5fcf499682b7aa2abce63fcefca9bb59d461d86a7506eddbd25616ad621&=&format=webp&width=991&height=930", desc: "Exclusive tools + Armor bonus + Prefix"},
      {name: "Darsik", price: 800, image: "https://media.discordapp.net/attachments/1430942895791407169/1431201013867745401/Screenshot_20251024_123754_CapCut.jpg?ex=68fc8d50&is=68fb3bd0&hm=496df3c98e655688d0d9d00477f42365de05320b449994c3986528e60dba4b03&=&format=webp&width=780&height=800", desc: "VIP Kit + Money boost + Custom skin"},
      {name: "King", price: 1000, image: "https://media.discordapp.net/attachments/1430942895791407169/1431201013532196904/Screenshot_20251024_123759_CapCut.jpg?ex=68fc8d50&is=68fb3bd0&hm=d9b46b4f4466de21adcba3b7aa824d3536c955b6edefa6df69d3ddd6e751e50c&=&format=webp&width=811&height=800", desc: "King Rank + Unique effects + Bonus Money"},
      {name: "Armenia", price: 1200, image: "https://media.discordapp.net/attachments/1430942895791407169/1431201012978286625/Screenshot_20251024_123806_CapCut.jpg?ex=68fc8d4f&is=68fb3bcf&hm=52ea6859166b0aac3255b28d4cf7044cf5981d5da22bf8f834d4f19025fcddfd&=&format=webp&width=796&height=800", desc: "Get 500,000 In-Game Coins"},
      {name: "Donate Case", price: 200, image: "https://cdn.easydonate.ru/images/products/d9/0b/d90bb4d33cb17f6292afa8632f4bf48b4109c872dc93b3a104dbaf7f48aa0373.png", desc: "Open & Win Random Reward"}
    ];

    const shopContainer = document.getElementById("shop");
    products.forEach(item => {
      const div = document.createElement("div");
      div.classList.add("item");
      div.innerHTML = `
        <img src="${item.image}" alt="${item.name}">
        <h2>${item.name}</h2>
        <p>${item.desc}</p>
        <div class="price">${item.price} ֏</div>
        <button class="buy-btn" onclick="buyItem('${item.name}', ${item.price})">Գնել</button>
      `;
      shopContainer.appendChild(div);
    });

    function buyItem(name, price) {
      alert(`Դուք ընտրեցիք "${name}" արժեքով ${price} դրամ 💰\nՎճարումը կատարելու համար գրեք Discord-ում՝ haroyan22213`);
    }
  </script>
</body>
</html>
