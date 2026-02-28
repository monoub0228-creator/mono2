<!DOCTYPE html>
<html lang="mn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MONO — Сарын Хайрцаг | Японы амттан хайрцаг</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@300;400;500;600;700&family=Noto+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #FFFFFF;
    --bg-soft: #F9F7F4;
    --text: #1A1A1A;
    --text-mid: #555;
    --text-soft: #888;
    --accent: #E84B2B;
    --accent-dark: #C73D22;
    --green: #27AE60;
    --gold: #D4A843;
    --border: #EBEBEB;
  }
  * { margin: 0; padding: 0; box-sizing: border-box; }
  body { font-family: 'DM Sans', 'Noto Sans', sans-serif; background: var(--bg); color: var(--text); -webkit-font-smoothing: antialiased; }
  img { max-width: 100%; display: block; }
  a { text-decoration: none; color: inherit; }

  /* === ANNOUNCEMENT === */
  .announce {
    background: var(--text);
    color: #fff;
    text-align: center;
    padding: 8px 16px;
    font-size: 12px;
    letter-spacing: 0.03em;
    overflow: hidden;
  }
  .announce-inner { animation: marquee 20s linear infinite; white-space: nowrap; }
  @keyframes marquee { 0%{transform:translateX(100%)} 100%{transform:translateX(-100%)} }
  .announce strong { color: var(--accent); }

  /* === HEADER === */
  header {
    background: #fff;
    border-bottom: 1px solid var(--border);
    position: sticky;
    top: 0;
    z-index: 1000;
  }
  .header-inner {
    max-width: 1280px;
    margin: 0 auto;
    padding: 12px 24px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .logo { font-size: 24px; font-weight: 700; letter-spacing: 0.08em; }
  .logo small { font-size: 10px; font-weight: 400; color: var(--text-soft); display: block; margin-top: -2px; }
  .main-nav { display: flex; gap: 4px; list-style: none; }
  .main-nav a {
    padding: 8px 14px; font-size: 13px; font-weight: 500; color: var(--text-mid);
    border-radius: 6px; transition: all 0.2s;
  }
  .main-nav a:hover { background: var(--bg-soft); color: var(--text); }
  .main-nav a.active { background: var(--text); color: #fff; }
  .header-right { display: flex; align-items: center; gap: 12px; }
  .cart-btn {
    background: var(--accent); color: #fff; border: none; padding: 8px 18px;
    font-size: 13px; font-weight: 600; cursor: pointer; border-radius: 6px;
    display: flex; align-items: center; gap: 6px; transition: background 0.2s;
  }
  .cart-btn:hover { background: var(--accent-dark); }
  .ig-btn {
    padding: 8px 14px; font-size: 13px; font-weight: 500; color: var(--text-mid);
    border: 1px solid var(--border); border-radius: 6px; transition: all 0.2s;
  }
  .ig-btn:hover { border-color: var(--accent); color: var(--accent); }

  /* === BREADCRUMB === */
  .breadcrumb {
    max-width: 1280px; margin: 0 auto; padding: 16px 24px;
    font-size: 12px; color: var(--text-soft);
  }
  .breadcrumb a { color: var(--text-soft); }
  .breadcrumb a:hover { color: var(--accent); }

  /* === PRODUCT PAGE LAYOUT === */
  .product-page {
    max-width: 1280px;
    margin: 0 auto;
    padding: 0 24px 60px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 48px;
    align-items: start;
  }

  /* LEFT - IMAGES */
  .product-gallery {
    position: sticky;
    top: 80px;
  }
  .main-image {
    width: 100%;
    border-radius: 12px;
    overflow: hidden;
    background: var(--bg-soft);
    margin-bottom: 12px;
  }
  .main-image img {
    width: 100%;
    aspect-ratio: 1;
    object-fit: cover;
    transition: transform 0.5s;
  }
  .main-image:hover img { transform: scale(1.03); }
  .thumb-row {
    display: flex;
    gap: 8px;
  }
  .thumb {
    width: 80px;
    height: 80px;
    border-radius: 8px;
    overflow: hidden;
    border: 2px solid transparent;
    cursor: pointer;
    transition: border-color 0.2s;
    background: var(--bg-soft);
  }
  .thumb:hover, .thumb.active { border-color: var(--accent); }
  .thumb img { width: 100%; height: 100%; object-fit: cover; }

  /* RIGHT - PRODUCT INFO */
  .product-detail { padding-top: 8px; }
  .brand-label {
    font-size: 12px; text-transform: uppercase; letter-spacing: 0.1em;
    color: var(--accent); font-weight: 600; margin-bottom: 8px;
  }
  .product-detail h1 {
    font-size: 32px; font-weight: 700; line-height: 1.2; margin-bottom: 8px;
  }
  .product-detail .subtitle {
    font-size: 14px; color: var(--text-mid); margin-bottom: 20px; line-height: 1.6;
  }
  .rating-row {
    display: flex; align-items: center; gap: 8px; margin-bottom: 20px;
  }
  .stars { color: var(--gold); font-size: 16px; }
  .rating-text { font-size: 12px; color: var(--text-soft); }

  /* PRICE */
  .price-section {
    background: var(--bg-soft);
    border-radius: 10px;
    padding: 20px;
    margin-bottom: 24px;
  }
  .price-big {
    font-size: 36px; font-weight: 700; color: var(--accent); margin-bottom: 4px;
  }
  .price-per { font-size: 13px; color: var(--text-soft); }
  .price-save {
    display: inline-block;
    background: var(--green);
    color: #fff;
    font-size: 11px;
    font-weight: 700;
    padding: 3px 10px;
    border-radius: 20px;
    margin-top: 8px;
  }

  /* BOX OPTIONS */
  .box-options { margin-bottom: 24px; }
  .box-options h3 {
    font-size: 14px; font-weight: 600; margin-bottom: 12px;
    display: flex; align-items: center; gap: 6px;
  }
  .option-cards { display: flex; flex-direction: column; gap: 8px; }
  .opt-card {
    border: 2px solid var(--border);
    border-radius: 10px;
    padding: 16px 20px;
    cursor: pointer;
    transition: all 0.2s;
    display: flex;
    align-items: center;
    justify-content: space-between;
    position: relative;
  }
  .opt-card:hover { border-color: var(--text); }
  .opt-card.selected { border-color: var(--accent); background: #FFF5F3; }
  .opt-card .opt-left { display: flex; align-items: center; gap: 12px; }
  .opt-radio {
    width: 20px; height: 20px; border-radius: 50%;
    border: 2px solid var(--border); display: flex;
    align-items: center; justify-content: center; flex-shrink: 0;
  }
  .opt-card.selected .opt-radio { border-color: var(--accent); }
  .opt-card.selected .opt-radio::after {
    content: ''; width: 10px; height: 10px; border-radius: 50%;
    background: var(--accent);
  }
  .opt-name { font-size: 14px; font-weight: 600; }
  .opt-desc { font-size: 12px; color: var(--text-soft); margin-top: 2px; }
  .opt-price { font-size: 16px; font-weight: 700; text-align: right; }
  .opt-price small { font-size: 11px; color: var(--text-soft); font-weight: 400; display: block; }
  .opt-badge {
    position: absolute; top: -8px; right: 16px;
    background: var(--accent); color: #fff; font-size: 10px;
    font-weight: 700; padding: 2px 10px; border-radius: 10px;
    text-transform: uppercase;
  }

  /* CTA */
  .cta-btn {
    width: 100%;
    padding: 16px;
    background: var(--accent);
    color: #fff;
    border: none;
    font-size: 16px;
    font-weight: 700;
    cursor: pointer;
    border-radius: 10px;
    letter-spacing: 0.03em;
    transition: all 0.2s;
    margin-bottom: 12px;
  }
  .cta-btn:hover { background: var(--accent-dark); transform: translateY(-1px); box-shadow: 0 4px 16px rgba(232,75,43,0.3); }
  .cta-sub {
    text-align: center;
    font-size: 12px;
    color: var(--text-soft);
    margin-bottom: 24px;
  }

  /* FEATURES */
  .features {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
    margin-bottom: 32px;
  }
  .feat {
    background: var(--bg-soft);
    border-radius: 8px;
    padding: 14px;
    text-align: center;
  }
  .feat .fi { font-size: 24px; margin-bottom: 6px; }
  .feat h4 { font-size: 12px; font-weight: 600; margin-bottom: 2px; }
  .feat p { font-size: 11px; color: var(--text-soft); line-height: 1.4; }

  /* ADVANTAGES */
  .advantages {
    border-top: 1px solid var(--border);
    padding-top: 24px;
    margin-bottom: 32px;
  }
  .advantages h3 { font-size: 18px; font-weight: 700; margin-bottom: 16px; }
  .adv-item {
    display: flex;
    gap: 16px;
    margin-bottom: 20px;
    align-items: flex-start;
  }
  .adv-num {
    width: 36px; height: 36px; border-radius: 50%;
    background: var(--accent); color: #fff; font-weight: 700;
    display: flex; align-items: center; justify-content: center;
    font-size: 14px; flex-shrink: 0;
  }
  .adv-item h4 { font-size: 14px; font-weight: 600; margin-bottom: 4px; }
  .adv-item p { font-size: 13px; color: var(--text-mid); line-height: 1.6; }

  /* WHAT'S INSIDE */
  .whats-inside {
    border-top: 1px solid var(--border);
    padding-top: 24px;
  }
  .whats-inside h3 { font-size: 18px; font-weight: 700; margin-bottom: 16px; }
  .inside-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
  }
  .inside-item {
    background: var(--bg-soft);
    border-radius: 10px;
    padding: 16px;
    text-align: center;
  }
  .inside-item .ii-icon { font-size: 32px; margin-bottom: 8px; }
  .inside-item h4 { font-size: 12px; font-weight: 600; margin-bottom: 2px; }
  .inside-item p { font-size: 11px; color: var(--text-soft); }

  /* === BOTTOM SECTIONS === */
  .other-boxes {
    max-width: 1280px;
    margin: 0 auto;
    padding: 48px 24px;
    border-top: 1px solid var(--border);
  }
  .other-boxes h2 {
    font-size: 24px; font-weight: 700; text-align: center; margin-bottom: 32px;
  }
  .boxes-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 16px;
  }
  .box-card {
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
    transition: all 0.3s;
    cursor: pointer;
  }
  .box-card:hover { box-shadow: 0 8px 30px rgba(0,0,0,0.1); transform: translateY(-3px); }
  .box-card-img {
    aspect-ratio: 1;
    background: var(--bg-soft);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 4rem;
    position: relative;
  }
  .box-card-img .bc-badge {
    position: absolute; top: 10px; left: 10px;
    font-size: 10px; font-weight: 700; padding: 3px 10px;
    border-radius: 4px; text-transform: uppercase;
    background: var(--accent); color: #fff;
  }
  .box-card-body { padding: 14px; }
  .box-card-body h3 { font-size: 14px; font-weight: 600; margin-bottom: 4px; }
  .box-card-body p { font-size: 12px; color: var(--text-mid); margin-bottom: 8px; line-height: 1.5; }
  .box-card-body .bc-price { font-size: 18px; font-weight: 700; color: var(--accent); margin-bottom: 8px; }
  .box-card-body .bc-btn {
    width: 100%; padding: 8px; background: var(--text); color: #fff;
    border: none; border-radius: 6px; font-size: 12px; font-weight: 600;
    cursor: pointer; transition: background 0.2s;
  }
  .box-card-body .bc-btn:hover { background: var(--accent); }

  /* === FAQ === */
  .faq-section {
    max-width: 800px;
    margin: 0 auto;
    padding: 48px 24px;
  }
  .faq-section h2 { font-size: 24px; font-weight: 700; text-align: center; margin-bottom: 32px; }
  .faq-item {
    border-bottom: 1px solid var(--border);
    padding: 16px 0;
  }
  .faq-q {
    font-size: 14px; font-weight: 600; cursor: pointer;
    display: flex; justify-content: space-between; align-items: center;
  }
  .faq-q::after { content: '+'; font-size: 20px; color: var(--text-soft); transition: transform 0.2s; }
  .faq-q.open::after { content: '−'; }
  .faq-a {
    font-size: 13px; color: var(--text-mid); line-height: 1.7;
    max-height: 0; overflow: hidden; transition: max-height 0.3s ease, padding 0.3s ease;
  }
  .faq-a.open { max-height: 200px; padding-top: 12px; }

  /* === FOOTER === */
  .site-footer {
    background: var(--text); color: #fff; padding: 48px 24px 24px;
  }
  .footer-grid {
    max-width: 1280px; margin: 0 auto;
    display: grid; grid-template-columns: 2fr 1fr 1fr 1fr; gap: 40px; margin-bottom: 40px;
  }
  .footer-brand p { font-size: 12px; color: rgba(255,255,255,0.5); line-height: 1.7; max-width: 280px; }
  .footer-col h4 { font-size: 12px; font-weight: 600; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 16px; color: rgba(255,255,255,0.4); }
  .footer-col ul { list-style: none; }
  .footer-col li { margin-bottom: 8px; }
  .footer-col a { font-size: 13px; color: rgba(255,255,255,0.65); transition: color 0.2s; }
  .footer-col a:hover { color: var(--accent); }
  .footer-bottom {
    max-width: 1280px; margin: 0 auto; padding-top: 24px;
    border-top: 1px solid rgba(255,255,255,0.1);
    display: flex; justify-content: space-between; align-items: center;
  }
  .footer-bottom p { font-size: 11px; color: rgba(255,255,255,0.3); }
  .payment-icons { display: flex; gap: 8px; }
  .payment-icons span { background: rgba(255,255,255,0.1); padding: 4px 10px; border-radius: 4px; font-size: 10px; color: rgba(255,255,255,0.5); }

  /* === MODAL === */
  .modal-overlay {
    display: none; position: fixed; inset: 0; background: rgba(0,0,0,0.5);
    z-index: 9999; align-items: center; justify-content: center; backdrop-filter: blur(4px);
  }
  .modal-overlay.show { display: flex; }
  .modal {
    background: #fff; border-radius: 12px; padding: 40px; max-width: 420px;
    width: 90%; text-align: center; position: relative; animation: modalIn 0.3s ease;
  }
  @keyframes modalIn { from{opacity:0;transform:scale(0.95) translateY(10px)} to{opacity:1;transform:scale(1) translateY(0)} }
  .modal-close { position: absolute; top: 12px; right: 16px; background: none; border: none; font-size: 20px; cursor: pointer; color: var(--text-soft); }
  .modal h3 { font-size: 20px; font-weight: 700; margin-bottom: 8px; }
  .modal p { font-size: 13px; color: var(--text-mid); margin-bottom: 20px; line-height: 1.6; }
  .modal .ig-link {
    display: inline-flex; align-items: center; gap: 8px; padding: 14px 28px;
    background: linear-gradient(45deg, #f09433, #e6683c, #dc2743, #cc2366, #bc1888);
    color: #fff; border-radius: 8px; font-size: 14px; font-weight: 600; transition: transform 0.2s;
  }
  .modal .ig-link:hover { transform: scale(1.03); }
  .modal .qpay { margin-top: 12px; font-size: 12px; color: var(--text-soft); }

  /* === RESPONSIVE === */
  @media (max-width: 1024px) {
    .boxes-grid { grid-template-columns: repeat(2, 1fr); }
  }
  @media (max-width: 768px) {
    .main-nav { display: none; }
    .product-page { grid-template-columns: 1fr; gap: 24px; }
    .product-gallery { position: static; }
    .product-detail h1 { font-size: 24px; }
    .price-big { font-size: 28px; }
    .inside-grid { grid-template-columns: repeat(2, 1fr); }
    .boxes-grid { grid-template-columns: 1fr 1fr; gap: 10px; }
    .footer-grid { grid-template-columns: 1fr; gap: 24px; }
  }
</style>
</head>
<body>

<!-- ANNOUNCEMENT -->
<div class="announce">
  <div class="announce-inner">
    📦 <strong>Үнэгүй хүргэлт</strong> — ₮100,000+ захиалгад УБ хот доторх хүргэлт үнэгүй!&nbsp;&nbsp;&nbsp;🇯🇵 Японоос шууд — жинхэнэ, оригинал бүтээгдэхүүн&nbsp;&nbsp;&nbsp;💬 Захиалга: Instagram @mono.ub руу DM бичнэ үү!
  </div>
</div>

<!-- HEADER -->
<header>
  <div class="header-inner">
    <a href="mono-full-shop.html" class="logo">MONO<small>Japan → Mongolia</small></a>
    <ul class="main-nav">
      <li><a href="#" class="active">📦 Сарын Хайрцаг</a></li>
      <li><a href="mono-full-shop.html">🍫 КитКат</a></li>
      <li><a href="#">🍡 Амттан</a></li>
      <li><a href="#">🪵 Утлага</a></li>
      <li><a href="#">✒️ Бичиг хэрэг</a></li>
      <li><a href="#">🍵 Матча</a></li>
      <li><a href="#">🎁 Бэлэг</a></li>
    </ul>
    <div class="header-right">
      <a href="https://instagram.com/mono.ub" target="_blank" class="ig-btn">📷 @mono.ub</a>
      <button class="cart-btn" onclick="openModal()">🛒 Сагс (0)</button>
    </div>
  </div>
</header>

<!-- BREADCRUMB -->
<div class="breadcrumb">
  <a href="mono-full-shop.html">Нүүр</a> / <strong>Сарын Хайрцаг</strong>
</div>

<!-- PRODUCT PAGE -->
<div class="product-page">

  <!-- LEFT: GALLERY -->
  <div class="product-gallery">
    <div class="main-image" id="mainImg">
      <img src="https://www.tokyosnackbox.com/cdn/shop/products/TokyoSnackBox_Mensuelle.jpg?v=1664096524&width=1000" alt="MONO Сарын Хайрцаг" id="heroImg">
    </div>
    <div class="thumb-row">
      <div class="thumb active" onclick="changeImg(this, 'https://www.tokyosnackbox.com/cdn/shop/products/TokyoSnackBox_Mensuelle.jpg?v=1664096524&width=1000')">
        <img src="https://www.tokyosnackbox.com/cdn/shop/products/TokyoSnackBox_Mensuelle.jpg?v=1664096524&width=150" alt="">
      </div>
      <div class="thumb" onclick="changeImg(this, 'https://www.tokyosnackbox.com/cdn/shop/products/800x800-prod.jpg?v=1678676241&width=1000')">
        <img src="https://www.tokyosnackbox.com/cdn/shop/products/800x800-prod.jpg?v=1678676241&width=150" alt="">
      </div>
      <div class="thumb" onclick="changeImg(this, 'https://www.tokyosnackbox.com/cdn/shop/products/KitKat_Japan_Koi_Matcha.jpg?v=1676712594&width=1000')">
        <img src="https://www.tokyosnackbox.com/cdn/shop/products/KitKat_Japan_Koi_Matcha.jpg?v=1676712594&width=150" alt="">
      </div>
      <div class="thumb" onclick="changeImg(this, 'https://www.tokyosnackbox.com/cdn/shop/files/KitKat_Japan_Fuji_Blueberry_Cheesecake.jpg?v=1730934755&width=1000')">
        <img src="https://www.tokyosnackbox.com/cdn/shop/files/KitKat_Japan_Fuji_Blueberry_Cheesecake.jpg?v=1730934755&width=150" alt="">
      </div>
    </div>
  </div>

  <!-- RIGHT: DETAIL -->
  <div class="product-detail">
    <p class="brand-label">MONO • JAPAN → MONGOLIA</p>
    <h1>🎁 MONO Сарын Хайрцаг</h1>
    <p class="subtitle">Сар бүр Японоос шууд 15-20 төрлийн амттан, чихэр, КитКат + нэг бяцхан бэлэг. Сар бүр өөр өөр амт, сюрприз!</p>

    <div class="rating-row">
      <span class="stars">★★★★★</span>
      <span class="rating-text">4.9 / 5 — Хамгийн эрэлттэй бүтээгдэхүүн</span>
    </div>

    <!-- PRICE -->
    <div class="price-section">
      <div class="price-big">₮99,000</div>
      <p class="price-per">сар бүр • 15-20 ширхэг амттан + бэлэг</p>
      <span class="price-save">Дангаар авахаас ₮40,000+ хэмнэнэ!</span>
    </div>

    <!-- OPTIONS -->
    <div class="box-options">
      <h3>📦 Хайрцагаа сонгоно уу</h3>
      <div class="option-cards">
        <div class="opt-card selected" onclick="selectOpt(this)">
          <div class="opt-left">
            <div class="opt-radio"></div>
            <div>
              <p class="opt-name">🍫 Амттан Хайрцаг (Жижиг)</p>
              <p class="opt-desc">5-6 төрлийн бүс нутгийн онцгой амттан</p>
            </div>
          </div>
          <div class="opt-price">₮99,000<small>/хайрцаг</small></div>
        </div>
        <div class="opt-card" onclick="selectOpt(this)">
          <span class="opt-badge">🔥 Хит</span>
          <div class="opt-left">
            <div class="opt-radio"></div>
            <div>
              <p class="opt-name">🎊 Амттан Хайрцаг (Том)</p>
              <p class="opt-desc">10-12 амттан + ундаа + Японы бэлэг</p>
            </div>
          </div>
          <div class="opt-price">₮169,000<small>/хайрцаг</small></div>
        </div>
        <div class="opt-card" onclick="selectOpt(this)">
          <div class="opt-left">
            <div class="opt-radio"></div>
            <div>
              <p class="opt-name">✒️ Бичиг хэрэг Хайрцаг</p>
              <p class="opt-desc">3-4 бал + тэмдэглэлийн дэвтэр + наалт</p>
            </div>
          </div>
          <div class="opt-price">₮129,000<small>/хайрцаг</small></div>
        </div>
        <div class="opt-card" onclick="selectOpt(this)">
          <span class="opt-badge">Бэлэгт #1</span>
          <div class="opt-left">
            <div class="opt-radio"></div>
            <div>
              <p class="opt-name">🇯🇵 "Японы Амт" Холимог</p>
              <p class="opt-desc">Амттан + утлага + цай — бүгд нэг хайрцагт</p>
            </div>
          </div>
          <div class="opt-price">₮159,000<small>/хайрцаг</small></div>
        </div>
      </div>
    </div>

    <!-- CTA -->
    <button class="cta-btn" onclick="openModal()">📦 ЗАХИАЛАХ — INSTAGRAM DM</button>
    <p class="cta-sub">💬 @mono.ub руу DM бичнэ үү • QPay / Банкны шилжүүлэг</p>

    <!-- FEATURES -->
    <div class="features">
      <div class="feat">
        <div class="fi">🇯🇵</div>
        <h4>100% Японы оригинал</h4>
        <p>Бүх бүтээгдэхүүн Японоос шууд</p>
      </div>
      <div class="feat">
        <div class="fi">📦</div>
        <h4>Хурдан хүргэлт</h4>
        <p>УБ хотод 1-2 хоногт</p>
      </div>
      <div class="feat">
        <div class="fi">🎁</div>
        <h4>Бэлэг дагалдана</h4>
        <p>Сар бүр Японы бяцхан бэлэг</p>
      </div>
      <div class="feat">
        <div class="fi">🔄</div>
        <h4>Сар бүр өөр</h4>
        <p>Хэзээ ч давтагдахгүй!</p>
      </div>
    </div>

    <!-- 3 ADVANTAGES -->
    <div class="advantages">
      <h3>Яагаад MONO Хайрцаг?</h3>
      <div class="adv-item">
        <div class="adv-num">1</div>
        <div>
          <h4>Сар бүр амттай сюрприз 🎉</h4>
          <p>15-20 төрлийн Японы амттан, чихэр, КитКат — сар бүр өөр өөр! Дээрээс нь Японы соёлтой холбоотой бяцхан бэлэг: фигурка, хаашиг, ном тэмдэглэгч гэх мэт.</p>
        </div>
      </div>
      <div class="adv-item">
        <div class="adv-num">2</div>
        <div>
          <h4>Дангаар авахаас хямд 💰</h4>
          <p>Хайрцагт байгаа амттан бүрийг дангаар авбал ₮140,000+ болно. Хайрцгаар авахад ₮99,000! Та ₮40,000+ хэмнэнэ.</p>
        </div>
      </div>
      <div class="adv-item">
        <div class="adv-num">3</div>
        <div>
          <h4>Монголд цор ганц 🇲🇳</h4>
          <p>Эдгээр амттан Монголын ямар ч дэлгүүрт зарагддаггүй. Бүс нутгийн хязгаарлагдмал хувилбарууд — зөвхөн Японд л олддог бүтээгдэхүүн.</p>
        </div>
      </div>
    </div>

    <!-- WHAT'S INSIDE -->
    <div class="whats-inside">
      <h3>Хайрцагт юу байна?</h3>
      <div class="inside-grid">
        <div class="inside-item">
          <div class="ii-icon">🍫</div>
          <h4>КитКат 4-6 ширхэг</h4>
          <p>Бүс нутгийн онцгой амтууд</p>
        </div>
        <div class="inside-item">
          <div class="ii-icon">🍬</div>
          <h4>Чихэр & Моти</h4>
          <p>Японы уламжлалт чихэр</p>
        </div>
        <div class="inside-item">
          <div class="ii-icon">🍘</div>
          <h4>Давслаг амттан</h4>
          <p>Рис крэкер, нори чипс</p>
        </div>
        <div class="inside-item">
          <div class="ii-icon">🍡</div>
          <h4>Дагаши</h4>
          <p>Японы гудамжны чихэр</p>
        </div>
        <div class="inside-item">
          <div class="ii-icon">🥤</div>
          <h4>Ундаа (Том хайрцаг)</h4>
          <p>Японы онцгой ундаа</p>
        </div>
        <div class="inside-item">
          <div class="ii-icon">🎁</div>
          <h4>Бэлэг</h4>
          <p>Японы соёлын бяцхан бэлэг</p>
        </div>
      </div>
    </div>

  </div>
</div>

<!-- OTHER BOXES -->
<div class="other-boxes">
  <h2>🎁 Бусад хайрцагнууд</h2>
  <div class="boxes-grid">
    <div class="box-card" onclick="openModal()">
      <div class="box-card-img">
        🍫🍬🍡
        <span class="bc-badge">Хит #1</span>
      </div>
      <div class="box-card-body">
        <h3>Амттан Хайрцаг (Жижиг)</h3>
        <p>5-6 төрлийн бүс нутгийн онцгой амттан нэг хайрцагт</p>
        <div class="bc-price">₮99,000</div>
        <button class="bc-btn">ЗАХИАЛАХ</button>
      </div>
    </div>
    <div class="box-card" onclick="openModal()">
      <div class="box-card-img">
        🎊🍫🥤
        <span class="bc-badge">🔥 Том</span>
      </div>
      <div class="box-card-body">
        <h3>Амттан Хайрцаг (Том)</h3>
        <p>10-12 амттан + ундаа + Японы бяцхан бэлэг</p>
        <div class="bc-price">₮169,000</div>
        <button class="bc-btn">ЗАХИАЛАХ</button>
      </div>
    </div>
    <div class="box-card" onclick="openModal()">
      <div class="box-card-img">
        ✒️📓🎨
      </div>
      <div class="box-card-body">
        <h3>Бичиг хэрэг Хайрцаг</h3>
        <p>3-4 бал + тэмдэглэлийн дэвтэр + washi наалт</p>
        <div class="bc-price">₮129,000</div>
        <button class="bc-btn">ЗАХИАЛАХ</button>
      </div>
    </div>
    <div class="box-card" onclick="openModal()">
      <div class="box-card-img">
        🇯🇵🍵🪵
        <span class="bc-badge">Бэлэгт #1</span>
      </div>
      <div class="box-card-body">
        <h3>"Японы Амт" Холимог</h3>
        <p>Амттан + Hibi утлага + матча цай — бүгд нэг дор</p>
        <div class="bc-price">₮159,000</div>
        <button class="bc-btn">ЗАХИАЛАХ</button>
      </div>
    </div>
  </div>
</div>

<!-- FAQ -->
<div class="faq-section">
  <h2>❓ Түгээмэл асуултууд</h2>

  <div class="faq-item">
    <div class="faq-q" onclick="toggleFaq(this)">Хэрхэн захиалга өгөх вэ?</div>
    <div class="faq-a">Instagram @mono.ub руу DM бичиж захиалга өгнө үү. Бид таны захиалгыг 24 цагийн дотор баталгаажуулж, QPay эсвэл банкны шилжүүлгээр төлбөр хийнэ. Төлбөр хийсний дараа 1-2 хоногт хүргэнэ!</div>
  </div>

  <div class="faq-item">
    <div class="faq-q" onclick="toggleFaq(this)">Хүргэлт хэдэн хоногт ирэх вэ?</div>
    <div class="faq-a">УБ хот доторх захиалга 1-2 ажлын хоногт хүргэгдэнэ. ₮100,000+ захиалгад хүргэлт үнэгүй! Түүнээс бага захиалгад ₮5,000 хүргэлтийн төлбөр.</div>
  </div>

  <div class="faq-item">
    <div class="faq-q" onclick="toggleFaq(this)">Амттан бүр жинхэнэ Японынх уу?</div>
    <div class="faq-a">Тийм ээ! Бүх бүтээгдэхүүн Японоос шууд ирнэ. Манай Японд амьдардаг хамтрагч бараа бүрийг шууд худалдан авч, Монгол руу илгээдэг. Хуурамч, хуулбар юм огт байхгүй.</div>
  </div>

  <div class="faq-item">
    <div class="faq-q" onclick="toggleFaq(this)">Сар бүр захиалах шаардлагатай юу?</div>
    <div class="faq-a">Үгүй! Та хүссэн үедээ нэг удаагийн захиалга өгч болно. Сар бүр захиалах албагүй — хэзээ хүсвэл тэр үед DM бичнэ үү.</div>
  </div>

  <div class="faq-item">
    <div class="faq-q" onclick="toggleFaq(this)">Хайрцагт юу юу байх вэ?</div>
    <div class="faq-a">Сар бүр өөр өөр! Жишээ: 4-6 КитКат (бүс нутгийн онцгой амт), 3-4 Японы чихэр, моти, рис крэкер, дагаши + нэг бяцхан бэлэг. Том хайрцагт 10-12 амттан + Японы ундаа.</div>
  </div>

  <div class="faq-item">
    <div class="faq-q" onclick="toggleFaq(this)">Бэлэг болгож өгч болох уу?</div>
    <div class="faq-a">Мэдээж! Бэлгийн хайрцаг, захидал нэмж өгч болно. DM-ээр хэлнэ үү, бид тусгай бэлгийн боодолтой хийж өгнө.</div>
  </div>
</div>

<!-- FOOTER -->
<footer class="site-footer">
  <div class="footer-grid">
    <div class="footer-brand">
      <span class="logo" style="color:#fff">MONO<small style="color:rgba(255,255,255,0.4)">Japan → Mongolia</small></span>
      <p>Японы шилдэг бүтээгдэхүүн, Монголд шууд хүргэнэ. Бүс нутгийн онцгой амттан, гар урлалын утлага, бичиг хэрэгсэл.</p>
    </div>
    <div class="footer-col">
      <h4>Дэлгүүр</h4>
      <ul>
        <li><a href="#">📦 Сарын Хайрцаг</a></li>
        <li><a href="mono-full-shop.html">🍫 КитКат</a></li>
        <li><a href="#">🍡 Амттан</a></li>
        <li><a href="#">🪵 Утлага</a></li>
        <li><a href="#">✒️ Бичиг хэрэг</a></li>
        <li><a href="#">🍵 Матча</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Мэдээлэл</h4>
      <ul>
        <li><a href="#">Бидний тухай</a></li>
        <li><a href="#">Хүргэлтийн нөхцөл</a></li>
        <li><a href="#">Түгээмэл асуулт</a></li>
        <li><a href="#">Буцаалтын бодлого</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Холбоо барих</h4>
      <ul>
        <li><a href="https://instagram.com/mono.ub" target="_blank">📷 @mono.ub</a></li>
        <li><a href="https://facebook.com/mono.ub" target="_blank">📘 Facebook</a></li>
        <li><a href="mailto:hello@mono.mn">✉️ hello@mono.mn</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <p>© 2026 MONO — Authentic Japan, Delivered to Mongolia</p>
    <div class="payment-icons">
      <span>QPay</span>
      <span>Хаан Банк</span>
      <span>Голомт</span>
      <span>Бэлнээр</span>
    </div>
  </div>
</footer>

<!-- MODAL -->
<div class="modal-overlay" id="orderModal">
  <div class="modal">
    <button class="modal-close" onclick="closeModal()">✕</button>
    <h3>📦 Захиалга өгөх</h3>
    <p>Хайрцагаа захиалахын тулд манай Instagram хуудас руу DM бичнэ үү. 24 цагийн дотор баталгаажуулна!</p>
    <a href="https://instagram.com/mono.ub" target="_blank" class="ig-link">📷 @mono.ub руу DM бичих</a>
    <p class="qpay">💳 Төлбөр: QPay, банкны шилжүүлэг, бэлнээр</p>
  </div>
</div>

<script>
  // Modal
  function openModal() { document.getElementById('orderModal').classList.add('show'); }
  function closeModal() { document.getElementById('orderModal').classList.remove('show'); }
  document.getElementById('orderModal').addEventListener('click', function(e) { if(e.target===this) closeModal(); });

  // Image gallery
  function changeImg(thumb, src) {
    document.getElementById('heroImg').src = src;
    document.querySelectorAll('.thumb').forEach(t => t.classList.remove('active'));
    thumb.classList.add('active');
  }

  // Option selection
  function selectOpt(card) {
    document.querySelectorAll('.opt-card').forEach(c => c.classList.remove('selected'));
    card.classList.add('selected');
  }

  // FAQ toggle
  function toggleFaq(q) {
    q.classList.toggle('open');
    q.nextElementSibling.classList.toggle('open');
  }
</script>

</body>
</html>
