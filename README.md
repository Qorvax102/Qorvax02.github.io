# Qorvax02.github.io
Qorvax - Online Shopping Website | A Cash on Delivery
<!DOCTYPE html>
<html lang="en"><head><meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Qorvax - Pakistan's Online Shopping Like Amazon</title>
<style>*{margin:0;padding:0;box-sizing:border-box;font-family:Arial,sans-serif}body{background:#eaeded}
header{background:#131921;color:#fff;padding:12px 18px;display:flex;gap:18px;align-items:center;flex-wrap:wrap;position:sticky;top:0;z-index:10}
.logo{font-size:30px;font-weight:900;color:#ff9900;cursor:pointer}.logo span{color:#fff}
.search{flex:1;display:flex;min-width:220px}.search input{flex:1;padding:12px;border:none;border-radius:4px 0 0 4px}.search button{background:#febd69;border:none;padding:12px 18px;border-radius:0 4px 4px 0;font-weight:bold;cursor:pointer}
.nav2{background:#232f3e;color:#fff;padding:9px 18px;display:flex;gap:16px;overflow:auto;font-size:14px}.nav2 a{color:#fff;text-decoration:none;white-space:nowrap}
.hero{background:linear-gradient(90deg,#ff9900,#ff6a00);color:#fff;padding:32px 18px;text-align:center}.hero h1{font-size:32px}
.filters{display:flex;gap:10px;padding:14px 18px;flex-wrap:wrap;justify-content:center}.filters button{padding:9px 16px;border:1px solid #ccc;background:#fff;border-radius:20px;cursor:pointer}.filters button.active{background:#131921;color:#fff}
.grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(230px,1fr));gap:16px;padding:0 18px 30px}
.card{background:#fff;border-radius:10px;overflow:hidden;border:1px solid #ddd}.card img{width:100%;height:180px;object-fit:cover}.card-body{padding:12px}.price{color:#B12704;font-weight:bold;font-size:20px}.old{color:#777;text-decoration:line-through;font-size:13px}.btn{background:#ffd814;border:none;width:100%;padding:10px;border-radius:20px;font-weight:bold;cursor:pointer;margin-top:8px}.btn2{background:#ff9900}
.drawer{position:fixed;right:0;top:0;bottom:0;width:360px;max-width:92vw;background:#fff;box-shadow:-5px 0 20px rgba(0,0,0,.3);padding:18px;display:none;z-index:20;overflow:auto}
.modal{position:fixed;inset:0;background:rgba(0,0,0,.6);display:none;align-items:center;justify-content:center;z-index:30}.modal>div{background:#fff;width:420px;max-width:92vw;padding:20px;border-radius:12px}.modal input,.modal select{width:100%;padding:11px;margin:6px 0;border:1px solid #ccc;border-radius:6px}
footer{background:#232f3e;color:#ddd;text-align:center;padding:22px}
</style></head><body>
<header><div class="logo" onclick="location.reload()">QOR<span>VAX</span></div>
<div class="search"><input id="q" placeholder="Search in Qorvax..."><button onclick="apply()">Search</button></div>
<div>Hello, Guest<br><b>Account & Lists</b></div><div>Returns<br><b>& Orders</b></div>
<div style="cursor:pointer" onclick="openCart()">🛒 Cart <b id="cartCount">0</b></div></header>
<div class="nav2"><a href="#" onclick="setCat('all')">☰ All</a><a href="#" onclick="setCat('mobile')">Mobiles</a><a href="#" onclick="setCat('fashion')">Fashion</a><a href="#" onclick="setCat('electronics')">Electronics</a><a href="#" onclick="setCat('watch')">Watches</a><a href="#" onclick="setCat('home')">Home</a><a href="#" onclick="setCat('beauty')">Beauty</a><a href="#" onclick="setCat('sports')">Sports</a><a href="#">Today's Deals</a></div>
<div class="hero"><h1>Welcome to Qorvax 🇵🇰</h1><p>Pakistan's Online Shopping Store - Like Amazon</p><p><b>Free Delivery on Orders Above Rs. 2000 | Cash on Delivery</b></p></div>
<div class="filters"><button class="active" onclick="setCat('all',this)">All</button><button onclick="setCat('mobile',this)">Mobiles</button><button onclick="setCat('fashion',this)">Fashion</button><button onclick="setCat('electronics',this)">Electronics</button><button onclick="setCat('watch',this)">Watches</button><button onclick="setCat('home',this)">Home</button><button onclick="setCat('beauty',this)">Beauty</button><button onclick="setCat('sports',this)">Sports</button></div>
<div class="grid" id="grid"></div>
<div class="drawer" id="drawer"><h2>Your Qorvax Cart 🛒</h2><div id="cartItems" style="margin:14px 0"></div><h3 id="total">Total: Rs. 0</h3><button class="btn" onclick="openCheckout()">Proceed to Checkout</button><button class="btn" style="background:#eee" onclick="closeCart()">Close</button></div>
<div class="modal" id="checkoutModal"><div><h2>Qorvax Checkout</h2><input id="cName" placeholder="Full Name"><input id="cPhone" placeholder="Phone - 03xx-xxxxxxx"><input id="cAddress" placeholder="Full Address"><select id="cCity"><option>Faisalabad</option><option>Lahore</option><option>Karachi</option><option>Islamabad</option><option>Rawalpindi</option><option>Multan</option></select><p><b>Payment: Cash on Delivery</b></p><button class="btn" onclick="placeOrder()">Place Order</button><button class="btn" style="background:#eee" onclick="document.getElementById('checkoutModal').style.display='none'">Cancel</button></div></div>
<footer><h3 style="color:#ff9900">QORVAX</h3><p>Made in Faisalabad, Pakistan | Cash on Delivery | 7 Days Return</p><p>© 2026 Qorvax. All Rights Reserved.</p></footer>
<script>
const P=[
{id:1,n:"Wireless Earbuds Pro - Bluetooth",c:"electronics",p:2499,o:3999,img:"https://images.unsplash.com/photo-1590658268037-6bf12165a8df?w=500"},
{id:2,n:"Smart Watch Ultra - Fitness Tracker",c:"watch",p:4999,o:7999,img:"https://images.unsplash.com/photo-1523275335684-37898b6baf30?w=500"},
{id:3,n:"Men's Sneakers - Running Shoes",c:"fashion",p:3499,o:5499,img:"https://images.unsplash.com/photo-1542291026-7eec264c27ff?w=500"},
{id:4,n:"Stylish Hoodie - Winter Collection",c:"fashion",p:1999,o:2999,img:"https://images.unsplash.com/photo-1556821840-3a63f95609a7?w=500"},
{id:5,n:"Wireless Headphones - Extra Bass",c:"electronics",p:3999,o:5999,img:"https://images.unsplash.com/photo-1505740420928-5e560c06d30e?w=500"},
{id:6,n:"Classic Watch - Leather Strap",c:"watch",p:2999,o:4599,img:"https://images.unsplash.com/photo-1524592094714-0f0654e20314?w=500"},
{id:7,n:"LED Lamp - Home Decor",c:"home",p:1499,o:2299,img:"https://images.unsplash.com/photo-1507473885765-e6ed057f782c?w=500"},
{id:8,n:"Backpack - School / Travel",c:"fashion",p:1799,o:2599,img:"https://images.unsplash.com/photo-1553062407-98eeb64c6a62?w=500"},
{id:9,n:"Smartphone - 128GB, 8GB RAM",c:"mobile",p:34999,o:44999,img:"https://images.unsplash.com/photo-1511707171634-5f897ff02aa9?w=500"},
{id:10,n:"Air Fryer - Healthy Cooking",c:"home",p:8999,o:12999,img:"https://images.unsplash.com/photo-1626074353765-517a681e40be?w=500"},
{id:11,n:"Sunglasses - UV Protection",c:"beauty",p:1299,o:1999,img:"https://images.unsplash.com/photo-1572635196237-14b3f281503f?w=500"},
{id:12,n:"Cricket Bat - Kashmir Willow",c:"sports",p:2999,o:3999,img:"https://images.unsplash.com/photo-1531415074968-036ba1b575da?w=500"},
];
let cur='all', cart=[];
function render(){let q=(document.getElementById('q').value||'').toLowerCase();let list=P.filter(x=>(cur==='all'||x.c===cur)&&x.n.toLowerCase().includes(q));document.getElementById('grid').innerHTML=list.map(x=>`<div class="card"><img src="${x.img}"><div class="card-body"><b>${x.n}</b><div>⭐⭐⭐⭐⭐ (1,245)</div><div class="price">Rs. ${x.p} <span class="old">Rs. ${x.o}</span></div><div style="color:green;font-size:13px">In Stock - Free Delivery</div><button class="btn" onclick="add(${x.id})">Add to Cart</button><button class="btn btn2" onclick="buy(${x.id})">Buy Now</button></div></div>`).join('');}
function setCat(c,el){cur=c;document.querySelectorAll('.filters button').forEach(b=>b.classList.remove('active'));if(el)el.classList.add('active');render();}
function apply(){render();}
function add(id){cart.push(P.find(x=>x.id===id));update();}
function buy(id){add(id);openCart();}
function update(){document.getElementById('cartCount').innerText=cart.length;let t=cart.reduce((s,x)=>s+x.p,0);document.getElementById('total').innerText='Total: Rs. '+t;document.getElementById('cartItems').innerHTML=cart.length?cart.map((x,i)=>`<div style="display:flex;justify-content:space-between;padding:8px 0;border-bottom:1px solid #eee"><span>${x.n}<br><b>Rs. ${x.p}</b></span><button onclick="removeItem(${i})">❌</button></div>`).join(''):'Cart khaali hai';}
function removeItem(i){cart.splice(i,1);update();}
function openCart(){update();document.getElementById('drawer').style.display='block';}
function closeCart(){document.getElementById('drawer').style.display='none';}
function openCheckout(){if(!cart.length){alert('Cart khaali hai!');return;}closeCart();document.getElementById('checkoutModal').style.display='flex';}
function placeOrder(){let n=document.getElementById('cName').value;if(!n){alert('Naam likho!');return;}alert('Shukriya '+n+'!\\nTumhara Qorvax Order Place Ho Gaya!\\nCash on Delivery - 2-3 din me pohanch jayega.');cart=[];update();document.getElementById('checkoutModal').style.display='none';}
render();
</script></body></html>
