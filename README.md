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