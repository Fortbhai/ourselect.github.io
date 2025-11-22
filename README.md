<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>BitQu — Circuit Shop</title>
  <meta name="description" content="BitQu — Electronics & Components | Circuit themed shop" />
  <style>
    :root{
      --bg:#061212; --panel:#071818; --accent:#00ffcc; --muted:#8cf0d8;
      --glass: rgba(255,255,255,0.03);
      --card-radius:14px;
      --max-width:1100px;
    }
    *{box-sizing:border-box}
    body{margin:0;font-family:Inter, system-ui, Arial, sans-serif;background:linear-gradient(180deg,#031414 0%, #041a1a 100%);color:var(--muted);min-height:100vh;scroll-behavior:smooth;}
    header{padding:24px 18px;display:flex;align-items:center;justify-content:space-between;max-width:var(--max-width);margin:0 auto;position:sticky;top:0;z-index:1000;background:var(--bg)}
    .logo{display:flex;gap:12px;align-items:center}
    .logo-mark{width:56px;height:56px;border-radius:12px;background:linear-gradient(135deg,#002a2a,#004646);display:flex;align-items:center;justify-content:center;box-shadow:0 6px 18px rgba(0,255,204,0.07);border:2px solid rgba(0,255,204,0.08)}
    .logo-mark svg{filter:drop-shadow(0 6px 14px rgba(0,255,204,0.06))}
    .brand{font-weight:700;color:var(--accent);letter-spacing:0.6px}
    nav{display:flex;gap:12px;align-items:center}
    nav a{color:var(--muted);text-decoration:none;padding:8px 12px;border-radius:8px;cursor:pointer}
    nav a:hover{background:var(--glass);color:var(--accent)}

    .container{max-width:var(--max-width);margin:18px auto;padding:0 18px}
    .hero{display:grid;grid-template-columns:1fr 420px;gap:28px;align-items:center;margin-bottom:24px}
    .hero-card{background:linear-gradient(180deg, rgba(0,255,204,0.02), transparent);padding:22px;border-radius:16px;border:1px solid rgba(0,255,204,0.06)}
    .headline{font-size:28px;color:#dffbf2;margin:0 0 8px}
    .sub{color:#9ff3de;margin:0 0 12px}
    .cta{display:flex;gap:10px}
    .btn{background:var(--accent);color:#023232;border:none;padding:10px 14px;border-radius:10px;cursor:pointer;font-weight:600}
    .btn.ghost{background:transparent;color:var(--muted);border:1px solid rgba(0,255,204,0.06)}

    .catalog{display:grid;grid-template-columns:repeat(auto-fill,minmax(220px,1fr));gap:16px}
    .card{background:linear-gradient(180deg,rgba(255,255,255,0.01),transparent);border-radius:var(--card-radius);padding:12px;border:1px solid rgba(0,255,204,0.04);display:flex;flex-direction:column;gap:10px}
    .thumb{height:140px;border-radius:10px;background:linear-gradient(135deg,#002a2a,#003f3f);display:flex;align-items:center;justify-content:center;color:var(--accent);font-weight:700}
    .title{font-weight:700;color:#e6fff8}
    .price{font-weight:700;color:var(--accent)}
    .meta{font-size:13px;color:#9ff3de}
    .add{margin-top:auto}

    footer{max-width:var(--max-width);margin:30px auto 60px;padding:18px;color:#7ef0d7;text-align:center}

    /* Floating cart */
    #cartBtn{position:fixed;right:18px;bottom:18px;z-index:9999;background:transparent;border:2px solid var(--accent);color:var(--accent);padding:12px 16px;border-radius:999px;backdrop-filter:blur(6px);cursor:pointer}
    #cartPopup{position:fixed;right:18px;bottom:78px;width:340px;max-height:70vh;overflow:auto;background:linear-gradient(180deg,#031617,#062121);border:1px solid rgba(0,255,204,0.07);padding:12px;border-radius:12px;display:none;z-index:9999}
    .cart-item{display:flex;justify-content:space-between;padding:8px;border-radius:8px;border:1px dashed rgba(0,255,204,0.04);margin-bottom:8px}
    .remove{background:#ff5b5b;border:none;color:#fff;padding:4px 6px;border-radius:6px;cursor:pointer}
    .checkout{width:100%;padding:10px;border-radius:10px;border:none;background:var(--accent);color:#023232;font-weight:700;cursor:pointer}

    /* Responsive */
    @media (max-width:880px){.hero{grid-template-columns:1fr;padding:12px}.hero-card{order:2}.thumb{height:120px}}

    .circuit-bg{position:fixed;inset:0;pointer-events:none;opacity:0.06}
  </style>
</head>
<body>
  <svg class="circuit-bg" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1600 900" preserveAspectRatio="xMidYMid slice">
    <defs><linearGradient id="g1" x1="0" x2="1"><stop offset="0" stop-color="#00ffcc" stop-opacity="0.18"/><stop offset="1" stop-color="#00a89a" stop-opacity="0.08"/></linearGradient></defs>
    <rect width="1600" height="900" fill="none"/>
    <g stroke="url(#g1)" stroke-width="1.4" fill="none">
      <path d="M40 120h520v40M600 160h300v80M920 240h520" stroke-linecap="round"/>
      <circle cx="40" cy="120" r="4" fill="#00ffcc"/>
      <circle cx="1120" cy="240" r="4" fill="#00ffcc"/>
    </g>
  </svg>

  <header>
    <div class="logo">
      <div class="logo-mark" aria-hidden>
        <svg width="34" height="34" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><rect x="4" y="4" width="16" height="16" rx="3" stroke="#00ffcc" stroke-width="1.6"/><path d="M8 2v4M16 2v4M8 22v-4M16 22v-4M2 8h4M2 16h4M22 8h-4M22 16h-4" stroke="#00ffcc" stroke-width="1.2" stroke-linecap="round"/></svg>
      </div>
      <div>
        <div class="brand">BitQu</div>
        <div style="font-size:12px;color:#6ef0d2;margin-top:2px">Circuit Components & Modules</div>
      </div>
    </div>
    <nav>
      <a href="#products" onclick="scrollToSection(event, 'products')">Products</a>
      <a href="#about" onclick="scrollToSection(event, 'about')">About</a>
      <a href="#contact" onclick="scrollToSection(event, 'contact')">Contact</a>
    </nav>
  </header>

  <main class="container">
    <section class="hero">
      <div class="hero-card">
        <h1 class="headline">Circuit-grade parts, curated for makers</h1>
        <p class="sub">Boards, sensors, modules and essentials — designed for hobbyists and professionals. Fast WhatsApp ordering built-in.</p>
        <div class="cta">
          <button class="btn" onclick="scrollToSection(event, 'products')">Shop components</button>
          <button class="btn ghost" onclick="openCart()">Open Cart (<span id="floatingCount">0</span>)</button>
        </div>
      </div>
      <div class="hero-card" style="text-align:center">
        <div style="font-size:14px;color:#9ff3de;font-weight:700;margin-bottom:8px">Featured</div>
        <div style="font-size:20px;color:#e9fff7;font-weight:800">Arduino UNO R3</div>
        <div style="margin-top:10px;color:#9ff3de">Classic microcontroller board — perfect for prototyping.</div>
        <div style="margin-top:12px">Price: <span class="price">₹599</span></div>
        <div style="margin-top:12px"><button class="btn" onclick="addToCart('Arduino UNO R3',599)">Add to cart</button></div>
      </div>
    </section>

    <section id="products">
      <h2 style="color:#e6fff8">Products</h2>
      <div class="catalog" id="catalog"></div>
    </section>

    <section id="about" style="margin-top:26px">
      <h3 style="color:#dffbf2">About BitQu</h3>
      <p style="color:#9ff3de;max-width:820px">BitQu is a small electronics store focused on makers, student projects and repair. This demo store supports unlimited products and includes a WhatsApp checkout flow so you can get orders instantly on your phone.</p>
    </section>

    <section id="contact" style="margin-top:20px">
      <h3 style="color:#dffbf2">Contact</h3>
      <p style="color:#9ff3de">WhatsApp ordering: <a href="https://wa.me/919333583147" target="_blank" style="color:#00ffcc;font-weight:700">+91 93335 83147</a></p>
    </section>
  </main>

  <div id="cartBtn">🛒 Cart (<span id="cartCount">0</span>)</div>
  <div id="cartPopup">
    <div style="font-weight:800;color:#e6fff8;margin-bottom:8px">BitQu Cart</div>
    <div id="cartItemsWrap"></div>
    <div style="margin-top:4px;font-weight:700;color:var(--accent)">Total: ₹<span id="cartTotal">0</span></div>
    <div style="margin-top:4px;font-size:14px;color:#9ff3de">WhatsApp: <a href="https://wa.me/919333583147" target="_blank" style="color:#00ffcc">+91 93335 83147</a></div>
    <div style="margin-top:10px">
      <button class="checkout" onclick="checkout()">Checkout via WhatsApp</button>
    </div>
  </div>

  <footer>
    Built for BitQu • Host on GitHub Pages / Netlify / Vercel
  </footer>

<script>
const PRODUCTS = [
  {id:1, name:'Arduino UNO R3', price:599, desc:'Classic microcontroller board'},
  {id:2, name:'ESP32 Dev Module', price:749, desc:'Wi‑Fi + Bluetooth, dual core'},
  {id:3, name:'HC‑SR04 Ultrasonic', price:149, desc:'Distance sensor'},
  {id:4, name:'DS18B20 Temp Sensor', price:99, desc:'Waterproof temp probe'},
  {id:5, name:'5V Relay Module (1‑CH)', price:129, desc:'Relay for switching loads'},
  {id:6, name:'Breadboard Kit', price:199, desc:'Prototyping essentials'},
  {id:7, name:'Jumper Wires (40pcs)', price:79, desc:'Male‑female set'},
  {id:8, name:'Lithium Battery 18650', price:249, desc:'High capacity cell'},
];

let cart = JSON.parse(localStorage.getItem('bitqu_cart')||'[]');
const WA_NUMBER = '919333583147';
const DELIVERY = 69;

function saveCart(){ localStorage.setItem('bitqu_cart', JSON.stringify(cart)); updateCartUI(); }
function addToCart(name,price){ cart.push({name,price}); saveCart(); alert(name+' added to cart'); }
function removeFromCart(i){ cart.splice(i,1); saveCart(); }

function updateCartUI(){
  document.getElementById('cartCount').innerText = cart.length;
  document.getElementById('floatingCount').innerText = cart.length;

  const wrap = document.getElementById('cartItemsWrap'); 
  wrap.innerHTML = '';
  let subtotal = 0;

  cart.forEach((it, idx) => {
    subtotal += Number(it.price);
    const div = document.createElement('div'); 
    div.className = 'cart-item';
    div.innerHTML = `<div style="max-width:72%">${escapeHtml(it.name)}<div style="font-size:12px;color:#9ff3de">₹${it.price}</div></div><div><button class='remove' onclick='removeFromCart(${idx});saveCart()'>Remove</button></div>`;
    wrap.appendChild(div);
  });

  const deliveryDiv = document.createElement('div');
  deliveryDiv.className = 'cart-item';
  deliveryDiv.innerHTML = `<div style="max-width:72%">Delivery Charge</div><div>₹${DELIVERY}</div>`;
  wrap.appendChild(deliveryDiv);

  document.getElementById('cartTotal').innerText = subtotal + DELIVERY;
}

function openCart(){ document.getElementById('cartPopup').style.display = 'block'; }
function toggleCart(){ const p = document.getElementById('cartPopup'); p.style.display = (p.style.display==='block')?'none':'block'; }
document.getElementById('cartBtn').onclick = toggleCart;

function checkout(){
  if(cart.length===0){ alert('Cart is empty'); return; }
  let msg = '*BitQu Order*%0A%0A';
  cart.forEach(it=>{ msg += '%E2%9C%94%EF%B8%8F '+encodeURIComponent(it.name)+ ' — ₹'+it.price+'%0A'; });
  msg += '%0A*Delivery:* ₹'+DELIVERY+'%0A*Total:* ₹'+document.getElementById('cartTotal').innerText+'%0A%0A';
  msg += 'Please confirm order and shipping address.';
  const url = 'https://wa.me/'+WA_NUMBER+'?text='+msg;
  window.open(url,'_blank');
}

function renderCatalog(){
  const el = document.getElementById('catalog'); el.innerHTML = '';
  PRODUCTS.forEach(p=>{
    const card = document.createElement('div'); card.className='card';
    card.innerHTML = `
      <div class='thumb'>${escapeHtml(p.name.split(' ')[0])}</div>
      <div class='title'>${escapeHtml(p.name)}</div>
      <div class='meta'>${escapeHtml(p.desc)}</div>
      <div style='display:flex;justify-content:space-between;align-items:center;margin-top:8px'>
        <div class='price'>₹${p.price}</div>
        <div class='add'><button class='btn' onclick='addToCart(${jsonSafe(p.name)},${p.price})'>Add</button></div>
      </div>`;
    el.appendChild(card);
  });
}

function scrollToSection(event, id) {
  event.preventDefault();
  const el = document.getElementById(id);
  const headerOffset = 90;
  const elementPosition = el.getBoundingClientRect().top;
  const offsetPosition = elementPosition + window.pageYOffset - headerOffset;

  window.scrollTo({
    top: offsetPosition,
    behavior: 'smooth'
  });
}

function jsonSafe(s){ return JSON.stringify(s); }
function escapeHtml(s){ return String(s).replace(/[&<>\"']/g,function(m){return {'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;','\'':'&#39;'}[m]; }); }

renderCatalog(); updateCartUI();
</script>
</body>
</html>
