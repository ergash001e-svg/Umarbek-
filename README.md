<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Midasbuy - SCARIX UC</title>
    <link href="https://fonts.googleapis.com" rel="stylesheet">
    <style>
        :root { --blue: #0072ff; --bg: #f4f7f9; --dark: #1a1d24; }
        body { font-family: 'Roboto', sans-serif; background: var(--bg); margin: 0; padding-bottom: 120px; }
        
        /* Yuqori qism (Header) */
        header { background: var(--dark); padding: 15px 5%; display: flex; align-items: center; justify-content: space-between; border-bottom: 3px solid var(--blue); }
        .logo { color: white; font-size: 24px; font-weight: bold; letter-spacing: 1px; }
        .logo span { color: var(--blue); }

        .container { max-width: 900px; margin: 20px auto; padding: 0 15px; }

        /* Telegram Blok */
        .promo-banner { background: linear-gradient(90deg, #24A1DE, #0072ff); color: white; padding: 20px; border-radius: 12px; margin-bottom: 20px; display: flex; justify-content: space-between; align-items: center; }
        .promo-btn { background: white; color: var(--blue); text-decoration: none; padding: 10px 20px; border-radius: 6px; font-weight: bold; font-size: 14px; }

        /* Bo'limlar */
        .card { background: white; border-radius: 12px; padding: 25px; box-shadow: 0 4px 15px rgba(0,0,0,0.05); margin-bottom: 25px; }
        .title { font-size: 18px; font-weight: bold; margin-bottom: 20px; display: flex; align-items: center; }
        .title::before { content: ""; width: 5px; height: 20px; background: var(--blue); margin-right: 12px; border-radius: 2px; }

        /* ID kiritish */
        input { width: 100%; padding: 15px; border: 1.5px solid #ddd; border-radius: 8px; font-size: 16px; box-sizing: border-box; transition: 0.3s; }
        input:focus { border-color: var(--blue); outline: none; background: #f0f7ff; }

        /* UC Grid */
        .uc-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(160px, 1fr)); gap: 15px; }
        .uc-box { border: 2px solid #eee; border-radius: 12px; padding: 20px; text-align: center; cursor: pointer; transition: 0.2s; position: relative; background: #fff; }
        .uc-box:hover { border-color: var(--blue); background: #f9fcff; }
        .uc-box.active { border-color: var(--blue); background: #f0f7ff; }
        .uc-box img { width: 50px; margin-bottom: 12px; }
        .uc-amount { display: block; font-size: 18px; font-weight: bold; color: #333; }
        .uc-price { display: block; font-size: 14px; color: var(--blue); font-weight: bold; margin-top: 5px; }
        
        /* Tanlangan belgisi */
        .check { display: none; position: absolute; top: 10px; right: 10px; color: var(--blue); font-size: 18px; }
        .uc-box.active .check { display: block; }

        /* Pastki To'lov Paneli */
        .footer { position: fixed; bottom: 0; left: 0; right: 0; background: white; padding: 20px 8%; box-shadow: 0 -5px 20px rgba(0,0,0,0.1); display: flex; justify-content: space-between; align-items: center; z-index: 1000; }
        .total-label { color: #888; font-size: 14px; }
        .total-val { color: #ff5722; font-size: 24px; font-weight: bold; }
        .pay-btn { background: var(--blue); color: white; border: none; padding: 16px 60px; border-radius: 8px; font-size: 18px; font-weight: bold; cursor: pointer; transition: 0.3s; box-shadow: 0 4px 15px rgba(0,114,255,0.4); }
        .pay-btn:hover { transform: translateY(-2px); background: #005fdb; }

        @media (max-width: 600px) {
            .footer { flex-direction: column; gap: 15px; text-align: center; }
            .pay-btn { width: 100%; }
        }
    </style>
</head>
<body>

<header>
    <div class="logo">SCARIX<span>BUY</span></div>
    <div style="color: #999; font-size: 12px;">PUBG MOBILE UC RECHARGE</div>
</header>

<div class="container">
    <!-- Telegram -->
    <div class="promo-banner">
        <div>
            <div style="font-weight: bold; font-size: 18px;">Rasmiy Kanalimiz</div>
            <div style="font-size: 13px; opacity: 0.9;">Chegirmalar va UC yutuqlarini o'tkazib yubormang!</div>
        </div>
        <a href="https://t.me" target="_blank" class="promo-btn">OBUNA BO'LISH</a>
    </div>

    <!-- 1-Qadam -->
    <div class="card">
        <div class="title">Player ID Verification</div>
        <input type="number" id="uid" placeholder="Iltimos, Player ID kiriting (UID)">
    </div>

    <!-- 2-Qadam -->
    <div class="card">
        <div class="title">Select Recharge</div>
        <div class="uc-grid">
            <div class="uc-box" onclick="select(60, 12000, this)">
                <span class="check">✔</span>
                <img src="https://www.midasbuy.com">
                <span class="uc-amount">60 UC</span>
                <span class="uc-price">12,000 UZS</span>
            </div>
            <div class="uc-box" onclick="select(325, 60000, this)">
                <span class="check">✔</span>
                <img src="https://www.midasbuy.com">
                <span class="uc-amount">325 UC</span>
                <span class="uc-price">60,000 UZS</span>
            </div>
            <div class="uc-box" onclick="select(660, 115000, this)">
                <span class="check">✔</span>
                <img src="https://www.midasbuy.com">
                <span class="uc-amount">660 UC</span>
                <span class="uc-price">115,000 UZS</span>
            </div>
            <div class="uc-box" onclick="select(1800, 310000, this)">
                <span class="check">✔</span>
                <img src="https://www.midasbuy.com">
                <span class="uc-amount">1800 UC</span>
                <span class="uc-price">310,000 UZS</span>
            </div>
        </div>
    </div>
</div>

<div class="footer">
    <div>
        <div class="total-label">Jami to'lov:</div>
        <div class="total-val" id="price_tag">0 UZS</div>
    </div>
    <button class="pay-btn" onclick="order()">PAY NOW</button>
</div>

<script>
    let ucAmount = 0;
    let priceVal = 0;

    function select(uc, price, el) {
        ucAmount = uc;
        priceVal = price;
        document.querySelectorAll('.uc-box').forEach(b => b.classList.remove('active'));
        el.classList.add('active');
        document.getElementById('price_tag').innerText = price.toLocaleString() + " UZS";
    }

    function order() {
        const id = document.getElementById('uid').value;
        if(!id || ucAmount === 0) {
            alert("Iltimos, ID raqamingizni va UC paketini tanlang!");
            return;
        }

        const confirmSub = confirm("Kanalimizga obuna bo'ldingizmi? Buyurtmalar faqat obunachilar uchun!");
        
        if(confirmSub) {
            const msg = `🚀 SCARIX BUYURTMA:\n\n🆔 UID: ${id}\n💎 Paket: ${ucAmount} UC\n💰 Narxi: ${priceVal.toLocaleString()} UZS\n\nAdmin: @umarbek63`;
            window.location.href = `https://t.me{encodeURIComponent(msg)}`;
        } else {
            window.open("https://t.me", "_blank");
        }
    }
</script>

</body>
</html>
