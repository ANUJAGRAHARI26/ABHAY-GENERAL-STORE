# ABHAY-GENERAL-STORE
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>ABHAY GENERAL STORE</title>
  <style>
    :root{
      --bg:#0f172a; --card:#ffffff; --muted:#6b7280;
      --accent1:#ff7a18; --accent2:#ffb86b; --accent3:#7c3aed;
      --glass: rgba(255,255,255,0.06);
      --container:1200px;
      font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }
    *{box-sizing:border-box}
    body{margin:0; background: linear-gradient(135deg,var(--accent3) 0%, #3b82f6 50%, #06b6d4 100%); color:#0b1220;}
    .wrap{max-width:var(--container); margin:28px auto; padding:24px;}
    header{display:flex;align-items:center;gap:18px;margin-bottom:18px}
    .logo{width:92px;height:92px;border-radius:18px;background:linear-gradient(135deg,var(--accent1),var(--accent2));display:flex;align-items:center;justify-content:center;color:white;font-weight:800;font-size:18px;box-shadow:0 8px 30px rgba(0,0,0,0.25)}
    h1{margin:0;font-size:26px;color:white}
    .sub{color:rgba(255,255,255,0.9);opacity:0.95}

    main{display:grid;grid-template-columns:1fr 420px;gap:22px}
    @media(max-width:980px){main{grid-template-columns:1fr} .right{order:2}}

    .card{background:rgba(255,255,255,0.95);border-radius:14px;padding:18px;box-shadow:0 10px 30px rgba(11,17,32,0.12)}
    .products{display:grid;grid-template-columns:repeat(3,1fr);gap:12px;margin-top:12px}
    @media(max-width:700px){.products{grid-template-columns:repeat(2,1fr)}}
    .prod{background:var(--glass);padding:10px;border-radius:10px;text-align:center}
    .prod img{width:100%;height:100px;object-fit:cover;border-radius:8px}
    .prod h4{margin:8px 0 4px 0;font-size:15px}
    .price{font-weight:700;color:#0b1220}
    .btn{display:inline-flex;align-items:center;gap:10px;background:linear-gradient(90deg,var(--accent3),#10b981);color:white;padding:12px 14px;border-radius:10px;border:none;cursor:pointer;font-weight:700;margin-top:10px}
    .btn.secondary{background:transparent;border:2px solid rgba(11,17,32,0.06);color:var(--muted);font-weight:700}
    input,textarea{width:100%;padding:10px;border-radius:8px;border:1px solid #e6e9ef;margin-top:6px;font-size:14px}
    textarea{min-height:110px;resize:vertical}
    .map{height:250px;border-radius:12px;overflow:hidden;margin-top:12px}
    footer{margin-top:18px;color:white;opacity:0.9;text-align:center}
    .owner-panel{margin-top:16px}
    .contact-links{display:flex;flex-direction:column;gap:8px;margin-top:8px}
  </style>
</head>
<body>
  <div class="wrap">
    <header>
      <div class="logo">ABHAY<br/>STORE</div>
      <div>
        <h1>ABHAY GENERAL STORE</h1>
        <div class="sub">Grocery • Local delivery requests • Open 7 AM – 9 PM</div>
      </div>
    </header>

    <main>
      <section>
        <div class="card">
          <h3>Popular Items</h3>
          <div id="productList" class="products">
            <div class="prod"><img src="https://picsum.photos/seed/rice/400/300"/><h4>Rice (5kg)</h4><div class="price">₹240</div></div>
            <div class="prod"><img src="https://picsum.photos/seed/oil/400/300"/><h4>Cooking Oil (1L)</h4><div class="price">₹160</div></div>
            <div class="prod"><img src="https://picsum.photos/seed/sugar/400/300"/><h4>Sugar (1kg)</h4><div class="price">₹48</div></div>
          </div>
          <div class="owner-panel">
            <h4>For Owner: Add Product</h4>
            <input id="pname" placeholder="Product name"/>
            <input id="pprice" placeholder="Price (₹)"/>
            <input id="pimg" placeholder="Image URL (optional)"/>
            <button class="btn" onclick="addProduct()">Add Product</button>
          </div>
        </div>

        <div class="card" style="margin-top:16px">
          <h3>Location</h3>
          <div>ABHAY GENERAL STORE, near Old CHC Jagatpur, Jagatpur, Raebareli, Uttar Pradesh 229402</div>
          <div class="map">
            <iframe width="100%" height="100%" frameborder="0" style="border:0"
              src="https://www.google.com/maps/embed/v1/place?key=AIzaSyDUMMYKEY&q=Abhay+General+Store+Jagatpur+Raebareli+229402" allowfullscreen></iframe>
          </div>
          <a class="btn" style="margin-top:10px" target="_blank" href="https://www.google.com/maps/dir/?api=1&destination=Abhay+General+Store+Jagatpur+Raebareli+229402">Get Directions on Google Maps</a>
        </div>
      </section>

      <aside class="right">
        <div class="card">
          <h3>Place an Order</h3>
          <form onsubmit="return submitOrder(event)">
            <input id="cname" placeholder="Your Name" />
            <input id="cphone" placeholder="Phone Number (required)" required />
            <textarea id="citems" placeholder="Type items and quantity"></textarea>
            <button class="btn" type="submit">Send Order via WhatsApp</button>
          </form>
        </div>

        <div class="card" style="margin-top:12px">
          <h3>Contact</h3>
          <div class="contact-links">
            <a class="btn" href="https://wa.me/918957621043" target="_blank">Chat on WhatsApp</a>
            <a class="btn" href="tel:+918957621043">Call: 8957621043</a>
            <a class="btn" href="mailto:anujkumaragrahari2601@gmail.com">Email: anujkumara...@gmail.com</a>
          </div>
        </div>
      </aside>
    </main>

    <footer>Built for ABHAY GENERAL STORE — Jagatpur, Raebareli — Pincode 229402 • Open 7 AM – 9 PM</footer>
  </div>

  <script>
    const shopWhats = '918957621043';
    function submitOrder(e){
      e.preventDefault();
      const name = document.getElementById('cname').value.trim() || 'Customer';
      const phone = document.getElementById('cphone').value.trim();
      const items = document.getElementById('citems').value.trim() || '(no items)';
      if(!phone){alert('Phone number is required');return false;}
      const msg = `New order from ${name}%0APhone: ${phone}%0AItems: ${items}`;
      window.open(`https://wa.me/${shopWhats}?text=${msg}`,'_blank');
      return false;
    }

    function addProduct(){
      const name=document.getElementById('pname').value.trim();
      const price=document.getElementById('pprice').value.trim();
      const img=document.getElementById('pimg').value.trim()||'https://picsum.photos/seed/'+Math.random()+'/400/300';
      if(!name||!price){alert('Please enter product name and price');return;}
      const prod=document.createElement('div');
      prod.className='prod';
      prod.innerHTML=`<img src="${img}"/><h4>${name}</h4><div class="price">₹${price}</div>`;
      document.getElementById('productList').appendChild(prod);
      document.getElementById('pname').value='';document.getElementById('pprice').value='';document.getElementById('pimg').value='';
    }
  </script>
</body>
</html>
