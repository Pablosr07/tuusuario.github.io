# tuusuario.github.io
<!doctype html>
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>TuMarca — Tienda</title>
  <link rel="stylesheet" href="styles.css" />
  <meta name="description" content="Tienda digital minimalista para vender ropa. Plantilla lista para GitHub Pages / Netlify.">
</head>
<body>
  <header class="site-header">
    <div class="container header-inner">
      <div class="brand">
        <h1>TuMarca</h1>
        <p class="tag">Ropa con actitud — desde casa</p>
      </div>
      <nav class="nav">
        <button id="cart-toggle" aria-label="Abrir carrito">Carrito (<span id="cart-count">0</span>)</button>
      </nav>
    </div>
  </header>

  <main class="container">
    <section class="hero">
      <div class="hero-text">
        <h2>Diseños únicos. Producción bajo demanda.</h2>
        <p>Sin inventario — imprimimos y enviamos cuando alguien compra.</p>
        <a class="cta" href="#catalog">Ver catálogo</a>
      </div>
      <div class="hero-image">
        <img src="https://images.unsplash.com/photo-1520975924434-6d2f7a449a07?auto=format&fit=crop&w=1000&q=60" alt="Moderno" />
      </div>
    </section>

    <section id="catalog" class="catalog">
      <h3>Catálogo</h3>
      <div id="products" class="products-grid">
        <!-- Productos se renderizan desde script.js -->
      </div>
    </section>

    <section class="about">
      <h3>Sobre TuMarca</h3>
      <p>Marca enfocada en estilos callejeros y sostenibilidad. Empezamos desde casa — cada prenda se imprime cuando la compras.</p>
    </section>
  </main>

  <!-- Carrito modal -->
  <aside id="cart" class="cart hidden" aria-hidden="true">
    <div class="cart-inner">
      <button id="close-cart" class="close">✕</button>
      <h4>Tu carrito</h4>
      <div id="cart-items" class="cart-items">
        <!-- items -->
      </div>

      <div class="cart-footer">
        <div class="totals">
          <span>Total:</span>
          <strong id="cart-total">0 €</strong>
        </div>

        <div class="cart-actions">
          <button id="clear-cart" class="btn outline">Vaciar</button>
          <button id="checkout" class="btn primary">Finalizar compra</button>
        </div>
        <p class="small">Checkout abre un correo con tu pedido. Reemplaza por tu integración de pago cuando quieras.</p>
      </div>
    </div>
  </aside>

  <footer class="site-footer">
    <div class="container">
      <p>© <span id="year"></span> TuMarca • Síguenos en <a href="#" target="_blank">Instagram</a> / <a href="#" target="_blank">TikTok</a></p>
    </div>
  </footer>

  <script src="script.js"></script>
</body>
</html>
:root{
  --bg: #ffffff;
  --text: #111827;
  --muted: #6b7280;
  --accent: #111827;
  --accent-2: #ef4444;
  --container: 1100px;
  --radius: 12px;
  --shadow: 0 6px 18px rgba(17,24,39,0.08);
  font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
}

*{box-sizing:border-box}
html,body{height:100%}
body{
  margin:0;
  background:var(--bg);
  color:var(--text);
  -webkit-font-smoothing:antialiased;
  -moz-osx-font-smoothing:grayscale;
}

.container{
  max-width:var(--container);
  margin:0 auto;
  padding:20px;
}

/* Header */
.site-header{
  border-bottom:1px solid #eee;
  background:#fff;
  position:sticky;
  top:0;
  z-index:40;
}
.header-inner{
  display:flex;
  justify-content:space-between;
  align-items:center;
  gap:16px;
}
.brand h1{margin:0;font-size:20px;letter-spacing:1px}
.brand .tag{margin:0;color:var(--muted);font-size:13px}

/* Hero */
.hero{
  display:grid;
  grid-template-columns:1fr 420px;
  gap:24px;
  align-items:center;
  margin:28px 0;
}
.hero-text h2{margin:0 0 10px;font-size:28px}
.hero-text p{margin:0 0 14px;color:var(--muted)}
.cta{
  display:inline-block;padding:10px 16px;border-radius:10px;background:var(--accent);color:#fff;text-decoration:none;
}
.hero-image img{
  width:100%;height:100%;max-height:320px;object-fit:cover;border-radius:12px;box-shadow:var(--shadow);
}

/* Products */
.catalog h3{margin:6px 0 18px}
.products-grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
  gap:18px;
}
.card{
  border-radius:12px;
  overflow:hidden;
  box-shadow:var(--shadow);
  background:#fff;
  display:flex;
  flex-direction:column;
}
.card img{width:100%;height:260px;object-fit:cover}
.card-body{padding:12px;display:flex;flex-direction:column;gap:8px}
.card-title{margin:0;font-weight:600}
.card-desc{margin:0;color:var(--muted);font-size:14px}
.card-foot{display:flex;justify-content:space-between;align-items:center;margin-top:auto;padding-top:6px}
.btn{
  border:0;padding:8px 12px;border-radius:10px;cursor:pointer;font-weight:600;
}
.btn.primary{background:var(--accent);color:#fff}
.btn.outline{background:transparent;border:1px solid #e6e6e6;color:var(--text)}

/* Cart */
.cart{
  position:fixed;right:18px;top:80px;width:360px;background:#fff;border-radius:12px;box-shadow:0 30px 60px rgba(2,6,23,0.2);z-index:50;
  overflow:hidden;
}
.cart.hidden{display:none}
.cart-inner{padding:16px}
.close{background:transparent;border:0;position:absolute;right:10px;top:8px;font-size:18px;cursor:pointer}
.cart-items{max-height:320px;overflow:auto;margin:8px 0 14px}
.cart-item{display:flex;gap:10px;align-items:center;padding:8px;border-bottom:1px solid #f1f1f1}
.cart-item img{width:60px;height:60px;object-fit:cover;border-radius:8px}
.item-info{flex:1}
.item-title{margin:0;font-size:14px}
.item-meta{color:var(--muted);font-size:13px}
.qty-controls{display:flex;gap:6px;align-items:center}
.totals{display:flex;justify-content:space-between;align-items:center;padding:8px 0}
.cart-footer .small{color:var(--muted);font-size:12px;margin-top:8px}

/* Footer */
.site-footer{border-top:1px solid #eee;padding:18px 0;margin-top:30px;text-align:center;color:var(--muted)}

@media (max-width:880px){
  .hero{grid-template-columns:1fr;grid-auto-rows:auto}
  .hero-image img{max-height:220px}
  .cart{left:12px;right:12px;width:auto}
}
// Tienda mínima: productos, carrito, renderizado y checkout via mailto
const PRODUCTS = [
  {
    id: "shirt-001",
    title: "Camiseta 'Street Vibes'",
    price: 19.99,
    img: "https://images.unsplash.com/photo-1520975924434-6d2f7a449a07?auto=format&fit=crop&w=800&q=60",
    desc: "Corte relajado, estampado exclusivo."
  },
  {
    id: "hoodie-001",
    title: "Sudadera 'Night Runner'",
    price: 34.50,
    img: "https://images.unsplash.com/photo-1520975924434-6d2f7a449a07?auto=format&fit=crop&w=1200&q=60",
    desc: "Tejido premium, tacto suave."
  },
  {
    id: "cap-001",
    title: "Gorra 'Logo'",
    price: 12.00,
    img: "https://images.unsplash.com/photo-1503342452485-86f7c9d1a8f4?auto=format&fit=crop&w=800&q=60",
    desc: "Ajustable, bordado minimal."
  }
];

// --- Helpers para DOM
const $ = sel => document.querySelector(sel);
const $all = sel => document.querySelectorAll(sel);

// --- Inicialización
document.addEventListener("DOMContentLoaded", () => {
  renderProducts();
  setupCartUI();
  document.getElementById("year").textContent = new Date().getFullYear();
});

// --- Renderizar productos
function renderProducts(){
  const container = document.getElementById("products");
  container.innerHTML = "";
  PRODUCTS.forEach(p=>{
    const card = document.createElement("article");
    card.className = "card";
    card.innerHTML = `
      <img src="${p.img}" alt="${p.title}">
      <div class="card-body">
        <h4 class="card-title">${p.title}</h4>
        <p class="card-desc">${p.desc}</p>
        <div class="card-foot">
          <strong>${p.price.toFixed(2)} €</strong>
          <button class="btn primary add-to-cart" data-id="${p.id}">Comprar</button>
        </div>
      </div>
    `;
    container.appendChild(card);
  });

  $all(".add-to-cart").forEach(btn=>{
    btn.addEventListener("click", e=>{
      addToCart(e.target.dataset.id, 1);
    });
  });
}

// --- Carrito (localStorage)
const CART_KEY = "tu_marca_cart_v1";
function getCart(){
  try {
    return JSON.parse(localStorage.getItem(CART_KEY)) || {};
  } catch(e){
    return {};
  }
}
function saveCart(cart){
  localStorage.setItem(CART_KEY, JSON.stringify(cart));
  updateCartCount();
}
function addToCart(id, qty=1){
  const cart = getCart();
  if(!cart[id]) cart[id] = 0;
  cart[id] += qty;
  saveCart(cart);
  showCart();
}
function setQty(id, qty){
  const cart = getCart();
  if(qty <= 0) { delete cart[id]; }
  else cart[id] = qty;
  saveCart(cart);
  renderCartItems();
}
function clearCart(){
  localStorage.removeItem(CART_KEY);
  updateCartCount();
  renderCartItems();
}

// --- UI del carrito
function setupCartUI(){
  $("#cart-toggle").addEventListener("click", showCart);
  $("#close-cart").addEventListener("click", hideCart);
  $("#clear-cart").addEventListener("click", ()=>{
    if(confirm("Vaciar carrito?")) clearCart();
  });
  $("#checkout").addEventListener("click", checkoutViaMail);
  renderCartItems();
  updateCartCount();
}
function showCart(){
  $("#cart").classList.remove("hidden");
  $("#cart").setAttribute("aria-hidden", "false");
  renderCartItems();
}
function hideCart(){
  $("#cart").classList.add("hidden");
  $("#cart").setAttribute("aria-hidden", "true");
}
function updateCartCount(){
  const cart = getCart();
  const count = Object.values(cart).reduce((s,n)=>s+n,0);
  $("#cart-count").textContent = count;
}

// --- Render items en carrito
function renderCartItems(){
  const container = document.getElementById("cart-items");
  const cart = getCart();
  container.innerHTML = "";
  let total = 0;
  if(Object.keys(cart).length === 0){
    container.innerHTML = "<p class='small'>El carrito está vacío.</p>";
  } else {
    for(const id of Object.keys(cart)){
      const product = PRODUCTS.find(p=>p.id===id);
      const qty = cart[id];
      const subtotal = product.price * qty;
      total += subtotal;

      const item = document.createElement("div");
      item.className = "cart-item";
      item.innerHTML = `
        <img src="${product.img}" alt="${product.title}">
        <div class="item-info">
          <p class="item-title">${product.title}</p>
          <p class="item-meta">${product.price.toFixed(2)} € x ${qty} = ${subtotal.toFixed(2)} €</p>
          <div class="qty-controls">
            <button class="btn outline change-qty" data-id="${id}" data-delta="-1">−</button>
            <button class="btn outline change-qty" data-id="${id}" data-delta="1">+</button>
            <button class="btn outline remove-item" data-id="${id}">Eliminar</button>
          </div>
        </div>
      `;
      container.appendChild(item);
    }

    // listeners
    $all(".change-qty").forEach(btn=>{
      btn.addEventListener("click", e=>{
        const id = e.target.dataset.id;
        const delta = Number(e.target.dataset.delta);
        const cart = getCart();
        const newQty = (cart[id] || 0) + delta;
        setQty(id, newQty);
      });
    });
    $all(".remove-item").forEach(btn=>{
      btn.addEventListener("click", e=>{
        const id = e.target.dataset.id;
        setQty(id, 0);
      });
    });
  }
  $("#cart-total").textContent = total.toFixed(2) + " €";
  updateCartCount();
}

// --- Checkout simple via mailto
function checkoutViaMail(){
  const cart = getCart();
  if(Object.keys(cart).length === 0){
    alert("Tu carrito está vacío.");
    return;
  }
  const lines = [];
  let total = 0;
  for(const id of Object.keys(cart)){
    const p = PRODUCTS.find(x=>x.id===id);
    const q = cart[id];
    const sub = p.price * q;
    total += sub;
    lines.push(`${p.title} — ${q} × ${p.price.toFixed(2)} € = ${sub.toFixed(2)} €`);
  }
  const body = encodeURIComponent(
    `Hola,\n\nQuiero realizar el siguiente pedido:\n\n${lines.join("\n")}\n\nTotal: ${total.toFixed(2)} €\n\nNombre:\nDirección de envío:\nTeléfono:\n\nGracias.`
  );

  // Cambia el email destino por el tuyo:
  const mail = "ventas@tumarca.com";
  // Abre el cliente de correo con resumen del pedido
  window.location.href = `mailto:${mail}?subject=${encodeURIComponent("Pedido - TuMarca")}&body=${body}`;
}
<!doctype html>
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>TuMarca — Tienda Online</title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <header class="site-header">
    <div class="container header-inner">
      <div class="brand">
        <h1>TuMarca</h1>
        <p class="tag">Ropa con estilo, directo a tu casa</p>
      </div>
      <nav>
        <button id="cart-toggle">🛒 Carrito (<span id="cart-count">0</span>)</button>
      </nav>
    </div>
  </header>

  <main class="container">
    <section class="hero">
      <div class="hero-text">
        <h2>Moda digital y accesible</h2>
        <p>Colecciones únicas impresas bajo demanda.</p>
        <a class="cta" href="#catalog">Explorar catálogo</a>
      </div>
      <div class="hero-image">
        <img src="https://images.unsplash.com/photo-1520975924434-6d2f7a449a07?auto=format&fit=crop&w=1000&q=60" alt="Moda urbana" />
      </div>
    </section>

    <section id="catalog" class="catalog">
      <h3>Catálogo</h3>
      <div id="products" class="products-grid"></div>
    </section>
  </main>

  <!-- Carrito -->
  <aside id="cart" class="cart hidden">
    <div class="cart-inner">
      <button id="close-cart" class="close">✕</button>
      <h4>Tu carrito</h4>
      <div id="cart-items" class="cart-items"></div>
      <div class="cart-footer">
        <div class="totals">
          <span>Total:</span>
          <strong id="cart-total">0 €</strong>
        </div>
        <div id="paypal-button-container"></div>
      </div>
    </div>
  </aside>

  <footer class="site-footer">
    <p>© <span id="year"></span> TuMarca — Hecho con ❤️ desde casa</p>
  </footer>

  <!-- PayPal SDK -->
  <script src="https://www.paypal.com/sdk/js?client-id=sb&currency=EUR"></script>
  <script src="script.js"></script>
</body>
</html>
// Productos
const PRODUCTS = [
  {
    id: "shirt-001",
    title: "Camiseta 'Street Vibes'",
    price: 19.99,
    img: "https://images.unsplash.com/photo-1520975924434-6d2f7a449a07?auto=format&fit=crop&w=800&q=60",
    desc: "Corte relajado, estampado exclusivo."
  },
  {
    id: "hoodie-001",
    title: "Sudadera 'Night Runner'",
    price: 34.50,
    img: "https://images.unsplash.com/photo-1520975924434-6d2f7a449a07?auto=format&fit=crop&w=1200&q=60",
    desc: "Tejido premium, tacto suave."
  },
  {
    id: "cap-001",
    title: "Gorra 'Logo'",
    price: 12.00,
    img: "https://images.unsplash.com/photo-1503342452485-86f7c9d1a8f4?auto=format&fit=crop&w=800&q=60",
    desc: "Ajustable, bordado minimal."
  }
];

// Helpers
const $ = sel => document.querySelector(sel);
const $all = sel => document.querySelectorAll(sel);

// Inicialización
document.addEventListener("DOMContentLoaded", () => {
  renderProducts();
  setupCartUI();
  $("#year").textContent = new Date().getFullYear();
});

// Render productos
function renderProducts(){
  const container = $("#products");
  container.innerHTML = "";
  PRODUCTS.forEach(p=>{
    const card = document.createElement("article");
    card.className = "card";
    card.innerHTML = `
      <img src="${p.img}" alt="${p.title}">
      <div class="card-body">
        <h4 class="card-title">${p.title}</h4>
        <p class="card-desc">${p.desc}</p>
        <div class="card-foot">
          <strong>${p.price.toFixed(2)} €</strong>
          <button class="btn primary add-to-cart" data-id="${p.id}">Añadir</button>
        </div>
      </div>
    `;
    container.appendChild(card);
  });

  $all(".add-to-cart").forEach(btn=>{
    btn.addEventListener("click", e=>{
      addToCart(e.target.dataset.id, 1);
    });
  });
}

// Carrito
const CART_KEY = "tu_marca_cart_v2";
function getCart(){ return JSON.parse(localStorage.getItem(CART_KEY)) || {}; }
function saveCart(c){ localStorage.setItem(CART_KEY, JSON.stringify(c)); updateCartCount(); }
function addToCart(id, qty=1){
  const cart = getCart();
  if(!cart[id]) cart[id]=0;
  cart[id]+=qty;
  saveCart(cart); showCart();
}
function setQty(id, qty){
  const cart = getCart();
  if(qty<=0) delete cart[id]; else cart[id]=qty;
  saveCart(cart); renderCartItems();
}
function clearCart(){ localStorage.removeItem(CART_KEY); updateCartCount(); renderCartItems(); }

// UI carrito
function setupCartUI(){
  $("#cart-toggle").addEventListener("click", showCart);
  $("#close-cart").addEventListener("click", hideCart);
  renderCartItems(); updateCartCount();
}
function showCart(){ $("#cart").classList.remove("hidden"); renderCartItems(); }
function hideCart(){ $("#cart").classList.add("hidden"); }
function updateCartCount(){
  const c=getCart(); $("#cart-count").textContent=Object.values(c).reduce((s,n)=>s+n,0);
}
function renderCartItems(){
  const c=getCart(), cont=$("#cart-items"); cont.innerHTML=""; let total=0;
  if(Object.keys(c).length===0){ cont.innerHTML="<p>Carrito vacío.</p>"; }
  else{
    for(const id of Object.keys(c)){
      const p=PRODUCTS.find(x=>x.id===id), q=c[id], sub=p.price*q; total+=sub;
      const item=document.createElement("div");
      item.className="cart-item";
      item.innerHTML=`
        <img src="${p.img}" alt="${p.title}">
        <div class="item-info">
          <p>${p.title}</p>
          <p>${p.price.toFixed(2)} € × ${q} = ${sub.toFixed(2)} €</p>
          <div class="qty-controls">
            <button class="btn outline" onclick="setQty('${id}',${q-1})">−</button>
            <button class="btn outline" onclick="setQty('${id}',${q+1})">+</button>
            <button class="btn outline" onclick="setQty('${id}',0)">Eliminar</button>
          </div>
        </div>
      `;
      cont.appendChild(item);
    }
  }
  $("#cart-total").textContent=total.toFixed(2)+" €";

  // Render PayPal
  renderPayPal(total);
}

// PayPal integrado
function renderPayPal(total){
  $("#paypal-button-container").innerHTML="";
  if(total<=0) return;
  paypal.Buttons({
    createOrder: function(data, actions){
      return actions.order.create({ purchase_units:[{ amount:{ value: total.toFixed(2) } }] });
    },
    onApprove: function(data, actions){
      return actions.order.capture().then(function(details){
        alert("¡Gracias por tu compra, " + details.payer.name.given_name + "!");
        clearCart(); hideCart();
      });
    }
  }).render("#paypal-button-container");
}
