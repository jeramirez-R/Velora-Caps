
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Velora Caps</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@500;700;800&family=Montserrat:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg-light: #f8fafc;
      --bg-surface: #ffffff;
      --bg-card: #0f0b14;
      
      --purple-accent: #6d28d9;
      --purple-glow: rgba(109, 40, 217, 0.15);
      --purple-light: #8b5cf6;
      
      --silver-bright: #ffffff;
      --silver-mid: #cbd5e1;
      --text-main: #0f172a;
      --text-muted: #64748b;
      
      --border-light: rgba(203, 213, 225, 0.6);
      
      --font-title: 'Cinzel', serif;
      --font-body: 'Montserrat', sans-serif;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: var(--font-body);
      background-color: var(--bg-light);
      color: var(--text-main);
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      overflow-x: hidden;
    }

    /* ENCABEZADO */
    .header-luxury {
      background-color: rgba(255, 255, 255, 0.95);
      border-bottom: 1px solid var(--border-light);
      backdrop-filter: blur(10px);
      position: sticky;
      top: 0;
      z-index: 100;
      padding: 22px 20px;
      display: flex;
      justify-content: center;
      align-items: center;
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.03);
    }

    .brand-hero {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
      cursor: default;
      user-select: none;
      position: relative;
    }

    .brand-logo-badge {
      width: 45px;
      height: 45px;
      border-radius: 50%;
      background: radial-gradient(circle, #4c1d95 0%, #0f0b14 100%);
      border: 1px solid var(--purple-light);
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: var(--font-title);
      font-weight: 700;
      font-size: 18px;
      color: #ffffff;
      margin-bottom: 6px;
    }

    .brand-title {
      font-family: var(--font-title);
      font-size: 34px;
      font-weight: 800;
      letter-spacing: 6px;
      color: var(--text-main);
      text-transform: uppercase;
    }

    .click-counter-badge {
      position: absolute;
      bottom: -18px;
      font-size: 9px;
      font-weight: 600;
      color: var(--purple-accent);
      background: rgba(109, 40, 217, 0.08);
      padding: 2px 8px;
      border-radius: 10px;
      border: 1px dashed var(--purple-light);
      opacity: 0;
      transition: opacity 0.2s ease;
      pointer-events: none;
    }

    .click-counter-badge.visible {
      opacity: 1;
    }

    .main-container {
      max-width: 1300px;
      margin: 0 auto;
      padding: 35px 20px;
      width: 100%;
      flex: 1;
    }

    /* CARRUSEL */
    .carousel-section {
      margin-bottom: 45px;
    }

    .carousel-header-wrapper {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 15px;
      margin-bottom: 18px;
      position: relative;
    }

    .section-label {
      font-family: var(--font-title);
      font-size: 11px;
      letter-spacing: 3px;
      color: var(--text-muted);
      text-transform: uppercase;
    }

    .carousel-admin-controls {
      display: none;
    }

    .is-admin-active .carousel-admin-controls {
      display: inline-flex;
    }

    .carousel-container {
      width: 100%;
      overflow: hidden;
      border-top: 1px solid var(--border-light);
      border-bottom: 1px solid var(--border-light);
      background: var(--bg-surface);
      padding: 16px 0;
      position: relative;
    }

    .carousel-track {
      display: flex;
      gap: 20px;
      width: max-content;
      animation: infiniteScroll 25s linear infinite;
    }

    .carousel-container:hover .carousel-track {
      animation-play-state: paused;
    }

    .carousel-item {
      width: 160px;
      height: 110px;
      flex-shrink: 0;
      background: #f1f5f9;
      border: 1px solid var(--border-light);
      border-radius: 8px;
      overflow: hidden;
      position: relative;
    }

    .carousel-item img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      display: block;
    }

    /* CORRECCIÓN APLICADA AQUÍ */
    .carousel-item-title {
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      background: rgba(15, 11, 20, 0.85);
      color: #fff;
      font-size: 8px;
      font-weight: 600;
      padding: 4px 4px;
      white-space: nowrap;
      overflow: hidden;
      text-overflow: ellipsis;
      text-align: center;
      box-sizing: border-box;
      width: 100%;
    }

    @keyframes infiniteScroll {
      0% { transform: translateX(0); }
      100% { transform: translateX(-50%); }
    }

    /* CATÁLOGO */
    .catalog-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 30px;
      padding-bottom: 12px;
      border-bottom: 1px solid var(--border-light);
      flex-wrap: wrap;
      gap: 15px;
    }

    .catalog-title {
      font-family: var(--font-title);
      font-size: 22px;
      font-weight: 700;
      letter-spacing: 1px;
      color: var(--text-main);
    }

    .secondary-actions {
      display: none;
      align-items: center;
      gap: 10px;
    }

    .is-admin-active .secondary-actions {
      display: flex;
    }

    .btn {
      padding: 8px 16px;
      border-radius: 6px;
      font-size: 11px;
      font-weight: 600;
      letter-spacing: 1px;
      cursor: pointer;
      transition: all 0.3s ease;
      text-decoration: none;
      display: inline-flex;
      align-items: center;
      gap: 6px;
      text-transform: uppercase;
    }

    .btn-primary {
      background: var(--purple-accent);
      border: 1px solid var(--purple-accent);
      color: #ffffff;
    }

    .btn-primary:hover {
      background: #5b21b6;
      box-shadow: 0 4px 12px var(--purple-glow);
    }

    .btn-outline {
      background: var(--bg-surface);
      border: 1px solid var(--border-light);
      color: var(--text-main);
    }

    .btn-outline:hover {
      border-color: var(--text-main);
    }

    input[type="file"] {
      display: none;
    }

    /* GRID Y TARJETAS */
    .catalog-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
      gap: 25px;
    }

    .card {
      background: var(--bg-card);
      border: 1px solid rgba(255, 255, 255, 0.1);
      border-radius: 12px;
      overflow: hidden;
      transition: all 0.3s ease;
      display: flex;
      flex-direction: column;
      position: relative;
      box-shadow: 0 10px 25px rgba(0, 0, 0, 0.08);
      cursor: pointer;
    }

    .card:hover {
      border-color: var(--purple-light);
      box-shadow: 0 15px 35px rgba(109, 40, 217, 0.25);
      transform: translateY(-4px);
    }

    .card-img-wrapper {
      width: 100%;
      height: 220px;
      position: relative;
      overflow: hidden;
    }

    .card-img-wrapper img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      display: block;
    }

    .card-tag {
      position: absolute;
      top: 12px;
      left: 12px;
      background: rgba(15, 11, 20, 0.85);
      border: 1px solid var(--purple-accent);
      color: var(--purple-light);
      font-size: 8px;
      text-transform: uppercase;
      letter-spacing: 1.5px;
      padding: 3px 8px;
      border-radius: 4px;
      z-index: 2;
      outline: none;
    }

    .card-body {
      padding: 20px;
      display: flex;
      flex-direction: column;
      flex-grow: 1;
    }

    .card-title {
      font-size: 14px;
      font-weight: 600;
      color: var(--silver-bright);
      margin-bottom: 6px;
      outline: none;
    }

    .card-desc {
      font-size: 11px;
      color: var(--silver-mid);
      margin-bottom: 12px;
      line-height: 1.4;
      outline: none;
      display: -webkit-box;
      -webkit-line-clamp: 2;
      -webkit-box-orient: vertical;
      overflow: hidden;
    }

    .card-stock {
      font-size: 10px;
      font-weight: 600;
      color: var(--purple-light);
      margin-bottom: 12px;
      display: flex;
      align-items: center;
      gap: 4px;
    }

    .card-footer {
      margin-top: auto;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding-top: 12px;
      border-top: 1px solid rgba(255,255,255,0.08);
    }

    .card-price {
      font-family: var(--font-title);
      font-size: 15px;
      font-weight: 700;
      color: var(--silver-bright);
      outline: none;
    }

    .buy-btn {
      background: transparent;
      border: 1px solid var(--purple-light);
      color: var(--silver-bright);
      padding: 6px 14px;
      border-radius: 4px;
      font-size: 10px;
      letter-spacing: 1px;
      text-transform: uppercase;
      cursor: pointer;
      transition: all 0.3s ease;
      text-decoration: none;
    }

    .buy-btn:hover {
      background: var(--purple-accent);
      color: #ffffff;
      border-color: var(--purple-accent);
    }

    .empty-state {
      grid-column: 1 / -1;
      text-align: center;
      padding: 60px 20px;
      background: var(--bg-surface);
      border: 1px solid var(--border-light);
      border-radius: 8px;
    }

    /* FOOTER */
    footer {
      background-color: var(--bg-surface);
      border-top: 1px solid var(--border-light);
      padding: 25px 5%;
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 15px;
      font-size: 11px;
      color: var(--text-muted);
    }

    .footer-contact-link {
      color: var(--purple-accent);
      text-decoration: none;
      font-weight: 600;
    }

    /* MODALES */
    .modal-overlay {
      display: none;
      position: fixed;
      top: 0; left: 0; width: 100%; height: 100%;
      background: rgba(15, 23, 42, 0.75);
      backdrop-filter: blur(8px);
      z-index: 1000;
      align-items: center;
      justify-content: center;
      padding: 20px;
    }

    .admin-modal-content {
      background: var(--bg-surface);
      border: 1px solid var(--border-light);
      padding: 30px;
      border-radius: 12px;
      width: 100%;
      max-width: 320px;
      box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1);
      text-align: center;
    }

    .admin-modal-content h3 {
      font-family: var(--font-title);
      font-size: 16px;
      margin-bottom: 15px;
      color: var(--text-main);
    }

    .admin-input {
      width: 100%;
      padding: 10px;
      margin-bottom: 10px;
      border-radius: 6px;
      background: var(--bg-light);
      border: 1px solid var(--border-light);
      color: var(--text-main);
      outline: none;
      font-size: 12px;
    }

    /* MODAL DE DETALLE DE PRODUCTO */
    .product-modal-content {
      background: var(--bg-card);
      border: 1px solid rgba(255,255,255,0.15);
      border-radius: 16px;
      width: 100%;
      max-width: 650px;
      overflow: hidden;
      display: flex;
      flex-direction: row;
      position: relative;
      box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5);
    }

    .product-modal-img {
      width: 50%;
      max-height: 380px;
      background: #000;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .product-modal-img img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .product-modal-info {
      width: 50%;
      padding: 30px;
      display: flex;
      flex-direction: column;
      color: var(--silver-bright);
    }

    .product-modal-info h2 {
      font-family: var(--font-title);
      font-size: 20px;
      margin-top: 8px;
      margin-bottom: 10px;
      outline: none;
    }

    .product-modal-desc {
      font-size: 12px;
      color: var(--silver-mid);
      line-height: 1.6;
      margin-bottom: 15px;
      outline: none;
    }

    .product-modal-stock {
      font-size: 12px;
      font-weight: 700;
      color: var(--purple-light);
      background: rgba(109, 40, 217, 0.2);
      padding: 6px 12px;
      border-radius: 6px;
      align-self: flex-start;
      margin-bottom: 20px;
      border: 1px solid rgba(139, 92, 246, 0.3);
      outline: none;
    }

    .modal-close-btn {
      position: absolute;
      top: 15px;
      right: 15px;
      background: rgba(255, 255, 255, 0.2);
      color: #fff;
      border: none;
      width: 30px;
      height: 30px;
      border-radius: 50%;
      cursor: pointer;
      font-size: 14px;
      z-index: 10;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .modal-close-btn:hover {
      background: rgba(255, 255, 255, 0.4);
    }

    .editable-input {
      background: rgba(109, 40, 217, 0.25) !important;
      border: 1px dashed var(--purple-light) !important;
      border-radius: 4px !important;
      padding: 2px 6px !important;
    }

    .delete-card-btn {
      position: absolute;
      top: 10px;
      right: 10px;
      background: rgba(220, 38, 38, 0.9);
      color: white;
      border: none;
      border-radius: 4px;
      width: 24px;
      height: 24px;
      cursor: pointer;
      display: none;
      align-items: center;
      justify-content: center;
      font-size: 12px;
      z-index: 10;
    }

    .is-admin-active .delete-card-btn {
      display: flex;
    }

    .admin-indicator {
      display: none;
      position: fixed;
      bottom: 20px;
      left: 20px;
      background: var(--bg-surface);
      border: 1px solid var(--purple-accent);
      padding: 8px 15px;
      border-radius: 6px;
      font-size: 11px;
      color: var(--text-main);
      box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
      z-index: 500;
    }

    /* ALERTA VISUAL GUARDADO AUTOMÁTICO */
    .save-toast {
      position: fixed;
      bottom: 20px;
      right: 20px;
      background: var(--purple-accent);
      color: white;
      font-size: 11px;
      padding: 8px 16px;
      border-radius: 20px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.15);
      opacity: 0;
      transform: translateY(10px);
      transition: all 0.3s ease;
      z-index: 1000;
      pointer-events: none;
    }

    .save-toast.visible {
      opacity: 1;
      transform: translateY(0);
    }

    @media (max-width: 768px) {
      .brand-title {
        font-size: 26px;
        letter-spacing: 4px;
      }

      .catalog-header {
        flex-direction: column;
        align-items: flex-start;
      }

      .catalog-grid {
        grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
        gap: 15px;
      }

      .product-modal-content {
        flex-direction: column;
      }

      .product-modal-img, .product-modal-info {
        width: 100%;
      }

      .product-modal-img {
        height: 220px;
      }
    }
  </style>
</head>
<body>

  <!-- ENCABEZADO -->
  <header class="header-luxury">
    <div class="brand-hero" id="brandLogoBtn">
      <div class="brand-logo-badge">VC</div>
      <h1 class="brand-title">Velora Caps</h1>
      <div class="click-counter-badge" id="clickBadge"></div>
    </div>
  </header>

  <!-- CONTENIDO PRINCIPAL -->
  <div class="main-container">
    
    <!-- CARRUSEL -->
    <section class="carousel-section">
      <div class="carousel-header-wrapper">
        <div class="section-label">— Colección Destacada —</div>
        <div class="carousel-admin-controls">
          <label for="carousel-file-input" class="btn btn-primary" style="font-size: 9px; padding: 4px 8px;">
            + Fotos Carrusel
          </label>
          <input type="file" id="carousel-file-input" multiple accept="image/*" onchange="handleCarouselUpload(event)">
        </div>
      </div>

      <div class="carousel-container">
        <div class="carousel-track" id="carousel-track">
          <!-- Generado dinámicamente -->
        </div>
      </div>
    </section>

    <!-- CATÁLOGO -->
    <section>
      <div class="catalog-header">
        <div>
          <h2 class="catalog-title">Catálogo Oficial</h2>
          <span style="font-size: 11px; color: var(--text-muted);" id="item-count">0 Productos</span>
        </div>

        <div class="secondary-actions">
          <label for="file-input" class="btn btn-outline">
            + Fotos Catálogo
          </label>
          <input type="file" id="file-input" multiple accept="image/*" onchange="handleFileUpload(event)">
        </div>
      </div>

      <div class="catalog-grid" id="catalog-grid">
        <div class="empty-state" id="empty-state">
          <p style="color: var(--text-muted); font-size: 13px; margin-bottom: 15px;">No hay modelos desplegados actualmente.</p>
        </div>
      </div>
    </section>

  </div>

  <!-- FOOTER -->
  <footer>
    <div>© 2026 VELORA CAPS • Todos los derechos reservados</div>
    <div>Ventas & Atención Directa: <a href="https://wa.me/573046753279" target="_blank" class="footer-contact-link">+57 304 6753279</a></div>
  </footer>

  <!-- MODAL ADMIN -->
  <div class="modal-overlay" id="adminModal">
    <div class="admin-modal-content">
      <h3>Modo Edición</h3>
      <input type="text" id="adminUser" placeholder="Usuario" class="admin-input">
      <input type="password" id="adminPass" placeholder="Contraseña" class="admin-input">
      <button class="btn btn-primary" style="width: 100%; margin-top: 5px; justify-content: center;" onclick="loginAdmin()">Ingresar</button>
      <button class="btn btn-outline" style="width: 100%; margin-top: 5px; border:none; justify-content: center;" onclick="toggleAdminModal()">Cancelar</button>
    </div>
  </div>

  <!-- MODAL DETALLE DE PRODUCTO -->
  <div class="modal-overlay" id="productModal">
    <div class="product-modal-content">
      <button class="modal-close-btn" onclick="closeProductModal()">✕</button>
      <div class="product-modal-img">
        <img id="modalImg" src="" alt="">
      </div>
      <div class="product-modal-info">
        <span class="card-tag" id="modalTag" style="position: static; display: inline-block; margin-bottom: 10px;">Exclusivo</span>
        <h2 id="modalTitle">Nombre del Producto</h2>
        <p class="product-modal-desc" id="modalDesc">Descripción completa detallada del producto.</p>
        <div class="product-modal-stock" id="modalStock">Disponibles: <span id="modalStockNum">10</span> unidades</div>
        
        <div class="card-footer" style="margin-top: auto;">
          <div class="card-price" id="modalPrice">$0.00 USD</div>
          <a id="modalBuyBtn" href="#" target="_blank" class="buy-btn">Adquirir por WhatsApp</a>
        </div>
      </div>
    </div>
  </div>

  <!-- INDICADOR MODO EDICIÓN -->
  <div class="admin-indicator" id="adminIndicator">
    <span>Modo Edición Activo</span>
    <button onclick="resetDataToDefault()" style="margin-left: 10px; background: transparent; border: none; color: #ef4444; cursor: pointer; text-decoration: underline; font-size: 10px;">Restablecer</button>
    <button onclick="logoutAdmin()" style="margin-left: 8px; background: transparent; border: none; color: var(--purple-accent); cursor: pointer; text-decoration: underline;">Salir</button>
  </div>

  <!-- TOAST DE ALERTA DE GUARDADO -->
  <div class="save-toast" id="saveToast">✓ Guardado Automático</div>

  <script>
    const catalogGrid = document.getElementById('catalog-grid');
    const emptyState = document.getElementById('empty-state');
    const itemCount = document.getElementById('item-count');
    const carouselTrack = document.getElementById('carousel-track');
    const clickBadge = document.getElementById('clickBadge');
    const saveToast = document.getElementById('saveToast');
    
    let isAdmin = false;
    let logoClicks = 0;
    let clickTimer = null;
    let activeCardRef = null;

    // DATOS DE MUESTRA POR DEFECTO
    const defaultCaps = [
      {
        id: "cap-1",
        name: "Velvet Crown Purple",
        desc: "Edición Velvet con finos bordados en hilo de plata y estructura reforzada de altísima calidad.",
        price: "$65.00 USD",
        badge: "Exclusivo",
        stock: 8,
        image: "data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 300 300'><rect width='100%' height='100%' fill='%230f0b14'/><path d='M60 180 Q150 90 240 180 Z' fill='%236d28d9'/><path d='M50 180 Q150 120 250 180 L230 200 L70 200 Z' fill='%233b0764'/><text x='150' y='165' font-family='Cinzel' font-size='26' fill='%23ffffff' text-anchor='middle'>VC</text></svg>"
      },
      {
        id: "cap-2",
        name: "Royal Diamond Snapback",
        desc: "Satinado negro profundo con logo VC estilo platino brillante e interiores de algodón suave.",
        price: "$75.00 USD",
        badge: "Edición Especial",
        stock: 5,
        image: "data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 300 300'><rect width='100%' height='100%' fill='%230f0b14'/><path d='M60 180 Q150 90 240 180 Z' fill='%231e1b4b'/><path d='M40 180 Q150 130 260 180 L230 205 L70 205 Z' fill='%23020617'/><text x='150' y='165' font-family='Cinzel' font-size='26' fill='%238b5cf6' text-anchor='middle'>VC</text></svg>"
      },
      {
        id: "cap-3",
        name: "Silver Mesh Performance",
        desc: "Estructura ultraligera respirable con matices plateados, ideal para un estilo urbano fresco.",
        price: "$50.00 USD",
        badge: "Nuevo",
        stock: 12,
        image: "data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 300 300'><rect width='100%' height='100%' fill='%230f0b14'/><path d='M60 180 Q150 90 240 180 Z' fill='%23334155'/><path d='M50 180 Q150 120 250 180 L230 200 L70 200 Z' fill='%230f172a'/><text x='150' y='160' font-family='Cinzel' font-size='26' fill='%23ffffff' text-anchor='middle'>VC</text></svg>"
      },
      {
        id: "cap-4",
        name: "Dark Orchid Edition",
        desc: "Diseño minimalista en tonalidades morado oscuro con broche de ajuste metálico personalizado.",
        price: "$58.00 USD",
        badge: "Limitado",
        stock: 3,
        image: "data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 300 300'><rect width='100%' height='100%' fill='%230f0b14'/><path d='M60 180 Q150 90 240 180 Z' fill='%23581c87'/><path d='M50 180 Q150 120 250 180 L230 200 L70 200 Z' fill='%233b0764'/><text x='150' y='158' font-family='Cinzel' font-size='22' fill='%23e2e8f0' text-anchor='middle'>VC</text></svg>"
      }
    ];

    let catalogProductsData = [];
    let carouselItemsData = [];

    // MOSTRAR TOAST GUARDADO
    function showSaveToast() {
      saveToast.classList.add('visible');
      setTimeout(() => {
        saveToast.classList.remove('visible');
      }, 1500);
    }

    // PERSISTENCIA DE DATOS (LOCAL STORAGE)
    function saveAllData() {
      const cards = document.querySelectorAll('.catalog-grid .card');
      const updatedCatalog = [];

      cards.forEach((card, idx) => {
        updatedCatalog.push({
          id: card.dataset.id || `cap-${Date.now()}-${idx}`,
          name: card.querySelector('.card-title').innerText.trim(),
          desc: card.querySelector('.card-desc').innerText.trim(),
          price: card.querySelector('.card-price').innerText.trim(),
          badge: card.querySelector('.card-tag').innerText.trim(),
          stock: card.querySelector('.stock-num').innerText.trim(),
          image: card.querySelector('img').src
        });
      });

      catalogProductsData = updatedCatalog;
      
      localStorage.setItem('velora_catalog_data', JSON.stringify(catalogProductsData));
      localStorage.setItem('velora_carousel_data', JSON.stringify(carouselItemsData));

      showSaveToast();
    }

    function loadSavedData() {
      const savedCatalog = localStorage.getItem('velora_catalog_data');
      const savedCarousel = localStorage.getItem('velora_carousel_data');

      catalogProductsData = savedCatalog ? JSON.parse(savedCatalog) : [...defaultCaps];
      carouselItemsData = savedCarousel ? JSON.parse(savedCarousel) : [...defaultCaps];

      renderCarousel();
      renderCatalog();
    }

    /* RENDERING DE CARRUSEL */
    function renderCarousel() {
      carouselTrack.innerHTML = '';
      if(carouselItemsData.length === 0) return;

      const itemsToRender = [...carouselItemsData, ...carouselItemsData, ...carouselItemsData];
      
      itemsToRender.forEach(cap => {
        const item = document.createElement('div');
        item.className = 'carousel-item';
        item.innerHTML = `
          <img src="${cap.image}" alt="${cap.name}">
          <div class="carousel-item-title">${cap.name}</div>
        `;
        carouselTrack.appendChild(item);
      });
    }

    function handleCarouselUpload(event) {
      const files = event.target.files;
      if (files.length === 0) return;

      Array.from(files).forEach((file) => {
        const reader = new FileReader();
        reader.onload = function(e) {
          const rawName = file.name.split('.')[0].replace(/[-_]/g, ' ');
          const formattedName = rawName.charAt(0).toUpperCase() + rawName.slice(1);
          
          carouselItemsData.push({
            name: formattedName,
            image: e.target.result
          });
          renderCarousel();
          saveAllData();
        };
        reader.readAsDataURL(file);
      });
    }

    /* RENDERING DE CATÁLOGO */
    function renderCatalog() {
      catalogGrid.innerHTML = '';
      
      if (catalogProductsData.length === 0) {
        if (emptyState) emptyState.style.display = 'block';
        itemCount.innerText = `0 Productos`;
        return;
      }

      if (emptyState) emptyState.style.display = 'none';

      catalogProductsData.forEach(cap => {
        createCardElement(cap);
      });

      itemCount.innerText = `${catalogProductsData.length} Productos`;
    }

    function createCardElement(cap) {
      const card = document.createElement('div');
      card.className = 'card';
      card.dataset.id = cap.id;
      
      card.innerHTML = `
        <button class="delete-card-btn" onclick="event.stopPropagation(); deleteCard(this)">✕</button>
        <div class="card-img-wrapper">
          <span class="card-tag ${isAdmin ? 'editable-input' : ''}" contenteditable="${isAdmin}" onclick="event.stopPropagation()">${cap.badge}</span>
          <img src="${cap.image}" alt="${cap.name}">
        </div>
        <div class="card-body">
          <div class="card-title ${isAdmin ? 'editable-input' : ''}" contenteditable="${isAdmin}" onclick="event.stopPropagation()">${cap.name}</div>
          <div class="card-desc ${isAdmin ? 'editable-input' : ''}" contenteditable="${isAdmin}" onclick="event.stopPropagation()">${cap.desc}</div>
          <div class="card-stock">Disponibles: <span class="stock-num ${isAdmin ? 'editable-input' : ''}" contenteditable="${isAdmin}" onclick="event.stopPropagation()">${cap.stock}</span> unidades</div>
          <div class="card-footer">
            <div class="card-price ${isAdmin ? 'editable-input' : ''}" contenteditable="${isAdmin}" onclick="event.stopPropagation()">${cap.price}</div>
            <button class="buy-btn" onclick="event.stopPropagation(); openProductModalFromCard(this.closest('.card'))">Ver Detalle</button>
          </div>
        </div>
      `;

      const editables = card.querySelectorAll('[contenteditable]');
      editables.forEach(el => {
        el.addEventListener('blur', () => {
          if (isAdmin) saveAllData();
        });
      });

      card.addEventListener('click', () => {
        openProductModalFromCard(card);
      });
      
      catalogGrid.appendChild(card);
    }

    /* SUBIR FOTOS AL CATÁLOGO */
    function handleFileUpload(event) {
      const files = event.target.files;
      if (files.length === 0) return;

      Array.from(files).forEach((file) => {
        const reader = new FileReader();
        reader.onload = function(e) {
          const rawName = file.name.split('.')[0].replace(/[-_]/g, ' ');
          const formattedName = "Gorra " + rawName.charAt(0).toUpperCase() + rawName.slice(1);
          const randomPrice = `$${(45 + Math.floor(Math.random() * 35)).toFixed(2)} USD`;
          
          const newCap = {
            id: `cap-${Date.now()}-${Math.random().toString(36).substr(2, 4)}`,
            name: formattedName,
            desc: "Diseño exclusivo fabricado con materiales premium de alta resistencia.",
            price: randomPrice,
            badge: "Personal",
            stock: 10,
            image: e.target.result
          };

          catalogProductsData.push(newCap);
          renderCatalog();
          if (isAdmin) enableAdminMode();
          saveAllData();
        };
        reader.readAsDataURL(file);
      });
    }

    /* ABRIR / EDITAR MODAL DE DETALLES */
    function openProductModalFromCard(cardElement) {
      activeCardRef = cardElement;

      const title = cardElement.querySelector('.card-title').innerText;
      const desc = cardElement.querySelector('.card-desc').innerText;
      const price = cardElement.querySelector('.card-price').innerText;
      const badge = cardElement.querySelector('.card-tag').innerText;
      const stock = cardElement.querySelector('.stock-num').innerText;
      const image = cardElement.querySelector('img').src;

      const modalTitle = document.getElementById('modalTitle');
      const modalDesc = document.getElementById('modalDesc');
      const modalPrice = document.getElementById('modalPrice');
      const modalTag = document.getElementById('modalTag');
      const modalStockNum = document.getElementById('modalStockNum');
      
      modalTitle.innerText = title;
      modalDesc.innerText = desc;
      modalPrice.innerText = price;
      modalTag.innerText = badge;
      modalStockNum.innerText = stock;
      document.getElementById('modalImg').src = image;

      [modalTitle, modalDesc, modalPrice, modalTag, modalStockNum].forEach(el => {
        el.setAttribute('contenteditable', isAdmin ? 'true' : 'false');
        if (isAdmin) el.classList.add('editable-input');
        else el.classList.remove('editable-input');
      });

      const whatsappMsg = `Hola, quisiera solicitar información/adquirir la gorra: ${title} (${price})`;
      document.getElementById('modalBuyBtn').href = `https://wa.me/573046753279?text=${encodeURIComponent(whatsappMsg)}`;

      document.getElementById('productModal').style.display = 'flex';
    }

    function closeProductModal() {
      if (isAdmin && activeCardRef) {
        activeCardRef.querySelector('.card-title').innerText = document.getElementById('modalTitle').innerText;
        activeCardRef.querySelector('.card-desc').innerText = document.getElementById('modalDesc').innerText;
        activeCardRef.querySelector('.card-price').innerText = document.getElementById('modalPrice').innerText;
        activeCardRef.querySelector('.card-tag').innerText = document.getElementById('modalTag').innerText;
        activeCardRef.querySelector('.stock-num').innerText = document.getElementById('modalStockNum').innerText;
        saveAllData();
      }

      document.getElementById('productModal').style.display = 'none';
      activeCardRef = null;
    }

    /* MODO ADMINISTRADOR */
    function handleLogoClick() {
      logoClicks++;

      clearTimeout(clickTimer);
      clickTimer = setTimeout(() => {
        logoClicks = 0;
        clickBadge.classList.remove('visible');
      }, 4000);

      if (logoClicks > 10 && logoClicks < 20) {
        const remaining = 20 - logoClicks;
        clickBadge.innerText = `Faltan ${remaining} clics...`;
        clickBadge.classList.add('visible');
      }

      if (logoClicks >= 20) {
        logoClicks = 0;
        clickBadge.classList.remove('visible');
        toggleAdminModal();
      }
    }

    function toggleAdminModal() {
      const modal = document.getElementById('adminModal');
      const isVisible = modal.style.display === 'flex';
      modal.style.display = isVisible ? 'none' : 'flex';
      if (!isVisible) {
        document.getElementById('adminUser').focus();
      }
    }

    function loginAdmin() {
      const user = document.getElementById('adminUser').value;
      const pass = document.getElementById('adminPass').value;

      if (user === 'FerneyGomez2026' && pass === 'VeloraCaps') {
        isAdmin = true;
        toggleAdminModal();
        enableAdminMode();
        document.getElementById('adminUser').value = '';
        document.getElementById('adminPass').value = '';
      } else {
        alert('Acceso Denegado');
      }
    }

    function enableAdminMode() {
      document.body.classList.add('is-admin-active');
      document.getElementById('adminIndicator').style.display = 'block';

      const editableElements = document.querySelectorAll('.card-title, .card-desc, .card-price, .stock-num, .card-tag');
      editableElements.forEach(el => {
        el.setAttribute('contenteditable', 'true');
        el.classList.add('editable-input');
      });
    }

    function logoutAdmin() {
      isAdmin = false;
      document.body.classList.remove('is-admin-active');
      document.getElementById('adminIndicator').style.display = 'none';

      const editableElements = document.querySelectorAll('[contenteditable]');
      editableElements.forEach(el => {
        el.setAttribute('contenteditable', 'false');
        el.classList.remove('editable-input');
      });
    }

    function deleteCard(btn) {
      if (confirm('¿Eliminar este elemento del catálogo?')) {
        const card = btn.closest('.card');
        card.remove();
        saveAllData();
        itemCount.innerText = `${document.querySelectorAll('.catalog-grid .card').length} Productos`;
      }
    }

    function resetDataToDefault() {
      if (confirm('¿Deseas borrar los cambios y regresar al estado inicial?')) {
        localStorage.removeItem('velora_catalog_data');
        localStorage.removeItem('velora_carousel_data');
        loadSavedData();
        if (isAdmin) enableAdminMode();
      }
    }

    window.addEventListener('DOMContentLoaded', () => {
      loadSavedData();

      const brandLogo = document.getElementById('brandLogoBtn');
      if (brandLogo) {
        brandLogo.addEventListener('click', handleLogoClick);
      }

      const passInput = document.getElementById('adminPass');
      if (passInput) {
        passInput.addEventListener('keypress', (e) => {
          if (e.key === 'Enter') loginAdmin();
        });
      }
    });
  </script>
</body>
</html>
