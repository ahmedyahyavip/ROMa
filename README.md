<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ROM — Real Orders More | متجرك الذكي</title>
<style>
/* ============ RESET & VARIABLES ============ */
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box}
:root{
  --bg:#000;
  --bg-soft:#f5f5f7;
  --text:#1d1d1f;
  --text-soft:#86868b;
  --accent:#0071e3;
  --accent-hover:#0077ed;
  --radius:18px;
  --max:1200px;
}
html{scroll-behavior:smooth}
body{font-family:"SF Pro Display","Segoe UI",Tahoma,Arial,sans-serif;background:var(--bg);color:var(--text);-webkit-font-smoothing:antialiased;overflow-x:hidden}
a{text-decoration:none;color:inherit}
button{font-family:inherit;cursor:pointer;border:none;background:none}
img{max-width:100%;display:block}
<style>
/* ============ NAVBAR ============ */
nav{position:fixed;top:0;right:0;left:0;z-index:1000;backdrop-filter:saturate(180%) blur(20px);-webkit-backdrop-filter:saturate(180%) blur(20px);background:rgba(0,0,0,.8);height:52px;display:flex;align-items:center;justify-content:center}
.nav-inner{display:flex;align-items:center;gap:34px;max-width:var(--max);width:100%;padding:0 22px}
.logo{color:#fff;font-size:20px;font-weight:700;letter-spacing:-.5px;display:flex;align-items:center;gap:8px}
.nav-links{display:flex;gap:30px;list-style:none}
.nav-links a{color:#d6d6da;font-size:13px;transition:color .2s}
.nav-links a:hover{color:#fff}
.nav-icons{display:flex;gap:18px;align-items:center;margin-right:auto}
.nav-icon{color:#fff;font-size:17px;position:relative;transition:transform .2s}
.nav-icon:hover{transform:scale(1.1)}
.cart-badge{position:absolute;top:-7px;right:-8px;background:var(--accent);color:#fff;font-size:10px;font-weight:700;width:16px;height:16px;border-radius:50%;display:flex;align-items:center;justify-content:center;transform:scale(0);transition:transform .25s cubic-bezier(.68,-0.55,.27,1.55)}
.cart-badge.show{transform:scale(1)}
.search-bar{display:none;position:fixed;top:52px;right:0;left:0;z-index:999;background:#1d1d1f;padding:14px;text-align:center;box-shadow:0 10px 30px rgba(0,0,0,.4)}
.search-bar input{width:min(600px,90%);padding:10px 18px;border-radius:10px;border:none;font-size:14px;font-family:inherit;outline:none}
.hamburger{display:none;color:#fff;font-size:22px}
/* ============ HERO ============ */.hero{min-height:92vh;display:flex;flex-direction:column;align-items:center;justify-content:center;text-align:center;padding:110px 20px 60px;background:radial-gradient(ellipse at 50% 0%,#1a1a2e 0%,#000 60%)}
.hero h1{font-size:clamp(42px,7vw,84px);font-weight:800;color:#fff;letter-spacing:-2px;line-height:1.1;background:linear-gradient(180deg,#fff 30%,#7d7aff);-webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:transparent}
.hero p{color:#a1a1a6;font-size:clamp(16px,2.2vw,22px);margin:20px 0 34px;max-width:640px}
.btn{display:inline-block;padding:13px 30px;border-radius:980px;font-size:16px;font-weight:600;transition:all .25s}
.btn-primary{background:var(--accent);color:#fff}
.btn-primary:hover{background:var(--accent-hover);transform:translateY(-2px);box-shadow:0 8px 25px rgba(0,113,227,.4)}
.btn-ghost{color:var(--accent);border:1px solid var(--accent)}
.btn-ghost:hover{background:var(--accent);color:#fff}
.hero-btns{display:flex;gap:16px;flex-wrap:wrap;justify-content:center}
.hero-visual{margin-top:50px;width:min(700px,90%);height:340px;background:linear-gradient(135deg,#2b2b4d,#0071e3 50%,#7d7aff);border-radius:30px;position:relative;overflow:hidden;box-shadow:0 40px 100px rgba(0,113,227,.3);animation:float 6s ease-in-out infinite;display:flex;align-items:center;justify-content:center;font-size:90px}
@keyframes float{0%,100%{transform:translateY(0)}50%{transform:translateY(-15px)}}
/* ============ SECTIONS ============ */section{padding:80px 20px}
.container{max-width:var(--max);margin:0 auto}
.section-title{font-size:clamp(30px,4.5vw,52px);font-weight:800;text-align:center;margin-bottom:10px;letter-spacing:-1px}
.section-sub{text-align:center;color:var(--text-soft);font-size:17px;margin-bottom:48px}
/* ============ PRODUCT GRID ============ */.grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(270px,1fr));gap:24px}
.card{background:var(--bg-soft);border-radius:var(--radius);padding:30px 24px;text-align:center;transition:transform .35s cubic-bezier(.2,.8,.2,1),box-shadow .35s;cursor:pointer;position:relative;overflow:hidden}
.card:hover{transform:translateY(-8px);box-shadow:0 20px 50px rgba(0,0,0,.12)}
.card .emoji{font-size:72px;margin-bottom:18px;transition:transform .35s}
.card:hover .emoji{transform:scale(1.15) rotate(-5deg)}
.card h3{font-size:19px;font-weight:700;margin-bottom:6px}
.card .cat-tag{font-size:12px;color:var(--accent);font-weight:600;margin-bottom:8px;display:block}
.card p{color:var(--text-soft);font-size:14px;margin-bottom:14px;line-height:1.6;min-height:44px}
.stars{color:#ff9500;font-size:14px;margin-bottom:10px;letter-spacing:2px}
.price{font-size:22px;font-weight:800;color:var(--text)}
.price small{font-size:13px;color:var(--text-soft);font-weight:400}
.card .actions{display:flex;gap:10px;margin-top:18px}
.btn-add{flex:1;background:var(--accent);color:#fff;padding:11px;border-radius:980px;font-size:14px;font-weight:600;transition:all .2s}
.btn-add:hover{background:#000}
.btn-view{padding:11px 16px;border:1px solid #d2d2d7;border-radius:980px;font-size:14px;transition:all .2s}
.btn-view:hover{border-color:var(--text)}
.new-badge{position:absolute;top:16px;right:16px;background:linear-gradient(135deg,#ff375f,#ff9500);color:#fff;font-size:11px;font-weight:700;padding:5px 12px;border-radius:980px}
/* ============ FEATURES BAND ============ */.band{background:var(--bg-soft)}
.band-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(230px,1fr));gap:24px}
.band-card{background:#fff;border-radius:var(--radius);padding:36px 24px;text-align:center;transition:transform .3s}
.band-card:hover{transform:translateY(-6px)}
.band-card .ic{font-size:44px;margin-bottom:16px}
.band-card h4{font-size:17px;margin-bottom:8px}
.band-card p{color:var(--text-soft);font-size:14px;line-height:1.7}
/* ============ FILTER BAR ============ */.filters{display:flex;gap:12px;justify-content:center;flex-wrap:wrap;margin-bottom:44px}
.chip{padding:9px 22px;border-radius:980px;border:1px solid #d2d2d7;font-size:14px;transition:all .2s;background:#fff}
.chip:hover{border-color:var(--text)}
.chip.active{background:var(--text);color:#fff;border-color:var(--text)}
/* ============ CART DRAWER ============ */.overlay{position:fixed;inset:0;background:rgba(0,0,0,.4);z-index:1100;opacity:0;pointer-events:none;transition:opacity .3s}
.overlay.open{opacity:1;pointer-events:auto}
.drawer{position:fixed;top:0;left:0;bottom:0;width:min(420px,92vw);background:#fff;z-index:1200;transform:translateX(-105%);transition:transform .4s cubic-bezier(.2,.8,.2,1);display:flex;flex-direction:column;box-shadow:20px 0 60px rgba(0,0,0,.2)}
.drawer.open{transform:translateX(0)}
.drawer-head{padding:22px 24px;border-bottom:1px solid #eee;display:flex;justify-content:space-between;align-items:center}
.drawer-head h3{font-size:20px}
.drawer-close{font-size:24px;color:var(--text-soft)}
.cart-items{flex:1;overflow-y:auto;padding:20px 24px}
.cart-item{display:flex;gap:14px;align-items:center;padding:14px 0;border-bottom:1px solid #f0f0f0}
.cart-item .ci-emoji{font-size:38px;width:56px;height:56px;background:var(--bg-soft);border-radius:14px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.ci-info{flex:1}
.ci-info h5{font-size:15px}
.ci-info .ci-price{color:var(--text-soft);font-size:13px}
.qty{display:flex;align-items:center;gap:10px}
.qty button{width:26px;height:26px;border:1px solid #d2d2d7;border-radius:50%;font-size:15px;display:flex;align-items:center;justify-content:center;transition:all .2s}
.qty button:hover{background:var(--text);color:#fff}
.ci-del{color:#ff375f;font-size:18px;transition:transform .2s}
.ci-del:hover{transform:scale(1.2)}
.empty-cart{text-align:center;padding:60px 20px;color:var(--text-soft)}
.empty-cart .big{font-size:60px;margin-bottom:16px}
.drawer-foot{padding:22px 24px;border-top:1px solid #eee}
.total-row{display:flex;justify-content:space-between;font-size:18px;font-weight:700;margin-bottom:16px}
.checkout-btn{width:100%;background:var(--accent);color:#fff;padding:15px;border-radius:14px;font-size:16px;font-weight:700;transition:all .2s}
.checkout-btn:hover{background:#000}
.checkout-btn:disabled{background:#d2d2d7;cursor:not-allowed}
/* ============ PRODUCT MODAL ============ */.modal{position:fixed;inset:0;z-index:1300;display:flex;align-items:center;justify-content:center;padding:20px;opacity:0;pointer-events:none;transition:opacity .3s}
.modal.open{opacity:1;pointer-events:auto}
.modal-bg{position:absolute;inset:0;background:rgba(0,0,0,.5);backdrop-filter:blur(6px)}
.modal-box{position:relative;background:#fff;border-radius:24px;max-width:640px;width:100%;max-height:88vh;overflow-y:auto;padding:40px;transform:scale(.92);transition:transform .35s}
.modal.open .modal-box{transform:scale(1)}
.modal-close{position:absolute;top:18px;left:18px;font-size:24px;color:var(--text-soft);width:36px;height:36px;border-radius:50%;background:var(--bg-soft);display:flex;align-items:center;justify-content:center}
.modal-emoji{font-size:100px;text-align:center;margin-bottom:20px}
.modal-box h2{text-align:center;font-size:28px;margin-bottom:8px}
.modal-box .m-price{text-align:center;font-size:26px;font-weight:800;color:var(--accent);margin-bottom:14px}
.modal-box .m-desc{color:var(--text-soft);text-align:center;line-height:1.8;margin-bottom:24px;font-size:15px}
.spec-list{background:var(--bg-soft);border-radius:14px;padding:18px 24px;margin-bottom:26px}
.spec-list li{display:flex;justify-content:space-between;padding:9px 0;font-size:14px;border-bottom:1px solid #e5e5ea;list-style:none}
.spec-list li:last-child{border:none}
.spec-list li b{font-weight:600}
/* ============ TOAST ============ */.toast{position:fixed;bottom:30px;right:50%;transform:translate(50%,100px);background:#1d1d1f;color:#fff;padding:14px 28px;border-radius:980px;font-size:14px;z-index:1400;transition:transform .4s cubic-bezier(.2,.8,.2,1);display:flex;align-items:center;gap:10px;box-shadow:0 10px 30px rgba(0,0,0,.3)}
.toast.show{transform:translate(50%,0)}
/* ============ FOOTER ============ */footer{background:#f5f5f7;padding:60px 20px 30px;border-top:1px solid #d2d2d7}
.footer-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(180px,1fr));gap:34px;max-width:var(--max);margin:0 auto 40px}
.footer-grid h5{font-size:14px;margin-bottom:14px}
.footer-grid a{display:block;color:var(--text-soft);font-size:13px;margin-bottom:9px;transition:color .2s}
.footer-grid a:hover{color:var(--text)}
.footer-bottom{text-align:center;color:var(--text-soft);font-size:12px;border-top:1px solid #d2d2d7;padding-top:22px;max-width:var(--max);margin:0 auto}
/* ============ CHECKOUT FORM ============ */.form-group{margin-bottom:16px}
.form-group label{display:block;font-size:13px;font-weight:600;margin-bottom:6px}
.form-group input{width:100%;padding:12px 16px;border:1px solid #d2d2d7;border-radius:12px;font-size:14px;font-family:inherit;outline:none;transition:border .2s}
.form-group input:focus{border-color:var(--accent)}
/* ============ RESPONSIVE ============ */
@media(max-width:768px){
  .nav-links{display:none}
  .hamburger{display:block}
  .nav-links.mobile-open{display:flex;position:fixed;top:52px;right:0;left:0;background:rgba(0,0,0,.95);flex-direction:column;padding:24px;gap:20px;z-index:998}
}
.reveal{opacity:0;transform:translateY(30px);transition:opacity .7s,transform .7s}
.reveal.visible{opacity:1;transform:translateY(0)}
</style>
<base target="_blank">
</head>
<body>

<!-- NAVBAR -->
<nav>
  <div class="nav-inner">
    <a href="#" class="logo"> <span style="font-weight:900;font-size:19px;background:linear-gradient(135deg,#7d7aff,#0071e3);-webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:transparent">ROM</span></a>
    <ul class="nav-links" id="navLinks">
      <li><a href="#home">الرئيسية</a></li>
      <li><a href="#products">المنتجات</a></li>
      <li><a href="#features">المميزات</a></li>
      <li><a href="#contact">تواصل</a></li>
    </ul>
    <div class="nav-icons">
      <button class="nav-icon" onclick="toggleSearch()" title="بحث">🔍</button>
      <button class="nav-icon" onclick="toggleCart(true)" title="السلة">🛒<span class="cart-badge" id="cartBadge">0</span></button>
      <button class="hamburger" onclick="document.getElementById('navLinks').classList.toggle('mobile-open')">☰</button>
    </div>
  </div>
</nav>
<div class="search-bar" id="searchBar">
  <input type="text" id="searchInput" placeholder="ابحث عن منتج..." oninput="renderProducts()">
</div>

<!-- HERO -->
<header class="hero" id="home">
  <h1>المستقبل بين يديك.</h1>
  <p>اكتشف أحدث الأجهزة والإلكترونيات بأفضل الأسعار. جودة عالمية، توصيل سريع، وضمان حقيقي.</p>
  <div class="hero-btns">
    <a href="#products" class="btn btn-primary">تسوق الآن</a>
    <a href="#features" class="btn btn-ghost">تعرف على المميزات</a>
  </div>
  <div class="hero-visual">🎧⌚💻</div>
</header>

<!-- PRODUCTS -->
<section id="products">
  <div class="container">
    <h2 class="section-title reveal">تسوق حسب الفئة</h2>
    <p class="section-sub reveal">اختر ما يناسبك من تشكيلتنا الواسعة</p>
    <div class="filters reveal" id="filters"></div>
    <div class="grid" id="productGrid"></div>
  </div>
</section>

<!-- FEATURES -->
<section id="features" class="band">
  <div class="container">
    <h2 class="section-title reveal">لماذا تختارنا؟</h2>
    <p class="section-sub reveal">نلتزم بتقديم أفضل تجربة تسوق</p>
    <div class="band-grid">
      <div class="band-card reveal"><div class="ic">🚚</div><h4>شحن سريع مجاني</h4><p>توصيل خلال 24-48 ساعة لجميع المدن دون رسوم إضافية.</p></div>
      <div class="band-card reveal"><div class="ic">🛡️</div><h4>ضمان سنتان</h4><p>ضمان شامل على جميع المنتجات مع إمكانية الاستبدال.</p></div>
      <div class="band-card reveal"><div class="ic">💳</div><h4>دفع آمن</h4><p>ادفع بأمان عبر مدى، Apple Pay، أو عند الاستلام.</p></div>
      <div class="band-card reveal"><div class="ic">🔄</div><h4>إرجاع مجاني</h4><p>غير راضٍ عن المنتج؟ أرجعه مجاناً خلال 30 يوماً.</p></div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer id="contact">
  <div class="footer-grid">
    <div>
      <h5 style="font-size:18px;font-weight:900;background:linear-gradient(135deg,#7d7aff,#0071e3);-webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:transparent">ROM</h5>
      <p style="color:var(--text-soft);font-size:13px;line-height:1.7;margin-bottom:10px">Real Orders More.<br>طلبات حقيقية، مبيعات أكثر.</p>
    </div>
    <div>
      <h5>تسوق</h5>
      <a href="#products">الهواتف الذكية</a><a href="#products">اللابتوبات</a><a href="#products">السماعات</a><a href="#products">الساعات</a>
    </div>
    <div>
      <h5>خدمة العملاء</h5>
      <a href="#">تتبع الطلب</a><a href="#">الشحن والتوصيل</a><a href="#">الإرجاع والاستبدال</a><a href="#">الأسئلة الشائعة</a>
    </div>
    <div>
      <h5>عن المتجر</h5>
      <a href="#">من نحن</a><a href="#">الوظائف</a><a href="#">الأخبار</a><a href="#">الاستدامة</a>
    </div>
    <div>
      <h5>تواصل معنا</h5>
      <a href="mailto:hello@techstore.com">hello@techstore.com</a>
      <a href="tel:+966500000000">+966 50 000 0000</a>
      <a href="#">الرياض، السعودية</a>
    </div>
  </div>
  <div class="footer-bottom"><b style="color:var(--text)">ROM</b> — Real Orders More.<br>© 2026 ROM. جميع الحقوق محفوظة. | صُنع بشغف 🖤</div>
</footer>

<!-- CART DRAWER -->
<div class="overlay" id="overlay" onclick="toggleCart(false)"></div>
<aside class="drawer" id="cartDrawer">
  <div class="drawer-head">
    <h3>🛍️ سلة التسوق</h3>
    <button class="drawer-close" onclick="toggleCart(false)">✕</button>
  </div>
  <div class="cart-items" id="cartItems"></div>
  <div class="drawer-foot">
    <div class="total-row"><span>الإجمالي</span><span id="cartTotal">0 ر.س</span></div>
    <button class="checkout-btn" id="checkoutBtn" onclick="openCheckout()">إتمام الشراء</button>
  </div>
</aside>

<!-- PRODUCT MODAL -->
<div class="modal" id="productModal">
  <div class="modal-bg" onclick="closeModal()"></div>
  <div class="modal-box" id="modalBox"></div>
</div>

<!-- TOAST -->
<div class="toast" id="toast">✅ تمت الإضافة إلى السلة</div>

<script>
/* ================= DATA ================= */
const PRODUCTS = [
  {id:1, name:"آيفون 17 برو ماكس", cat:"هواتف", price:5299, emoji:"📱", isNew:true, rating:5, desc:"شريحة A19 Pro، كاميرا 48MP، شاشة ProMotion 120Hz، وتصميم من التيتانيوم.", specs:{"الشاشة":"6.9 بوصة OLED","التخزين":"256GB","الكاميرا":"48MP ثلاثية","البطارية":"30 ساعة تشغيل"}},
  {id:2, name:"ماك بوك برو 16", cat:"لابتوبات", price:9499, emoji:"💻", isNew:true, rating:5, desc:"شريحة M5 Pro مع ذاكرة 36GB وشاشة Liquid Retina XDR مذهلة.", specs:{"المعالج":"M5 Pro","الذاكرة":"36GB","التخزين":"512GB SSD","البطارية":"22 ساعة"}},
  {id:3, name:"سماعات AirPods Max", cat:"سماعات", price:1999, emoji:"🎧", isNew:false, rating:4, desc:"إلغاء ضوضاء نشط، صوت فضائي، وبطارية تدوم حتى 20 ساعة.", specs:{"إلغاء الضوضاء":"نشط","البطارية":"20 ساعة","الاتصال":"Bluetooth 5.3","الوزن":"385 جم"}},
  {id:4, name:"ساعة Apple Watch Ultra 3", cat:"ساعات", price:3299, emoji:"⌚", isNew:true, rating:5, desc:"مصنوعة من التيتانيوم، مقاومة للماء حتى 100 متر، وبطارية 72 ساعة.", specs:{"المعالج":"S11","البطارية":"72 ساعة","المقاومة":"100 متر","GPS":"مزدوج التردد"}},
  {id:5, name:"آيباد برو 13 بوصة", cat:"هواتف", price:4599, emoji:"📲", isNew:false, rating:4, desc:"أنحف آيباد على الإطلاق مع شريحة M5 وشاشة Ultra Retina XDR.", specs:{"الشاشة":"13 بوصة XDR","المعالج":"M5","التخزين":"256GB","القلم":"مدعوم"}},
  {id:6, name:"سماعات AirPods Pro 3", cat:"سماعات", price:949, emoji:"🎵", isNew:false, rating:4, desc:"إلغاء ضوضاء مضاعف، وضع الشفافية التكيفية، وصوت مخصص.", specs:{"إلغاء الضوضاء":"2x أقوى","البطارية":"30 ساعة","الشحن":"MagSafe","الصندوق":"USB-C"}},
  {id:7, name:"آيفون 16", cat:"هواتف", price:3699, emoji:"📱", isNew:false, rating:5, desc:"التوازن المثالي بين الأداء والسعر مع شريحة A18.", specs:{"الشاشة":"6.1 بوصة","المعالج":"A18","الكاميرا":"48MP","البطارية":"27 ساعة"}},
  {id:8, name:"ماك بوك Air 15", cat:"لابتوبات", price:5899, emoji:"💻", isNew:false, rating:4, desc:"أخف وأنحف ماك بوك مع شريحة M4 وألوان مبهجة.", specs:{"المعالج":"M4","الذاكرة":"16GB","التخزين":"512GB","الوزن":"1.51 كجم"}},
  {id:9, name:"ساعة Apple Watch SE", cat:"ساعات", price:1249, emoji:"⌚", isNew:false, rating:4, desc:"ساعة ذكية مثالية للمبتدئين مع تتبع الصحة واللياقة.", specs:{"المعالج":"S9","البطارية":"18 ساعة","المقاومة":"50 متر","المقاسات":"40/44mm"}},
  {id:10, name:"سماعات Beats Studio Pro", cat:"سماعات", price:1349, emoji:"🎶", isNew:false, rating:4, desc:"صوت احترافي مع إلغاء ضوضاء وتشغيل 40 ساعة.", specs:{"البطارية":"40 ساعة","الشحن":"USB-C","الكودك":"Lossless","الألوان":"4 خيارات"}},
  {id:11, name:"آيباد ميني 7", cat:"هواتف", price:2099, emoji:"📲", isNew:true, rating:5, desc:"قوة A17 Pro بحجم الجيب، مثلي للقراءة والرسم.", specs:{"الشاشة":"8.3 بوصة","المعالج":"A17 Pro","القلم":"Apple Pencil Pro","الوزن":"297 جم"}},
  {id:12, name:"ماك ستوديو", cat:"لابتوبات", price:12499, emoji:"🖥️", isNew:true, rating:5, desc:"وحش الأداء الإبداعي مع شريحة M5 Ultra للمحترفين.", specs:{"المعالج":"M5 Ultra","الذاكرة":"96GB","التخزين":"1TB SSD","المنافذ":"12 منفذ"}},
];
const CATS = ["الكل","هواتف","لابتوبات","سماعات","ساعات"];

/* ================= STATE ================= */
let cart = JSON.parse(localStorage.getItem('cart')||'[]');
let activeCat = "الكل";

/* ================= RENDER ================= */
function renderFilters(){
  document.getElementById('filters').innerHTML = CATS.map(c=>
    `<button class="chip ${c===activeCat?'active':''}" onclick="setCat('${c}')">${c}</button>`).join('');
}
function setCat(c){ activeCat=c; renderFilters(); renderProducts(); }

function starStr(n){ return "★".repeat(n)+"☆".repeat(5-n); }

function renderProducts(){
  const q = (document.getElementById('searchInput').value||'').trim();
  const list = PRODUCTS.filter(p =>
    (activeCat==="الكل"||p.cat===activeCat) &&
    (!q || p.name.includes(q)||p.desc.includes(q)||p.cat.includes(q))
  );
  const grid = document.getElementById('productGrid');
  grid.innerHTML = list.length ? list.map(p=>`
    <div class="card reveal visible" onclick="openProduct(${p.id})">
      ${p.isNew?'<span class="new-badge">جديد</span>':''}
      <div class="emoji">${p.emoji}</div>
      <span class="cat-tag">${p.cat}</span>
      <h3>${p.name}</h3>
      <p>${p.desc}</p>
      <div class="stars">${starStr(p.rating)}</div>
      <div class="price">${p.price.toLocaleString()} <small>ر.س</small></div>
      <div class="actions">
        <button class="btn-add" onclick="event.stopPropagation();addToCart(${p.id})">أضف للسلة</button>
        <button class="btn-view" onclick="event.stopPropagation();openProduct(${p.id})">عرض</button>
      </div>
    </div>`).join('')
  : '<p style="grid-column:1/-1;text-align:center;color:#86868b;font-size:18px;padding:40px">لا توجد نتائج مطابقة 😕</p>';
}

/* ================= CART ================= */
function saveCart(){ localStorage.setItem('cart',JSON.stringify(cart)); updateCartUI(); }

function addToCart(id){
  const item = cart.find(i=>i.id===id);
  if(item) item.qty++;
  else { const p=PRODUCTS.find(x=>x.id===id); cart.push({...p,qty:1}); }
  saveCart(); showToast('✅ تمت الإضافة إلى السلة');
}

function changeQty(id,d){
  const item = cart.find(i=>i.id===id);
  if(!item) return;
  item.qty += d;
  if(item.qty<=0) cart = cart.filter(i=>i.id!==id);
  saveCart();
}

function removeItem(id){ cart = cart.filter(i=>i.id!==id); saveCart(); }

function updateCartUI(){
  const count = cart.reduce((s,i)=>s+i.qty,0);
  const badge = document.getElementById('cartBadge');
  badge.textContent = count; badge.classList.toggle('show', count>0);
  const box = document.getElementById('cartItems');
  if(!cart.length){
    box.innerHTML = `<div class="empty-cart"><div class="big">🛒</div><h4>سلتك فارغة</h4><p>ابدأ التسوق الآن واملأها بأفضل المنتجات</p></div>`;
  } else {
    box.innerHTML = cart.map(i=>`
      <div class="cart-item">
        <div class="ci-emoji">${i.emoji}</div>
        <div class="ci-info"><h5>${i.name}</h5><span class="ci-price">${i.price.toLocaleString()} ر.س</span></div>
        <div class="qty">
          <button onclick="changeQty(${i.id},1)">+</button><span>${i.qty}</span><button onclick="changeQty(${i.id},-1)">−</button>
        </div>
        <button class="ci-del" onclick="removeItem(${i.id})">🗑</button>
      </div>`).join('');
  }
  document.getElementById('cartTotal').textContent = cart.reduce((s,i)=>s+i.price*i.qty,0).toLocaleString()+' ر.س';
  document.getElementById('checkoutBtn').disabled = !cart.length;
}

function toggleCart(open){
  document.getElementById('cartDrawer').classList.toggle('open',open);
  document.getElementById('overlay').classList.toggle('open',open);
}

/* ================= SEARCH ================= */
function toggleSearch(){
  const bar = document.getElementById('searchBar');
  bar.style.display = bar.style.display==='block'?'none':'block';
  if(bar.style.display==='block') document.getElementById('searchInput').focus();
}

/* ================= MODAL ================= */
function openProduct(id){
  const p = PRODUCTS.find(x=>x.id===id);
  document.getElementById('modalBox').innerHTML = `
    <button class="modal-close" onclick="closeModal()">✕</button>
    <div class="modal-emoji">${p.emoji}</div>
    <h2>${p.name}</h2>
    <div class="m-price">${p.price.toLocaleString()} ر.س</div>
    <div class="stars" style="text-align:center;margin-bottom:18px">${starStr(p.rating)}</div>
    <p class="m-desc">${p.desc}</p>
    <ul class="spec-list">${Object.entries(p.specs).map(([k,v])=>`<li><span>${k}</span><b>${v}</b></li>`).join('')}</ul>
    <button class="btn btn-primary" style="width:100%;text-align:center" onclick="addToCart(${p.id})">أضف إلى السلة 🛒</button>`;
  document.getElementById('productModal').classList.add('open');
}
function closeModal(){ document.getElementById('productModal').classList.remove('open'); }

/* ================= CHECKOUT ================= */
function openCheckout(){
  if(!cart.length) return;
  const total = cart.reduce((s,i)=>s+i.price*i.qty,0);
  document.getElementById('modalBox').innerHTML = `
    <button class="modal-close" onclick="closeModal()">✕</button>
    <h2>🧾 إتمام الطلب</h2>
    <p class="m-desc">الإجمالي: <b style="color:var(--accent)">${total.toLocaleString()} ر.س</b> — شامل الشحن المجاني</p>
    <form onsubmit="placeOrder(event)">
      <div class="form-group"><label>الاسم الكامل</label><input required placeholder="محمد أحمد"></div>
      <div class="form-group"><label>رقم الجوال</label><input required placeholder="05xxxxxxxx" pattern="[0-9+]{9,}"></div>
      <div class="form-group"><label>المدينة</label><input required placeholder="الرياض"></div>
      <div class="form-group"><label>العنوان</label><input required placeholder="الحي، الشارع، رقم المبنى"></div>
      <button class="btn btn-primary" style="width:100%;text-align:center">تأكيد الطلب ✅</button>
    </form>`;
  document.getElementById('productModal').classList.add('open');
}

function placeOrder(e){
  e.preventDefault();
  const orderNo = Math.floor(100000+Math.random()*900000);
  cart = []; saveCart(); toggleCart(false); closeModal();
  document.getElementById('modalBox').innerHTML = `
    <button class="modal-close" onclick="closeModal()">✕</button>
    <div class="modal-emoji">🎉</div>
    <h2>تم استلام طلبك!</h2>
    <p class="m-desc">رقم الطلب: <b style="color:var(--accent)">#${orderNo}</b><br>سنتواصل معك قريباً لتأكيد التوصيل.</p>
    <button class="btn btn-primary" style="width:100%;text-align:center" onclick="closeModal()">متابعة التسوق</button>`;
  document.getElementById('productModal').classList.add('open');
}

/* ================= TOAST ================= */
let toastTimer;
function showToast(msg){
  const t = document.getElementById('toast');
  t.textContent = msg; t.classList.add('show');
  clearTimeout(toastTimer);
  toastTimer = setTimeout(()=>t.classList.remove('show'),2200);
}

/* ================= SCROLL ANIMATION ================= */
const obs = new IntersectionObserver(es=>es.forEach(e=>{
  if(e.isIntersecting) e.target.classList.add('visible');
}),{threshold:.12});
document.querySelectorAll('.reveal').forEach(el=>obs.observe(el));

/* close mobile menu on link click */
document.querySelectorAll('#navLinks a').forEach(a=>
  a.addEventListener('click',()=>document.getElementById('navLinks').classList.remove('mobile-open')));

/* ================= INIT ================= */
renderFilters(); renderProducts(); updateCartUI();
</script>
</body>
</html>
