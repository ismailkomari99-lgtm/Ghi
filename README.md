<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>NOIR — أزياء فاخرة</title>
<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700;900&family=Playfair+Display:ital,wght@0,700;1,400&display=swap" rel="stylesheet">
<style>
:root {
  --bg: #f8f5f0;
  --dark: #0e0c0a;
  --cream: #f0ebe3;
  --gold: #c9a84c;
  --gold2: #e8c96a;
  --text: #1a1814;
  --muted: #8a8070;
  --card: #ffffff;
  --border: #e0d8cc;
  --red: #c0392b;
}

* { margin:0; padding:0; box-sizing:border-box; }

html { scroll-behavior: smooth; }

body {
  background: var(--bg);
  color: var(--text);
  font-family: 'Cairo', sans-serif;
  overflow-x: hidden;
}

/* ─── TOPBAR ─── */
.topbar {
  background: var(--dark);
  color: #d4c9b8;
  text-align: center;
  padding: 9px;
  font-size: 0.78rem;
  letter-spacing: 1px;
  font-weight: 500;
}

/* ─── HEADER ─── */
header {
  background: var(--bg);
  border-bottom: 1px solid var(--border);
  position: sticky;
  top: 0;
  z-index: 200;
  padding: 0 32px;
  height: 70px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo {
  font-family: 'Playfair Display', serif;
  font-size: 1.8rem;
  font-weight: 700;
  letter-spacing: 4px;
  color: var(--dark);
}
.logo span { color: var(--gold); }

.header-nav { display: flex; gap: 28px; }
.header-nav a {
  text-decoration: none;
  color: var(--muted);
  font-size: 0.85rem;
  font-weight: 600;
  letter-spacing: 0.5px;
  transition: color 0.2s;
  cursor: pointer;
}
.header-nav a:hover { color: var(--dark); }

.header-actions { display: flex; gap: 16px; align-items: center; }

.icon-btn {
  background: none;
  border: none;
  cursor: pointer;
  font-size: 1.2rem;
  color: var(--dark);
  position: relative;
  transition: transform 0.2s;
}
.icon-btn:hover { transform: scale(1.1); }

.cart-count {
  position: absolute;
  top: -6px; left: -6px;
  background: var(--gold);
  color: var(--dark);
  font-size: 0.6rem;
  font-weight: 900;
  width: 16px; height: 16px;
  border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-family: 'Cairo', sans-serif;
}

/* ─── HERO ─── */
.hero {
  display: grid;
  grid-template-columns: 1fr 1fr;
  min-height: 88vh;
  overflow: hidden;
}

.hero-left {
  background: var(--dark);
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 80px 60px;
  position: relative;
  overflow: hidden;
}

.hero-left::before {
  content: '';
  position: absolute;
  width: 400px; height: 400px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(201,168,76,0.12), transparent 70%);
  top: -100px; right: -100px;
}

.hero-tag {
  display: inline-block;
  border: 1px solid rgba(201,168,76,0.4);
  color: var(--gold);
  font-size: 0.72rem;
  letter-spacing: 3px;
  padding: 6px 16px;
  margin-bottom: 28px;
  font-weight: 600;
  width: fit-content;
}

.hero-left h1 {
  font-family: 'Playfair Display', serif;
  font-size: clamp(2.5rem, 4vw, 4rem);
  font-weight: 700;
  color: #f5f0e8;
  line-height: 1.15;
  margin-bottom: 20px;
}

.hero-left h1 em {
  font-style: italic;
  color: var(--gold);
}

.hero-left p {
  color: #8a8070;
  font-size: 0.95rem;
  line-height: 1.9;
  margin-bottom: 40px;
  max-width: 380px;
  font-weight: 300;
}

.hero-btns { display: flex; gap: 14px; flex-wrap: wrap; }

.btn-primary {
  background: var(--gold);
  color: var(--dark);
  border: none;
  padding: 14px 32px;
  font-family: 'Cairo', sans-serif;
  font-weight: 700;
  font-size: 0.9rem;
  cursor: pointer;
  letter-spacing: 0.5px;
  transition: all 0.3s;
}
.btn-primary:hover { background: var(--gold2); transform: translateY(-2px); }

.btn-outline {
  background: transparent;
  color: #f5f0e8;
  border: 1px solid rgba(245,240,232,0.3);
  padding: 14px 32px;
  font-family: 'Cairo', sans-serif;
  font-weight: 600;
  font-size: 0.9rem;
  cursor: pointer;
  transition: all 0.3s;
}
.btn-outline:hover { border-color: var(--gold); color: var(--gold); }

.hero-right {
  background: var(--cream);
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  overflow: hidden;
}

.hero-emoji-display {
  font-size: 12rem;
  animation: float 4s ease-in-out infinite;
  filter: drop-shadow(0 30px 60px rgba(0,0,0,0.15));
}

@keyframes float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-16px); }
}

.hero-badge {
  position: absolute;
  bottom: 40px;
  right: 40px;
  background: var(--dark);
  color: var(--gold);
  padding: 14px 20px;
  text-align: center;
  font-size: 0.75rem;
  font-weight: 700;
  letter-spacing: 1px;
}
.hero-badge strong { display: block; font-size: 1.4rem; color: #fff; }

/* ─── SECTION ─── */
.section { padding: 80px 32px; max-width: 1300px; margin: 0 auto; }

.section-title {
  display: flex;
  align-items: center;
  gap: 16px;
  margin-bottom: 48px;
}
.section-title h2 {
  font-family: 'Playfair Display', serif;
  font-size: 2rem;
  font-weight: 700;
}
.section-title::after {
  content: '';
  flex: 1;
  height: 1px;
  background: var(--border);
}

/* ─── CATEGORIES ROW ─── */
.cats-row {
  display: flex;
  gap: 12px;
  margin-bottom: 40px;
  flex-wrap: wrap;
}
.cat-pill {
  background: var(--card);
  border: 1px solid var(--border);
  color: var(--muted);
  padding: 8px 20px;
  cursor: pointer;
  font-family: 'Cairo', sans-serif;
  font-size: 0.85rem;
  font-weight: 600;
  transition: all 0.2s;
}
.cat-pill:hover, .cat-pill.active {
  background: var(--dark);
  color: var(--gold);
  border-color: var(--dark);
}

/* ─── PRODUCTS GRID ─── */
.products-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
  gap: 24px;
}

.product-card {
  background: var(--card);
  border: 1px solid var(--border);
  cursor: pointer;
  transition: all 0.3s ease;
  animation: fadeUp 0.5s ease both;
  position: relative;
  overflow: hidden;
}
.product-card:hover {
  box-shadow: 0 20px 60px rgba(0,0,0,0.1);
  transform: translateY(-4px);
}

@keyframes fadeUp {
  from { opacity:0; transform:translateY(24px); }
  to { opacity:1; transform:translateY(0); }
}

.product-img {
  height: 280px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 6rem;
  position: relative;
  overflow: hidden;
}

.product-overlay {
  position: absolute;
  inset: 0;
  background: rgba(14,12,10,0.6);
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.3s;
}
.product-card:hover .product-overlay { opacity: 1; }

.quick-add {
  background: var(--gold);
  color: var(--dark);
  border: none;
  padding: 12px 28px;
  font-family: 'Cairo', sans-serif;
  font-weight: 700;
  font-size: 0.85rem;
  cursor: pointer;
  transform: translateY(10px);
  transition: transform 0.3s;
}
.product-card:hover .quick-add { transform: translateY(0); }

.p-badge {
  position: absolute;
  top: 14px;
  right: 14px;
  padding: 3px 12px;
  font-size: 0.7rem;
  font-weight: 700;
  letter-spacing: 1px;
}
.p-badge.new { background: var(--dark); color: var(--gold); }
.p-badge.sale { background: var(--red); color: white; }

.wish-btn {
  position: absolute;
  top: 14px;
  left: 14px;
  background: white;
  border: none;
  width: 34px; height: 34px;
  border-radius: 50%;
  cursor: pointer;
  font-size: 0.95rem;
  transition: transform 0.2s;
  display: flex; align-items: center; justify-content: center;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
}
.wish-btn:hover { transform: scale(1.1); }

.product-info { padding: 18px 18px 20px; }
.product-name { font-size: 0.95rem; font-weight: 700; margin-bottom: 4px; }
.product-sub { color: var(--muted); font-size: 0.78rem; margin-bottom: 10px; }

.product-bottom {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.price-wrap { display: flex; align-items: baseline; gap: 8px; }
.price { font-size: 1.1rem; font-weight: 900; color: var(--dark); }
.old-price { font-size: 0.78rem; color: var(--muted); text-decoration: line-through; }
.discount { font-size: 0.72rem; color: var(--red); font-weight: 700; }

.stars { color: var(--gold); font-size: 0.78rem; letter-spacing: 1px; }

/* ─── SIZES ─── */
.sizes { display: flex; gap: 6px; margin: 8px 0; flex-wrap: wrap; }
.size-tag {
  border: 1px solid var(--border);
  color: var(--muted);
  font-size: 0.7rem;
  padding: 2px 8px;
  font-weight: 600;
}

/* ─── BANNER ─── */
.banner {
  background: var(--dark);
  color: #f5f0e8;
  padding: 80px 32px;
  text-align: center;
  position: relative;
  overflow: hidden;
}
.banner::before {
  content: '';
  position: absolute;
  inset: 0;
  background: repeating-linear-gradient(
    45deg,
    transparent,
    transparent 40px,
    rgba(201,168,76,0.03) 40px,
    rgba(201,168,76,0.03) 80px
  );
}
.banner h2 {
  font-family: 'Playfair Display', serif;
  font-size: clamp(2rem, 5vw, 3.5rem);
  margin-bottom: 12px;
  position: relative;
}
.banner h2 span { color: var(--gold); font-style: italic; }
.banner p { color: #8a8070; margin-bottom: 32px; font-size: 1rem; position: relative; }

/* ─── FEATURES ─── */
.features {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1px;
  background: var(--border);
  border-top: 1px solid var(--border);
  border-bottom: 1px solid var(--border);
}
.feature {
  background: var(--bg);
  padding: 32px 24px;
  text-align: center;
}
.feature-icon { font-size: 1.8rem; margin-bottom: 10px; }
.feature h4 { font-size: 0.9rem; font-weight: 700; margin-bottom: 4px; }
.feature p { color: var(--muted); font-size: 0.78rem; line-height: 1.6; }

/* ─── CART DRAWER ─── */
.overlay {
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,0.5);
  z-index: 300;
  opacity: 0;
  pointer-events: none;
  transition: opacity 0.3s;
}
.overlay.open { opacity: 1; pointer-events: all; }

.cart-drawer {
  position: fixed;
  top: 0; left: 0;
  width: min(420px, 100vw);
  height: 100vh;
  background: var(--bg);
  z-index: 400;
  transform: translateX(-100%);
  transition: transform 0.4s cubic-bezier(0.4,0,0.2,1);
  display: flex;
  flex-direction: column;
  overflow: hidden;
}
.cart-drawer.open { transform: translateX(0); }

.cart-header {
  padding: 24px;
  border-bottom: 1px solid var(--border);
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.cart-header h3 { font-size: 1.1rem; font-weight: 700; }
.close-btn {
  background: none;
  border: none;
  font-size: 1.4rem;
  cursor: pointer;
  color: var(--muted);
}

.cart-items {
  flex: 1;
  overflow-y: auto;
  padding: 20px 24px;
}

.cart-item {
  display: flex;
  gap: 14px;
  padding: 16px 0;
  border-bottom: 1px solid var(--border);
  animation: fadeUp 0.3s ease;
}
.cart-item-emoji {
  font-size: 2.5rem;
  background: var(--cream);
  width: 70px; height: 70px;
  display: flex; align-items: center; justify-content: center;
  flex-shrink: 0;
}
.cart-item-info { flex: 1; }
.cart-item-name { font-weight: 700; font-size: 0.9rem; margin-bottom: 4px; }
.cart-item-price { color: var(--gold); font-weight: 700; font-size: 0.9rem; }
.cart-item-remove {
  background: none;
  border: none;
  color: var(--muted);
  cursor: pointer;
  font-size: 1rem;
  align-self: flex-start;
}

.cart-empty {
  text-align: center;
  padding: 60px 20px;
  color: var(--muted);
}
.cart-empty .empty-icon { font-size: 3rem; margin-bottom: 12px; }

.cart-footer {
  padding: 20px 24px;
  border-top: 1px solid var(--border);
}
.cart-total {
  display: flex;
  justify-content: space-between;
  margin-bottom: 16px;
  font-weight: 700;
  font-size: 1rem;
}
.checkout-btn {
  width: 100%;
  background: var(--dark);
  color: var(--gold);
  border: none;
  padding: 16px;
  font-family: 'Cairo', sans-serif;
  font-weight: 700;
  font-size: 0.95rem;
  cursor: pointer;
  letter-spacing: 1px;
  transition: background 0.2s;
}
.checkout-btn:hover { background: #1a1814; }

/* ─── ADMIN PANEL ─── */
.admin-panel {
  background: var(--dark);
  color: #f5f0e8;
  padding: 60px 32px;
  max-width: 1300px;
  margin: 0 auto;
}
.admin-panel .section-title h2 { color: #f5f0e8; }
.admin-panel .section-title::after { background: #2a2820; }

.admin-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 24px;
}

.admin-form {
  background: #1a1814;
  border: 1px solid #2a2820;
  padding: 28px;
}
.admin-form h4 { font-size: 0.95rem; font-weight: 700; margin-bottom: 20px; color: var(--gold); letter-spacing: 1px; }

.form-group { margin-bottom: 16px; }
.form-group label { display: block; font-size: 0.78rem; color: #8a8070; margin-bottom: 6px; font-weight: 600; letter-spacing: 0.5px; }
.form-group input, .form-group select, .form-group textarea {
  width: 100%;
  background: #0e0c0a;
  border: 1px solid #2a2820;
  color: #f5f0e8;
  padding: 10px 14px;
  font-family: 'Cairo', sans-serif;
  font-size: 0.88rem;
  outline: none;
  transition: border-color 0.2s;
  text-align: right;
}
.form-group input:focus, .form-group select:focus { border-color: var(--gold); }
.form-group textarea { height: 80px; resize: none; }
.form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }

.add-product-btn {
  width: 100%;
  background: var(--gold);
  color: var(--dark);
  border: none;
  padding: 12px;
  font-family: 'Cairo', sans-serif;
  font-weight: 700;
  font-size: 0.9rem;
  cursor: pointer;
  margin-top: 4px;
  transition: background 0.2s;
}
.add-product-btn:hover { background: var(--gold2); }

.admin-products-list { display: flex; flex-direction: column; gap: 10px; }
.admin-item {
  background: #1a1814;
  border: 1px solid #2a2820;
  padding: 14px 16px;
  display: flex;
  align-items: center;
  gap: 12px;
  transition: border-color 0.2s;
}
.admin-item:hover { border-color: var(--gold); }
.admin-item-emoji { font-size: 1.8rem; width: 44px; text-align: center; }
.admin-item-info { flex: 1; }
.admin-item-name { font-weight: 700; font-size: 0.88rem; }
.admin-item-meta { color: #8a8070; font-size: 0.75rem; margin-top: 2px; }
.admin-item-price { color: var(--gold); font-weight: 700; font-size: 0.9rem; }
.admin-delete {
  background: none;
  border: 1px solid #3a3830;
  color: #8a8070;
  padding: 5px 10px;
  cursor: pointer;
  font-size: 0.75rem;
  font-family: 'Cairo', sans-serif;
  transition: all 0.2s;
}
.admin-delete:hover { border-color: var(--red); color: var(--red); }

/* ─── TOAST ─── */
.toast {
  position: fixed;
  bottom: 28px;
  left: 50%;
  transform: translateX(-50%) translateY(80px);
  background: var(--dark);
  color: var(--gold);
  padding: 12px 28px;
  font-weight: 700;
  font-size: 0.88rem;
  z-index: 999;
  letter-spacing: 0.5px;
  transition: transform 0.4s cubic-bezier(0.34,1.56,0.64,1);
  border: 1px solid rgba(201,168,76,0.3);
  white-space: nowrap;
}
.toast.show { transform: translateX(-50%) translateY(0); }

/* ─── FOOTER ─── */
footer {
  background: var(--dark);
  color: #8a8070;
  padding: 60px 32px 32px;
}
.footer-grid {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr 1fr;
  gap: 40px;
  margin-bottom: 40px;
}
.footer-brand .logo { color: #f5f0e8; font-size: 1.5rem; margin-bottom: 12px; display: block; }
.footer-brand p { font-size: 0.82rem; line-height: 1.8; max-width: 240px; }
.footer-col h5 { color: #f5f0e8; font-size: 0.82rem; font-weight: 700; letter-spacing: 1px; margin-bottom: 16px; }
.footer-col a { display: block; color: #8a8070; text-decoration: none; font-size: 0.8rem; margin-bottom: 8px; transition: color 0.2s; }
.footer-col a:hover { color: var(--gold); }
.footer-bottom { border-top: 1px solid #1a1814; padding-top: 24px; text-align: center; font-size: 0.78rem; }

/* ─── RESPONSIVE ─── */
@media (max-width: 768px) {
  .hero { grid-template-columns: 1fr; }
  .hero-right { height: 300px; }
  .hero-left { padding: 48px 24px; }
  .header-nav { display: none; }
  header { padding: 0 16px; }
  .section { padding: 48px 16px; }
  .footer-grid { grid-template-columns: 1fr 1fr; }
  .admin-grid { grid-template-columns: 1fr; }
  .products-grid { grid-template-columns: repeat(2, 1fr); gap: 14px; }
}
</style>
</head>
<body>

<!-- TOPBAR -->
<div class="topbar">🚚 شحن مجاني للطلبات فوق 299 ر.س &nbsp;|&nbsp; عروض نهاية الموسم حتى 50%</div>

<!-- HEADER -->
<header>
  <div class="logo">NOIR<span>.</span></div>
  <nav class="header-nav">
    <a onclick="scrollTo('#products')">المنتجات</a>
    <a onclick="scrollTo('#collections')">الكولكشن</a>
    <a onclick="scrollTo('#admin')">إدارة المتجر</a>
    <a onclick="scrollTo('#contact')">تواصل</a>
  </nav>
  <div class="header-actions">
    <button class="icon-btn" onclick="openCart()">
      🛍️
      <span class="cart-count" id="cartCount">0</span>
    </button>
    <button class="icon-btn">🔍</button>
  </div>
</header>

<!-- HERO -->
<section class="hero">
  <div class="hero-left">
    <div class="hero-tag">✦ كولكشن 2025</div>
    <h1>أزياء تُعبّر<br>عن <em>شخصيتك</em></h1>
    <p>اكتشف أحدث صيحات الموضة العالمية بلمسة شرقية أصيلة. جودة استثنائية وتصاميم حصرية تجعلك مميزاً في كل مناسبة.</p>
    <div class="hero-btns">
      <button class="btn-primary" onclick="scrollTo('#products')">تسوّق الآن</button>
      <button class="btn-outline" onclick="scrollTo('#collections')">اكتشف الكولكشن</button>
    </div>
  </div>
  <div class="hero-right">
    <div class="hero-emoji-display">👗</div>
    <div class="hero-badge">
      <strong>+500</strong>
      منتج متوفر
    </div>
  </div>
</section>

<!-- FEATURES -->
<div class="features">
  <div class="feature">
    <div class="feature-icon">🚚</div>
    <h4>شحن سريع</h4>
    <p>توصيل خلال 24-48 ساعة لجميع المناطق</p>
  </div>
  <div class="feature">
    <div class="feature-icon">↩️</div>
    <h4>إرجاع مجاني</h4>
    <p>ضمان الإرجاع خلال 14 يوم بدون شروط</p>
  </div>
  <div class="feature">
    <div class="feature-icon">🔒</div>
    <h4>دفع آمن</h4>
    <p>جميع طرق الدفع مشفرة وآمنة 100%</p>
  </div>
  <div class="feature">
    <div class="feature-icon">💎</div>
    <h4>جودة مضمونة</h4>
    <p>منتجات مختارة بعناية من أفضل الماركات</p>
  </div>
</div>

<!-- PRODUCTS -->
<div id="products" style="max-width:1300px;margin:0 auto;padding:80px 32px 0;">
  <div class="section-title">
    <h2>أحدث المنتجات</h2>
  </div>
  <div class="cats-row" id="catRow">
    <div class="cat-pill active" onclick="filterCat('الكل',this)">الكل</div>
    <div class="cat-pill" onclick="filterCat('فساتين',this)">فساتين</div>
    <div class="cat-pill" onclick="filterCat('عبايات',this)">عبايات</div>
    <div class="cat-pill" onclick="filterCat('رجالي',this)">رجالي</div>
    <div class="cat-pill" onclick="filterCat('إكسسوار',this)">إكسسوار</div>
  </div>
  <div class="products-grid" id="productsGrid"></div>
</div>

<!-- BANNER -->
<div id="collections" style="margin-top:80px;">
  <div class="banner">
    <h2>كولكشن <span>الصيف</span> وصل</h2>
    <p>تصاميم حصرية مستوحاة من أجمال الوجهات العالمية</p>
    <button class="btn-primary" onclick="scrollTo('#products')">اكتشف الكولكشن</button>
  </div>
</div>

<!-- ADMIN PANEL -->
<div id="admin" style="padding:80px 0;">
  <div class="admin-panel">
    <div class="section-title">
      <h2>🛠️ إدارة المتجر</h2>
    </div>
    <div class="admin-grid">
      <!-- ADD FORM -->
      <div class="admin-form">
        <h4>+ إضافة منتج جديد</h4>
        <div class="form-group">
          <label>اسم المنتج</label>
          <input type="text" id="pName" placeholder="مثال: فستان سهرة فاخر">
        </div>
        <div class="form-row">
          <div class="form-group">
            <label>السعر (ر.س)</label>
            <input type="number" id="pPrice" placeholder="299">
          </div>
          <div class="form-group">
            <label>السعر القديم</label>
            <input type="number" id="pOld" placeholder="400">
          </div>
        </div>
        <div class="form-row">
          <div class="form-group">
            <label>الفئة</label>
            <select id="pCat">
              <option>فساتين</option>
              <option>عبايات</option>
              <option>رجالي</option>
              <option>إكسسوار</option>
            </select>
          </div>
          <div class="form-group">
            <label>الإيموجي</label>
            <input type="text" id="pEmoji" placeholder="👗">
          </div>
        </div>
        <div class="form-group">
          <label>الوسم</label>
          <select id="pBadge">
            <option value="">بدون</option>
            <option value="new">جديد</option>
            <option value="sale">تخفيض</option>
          </select>
        </div>
        <button class="add-product-btn" onclick="addProduct()">✦ إضافة المنتج</button>
      </div>

      <!-- PRODUCTS LIST -->
      <div>
        <div class="admin-form" style="margin-bottom:14px;padding:16px 20px;">
          <h4 style="margin-bottom:0;">📦 المنتجات (<span id="totalCount">0</span>)</h4>
        </div>
        <div class="admin-products-list" id="adminList"></div>
      </div>
    </div>
  </div>
</div>

<!-- CONTACT -->
<div id="contact" style="max-width:1300px;margin:0 auto;padding:0 32px 80px;">
  <div class="section-title">
    <h2>تواصل معنا</h2>
  </div>
  <div style="display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:20px;text-align:center;">
    <div style="background:var(--card);border:1px solid var(--border);padding:32px 20px;">
      <div style="font-size:2rem;margin-bottom:12px;">📱</div>
      <h4 style="margin-bottom:6px;">واتساب</h4>
      <p style="color:var(--muted);font-size:0.85rem;">+966 5X XXX XXXX</p>
    </div>
    <div style="background:var(--card);border:1px solid var(--border);padding:32px 20px;">
      <div style="font-size:2rem;margin-bottom:12px;">📸</div>
      <h4 style="margin-bottom:6px;">انستغرام</h4>
      <p style="color:var(--muted);font-size:0.85rem;">@noir.fashion</p>
    </div>
    <div style="background:var(--card);border:1px solid var(--border);padding:32px 20px;">
      <div style="font-size:2rem;margin-bottom:12px;">✉️</div>
      <h4 style="margin-bottom:6px;">البريد</h4>
      <p style="color:var(--muted);font-size:0.85rem;">hello@noir.sa</p>
    </div>
  </div>
</div>

<!-- FOOTER -->
<footer>
  <div class="footer-grid">
    <div class="footer-brand">
      <span class="logo">NOIR<span style="color:var(--gold)">.</span></span>
      <p>متجر أزياء فاخر يجمع بين الأناقة العصرية والهوية العربية الأصيلة.</p>
    </div>
    <div class="footer-col">
      <h5>المتجر</h5>
      <a href="#">الرئيسية</a>
      <a href="#">المنتجات</a>
      <a href="#">العروض</a>
      <a href="#">الجديد</a>
    </div>
    <div class="footer-col">
      <h5>المساعدة</h5>
      <a href="#">الشحن والتوصيل</a>
      <a href="#">سياسة الإرجاع</a>
      <a href="#">الأسئلة الشائعة</a>
    </div>
    <div class="footer-col">
      <h5>تواصل</h5>
      <a href="#">واتساب</a>
      <a href="#">انستغرام</a>
      <a href="#">البريد الإلكتروني</a>
    </div>
  </div>
  <div class="footer-bottom">© 2025 NOIR — جميع الحقوق محفوظة</div>
</footer>

<!-- CART DRAWER -->
<div class="overlay" id="overlay" onclick="closeCart()"></div>
<div class="cart-drawer" id="cartDrawer">
  <div class="cart-header">
    <h3>🛍️ سلة التسوق</h3>
    <button class="close-btn" onclick="closeCart()">×</button>
  </div>
  <div class="cart-items" id="cartItems"></div>
  <div class="cart-footer" id="cartFooter" style="display:none">
    <div class="cart-total">
      <span>الإجمالي</span>
      <span id="cartTotal">0 ر.س</span>
    </div>
    <button class="checkout-btn">إتمام الشراء ✦</button>
  </div>
</div>

<!-- TOAST -->
<div class="toast" id="toast"></div>

<script>
// ─── DATA ───
let products = [
  { id:1, name:'فستان سهرة راقي', cat:'فساتين', emoji:'👗', price:450, old:680, badge:'sale', sizes:['S','M','L','XL'] },
  { id:2, name:'عباءة كلاسيكية', cat:'عبايات', emoji:'🥻', price:320, old:null, badge:'new', sizes:['M','L','XL'] },
  { id:3, name:'جاكيت جلد فاخر', cat:'رجالي', emoji:'🧥', price:580, old:800, badge:'sale', sizes:['M','L','XL','XXL'] },
  { id:4, name:'حقيبة يد أنيقة', cat:'إكسسوار', emoji:'👜', price:290, old:null, badge:'new', sizes:[] },
  { id:5, name:'فستان كاجوال', cat:'فساتين', emoji:'👘', price:195, old:260, badge:'sale', sizes:['XS','S','M','L'] },
  { id:6, name:'عباءة مطرزة', cat:'عبايات', emoji:'🩱', price:420, old:null, badge:null, sizes:['M','L','XL'] },
  { id:7, name:'قميص رسمي', cat:'رجالي', emoji:'👔', price:150, old:200, badge:null, sizes:['S','M','L','XL'] },
  { id:8, name:'نظارة شمسية', cat:'إكسسوار', emoji:'🕶️', price:85, old:null, badge:'new', sizes:[] },
];

let cart = [];
let nextId = 9;
let currentCat = 'الكل';

const bgColors = ['#fef9f0','#f0f5fe','#f5f0fe','#f0fef5','#fef0f0','#f0fefe'];

// ─── RENDER PRODUCTS ───
function renderProducts() {
  const grid = document.getElementById('productsGrid');
  const list = currentCat === 'الكل' ? products : products.filter(p => p.cat === currentCat);
  grid.innerHTML = '';
  list.forEach((p, i) => {
    const disc = p.old ? Math.round((1 - p.price/p.old)*100) : 0;
    grid.innerHTML += `
    <div class="product-card" style="animation-delay:${i*0.07}s">
      <div class="product-img" style="background:${bgColors[i%bgColors.length]}">
        <span>${p.emoji}</span>
        <div class="product-overlay">
          <button class="quick-add" onclick="addToCart(${p.id})">+ أضف للسلة</button>
        </div>
        ${p.badge === 'new' ? '<div class="p-badge new">جديد</div>' : p.badge === 'sale' ? '<div class="p-badge sale">خصم</div>' : ''}
        <button class="wish-btn" onclick="this.textContent=this.textContent==='🤍'?'❤️':'🤍'">🤍</button>
      </div>
      <div class="product-info">
        <div class="product-name">${p.name}</div>
        <div class="product-sub">${p.cat}</div>
        ${p.sizes.length ? `<div class="sizes">${p.sizes.map(s=>`<span class="size-tag">${s}</span>`).join('')}</div>` : ''}
        <div class="product-bottom">
          <div class="price-wrap">
            <span class="price">${p.price} ر.س</span>
            ${p.old ? `<span class="old-price">${p.old}</span><span class="discount">-${disc}%</span>` : ''}
          </div>
          <div class="stars">★★★★★</div>
        </div>
      </div>
    </div>`;
  });
}

// ─── FILTER ───
function filterCat(cat, el) {
  currentCat = cat;
  document.querySelectorAll('.cat-pill').forEach(b => b.classList.remove('active'));
  el.classList.add('active');
  renderProducts();
}

// ─── CART ───
function addToCart(id) {
  const p = products.find(x => x.id === id);
  if (!p) return;
  const ex = cart.find(x => x.id === id);
  if (ex) ex.qty++;
  else cart.push({ ...p, qty: 1 });
  updateCartUI();
  showToast(`✓ تمت إضافة "${p.name}"`);
}

function removeFromCart(id) {
  cart = cart.filter(x => x.id !== id);
  updateCartUI();
}

function updateCartUI() {
  const total = cart.reduce((s, x) => s + x.qty, 0);
  document.getElementById('cartCount').textContent = total;
  renderCartItems();
}

function renderCartItems() {
  const el = document.getElementById('cartItems');
  const footer = document.getElementById('cartFooter');
  if (!cart.length) {
    el.innerHTML = `<div class="cart-empty"><div class="empty-icon">🛍️</div><p>السلة فارغة</p></div>`;
    footer.style.display = 'none';
    return;
  }
  footer.style.display = 'block';
  el.innerHTML = cart.map(p => `
    <div class="cart-item">
      <div class="cart-item-emoji">${p.emoji}</div>
      <div class="cart-item-info">
        <div class="cart-item-name">${p.name}</div>
        <div class="cart-item-price">${p.price * p.qty} ر.س${p.qty > 1 ? ` (×${p.qty})` : ''}</div>
      </div>
      <button class="cart-item-remove" onclick="removeFromCart(${p.id})">🗑️</button>
    </div>`).join('');
  const sum = cart.reduce((s, x) => s + x.price * x.qty, 0);
  document.getElementById('cartTotal').textContent = sum + ' ر.س';
}

function openCart() {
  document.getElementById('cartDrawer').classList.add('open');
  document.getElementById('overlay').classList.add('open');
  renderCartItems();
}
function closeCart() {
  document.getElementById('cartDrawer').classList.remove('open');
  document.getElementById('overlay').classList.remove('open');
}

// ─── ADMIN ───
function renderAdmin() {
  const list = document.getElementById('adminList');
  document.getElementById('totalCount').textContent = products.length;
  list.innerHTML = products.slice().reverse().map(p => `
    <div class="admin-item">
      <div class="admin-item-emoji">${p.emoji}</div>
      <div class="admin-item-info">
        <div class="admin-item-name">${p.name}</div>
        <div class="admin-item-meta">${p.cat} ${p.badge ? '· ' + (p.badge === 'new' ? 'جديد' : 'تخفيض') : ''}</div>
      </div>
      <div class="admin-item-price">${p.price} ر.س</div>
      <button class="admin-delete" onclick="deleteProduct(${p.id})">حذف</button>
    </div>`).join('');
}

function addProduct() {
  const name = document.getElementById('pName').value.trim();
  const price = +document.getElementById('pPrice').value;
  const old = +document.getElementById('pOld').value || null;
  const cat = document.getElementById('pCat').value;
  const emoji = document.getElementById('pEmoji').value || '👕';
  const badge = document.getElementById('pBadge').value || null;
  if (!name || !price) { showToast('⚠️ اكتب اسم المنتج والسعر'); return; }
  products.push({ id: nextId++, name, cat, emoji, price, old, badge, sizes:['S','M','L','XL'] });
  renderProducts();
  renderAdmin();
  document.getElementById('pName').value = '';
  document.getElementById('pPrice').value = '';
  document.getElementById('pOld').value = '';
  document.getElementById('pEmoji').value = '';
  showToast('✓ تمت إضافة المنتج بنجاح');
}

function deleteProduct(id) {
  products = products.filter(p => p.id !== id);
  renderProducts();
  renderAdmin();
  showToast('🗑️ تم حذف المنتج');
}

// ─── TOAST ───
let toastTimer;
function showToast(msg) {
  const t = document.getElementById('toast');
  t.textContent = msg;
  t.classList.add('show');
  clearTimeout(toastTimer);
  toastTimer = setTimeout(() => t.classList.remove('show'), 2800);
}

// ─── SCROLL ───
function scrollTo(id) {
  document.querySelector(id)?.scrollIntoView({ behavior: 'smooth' });
}

// ─── INIT ───
renderProducts();
renderAdmin();
</script>
</body>
</html>
