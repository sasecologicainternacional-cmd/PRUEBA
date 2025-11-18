<!doctype html>

<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Mile Beauty — Sitio Oficial</title>
  <meta name="description" content="Tienda online de maquillaje: labiales, sombras, bases y accesorios." />  <style>
    :root{
      --accent:#644f70;
      --dark:#341d54ba;
      --muted:#09060f;
      --bg:#7b64ce4f;
      --card:#706085;
      --glass: rgba(182, 141, 141, 0.6);
      font-family: Inter, system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
    }
    *{box-sizing:border-box}
    body{margin:0; background:linear-gradient(180deg,var(--bg),#fff); color:var(--dark);}

   /* Header */
    header{display:flex;align-items:center;justify-content:space-between;padding:18px 28px;background:transparent}
    .brand{display:flex;gap:12px;align-items:center}
    .logo{width:48px;height:48px;border-radius:12px;background:linear-gradient(135deg,var(--accent),#8b77a5);display:flex;align-items:center;justify-content:center;color:white;font-weight:700;font-size:18px}
    nav{display:flex;gap:18px;align-items:center}
    a{color:var(--dark);text-decoration:none}
    .cta{background:var(--accent);color:white;padding:8px 14px;border-radius:10px;font-weight:600}

   /* Hero */
    .hero{display:flex;flex-wrap:wrap;gap:20px;align-items:center;padding:40px 28px}
    .hero-left{flex:1;min-width:260px}
    .hero h1{font-size:34px;margin:0 0 10px}
    .hero p{color:var(--muted);margin:0 0 18px}
    .search{display:flex;gap:8px}
    .search input{flex:1;padding:12px 14px;border-radius:12px;border:1px solid #e6e7eb}
    .search button{padding:12px 16px;border-radius:12px;border:0;background:var(--accent);color:white;font-weight:600}

   .hero-right{flex:1;min-width:260px;display:flex;justify-content:center}
    .promo-card{width:320px;border-radius:16px;box-shadow:0 8px 30px rgba(0,0,0,0.08);background:linear-gradient(180deg,rgba(255,255,255,0.8),var(--card));padding:18px}
    .promo-card img{width:100%;border-radius:12px}

  /* Products grid */
    .section{padding:22px 28px}
    .section h2{margin:0 0 14px}
    .grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(180px,1fr));gap:16px}
    .card{background:var(--card);padding:12px;border-radius:12px;box-shadow:0 6px 18px rgba(15,23,42,0.04);display:flex;flex-direction:column;gap:10px}
    .card img{width:100%;height:140px;object-fit:cover;border-radius:10px}
    .card h3{margin:0;font-size:16px}
    .price{font-weight:700}
    .small{font-size:13px;color:var(--muted)}
    .actions{display:flex;gap:8px;margin-top:auto}
    .btn{padding:8px 10px;border-radius:10px;border:1px solid #e6e7eb;background:transparent;cursor:pointer}
    .btn-primary{background:var(--accent);color:white;border:0}

   /* Filters */
    .filters{display:flex;gap:10px;flex-wrap:wrap;margin-bottom:12px}
    .chip{padding:8px 12px;border-radius:999px;border:1px solid #eee;background:white;cursor:pointer}

   /* Footer */
    footer{padding:28px;border-top:1px solid #f1f2f4;margin-top:28px;color:var(--muted)}

   /* Modal */
    .modal{position:fixed;inset:0;display:none;align-items:center;justify-content:center;background:rgba(0,0,0,0.35)}
    .modal.open{display:flex}
    .modal-card{width:min(900px,96%);background:var(--card);border-radius:12px;padding:18px;display:grid;grid-template-columns:1fr 1fr;gap:12px}

   /* Responsive */
    @media (max-width:720px){
      .hero{flex-direction:column}
      .modal-card{grid-template-columns:1fr}
      header{padding:12px}
    }
  </style></head>
<body>
  <header>
    <div class="brand">
      <div class="logo">MB</div>
      <div>
        <div style="font-weight:700">Mile Beauty</div>
        <div style="font-size:12px;color:var(--muted)">Productos - Inspiración - Tutoriales</div>
      </div>
    </div>
    <nav>
      <a href="#productos">Productos</a>
      <a href="#novedades">Novedades</a>
      <a href="#contacto">Contacto</a>
      <a class="cta" href="#">Carrito (0)</a>
    </nav>
  </header>  <main>
    <section class="hero">
      <div class="hero-left">
        <h1>Tu tienda de maquillaje online</h1>
        <p>Encuentra labiales, sombras, bases y herramientas seleccionadas por profesionales. Envíos a todo el país y devoluciones en 15 días.</p><div class="search" role="search">
      <input id="searchInput" placeholder="Buscar producto, marca o tono..." />
      <button onclick="searchProducts()">Buscar</button>
    </div>

  <div style="margin-top:16px">
      <div class="filters">
        <div class="chip" onclick="filter('Labios')">Labios</div>
        <div class="chip" onclick="filter('Ojos')">Ojos</div>
        <div class="chip" onclick="filter('Rostro')">Rostro</div>
        <div class="chip" onclick="filter('Pinceles')">Pinceles</div>
        <div class="chip" onclick="filter('Ofertas')">Ofertas</div>
        <div class="chip" onclick="filter('Rubores')">Rubores</div>
        <div class="chip" onclick="filter('Polvos')">Polvos</div>
      </div>
    </div>
  </div>

  <div class="hero-right">
    <div class="promo-card">
      <img src="promocion.jpg" alt="Promo" />
      <h3 style="margin:10px 0 6px">Colección Primavera — 20% off</h3>
      <p class="small">Tonos cálidos seleccionados. Promoción válida hasta fin de stock.</p>
      <div style="display:flex;gap:8px;margin-top:12px">
        <button class="btn btn-primary" onclick="openModal(1)">Ver colección</button>
        <button class="btn">Suscribirme</button>
      </div>
    </div>
  </div>
</section>

<section id="productos" class="section">
  <h2>Productos destacados</h2>
  <div class="grid" id="productsGrid">
    <!-- Product cards rendered by JS -->
  </div>
</section>

<section id="novedades" class="section">
  <h2>Novedades</h2>
  <div style="display:flex;gap:12px;overflow:auto;padding-bottom:6px">
    <div style="min-width:20px;background:linear-gradient(180deg,#fff,#fff);padding:12px;border-radius:12px;box-shadow:0 6px 12px rgba(0,0,0,0.04)">
      <img src="paleta.jpg" style="width:80%;border-radius:8px" />
      <h3 style="margin:2px 0 2px">Paleta Nars</h3>
      <p class="small">Tonos Marrones y Satinados</p>
    </div>
    <div style="min-width:20px;background:linear-gradient(180deg,#fff,#fff);padding:12px;border-radius:12px;box-shadow:0 6px 12px rgba(0,0,0,0.04)">
      <img src="base.jpg" style="width:50%;border-radius:2px"/>
      <h3 style="margin:1px 0 1px">Corrector Elf efecto Glow</h3>
      <p class="small">Acabado natural y cobertura modulable.</p>
    </div>
  </div>
</section>

<section id="contacto" class="section">
  <h2>Contacto</h2>
  <form onsubmit="event.preventDefault();enviarContacto();" style="max-width:720px;display:grid;grid-template-columns:1fr 1fr;gap:12px">
    <input name="nombre" placeholder="Nombre" required style="padding:10px;border-radius:8px;border:1px solid #e6e7eb" />
    <input name="email" placeholder="Email" required style="padding:10px;border-radius:8px;border:1px solid #e6e7eb" />
    <input name="asunto" placeholder="Asunto" style="padding:10px;border-radius:8px;border:1px solid #e6e7eb" />
    <textarea name="mensaje" placeholder="Tu mensaje" style="padding:10px;border-radius:8px;border:1px solid #e6e7eb;grid-column:1/3" rows="4"></textarea>
    <button class="btn btn-primary" type="submit">Enviar</button>
  </form>
</section>

  </main>  <footer>
    <div style="display:flex;justify-content:space-between;align-items:center;gap:12px;flex-wrap:wrap">
      <div>
        <strong>Mile Beauty</strong>
        <div class="small">© "Mile Beauty" — Todos los derechos reservados</div>
      </div>
      <div class="small">Soporte: hola@tiendabelleza.com · Envíos en 48-72h</div>
    </div>
  </footer>  <!-- Modal -->  <div id="modal" class="modal" role="dialog" aria-hidden="true">
    <div class="modal-card" role="document">
      <div style="padding:8px">
        <img id="modalImg" src="https://via.placeholder.com/640x480.png?text=Producto" style="width:100%;border-radius:8px" />
      </div>
      <div style="padding:8px;display:flex;flex-direction:column">
        <h3 id="modalTitle">Producto</h3>
        <div id="modalDesc" class="small">Descripción del producto.</div>
        <div style="margin-top:12px;font-size:18px" id="modalPrice">$0</div>
        <div style="margin-top:14px;display:flex;gap:8px">
          <button class="btn btn-primary" onclick="addToCart()">Añadir al carrito</button>
          <button class="btn" onclick="closeModal()">Cerrar</button>
        </div>
        <div style="margin-top:auto;font-size:13px;color:var(--muted)">Envío gratis a partir de $5.000</div>
      </div>
    </div>
  </div>  <script>
    // Datos de ejemplo (puedes reemplazarlos por lo que quieras)
    const PRODUCTS = [
      {id:1,name:'Labial Mate - Italia Deluxe',category:'Labios',price:2000,img:'labial matte.jpg',desc:'Labial mate de larga duración,Tono Terracota.'},
      {id:2,name:'Paleta Sombras Nars',category:'Ojos',price:4200,img:'paleta.jpg',desc:'12 Tonos mate y satinados.'},
      {id:3,name:'Base Dior - 30ml',category:'Rostro',price:3500,img:'base dior.jpg',desc:'Acabado natural, cobertura media.'},
      {id:4,name:'Set Pinceles x10',category:'Pinceles',price:4800,img:'set brochas.jpg',desc:'Pinceles profesionales para rostro y ojos.'},
      {id:5,name:'Lip Oil Dior ',category:'Labios',price:900,img:'gloss.jpg',desc:'Lip Oil Dior,Tono Pink.'},
      {id:6,name:'Corrector Líquido',category:'Rostro',price:1800,img:'base.jpg',desc:'Cobertura alta y textura ligera.'},
      {id:7,name:'Set x4 Esponjas',category:'Pinceles',price:1500,img:'esponjas.jpg',desc:' Esponjas Para base.'},
      {id:8,name:'Rubor Liquido Nars',category:'Rubores',price:3500,img:'rubor2.jpg',desc:'Rubor en crema, tono Coral.'},
      {id:9,name:'Polvo Volatil Nars',category:'Polvos',price:2500,img:'polvo nars.jpg',desc:'Polvo Traslucido Volatil Nars.'},
      {id:10,name:'Polvo Compacto Mac',category:'Polvos',price:2300,img:'compacto.jpg',desc:'Polvo Compacto Mac Medium.'},
      {id:11,name:'Rubor Compacto Bissu',category:'Rubores',price:2300,img:'bissu.jpg',desc:'Rubor Compacto Bissu,Tono DUrazno.'},
      {id:12,name:'Lip Oil Bissu',category:'Labios',price:1800,img:'lip oil.jpg',desc:'Lip Oil Bissu,Tono Frutos del Bosque.'},
      {id:13,name:'Paleta Sombras Revolution',category:'Ojos',price:4200,img:'revolution.jpg',desc:'32 Tonos Calidos.'},
     ];

  const grid = document.getElementById('productsGrid');
    const modal = document.getElementById('modal');
    const modalImg = document.getElementById('modalImg');
    const modalTitle = document.getElementById('modalTitle');
    const modalDesc = document.getElementById('modalDesc');
    const modalPrice = document.getElementById('modalPrice');
    let cartCount = 0;

  function renderProducts(list = PRODUCTS){
      grid.innerHTML = '';
      list.forEach(p=>{
        const card = document.createElement('article');
        card.className = 'card';
    card.innerHTML = `\n         
    <img src="${p.img}" alt="${p.name}" />\n          
    <h3>${p.name}</h3>\n          
    <div class="small">${p.category}</div>\n          
    <div class="price">$${p.price.toLocaleString()}</div>\n          
    <div class="actions">\n           
    <button class="btn" onclick="openModal(${p.id})">Ver</button>\n           
    <button class="btn btn-primary" onclick="addToCart(${p.id})">Comprar</button>\n       
    </div>\n        `;
        grid.appendChild(card);
      })
    }

  function openModal(id){
      const p = PRODUCTS.find(x=>x.id===id) || PRODUCTS[0];
      modalImg.src = p.img;
      modalTitle.textContent = p.name;
      modalDesc.textContent = p.desc;
      modalPrice.textContent = `$${p.price.toLocaleString()}`;
      modal.classList.add('open');
      modal.setAttribute('aria-hidden','false');
    }
    function closeModal(){
      modal.classList.remove('open');
      modal.setAttribute('aria-hidden','true');
    }

  function addToCart(id){
      // Si id no dado, se añade el primer producto (ejemplo)
      if(id) console.log('Añadido al carrito: ', id);
      cartCount++;
      document.querySelector('.cta').textContent = `Carrito (${cartCount})`;
      alert('Producto añadido al carrito (ejemplo).');
    }

  function filter(cat){
      const filtered = PRODUCTS.filter(p=>p.category === cat);
      if(filtered.length) renderProducts(filtered);
      else renderProducts(PRODUCTS);
    }

  function searchProducts(){
      const q = document.getElementById('searchInput').value.trim().toLowerCase();
      if(!q){renderProducts();return}
      const results = PRODUCTS.filter(p=> (p.name+ ' '+p.category+' '+p.desc).toLowerCase().includes(q));
      renderProducts(results);
    }

   function enviarContacto(){
      alert('Mensaje enviado. Gracias — (ejemplo)');
    }

  // Cerrar modal al hacer click fuera
    modal.addEventListener('click', (e)=>{ if(e.target===modal) closeModal(); });

   // Renderizar al inicio
    renderProducts();
  </script></body>
</html>
