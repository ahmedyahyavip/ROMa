   <!DOCTYPE html>
<html lang="ar" dir="rtl">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>ROM — Real Orders More | متجرك الذكي</title>
    <style>
      :root {
        --bg: #07111f;
        --bg-elevated: #101b2d;
        --panel: #f6f8fb;
        --panel-strong: #ffffff;
        --text: #131b2a;
        --text-soft: #606d7a;
        --text-on-dark: #edf3ff;
        --accent: #0071e3;
        --accent-strong: #0057bd;
        --accent-soft: rgba(0, 113, 227, 0.12);
        --line: #e4e9f2;
        --success: #1fa76a;
        --warning: #ffb020;
        --danger: #ea4b51;
        --shadow: 0 25px 60px rgba(8, 18, 33, 0.18);
        --radius: 22px;
        --max-width: 1200px;
      }

      * { box-sizing: border-box; }

      html { scroll-behavior: smooth; }

      body {
        margin: 0;
        font-family: "Segoe UI", Tahoma, Arial, sans-serif;
        background: linear-gradient(180deg, #07111f 0%, #0e1830 100%);
        color: var(--text);
        line-height: 1.6;
        -webkit-font-smoothing: antialiased;
        overflow-x: hidden;
      }

      img, svg { display: block; max-width: 100%; }
      a { color: inherit; text-decoration: none; }
      button, input { font: inherit; }
      button {
        border: 0;
        background: none;
        cursor: pointer;
      }

      .container {
        width: min(var(--max-width), calc(100% - 32px));
        margin-inline: auto;
      }

      .sr-only {
        position: absolute;
        width: 1px;
        height: 1px;
        padding: 0;
        margin: -1px;
        overflow: hidden;
        clip: rect(0, 0, 0, 0);
        white-space: nowrap;
        border: 0;
      }

      .topbar {
        position: sticky;
        top: 0;
        z-index: 30;
        background: rgba(7, 17, 31, 0.78);
        backdrop-filter: blur(16px);
        -webkit-backdrop-filter: blur(16px);
        border-bottom: 1px solid rgba(255, 255, 255, 0.08);
      }

      .nav-inner {
        width: min(var(--max-width), calc(100% - 32px));
        margin-inline: auto;
        height: 68px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        gap: 16px;
      }

      .brand {
        display: inline-flex;
        align-items: center;
        gap: 10px;
        color: var(--text-on-dark);
        font-weight: 800;
        letter-spacing: -0.04em;
        font-size: 1.35rem;
      }

      .brand-mark {
        width: 34px;
        height: 34px;
        display: inline-flex;
        align-items: center;
        justify-content: center;
        border-radius: 12px;
        font-size: 1.1rem;
        background: linear-gradient(135deg, #7d7aff, #0071e3);
        box-shadow: 0 12px 28px rgba(0, 113, 227, 0.38);
      }

      .nav-links {
        display: flex;
        align-items: center;
        gap: 28px;
        list-style: none;
        padding: 0;
        margin: 0;
        color: rgba(237, 243, 255, 0.78);
      }

      .nav-links a {
        font-size: 0.92rem;
        transition: color 0.2s ease;
      }

      .nav-links a:hover,
      .nav-links a:focus-visible {
        color: #ffffff;
      }

      .nav-actions {
        display: flex;
        align-items: center;
        gap: 12px;
      }

      .icon-button {
        position: relative;
        width: 42px;
        height: 42px;
        border-radius: 50%;
        display: inline-flex;
        align-items: center;
        justify-content: center;
        background: rgba(255, 255, 255, 0.06);
        border: 1px solid rgba(255, 255, 255, 0.08);
        color: var(--text-on-dark);
        transition: transform 0.2s ease, background 0.2s ease;
      }

      .icon-button:hover,
      .icon-button:focus-visible {
        transform: translateY(-1px);
        background: rgba(255, 255, 255, 0.1);
      }

      .badge {
        position: absolute;
        top: -6px;
        left: -6px;
        min-width: 20px;
        height: 20px;
        padding: 0 6px;
        display: grid;
        place-items: center;
        border-radius: 999px;
        background: var(--accent);
        color: white;
        font-size: 0.72rem;
        font-weight: 700;
        transform: scale(0);
        transition: transform 0.2s ease;
      }

      .badge.visible {
        transform: scale(1);
      }

      .nav-toggle { display: none; }

      .search-bar {
        display: none;
        background: rgba(16, 27, 45, 0.96);
        border-bottom: 1px solid rgba(255, 255, 255, 0.08);
      }

      .search-wrap {
        width: min(var(--max-width), calc(100% - 32px));
        margin-inline: auto;
        padding: 12px 0 18px;
      }

      .search-wrap input {
        width: min(600px, 100%);
        display: block;
        margin: 0 auto;
        border: 1px solid rgba(255, 255, 255, 0.1);
        background: rgba(255, 255, 255, 0.06);
        border-radius: 999px;
        padding: 14px 18px;
        color: var(--text-on-dark);
        outline: none;
      }

      .search-wrap input::placeholder { color: rgba(237, 243, 255, 0.6); }

      .hero {
        padding: 88px 0 56px;
        background: radial-gradient(circle at top, rgba(125, 122, 255, 0.25), transparent 28%), linear-gradient(180deg, #091423 0%, #07111f 100%);
      }

      .hero-inner {
        width: min(var(--max-width), calc(100% - 32px));
        margin-inline: auto;
        text-align: center;
      }

      .eyebrow {
        display: inline-flex;
        align-items: center;
        gap: 8px;
        padding: 8px 14px;
        border-radius: 999px;
        background: rgba(255, 255, 255, 0.05);
        color: rgba(237, 243, 255, 0.82);
        border: 1px solid rgba(255, 255, 255, 0.1);
        font-size: 0.8rem;
        margin-bottom: 18px;
      }

      .hero h1 {
        margin: 0;
        color: #fff;
        font-size: clamp(2.7rem, 6vw, 5.2rem);
        line-height: 1.04;
        letter-spacing: -0.06em;
      }

      .hero h1 span {
        background: linear-gradient(180deg, #fff 20%, #8d9cff 100%);
        -webkit-background-clip: text;
        background-clip: text;
        color: transparent;
      }

      .hero p {
        max-width: 720px;
        margin: 18px auto 0;
        color: rgba(237, 243, 255, 0.74);
        font-size: clamp(1.02rem, 2vw, 1.45rem);
      }

      .hero-actions {
        display: flex;
        flex-wrap: wrap;
        gap: 14px;
        justify-content: center;
        margin-top: 32px;
      }

      .btn {
        display: inline-flex;
        align-items: center;
        justify-content: center;
        min-height: 48px;
        padding: 0 22px;
        border-radius: 999px;
        font-weight: 700;
        transition: transform 0.2s ease, box-shadow 0.2s ease, background 0.2s ease;
      }

      .btn:hover,
      .btn:focus-visible { transform: translateY(-1px); }

      .btn-primary {
        background: linear-gradient(135deg, var(--accent), #1383ff);
        color: #fff;
        box-shadow: 0 16px 30px rgba(0, 113, 227, 0.3);
      }

      .btn-primary:hover,
      .btn-primary:focus-visible {
        background: linear-gradient(135deg, var(--accent-strong), var(--accent));
      }

      .btn-secondary {
        background: rgba(255, 255, 255, 0.04);
        color: var(--text-on-dark);
        border: 1px solid rgba(255, 255, 255, 0.12);
      }

      .hero-visual {
        width: min(760px, 88%);
        height: 280px;
        margin: 36px auto 0;
        border-radius: 28px;
        display: grid;
        place-items: center;
        font-size: clamp(4rem, 9vw, 9rem);
        background: linear-gradient(135deg, rgba(102, 109, 255, 0.55), rgba(0, 113, 227, 0.7), rgba(18, 35, 61, 0.78));
        box-shadow: 0 25px 80px rgba(0, 113, 227, 0.3);
        animation: float 6s ease-in-out infinite;
      }

      @keyframes float {
        0%, 100% { transform: translateY(0); }
        50% { transform: translateY(-12px); }
      }

      section { padding: 84px 0; }

      .section-header { text-align: center; margin-bottom: 40px; }

      .section-header h2 {
        margin: 0;
        color: var(--text);
        font-size: clamp(2rem, 4vw, 3.2rem);
        letter-spacing: -0.04em;
      }

      .section-header p {
        margin: 12px auto 0;
        color: var(--text-soft);
        font-size: 1.06rem;
        max-width: 640px;
      }

      .filter-row {
        display: flex;
        flex-wrap: wrap;
        gap: 12px;
        justify-content: center;
        margin-bottom: 28px;
      }

      .chip {
        padding: 10px 18px;
        border-radius: 999px;
        border: 1px solid var(--line);
        background: #fff;
        color: var(--text);
        font-weight: 600;
        transition: all 0.2s ease;
      }

      .chip:hover,
      .chip:focus-visible { border-color: var(--text); }

      .chip.active {
        background: var(--text);
        border-color: var(--text);
        color: #fff;
      }

      .product-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(230px, 1fr));
        gap: 24px;
      }

      .card {
        position: relative;
        background: rgba(255, 255, 255, 0.96);
        border: 1px solid rgba(17, 27, 42, 0.05);
        border-radius: var(--radius);
        padding: 22px 20px 18px;
        box-shadow: 0 20px 40px rgba(16, 27, 45, 0.04);
        transition: transform 0.24s ease, box-shadow 0.24s ease;
      }

      .card:hover,
      .card:focus-within {
        transform: translateY(-4px);
        box-shadow: var(--shadow);
      }

      .new-badge {
        position: absolute;
        top: 16px;
        left: 16px;
        background: linear-gradient(135deg, #ff496b, #ff8a00);
        color: white;
        padding: 6px 10px;
        border-radius: 999px;
        font-size: 0.7rem;
        font-weight: 800;
      }

      .product-icon {
        width: 88px;
        height: 88px;
        margin: 10px auto 16px;
        display: grid;
        place-items: center;
        font-size: 3.3rem;
        border-radius: 22px;
        background: linear-gradient(135deg, rgba(0, 113, 227, 0.08), rgba(125, 122, 255, 0.08));
      }

      .cat-tag {
        display: inline-block;
        color: var(--accent);
        font-size: 0.72rem;
        font-weight: 800;
        letter-spacing: 0.02em;
        margin-bottom: 8px;
      }

      .card h3 {
        margin: 0 0 8px;
        font-size: 1.2rem;
        color: var(--text);
      }

      .card p {
        margin: 0;
        color: var(--text-soft);
        font-size: 0.9rem;
        min-height: 54px;
      }

      .rating {
        display: inline-flex;
        align-items: center;
        gap: 4px;
        margin: 14px 0 12px;
        color: #f7b93b;
        letter-spacing: 0.12em;
      }

      .price {
        font-weight: 900;
        font-size: 1.5rem;
        color: var(--text);
      }

      .price small {
        font-size: 0.72rem;
        color: var(--text-soft);
        font-weight: 700;
      }

      .card-actions {
        display: flex;
        gap: 10px;
        margin-top: 18px;
      }

      .card-actions .btn {
        flex: 1;
        min-height: 42px;
        padding: 0 14px;
        font-size: 0.88rem;
      }

      .btn-light {
        background: #f3f6fb;
        border: 1px solid var(--line);
        color: var(--text);
      }

      .band { background: linear-gradient(180deg, #f4f7fb 0%, #edf3f9 100%); }

      .feature-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
        gap: 22px;
      }

      .feature {
        background: rgba(255, 255, 255, 0.9);
        border: 1px solid rgba(17, 27, 42, 0.04);
        border-radius: 20px;
        padding: 30px 22px;
        text-align: center;
        box-shadow: 0 12px 34px rgba(16, 27, 45, 0.04);
      }

      .feature .icon { font-size: 2.7rem; margin-bottom: 14px; }

      .feature h3 {
        margin: 0 0 8px;
        font-size: 1.1rem;
      }

      .feature p {
        margin: 0;
        color: var(--text-soft);
        font-size: 0.92rem;
      }

      footer {
        background: #091423;
        color: rgba(237, 243, 255, 0.8);
        padding: 52px 0 28px;
      }

      .footer-grid {
        width: min(var(--max-width), calc(100% - 32px));
        margin-inline: auto;
        display: grid;
        grid-template-columns: repeat(5, minmax(0, 1fr));
        gap: 28px;
      }

      .footer-brand h3 {
        margin: 0 0 10px;
        color: #fff;
        font-size: 1.55rem;
      }

      .footer-brand p,
      .footer-column a {
        color: rgba(237, 243, 255, 0.75);
        font-size: 0.9rem;
      }

      .footer-column h4 {
        margin: 0 0 14px;
        color: #fff;
        font-size: 1.06rem;
      }

      .footer-column {
        display: flex;
        flex-direction: column;
        gap: 8px;
      }

      .footer-bottom {
        width: min(var(--max-width), calc(100% - 32px));
        margin: 32px auto 0;
        padding-top: 24px;
        border-top: 1px solid rgba(255, 255, 255, 0.08);
        color: rgba(237, 243, 255, 0.74);
        text-align: center;
        font-size: 0.88rem;
      }

      .overlay {
        position: fixed;
        inset: 0;
        background: rgba(7, 17, 31, 0.45);
        opacity: 0;
        pointer-events: none;
        transition: opacity 0.25s ease;
        z-index: 80;
      }

      .overlay.open {
        opacity: 1;
        pointer-events: auto;
      }

      .drawer {
        position: fixed;
        top: 0;
        right: 0;
        height: 100vh;
        width: min(420px, 92vw);
        background: #fff;
        box-shadow: -16px 0 30px rgba(0, 0, 0, 0.18);
        transform: translateX(102%);
        transition: transform 0.28s ease;
        z-index: 90;
        display: flex;
        flex-direction: column;
      }

      .drawer.open { transform: translateX(0); }

      .drawer-header,
      .drawer-footer {
        padding: 18px 20px;
        border-bottom: 1px solid var(--line);
      }

      .drawer-header {
        display: flex;
        align-items: center;
        justify-content: space-between;
        gap: 12px;
      }

      .drawer-header h3 { margin: 0; font-size: 1.3rem; }

      .drawer-close {
        width: 36px;
        height: 36px;
        border-radius: 50%;
        display: grid;
        place-items: center;
        color: var(--text-soft);
        background: #f5f7fa;
      }

      .cart-items {
        flex: 1;
        overflow-y: auto;
        padding: 12px 20px 10px;
      }

      .cart-item {
        display: flex;
        align-items: center;
        gap: 12px;
        padding: 12px 0;
        border-bottom: 1px solid #edf1f5;
      }

      .cart-item-icon {
        width: 60px;
        height: 60px;
        border-radius: 16px;
        display: grid;
        place-items: center;
        background: #f2f6ff;
        font-size: 2rem;
      }

      .cart-item-info { flex: 1; }

      .cart-item-info h4 { margin: 0; font-size: 0.98rem; }

      .cart-item-price {
        display: block;
        color: var(--text-soft);
        font-size: 0.8rem;
        margin-top: 2px;
      }

      .quantity {
        display: flex;
        align-items: center;
        gap: 8px;
        background: #f5f7fa;
        border-radius: 999px;
        padding: 4px 8px;
        font-weight: 700;
      }

      .quantity button {
        width: 24px;
        height: 24px;
        border-radius: 50%;
        display: grid;
        place-items: center;
        background: #fff;
        border: 1px solid var(--line);
      }

      .cart-remove { color: var(--danger); font-size: 1.2rem; }

      .empty-cart {
        text-align: center;
        color: var(--text-soft);
        padding: 32px 12px 12px;
      }

      .empty-cart .big { font-size: 3.2rem; margin-bottom: 8px; }

      .empty-cart h4 {
        margin: 0 0 6px;
        color: var(--text);
      }

      .drawer-footer { border-top: 1px solid var(--line); border-bottom: 0; }

      .total-row {
        display: flex;
        align-items: center;
        justify-content: space-between;
        font-weight: 700;
        margin-bottom: 14px;
      }

      .checkout-btn {
        width: 100%;
        min-height: 48px;
        border-radius: 999px;
        background: linear-gradient(135deg, var(--accent), #1383ff);
        color: white;
        font-weight: 800;
      }

      .checkout-btn:disabled {
        opacity: 0.5;
        cursor: not-allowed;
      }

      .modal {
        position: fixed;
        inset: 0;
        display: grid;
        place-items: center;
        opacity: 0;
        pointer-events: none;
        transition: opacity 0.2s ease;
        z-index: 100;
      }

      .modal.open {
        opacity: 1;
        pointer-events: auto;
      }

      .modal-bg {
        position: absolute;
        inset: 0;
        background: rgba(7, 17, 31, 0.55);
      }

      .modal-box {
        position: relative;
        z-index: 1;
        width: min(560px, calc(100vw - 24px));
        background: #fff;
        border-radius: 28px;
        padding: 22px 20px 18px;
        box-shadow: var(--shadow);
      }

      .modal-close {
        position: absolute;
        top: 14px;
        left: 14px;
        width: 36px;
        height: 36px;
        border-radius: 50%;
        display: grid;
        place-items: center;
        background: #f5f7fa;
        color: var(--text-soft);
      }

      .modal-emoji {
        display: grid;
        place-items: center;
        width: 96px;
        height: 96px;
        margin: 10px auto 12px;
        border-radius: 24px;
        background: linear-gradient(135deg, rgba(0, 113, 227, 0.12), rgba(125, 122, 255, 0.12));
        font-size: 3rem;
      }

      .modal-box h2 {
        margin: 0 0 8px;
        text-align: center;
        color: var(--text);
      }

      .m-price {
        text-align: center;
        color: var(--accent);
        font-weight: 800;
        font-size: 1.65rem;
        margin-bottom: 8px;
      }

      .m-desc {
        margin: 0 0 18px;
        text-align: center;
        color: var(--text-soft);
      }

      .spec-list {
        list-style: none;
        padding: 0;
        margin: 0 0 16px;
        display: grid;
        gap: 10px;
      }

      .spec-list li {
        display: flex;
        justify-content: space-between;
        align-items: center;
        gap: 12px;
        background: #f7f9fc;
        border: 1px solid #eef2f8;
        border-radius: 12px;
        padding: 10px 12px;
      }

      .spec-list span { color: var(--text-soft); }
      .spec-list b { color: var(--text); }

      .form-grid { display: grid; gap: 14px; }

      .field {
        display: grid;
        gap: 8px;
        text-align: right;
      }

      .field label {
        color: var(--text);
        font-weight: 700;
        font-size: 0.9rem;
      }

      .field input {
        width: 100%;
        min-height: 46px;
        border-radius: 12px;
        border: 1px solid var(--line);
        background: #f9fafc;
        padding: 0 12px;
        color: var(--text);
      }

      .field input:focus {
        outline: 2px solid rgba(0, 113, 227, 0.18);
        border-color: rgba(0, 113, 227, 0.5);
      }

      .toast {
        position: fixed;
        right: 20px;
        bottom: 20px;
        background: #102338;
        color: #fff;
        border-radius: 999px;
        padding: 12px 16px;
        box-shadow: 0 16px 30px rgba(0, 0, 0, 0.2);
        opacity: 0;
        transform: translateY(12px);
        pointer-events: none;
        transition: opacity 0.2s ease, transform 0.2s ease;
        z-index: 120;
      }

      .toast.show {
        opacity: 1;
        transform: translateY(0);
      }

      @media (max-width: 900px) {
        .nav-links {
          position: absolute;
          top: 68px;
          right: 16px;
          left: 16px;
          display: none;
          flex-direction: column;
          align-items: flex-start;
          padding: 16px;
          background: rgba(9, 20, 35, 0.98);
          border: 1px solid rgba(255, 255, 255, 0.08);
          border-radius: 18px;
          box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
        }

        .nav-links.open { display: flex; }
        .nav-toggle { display: inline-flex; }
        .footer-grid { grid-template-columns: repeat(2, minmax(0, 1fr)); }
      }

      @media (max-width: 620px) {
        .hero { padding-top: 68px; }
        .hero-visual { height: 200px; }
        .product-grid, .feature-grid, .footer-grid { grid-template-columns: 1fr; }
        .card-actions { flex-direction: column; }
      }

      @media (prefers-reduced-motion: reduce) {
        *, *::before, *::after {
          animation: none !important;
          transition: none !important;
          scroll-behavior: auto !important;
        }
      }
    </style>
  </head>
  <body>
    <nav class="topbar" aria-label="التنقل الرئيسي">
      <div class="nav-inner">
        <a href="#home" class="brand" aria-label="ROM الرئيسية">
          <span class="brand-mark">R</span>
          <span>ROM</span>
        </a>

        <ul class="nav-links" id="navLinks">
          <li><a href="#home">الرئيسية</a></li>
          <li><a href="#products">المنتجات</a></li>
          <li><a href="#features">المميزات</a></li>
          <li><a href="#contact">تواصل</a></li>
        </ul>

        <div class="nav-actions">
          <button class="icon-button" id="toggleSearch" type="button" aria-label="بحث">🔎</button>
          <button class="icon-button" id="toggleCart" type="button" aria-label="فتح السلة">
            🛒
            <span class="badge" id="cartBadge">0</span>
          </button>
          <button class="icon-button nav-toggle" id="navToggle" type="button" aria-label="فتح القائمة">☰</button>
        </div>
      </div>

      <div class="search-bar" id="searchBar" aria-label="بحث المنتجات">
        <div class="search-wrap">
          <label class="sr-only" for="searchInput">ابحث عن منتج</label>
          <input id="searchInput" type="search" placeholder="ابحث عن هاتف، كمبيوتر، سماعة..." />
        </div>
      </div>
    </nav>

    <header class="hero" id="home">
      <div class="hero-inner">
        <div class="eyebrow">⚡ جديد هذا الأسبوع</div>
        <h1><span>المستقبل</span> بين يديك.</h1>
        <p>اكتشف أحدث الأجهزة الإلكترونية، واحصل على أفضل الأسعار في تجربة تسوق ذكية وسريعة.</p>
        <div class="hero-actions">
          <a href="#products" class="btn btn-primary">تسوق الآن</a>
          <a href="#features" class="btn btn-secondary">اكتشف المزايا</a>
        </div>
        <div class="hero-visual" aria-hidden="true">🎧⌚💻</div>
      </div>
    </header>

    <main>
      <section id="products">
        <div class="container">
          <div class="section-header">
            <h2>تسوق حسب الفئة</h2>
            <p>اختر أفضل ما يناسب أسلوبك من تشكيلة مختارة بعناية.</p>
          </div>
          <div class="filter-row" id="filters" aria-label="فلترة المنتجات"></div>
          <div class="product-grid" id="productGrid"></div>
        </div>
      </section>

      <section class="band" id="features">
        <div class="container">
          <div class="section-header">
            <h2>لماذا تختارنا؟</h2>
            <p>تجربة تسوق آمنة، سريعة، وعملية من أول خطوة إلى آخرها.</p>
          </div>
          <div class="feature-grid">
            <article class="feature">
              <div class="icon">🚚</div>
              <h3>شحن سريع</h3>
              <p>توصيل خلال 24-48 ساعة إلى أغلب المدن، مع شحن مجاني.</p>
            </article>
            <article class="feature">
              <div class="icon">🛡️</div>
              <h3>ضمان حقيقي</h3>
              <p>جميع المنتجات تأتي بضمان موثوق واستبدال سهل عند الحاجة.</p>
            </article>
            <article class="feature">
              <div class="icon">💳</div>
              <h3>دفع آمن</h3>
              <p>خيارات دفع متعددة، وبيئة شراء موثوقة ومشفرة.</p>
            </article>
            <article class="feature">
              <div class="icon">🔄</div>
              <h3>إرجاع مجاني</h3>
              <p>إرجاع المنتجات خلال 30 يومًا بسهولة وبدون تعقيد.</p>
            </article>
          </div>
        </div>
      </section>
    </main>

    <footer id="contact">
      <div class="footer-grid">
        <div class="footer-brand">
          <h3>ROM</h3>
          <p>Real Orders More.<br />طلبات حقيقية، تجربة أكثر.</p>
        </div>
        <div class="footer-column">
          <h4>تسوق</h4>
          <a href="#products">الهواتف</a>
          <a href="#products">اللابتوبات</a>
          <a href="#products">السماعات</a>
          <a href="#products">الساعات</a>
        </div>
        <div class="footer-column">
          <h4>خدمة العملاء</h4>
          <a href="#">تتبع الطلب</a>
          <a href="#">الشحن والتوصيل</a>
          <a href="#">الإرجاع</a>
          <a href="#">الأسئلة الشائعة</a>
        </div>
        <div class="footer-column">
          <h4>عن المتجر</h4>
          <a href="#">من نحن</a>
          <a href="#">الوظائف</a>
          <a href="#">الأخبار</a>
          <a href="#">الاستدامة</a>
        </div>
        <div class="footer-column">
          <h4>تواصل معنا</h4>
          <a href="mailto:hello@techstore.com">hello@techstore.com</a>
          <a href="tel:+966500000000">+966 50 000 0000</a>
          <a href="#">الرياض، السعودية</a>
        </div>
      </div>
      <div class="footer-bottom">
        <strong>ROM</strong> — Real Orders More. © 2026 جميع الحقوق محفوظة. | صُنع بشغف 🖤
      </div>
    </footer>

    <div class="overlay" id="overlay"></div>

    <aside class="drawer" id="cartDrawer" aria-label="سلة التسوق">
      <div class="drawer-header">
        <h3>🛍️ سلة التسوق</h3>
        <button class="drawer-close" type="button" id="closeCart" aria-label="إغلاق السلة">✕</button>
      </div>
      <div class="cart-items" id="cartItems"></div>
      <div class="drawer-footer">
        <div class="total-row">
          <span>الإجمالي</span>
          <span id="cartTotal">0 ر.س</span>
        </div>
        <button class="checkout-btn" type="button" id="checkoutBtn" disabled>إتمام الشراء</button>
      </div>
    </aside>

    <div class="modal" id="productModal" aria-hidden="true">
      <div class="modal-bg" id="modalBg"></div>
      <div class="modal-box" id="modalBox"></div>
    </div>

    <div class="toast" id="toast" role="status" aria-live="polite">✅ تمت الإضافة إلى السلة</div>

    <script>
      const PRODUCTS = [
        { id: 1, name: 'آيفون 17 برو ماكس', cat: 'هواتف', price: 5299, emoji: '📱', isNew: true, rating: 5, desc: 'شريحة A19 Pro، كاميرا 48MP، شاشة ProMotion 120Hz، وتصميم من التيتانيوم.', specs: { 'الشاشة': '6.9 بوصة OLED', 'التخزين': '256GB', 'الكاميرا': '48MP ثلاثية', 'البطارية': '30 ساعة تشغيل' } },
        { id: 2, name: 'ماك بوك برو 16', cat: 'لابتوبات', price: 9499, emoji: '💻', isNew: true, rating: 5, desc: 'شريحة M5 Pro مع ذاكرة 36GB وشاشة Liquid Retina XDR مذهلة.', specs: { 'المعالج': 'M5 Pro', 'الذاكرة': '36GB', 'التخزين': '512GB SSD', 'البطارية': '22 ساعة' } },
        { id: 3, name: 'سماعات AirPods Max', cat: 'سماعات', price: 1999, emoji: '🎧', isNew: false, rating: 4, desc: 'إلغاء ضوضاء نشط، صوت فضائي، وبطارية تدوم حتى 20 ساعة.', specs: { 'إلغاء الضوضاء': 'نشط', 'البطارية': '20 ساعة', 'الاتصال': 'Bluetooth 5.3', 'الوزن': '385 جم' } },
        { id: 4, name: 'ساعة Apple Watch Ultra 3', cat: 'ساعات', price: 3299, emoji: '⌚', isNew: true, rating: 5, desc: 'مصنوعة من التيتانيوم، مقاومة للماء حتى 100 متر، وبطارية 72 ساعة.', specs: { 'المعالج': 'S11', 'البطارية': '72 ساعة', 'المقاومة': '100 متر', 'GPS': 'مزدوج التردد' } },
        { id: 5, name: 'آيباد برو 13 بوصة', cat: 'هواتف', price: 4599, emoji: '📲', isNew: false, rating: 4, desc: 'أنحف آيباد على الإطلاق مع شريحة M5 وشاشة Ultra Retina XDR.', specs: { 'الشاشة': '13 بوصة XDR', 'المعالج': 'M5', 'التخزين': '256GB', 'القلم': 'مدعوم' } },
        { id: 6, name: 'سماعات AirPods Pro 3', cat: 'سماعات', price: 949, emoji: '🎵', isNew: false, rating: 4, desc: 'إلغاء ضوضاء مضاعف، وضع الشفافية التكيفية، وصوت مخصص.', specs: { 'إلغاء الضوضاء': '2x أقوى', 'البطارية': '30 ساعة', 'الشحن': 'MagSafe', 'الصندوق': 'USB-C' } },
        { id: 7, name: 'آيفون 16', cat: 'هواتف', price: 3699, emoji: '📱', isNew: false, rating: 5, desc: 'التوازن المثالي بين الأداء والسعر مع شريحة A18.', specs: { 'الشاشة': '6.1 بوصة', 'المعالج': 'A18', 'الكاميرا': '48MP', 'البطارية': '27 ساعة' } },
        { id: 8, name: 'ماك بوك Air 15', cat: 'لابتوبات', price: 5899, emoji: '💻', isNew: false, rating: 4, desc: 'أخف وأنحف ماك بوك مع شريحة M4 وألوان مبهجة.', specs: { 'المعالج': 'M4', 'الذاكرة': '16GB', 'التخزين': '512GB', 'الوزن': '1.51 كجم' } },
        { id: 9, name: 'ساعة Apple Watch SE', cat: 'ساعات', price: 1249, emoji: '⌚', isNew: false, rating: 4, desc: 'ساعة ذكية مثالية للمبتدئين مع تتبع الصحة واللياقة.', specs: { 'المعالج': 'S9', 'البطارية': '18 ساعة', 'المقاومة': '50 متر', 'المقاسات': '40/44mm' } },
        { id: 10, name: 'سماعات Beats Studio Pro', cat: 'سماعات', price: 1349, emoji: '🎶', isNew: false, rating: 4, desc: 'صوت احترافي مع إلغاء ضوضاء وتشغيل 40 ساعة.', specs: { 'البطارية': '40 ساعة', 'الشحن': 'USB-C', 'الكودك': 'Lossless', 'الألوان': '4 خيارات' } },
        { id: 11, name: 'آيباد ميني 7', cat: 'هواتف', price: 2099, emoji: '📲', isNew: true, rating: 5, desc: 'قوة A17 Pro بحجم الجيب، مثلي للقراءة والرسم.', specs: { 'الشاشة': '8.3 بوصة', 'المعالج': 'A17 Pro', 'القلم': 'Apple Pencil Pro', 'الوزن': '297 جم' } },
        { id: 12, name: 'ماك ستوديو', cat: 'لابتوبات', price: 12499, emoji: '🖥️', isNew: true, rating: 5, desc: 'وحش الأداء الإبداعي مع شريحة M5 Ultra للمحترفين.', specs: { 'المعالج': 'M5 Ultra', 'الذاكرة': '96GB', 'التخزين': '1TB SSD', 'المنافذ': '12 منفذ' } }
      ];

      const CATEGORIES = ['الكل', 'هواتف', 'لابتوبات', 'سماعات', 'ساعات'];
      const state = { activeCategory: 'الكل', cart: readCart() };

      const els = {
        filters: document.getElementById('filters'),
        products: document.getElementById('productGrid'),
        search: document.getElementById('searchInput'),
        cartBadge: document.getElementById('cartBadge'),
        cartItems: document.getElementById('cartItems'),
        cartTotal: document.getElementById('cartTotal'),
        checkoutBtn: document.getElementById('checkoutBtn'),
        cartDrawer: document.getElementById('cartDrawer'),
        overlay: document.getElementById('overlay'),
        modal: document.getElementById('productModal'),
        modalBox: document.getElementById('modalBox'),
        toast: document.getElementById('toast'),
        searchBar: document.getElementById('searchBar'),
        navLinks: document.getElementById('navLinks')
      };

      function currency(value) {
        return new Intl.NumberFormat('ar-SA', { style: 'currency', currency: 'SAR', maximumFractionDigits: 0 }).format(value);
      }

      function readCart() {
        try {
          const raw = localStorage.getItem('rom-cart');
          return raw ? JSON.parse(raw) : [];
        } catch (error) {
          return [];
        }
      }

      function saveCart() {
        localStorage.setItem('rom-cart', JSON.stringify(state.cart));
        updateCartUI();
      }

      function renderFilters() {
        els.filters.innerHTML = CATEGORIES.map((cat) => `
          <button type="button" class="chip ${cat === state.activeCategory ? 'active' : ''}" data-category="${cat}">${cat}</button>
        `).join('');

        document.querySelectorAll('.chip').forEach((button) => {
          button.addEventListener('click', () => {
            state.activeCategory = button.dataset.category;
            renderFilters();
            renderProducts();
          });
        });
      }

      function stars(value) {
        return '★'.repeat(value) + '☆'.repeat(5 - value);
      }

      function renderProducts() {
        const searchText = (els.search.value || '').trim().toLowerCase();
        const filtered = PRODUCTS.filter((product) => {
          const matchesCategory = state.activeCategory === 'الكل' || product.cat === state.activeCategory;
          const haystack = `${product.name} ${product.desc} ${product.cat}`.toLowerCase();
          const matchesQuery = !searchText || haystack.includes(searchText);
          return matchesCategory && matchesQuery;
        });

        if (!filtered.length) {
          els.products.innerHTML = '<div style="grid-column:1/-1;text-align:center;padding:32px;color:#606d7a;font-size:1.08rem;">لا توجد منتجات مطابقة لبحثك في الوقت الحالي 😕</div>';
          return;
        }

        els.products.innerHTML = filtered.map((product) => `
          <article class="card" aria-label="${product.name}">
            ${product.isNew ? '<span class="new-badge">جديد</span>' : ''}
            <div class="product-icon" aria-hidden="true">${product.emoji}</div>
            <span class="cat-tag">${product.cat}</span>
            <h3>${product.name}</h3>
            <p>${product.desc}</p>
            <div class="rating" aria-label="تقييم ${product.rating} من 5">${stars(product.rating)}</div>
            <div class="price">${currency(product.price).replace('SAR', '').trim()} <small>ر.س</small></div>
            <div class="card-actions">
              <button type="button" class="btn btn-primary" onclick="addToCart(${product.id})">أضف للسلة</button>
              <button type="button" class="btn btn-light" onclick="openProduct(${product.id})">عرض</button>
            </div>
          </article>
        `).join('');
      }

      function updateCartUI() {
        const totalItems = state.cart.reduce((sum, item) => sum + item.qty, 0);
        els.cartBadge.textContent = totalItems;
        els.cartBadge.classList.toggle('visible', totalItems > 0);

        if (!state.cart.length) {
          els.cartItems.innerHTML = `
            <div class="empty-cart">
              <div class="big">🛒</div>
              <h4>سلتك فارغة</h4>
              <p>ابدأ التسوق الآن واملأ السلة بمنتجاتك المفضلة.</p>
            </div>
          `;
        } else {
          els.cartItems.innerHTML = state.cart.map((item) => `
            <div class="cart-item">
              <div class="cart-item-icon">${item.emoji}</div>
              <div class="cart-item-info">
                <h4>${item.name}</h4>
                <span class="cart-item-price">${currency(item.price)}</span>
              </div>
              <div class="quantity">
                <button type="button" onclick="changeQty(${item.id}, -1)">−</button>
                <span>${item.qty}</span>
                <button type="button" onclick="changeQty(${item.id}, 1)">+</button>
              </div>
              <button type="button" class="cart-remove" onclick="removeItem(${item.id})" aria-label="حذف ${item.name}">🗑</button>
            </div>
          `).join('');
        }

        const total = state.cart.reduce((sum, item) => sum + (item.price * item.qty), 0);
        els.cartTotal.textContent = `${currency(total)}`;
        els.checkoutBtn.disabled = !state.cart.length;
      }

      function addToCart(productId) {
        const product = PRODUCTS.find((item) => item.id === productId);
        if (!product) return;

        const existing = state.cart.find((item) => item.id === productId);
        if (existing) {
          existing.qty += 1;
        } else {
          state.cart.push({ ...product, qty: 1 });
        }

        saveCart();
        showToast('✅ تمت الإضافة إلى السلة');
      }

      function changeQty(productId, delta) {
        const item = state.cart.find((entry) => entry.id === productId);
        if (!item) return;

        item.qty += delta;
        if (item.qty <= 0) {
          state.cart = state.cart.filter((entry) => entry.id !== productId);
        }

        saveCart();
      }

      function removeItem(productId) {
        state.cart = state.cart.filter((entry) => entry.id !== productId);
        saveCart();
      }

      function toggleCart(open) {
        els.cartDrawer.classList.toggle('open', open);
        els.overlay.classList.toggle('open', open);
      }

      function openProduct(productId) {
        const product = PRODUCTS.find((item) => item.id === productId);
        if (!product) return;

        els.modalBox.innerHTML = `
          <button type="button" class="modal-close" id="closeModal" aria-label="إغلاق">✕</button>
          <div class="modal-emoji" aria-hidden="true">${product.emoji}</div>
          <h2>${product.name}</h2>
          <div class="m-price">${currency(product.price)}</div>
          <div class="rating" style="justify-content:center; margin-bottom:18px;">${stars(product.rating)}</div>
          <p class="m-desc">${product.desc}</p>
          <ul class="spec-list">
            ${Object.entries(product.specs).map(([key, value]) => `<li><span>${key}</span><b>${value}</b></li>`).join('')}
          </ul>
          <button type="button" class="btn btn-primary" style="width:100%;" onclick="addToCart(${product.id}); closeModal();">أضف إلى السلة 🛒</button>
        `;

        els.modal.classList.add('open');
        els.modal.setAttribute('aria-hidden', 'false');
        document.getElementById('closeModal').addEventListener('click', closeModal);
      }

      function closeModal() {
        els.modal.classList.remove('open');
        els.modal.setAttribute('aria-hidden', 'true');
      }

      function openCheckout() {
        if (!state.cart.length) return;

        const total = state.cart.reduce((sum, item) => sum + item.price * item.qty, 0);

        els.modalBox.innerHTML = `
          <button type="button" class="modal-close" id="closeModal" aria-label="إغلاق">✕</button>
          <h2>🧾 إتمام الطلب</h2>
          <p class="m-desc">الإجمالي: <strong style="color:var(--accent);">${currency(total)}</strong> — شحن مجاني</p>
          <form id="checkoutForm" class="form-grid">
            <div class="field">
              <label for="userName">الاسم الكامل</label>
              <input id="userName" type="text" required placeholder="محمد أحمد" />
            </div>
            <div class="field">
              <label for="phone">رقم الجوال</label>
              <input id="phone" type="tel" required placeholder="05xxxxxxxx" pattern="[0-9+]{9,}" />
            </div>
            <div class="field">
              <label for="city">المدينة</label>
              <input id="city" type="text" required placeholder="الرياض" />
            </div>
            <div class="field">
              <label for="address">العنوان</label>
              <input id="address" type="text" required placeholder="الحي، الشارع، رقم المبنى" />
            </div>
            <button type="submit" class="btn btn-primary" style="width:100%;">تأكيد الطلب ✅</button>
          </form>
        `;

        els.modal.classList.add('open');
        els.modal.setAttribute('aria-hidden', 'false');
        document.getElementById('closeModal').addEventListener('click', closeModal);
        document.getElementById('checkoutForm').addEventListener('submit', (event) => {
          event.preventDefault();
          placeOrder();
        });
      }

      function placeOrder() {
        const orderNo = Math.floor(100000 + Math.random() * 900000);
        state.cart = [];
        localStorage.setItem('rom-cart', JSON.stringify(state.cart));
        closeModal();
        toggleCart(false);
        updateCartUI();

        els.modalBox.innerHTML = `
          <button type="button" class="modal-close" id="closeModal" aria-label="إغلاق">✕</button>
          <div class="modal-emoji" aria-hidden="true">🎉</div>
          <h2>تم استلام طلبك!</h2>
          <p class="m-desc">رقم الطلب: <strong style="color:var(--accent);">#${orderNo}</strong><br />سنتواصل معك قريباً لتأكيد التوصيل.</p>
          <button type="button" class="btn btn-primary" style="width:100%;" onclick="closeModal();">متابعة التسوق</button>
        `;

        els.modal.classList.add('open');
        els.modal.setAttribute('aria-hidden', 'false');
        document.getElementById('closeModal').addEventListener('click', closeModal);
      }

      function showToast(message) {
        els.toast.textContent = message;
        els.toast.classList.add('show');
        clearTimeout(showToast.timeout);
        showToast.timeout = setTimeout(() => els.toast.classList.remove('show'), 2200);
      }

      document.getElementById('toggleSearch').addEventListener('click', () => {
        const isVisible = els.searchBar.style.display === 'block';
        els.searchBar.style.display = isVisible ? 'none' : 'block';
        if (!isVisible) {
          els.search.focus();
        }
      });

      document.getElementById('toggleCart').addEventListener('click', () => toggleCart(true));
      document.getElementById('closeCart').addEventListener('click', () => toggleCart(false));
      document.getElementById('overlay').addEventListener('click', () => toggleCart(false));
      document.getElementById('modalBg').addEventListener('click', closeModal);
      document.getElementById('checkoutBtn').addEventListener('click', openCheckout);
      document.getElementById('navToggle').addEventListener('click', () => { els.navLinks.classList.toggle('open'); });
      els.search.addEventListener('input', renderProducts);
      document.querySelectorAll('#navLinks a').forEach((link) => {
        link.addEventListener('click', () => els.navLinks.classList.remove('open'));
      });

      renderFilters();
      renderProducts();
      updateCartUI();
    </script>
  </body>
</html>
