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