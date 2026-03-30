<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>سوق | متجر إلكتروني</title>
<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700;900&family=Tajawal:wght@300;400;500;700&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0a0f;
    --surface: #12121a;
    --card: #1a1a26;
    --accent: #f0a500;
    --accent2: #e05c00;
    --text: #f0ede8;
    --muted: #7a7890;
    --border: #2a2a3a;
    --glow: rgba(240,165,0,0.15);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Cairo', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Noise texture overlay */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.03'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 1000;
    opacity: 0.4;
  }

  /* ─── HEADER ─── */
  header {
    position: sticky;
    top: 0;
    z-index: 100;
    background: rgba(10,10,15,0.85);
    backdrop-filter: blur(16px);
    border-bottom: 1px solid var(--border);
    padding: 0 24px;
    height: 64px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .logo {
    font-size: 1.6rem;
    font-weight: 900;
    letter-spacing: -1px;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  nav { display: flex; gap: 8px; align-items: center; }

  nav a {
    color: var(--muted);
    text-decoration: none;
    font-size: 0.9rem;
    padding: 6px 14px;
    border-radius: 8px;
    transition: all 0.2s;
    font-weight: 500;
  }
  nav a:hover { color: var(--text); background: var(--card); }

  .cart-btn {
    background: var(--accent);
    color: #000;
    border: none;
    padding: 8px 18px;
    border-radius: 10px;
    cursor: pointer;
    font-family: 'Cairo', sans-serif;
    font-weight: 700;
    font-size: 0.9rem;
    display: flex;
    align-items: center;
    gap: 6px;
    transition: all 0.2s;
    position: relative;
  }
  .cart-btn:hover { background: #ffc133; transform: translateY(-1px); }
  .cart-badge {
    background: var(--accent2);
    color: white;
    border-radius: 50%;
    width: 18px; height: 18px;
    font-size: 0.65rem;
    display: flex; align-items: center; justify-content: center;
    position: absolute;
    top: -6px; left: -6px;
    font-weight: 900;
    transition: transform 0.3s;
  }
  .cart-badge.bump { transform: scale(1.4); }

  /* ─── HERO ─── */
  .hero {
    padding: 80px 24px 60px;
    text-align: center;
    position: relative;
    overflow: hidden;
  }

  .hero::before {
    content: '';
    position: absolute;
    top: -100px; left: 50%; transform: translateX(-50%);
    width: 600px; height: 600px;
    background: radial-gradient(circle, rgba(240,165,0,0.08) 0%, transparent 70%);
    pointer-events: none;
  }

  .hero-tag {
    display: inline-block;
    background: var(--card);
    border: 1px solid var(--border);
    color: var(--accent);
    font-size: 0.75rem;
    font-weight: 700;
    padding: 4px 14px;
    border-radius: 100px;
    margin-bottom: 20px;
    letter-spacing: 1px;
  }

  .hero h1 {
    font-size: clamp(2.2rem, 6vw, 4rem);
    font-weight: 900;
    line-height: 1.1;
    margin-bottom: 16px;
  }

  .hero h1 span {
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  .hero p {
    color: var(--muted);
    font-size: 1rem;
    max-width: 420px;
    margin: 0 auto 32px;
    font-family: 'Tajawal', sans-serif;
    font-weight: 300;
    line-height: 1.8;
  }

  /* ─── SEARCH ─── */
  .search-bar {
    max-width: 480px;
    margin: 0 auto 48px;
    display: flex;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    overflow: hidden;
    transition: border-color 0.2s;
  }
  .search-bar:focus-within { border-color: var(--accent); }
  .search-bar input {
    flex: 1;
    background: none;
    border: none;
    padding: 14px 18px;
    color: var(--text);
    font-family: 'Cairo', sans-serif;
    font-size: 0.95rem;
    outline: none;
    text-align: right;
  }
  .search-bar input::placeholder { color: var(--muted); }
  .search-bar button {
    background: var(--accent);
    border: none;
    padding: 12px 20px;
    cursor: pointer;
    font-size: 1.1rem;
    transition: background 0.2s;
  }
  .search-bar button:hover { background: #ffc133; }

  /* ─── CATEGORIES ─── */
  .categories {
    display: flex;
    gap: 10px;
    justify-content: center;
    flex-wrap: wrap;
    margin-bottom: 56px;
    padding: 0 24px;
  }

  .cat-btn {
    background: var(--card);
    border: 1px solid var(--border);
    color: var(--muted);
    padding: 8px 18px;
    border-radius: 100px;
    cursor: pointer;
    font-family: 'Cairo', sans-serif;
    font-size: 0.85rem;
    font-weight: 600;
    transition: all 0.2s;
  }
  .cat-btn:hover, .cat-btn.active {
    background: var(--accent);
    color: #000;
    border-color: var(--accent);
  }

  /* ─── SECTION TITLE ─── */
  .section-header {
    padding: 0 24px 24px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    max-width: 1200px;
    margin: 0 auto;
  }
  .section-header h2 {
    font-size: 1.4rem;
    font-weight: 700;
  }
  .section-header span {
    color: var(--muted);
    font-size: 0.85rem;
    cursor: pointer;
  }
  .section-header span:hover { color: var(--accent); }

  /* ─── PRODUCTS GRID ─── */
  .products-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
    gap: 20px;
    padding: 0 24px 80px;
    max-width: 1200px;
    margin: 0 auto;
  }

  .product-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    overflow: hidden;
    cursor: pointer;
    transition: all 0.3s ease;
    animation: fadeUp 0.5s ease both;
  }

  .product-card:hover {
    border-color: var(--accent);
    transform: translateY(-4px);
    box-shadow: 0 12px 40px rgba(240,165,0,0.1);
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .product-img {
    height: 200px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 4rem;
    position: relative;
    overflow: hidden;
  }

  .badge {
    position: absolute;
    top: 12px;
    right: 12px;
    background: var(--accent2);
    color: white;
    font-size: 0.7rem;
    font-weight: 700;
    padding: 3px 10px;
    border-radius: 100px;
  }

  .wishlist-btn {
    position: absolute;
    top: 12px;
    left: 12px;
    background: rgba(0,0,0,0.4);
    border: none;
    color: var(--muted);
    width: 32px; height: 32px;
    border-radius: 50%;
    cursor: pointer;
    font-size: 0.9rem;
    transition: all 0.2s;
    display: flex; align-items: center; justify-content: center;
  }
  .wishlist-btn:hover, .wishlist-btn.active { color: #ff4d6d; }

  .product-info { padding: 16px; }

  .product-name {
    font-size: 0.95rem;
    font-weight: 700;
    margin-bottom: 4px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }

  .product-cat {
    color: var(--muted);
    font-size: 0.78rem;
    margin-bottom: 10px;
    font-family: 'Tajawal', sans-serif;
  }

  .stars { color: var(--accent); font-size: 0.8rem; margin-bottom: 12px; letter-spacing: 1px; }

  .product-footer {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .price {
    font-size: 1.1rem;
    font-weight: 900;
    color: var(--accent);
  }

  .old-price {
    font-size: 0.78rem;
    color: var(--muted);
    text-decoration: line-through;
    margin-right: 6px;
  }

  .add-btn {
    background: var(--surface);
    border: 1px solid var(--border);
    color: var(--text);
    padding: 7px 14px;
    border-radius: 8px;
    cursor: pointer;
    font-family: 'Cairo', sans-serif;
    font-size: 0.82rem;
    font-weight: 600;
    transition: all 0.2s;
    display: flex; align-items: center; gap: 5px;
  }
  .add-btn:hover {
    background: var(--accent);
    color: #000;
    border-color: var(--accent);
  }

  /* ─── TOAST ─── */
  .toast {
    position: fixed;
    bottom: 24px;
    left: 50%;
    transform: translateX(-50%) translateY(80px);
    background: var(--accent);
    color: #000;
    padding: 12px 24px;
    border-radius: 12px;
    font-weight: 700;
    font-size: 0.9rem;
    z-index: 999;
    transition: transform 0.4s cubic-bezier(0.34,1.56,0.64,1);
    white-space: nowrap;
  }
  .toast.show { transform: translateX(-50%) translateY(0); }

  /* ─── FOOTER ─── */
  footer {
    border-top: 1px solid var(--border);
    padding: 32px 24px;
    text-align: center;
    color: var(--muted);
    font-size: 0.85rem;
    font-family: 'Tajawal', sans-serif;
  }

  /* ─── RESPONSIVE ─── */
  @media (max-width: 600px) {
    .products-grid { grid-template-columns: repeat(2, 1fr); gap: 12px; padding: 0 12px 60px; }
    .hero { padding: 48px 16px 40px; }
    nav a { display: none; }
  }
</style>
</head>
<body>

<!-- HEADER -->
<header>
  <div class="logo">سوق</div>
  <nav>
    <a href="#">الرئيسية</a>
    <a href="#">العروض</a>
    <a href="#">تواصل معنا</a>
  </nav>
  <button class="cart-btn" onclick="openCart()">
    <span class="cart-badge" id="badge">0</span>
    🛒 السلة
  </button>
</header>

<!-- HERO -->
<section class="hero">
  <div class="hero-tag">✦ وصل حديثاً</div>
  <h1>تسوّق بذكاء،<br>وفّر <span>أكثر</span></h1>
  <p>اكتشف آلاف المنتجات بأسعار لا تُضاهى، مع توصيل سريع إلى باب منزلك</p>
  <div class="search-bar">
    <input type="text" placeholder="ابحث عن منتج..." id="searchInput" oninput="filterProducts()">
    <button>🔍</button>
  </div>
</section>

<!-- CATEGORIES -->
<div class="categories" id="catButtons">
  <button class="cat-btn active" onclick="filterCat('الكل', this)">الكل</button>
  <button class="cat-btn" onclick="filterCat('إلكترونيات', this)">📱 إلكترونيات</button>
  <button class="cat-btn" onclick="filterCat('ملابس', this)">👕 ملابس</button>
  <button class="cat-btn" onclick="filterCat('طعام', this)">🍫 طعام</button>
  <button class="cat-btn" onclick="filterCat('رياضة', this)">⚽ رياضة</button>
  <button class="cat-btn" onclick="filterCat('منزل', this)">🏠 منزل</button>
</div>

<!-- PRODUCTS -->
<div class="section-header">
  <h2>المنتجات</h2>
  <span id="countLabel">جميع المنتجات</span>
</div>

<div class="products-grid" id="grid"></div>

<!-- TOAST -->
<div class="toast" id="toast">✓ تمت الإضافة إلى السلة</div>

<footer>
  © 2025 سوق — جميع الحقوق محفوظة
</footer>

<script>
const allProducts = [
  { id:1, name:'سماعات لاسلكية Pro', cat:'إلكترونيات', emoji:'🎧', price:199, old:280, stars:5, badge:'جديد' },
  { id:2, name:'ساعة ذكية Ultra', cat:'إلكترونيات', emoji:'⌚', price:349, old:500, stars:5, badge:'خصم' },
  { id:3, name:'شاحن سريع 65W', cat:'إلكترونيات', emoji:'🔌', price:59, old:null, stars:4, badge:null },
  { id:4, name:'تيشيرت قطن فاخر', cat:'ملابس', emoji:'👕', price:49, old:80, stars:4, badge:'خصم' },
  { id:5, name:'جاكيت شتوي', cat:'ملابس', emoji:'🧥', price:220, old:350, stars:5, badge:null },
  { id:6, name:'بنطلون جينز Slim', cat:'ملابس', emoji:'👖', price:89, old:null, stars:4, badge:null },
  { id:7, name:'شوكولاتة بلجيكية', cat:'طعام', emoji:'🍫', price:25, old:null, stars:5, badge:'الأكثر مبيعاً' },
  { id:8, name:'قهوة إثيوبية فاخرة', cat:'طعام', emoji:'☕', price:75, old:90, stars:5, badge:null },
  { id:9, name:'كرة قدم احترافية', cat:'رياضة', emoji:'⚽', price:120, old:160, stars:4, badge:null },
  { id:10, name:'حقيبة رياضية', cat:'رياضة', emoji:'🎒', price:95, old:null, stars:4, badge:'جديد' },
  { id:11, name:'مصباح ذكي RGB', cat:'منزل', emoji:'💡', price:65, old:85, stars:4, badge:null },
  { id:12, name:'إبريق شاي فاخر', cat:'منزل', emoji:'🫖', price:110, old:150, stars:5, badge:'خصم' },
];

let cartCount = 0;
let wishlist = new Set();
let currentCat = 'الكل';

const bg = [
  '#1a1020','#101a10','#0f1520','#1a1510','#101520','#1a0f15'
];

function renderProducts(list) {
  const grid = document.getElementById('grid');
  document.getElementById('countLabel').textContent = list.length + ' منتج';
  grid.innerHTML = '';
  list.forEach((p, i) => {
    const isWished = wishlist.has(p.id);
    const bgColor = bg[i % bg.length];
    grid.innerHTML += `
      <div class="product-card" style="animation-delay:${i * 0.06}s">
        <div class="product-img" style="background:${bgColor}">
          <span>${p.emoji}</span>
          ${p.badge ? `<div class="badge">${p.badge}</div>` : ''}
          <button class="wishlist-btn ${isWished ? 'active' : ''}" onclick="toggleWish(${p.id}, this)">
            ${isWished ? '❤️' : '🤍'}
          </button>
        </div>
        <div class="product-info">
          <div class="product-name">${p.name}</div>
          <div class="product-cat">${p.cat}</div>
          <div class="stars">${'★'.repeat(p.stars)}${'☆'.repeat(5-p.stars)}</div>
          <div class="product-footer">
            <div>
              ${p.old ? `<span class="old-price">${p.old} ر.س</span>` : ''}
              <span class="price">${p.price} ر.س</span>
            </div>
            <button class="add-btn" onclick="addToCart('${p.name}')">+ أضف</button>
          </div>
        </div>
      </div>`;
  });
}

function filterCat(cat, btn) {
  currentCat = cat;
  document.querySelectorAll('.cat-btn').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  applyFilters();
}

function filterProducts() { applyFilters(); }

function applyFilters() {
  const q = document.getElementById('searchInput').value.trim().toLowerCase();
  let list = currentCat === 'الكل' ? allProducts : allProducts.filter(p => p.cat === currentCat);
  if (q) list = list.filter(p => p.name.includes(q) || p.cat.includes(q));
  renderProducts(list);
}

function addToCart(name) {
  cartCount++;
  const badge = document.getElementById('badge');
  badge.textContent = cartCount;
  badge.classList.add('bump');
  setTimeout(() => badge.classList.remove('bump'), 300);
  showToast(`✓ تمت إضافة "${name}"`);
}

function toggleWish(id, btn) {
  if (wishlist.has(id)) {
    wishlist.delete(id);
    btn.textContent = '🤍';
    btn.classList.remove('active');
  } else {
    wishlist.add(id);
    btn.textContent = '❤️';
    btn.classList.add('active');
  }
}

function openCart() {
  showToast(cartCount > 0 ? `🛒 لديك ${cartCount} منتج في السلة` : '🛒 السلة فارغة');
}

let toastTimer;
function showToast(msg) {
  const t = document.getElementById('toast');
  t.textContent = msg;
  t.classList.add('show');
  clearTimeout(toastTimer);
  toastTimer = setTimeout(() => t.classList.remove('show'), 2500);
}

// init
renderProducts(allProducts);
</script>
</body>
</html>
