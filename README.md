<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>ÉLÉGANCE - Pakistani Fashion Store</title>

<style>
*{
 margin:0;
 padding:0;
 box-sizing:border-box;
}

body{
 font-family:Arial,sans-serif;
 color:#263238;
 background:
 linear-gradient(135deg,
 #fff1e6,
 #dff8f5,
 #e9e1ff,
 #fff0f6,
 #eaf7ff);
 min-height:100vh;
}

header{
 position:sticky;
 top:0;
 z-index:1000;
 display:flex;
 justify-content:space-between;
 align-items:center;
 flex-wrap:wrap;
 gap:10px;
 padding:15px 5%;
 background:rgba(255,255,255,.96);
 box-shadow:0 4px 20px rgba(0,0,0,.08);
}

.logo{
 font-family:Georgia,serif;
 font-size:28px;
 letter-spacing:3px;
}

.logo span{
 color:#b78350;
}

nav button{
 border:0;
 background:none;
 padding:9px 10px;
 font-weight:bold;
 cursor:pointer;
}

.cart{
 border:0;
 background:#263238;
 color:white;
 padding:11px 18px;
 border-radius:25px;
 cursor:pointer;
}

.hero{
 text-align:center;
 padding:70px 5%;
}

.hero h1{
 font-family:Georgia,serif;
 font-size:clamp(42px,7vw,72px);
 margin-bottom:18px;
}

.hero p{
 max-width:800px;
 margin:auto;
 color:#637179;
 line-height:1.8;
 font-size:18px;
}

.shopTools{
 display:flex;
 justify-content:center;
 flex-wrap:wrap;
 gap:10px;
 padding:10px 5% 35px;
}

.search{
 display:flex;
 width:500px;
 max-width:100%;
}

.search input{
 flex:1;
 padding:14px;
 border:1px solid #ddd;
 border-radius:10px 0 0 10px;
}

.search button{
 border:0;
 padding:0 20px;
 background:#263238;
 color:white;
 border-radius:0 10px 10px 0;
 cursor:pointer;
 font-size:18px;
}

select{
 padding:13px;
 border:1px solid #ddd;
 border-radius:10px;
 background:white;
}

.products{
 max-width:1450px;
 margin:auto;
 padding:0 5% 70px;
 display:grid;
 grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
 gap:22px;
}

.card{
 background:white;
 border-radius:20px;
 overflow:hidden;
 box-shadow:0 10px 30px rgba(30,40,50,.12);
 transition:.25s;
}

.card:hover{
 transform:translateY(-6px);
}

.photo{
 width:100%;
 height:300px;
 overflow:hidden;
 background:#eee;
}

.photo img{
 width:100%;
 height:100%;
 object-fit:cover;
 display:block;
}

.info{
 padding:16px;
}

.badge{
 display:inline-block;
 background:#b78350;
 color:white;
 padding:5px 9px;
 border-radius:20px;
 font-size:11px;
}

.info h3{
 margin:10px 0 5px;
 font-size:17px;
}

.category{
 color:#758188;
 font-size:13px;
}

.price{
 margin-top:12px;
 font-size:21px;
 font-weight:bold;
}

.old{
 color:#999;
 text-decoration:line-through;
 font-size:14px;
 margin-left:6px;
}

.purchase{
 width:100%;
 margin-top:13px;
 padding:12px;
 border:0;
 border-radius:10px;
 background:#263238;
 color:white;
 cursor:pointer;
 font-weight:bold;
}

.purchase:hover{
 background:#b78350;
}

.section{
 max-width:1200px;
 margin:25px auto;
 padding:50px 7%;
 text-align:center;
 background:rgba(255,255,255,.82);
 border-radius:25px;
}

.section h2{
 font-family:Georgia,serif;
 font-size:35px;
 margin-bottom:15px;
}

.section p{
 color:#637179;
 line-height:1.8;
}

.form{
 max-width:650px;
 margin:25px auto;
 display:grid;
 gap:12px;
}

.form input,
.form textarea,
.form select{
 width:100%;
 padding:13px;
 border:1px solid #ddd;
 border-radius:10px;
}

footer{
 margin-top:50px;
 padding:35px;
 text-align:center;
 background:rgba(255,255,255,.8);
 color:#68757b;
}

@media(max-width:600px){

 .products{
  grid-template-columns:repeat(2,1fr);
  gap:12px;
 }

 .photo{
  height:235px;
 }

 .info{
  padding:11px;
 }

 .info h3{
  font-size:14px;
 }

 .price{
  font-size:17px;
 }
}
</style>
</head>

<body>

<header>

<div class="logo">
ÉLÉ<span>GANCE</span>
</div>

<nav>
<button onclick="shop()">Shop</button>
<button onclick="about()">About Us</button>
<button onclick="delivery()">Home Delivery</button>
<button onclick="contact()">Contact</button>
</nav>

<button class="cart">
🛒 Cart (<span id="cartCount">0</span>)
</button>

</header>


<section class="hero">

<h1>Pakistani Fashion Collection</h1>

<p>
Modern Pakistani fashion for the new generation.
Lawn, embroidered suits, silk, velvet,
co-ords, western wear, shalwar kameez,
formal and party collections.
</p>

</section>


<div class="shopTools">

<div class="search">

<input
id="search"
placeholder="Search Lawn, Kurta, Silk, Eid..."
>

<button onclick="searchProducts()">🔍</button>

</div>

<select id="category" onchange="searchProducts()">

<option value="all">All Clothing</option>

<option value="Women">Women</option>
<option value="Men">Men</option>

<option value="Lawn">Lawn</option>
<option value="3 Piece">3 Piece</option>
<option value="2 Piece">2 Piece</option>
<option value="Co-Ord">Co-Ord</option>
<option value="Silk">Silk</option>
<option value="Velvet">Velvet</option>
<option value="Formal">Formal</option>
<option value="Party Wear">Party Wear</option>
<option value="Eid">Eid Collection</option>
<option value="Kurta">Kurta</option>
<option value="Shalwar Kameez">Shalwar Kameez</option>
<option value="Western">Western</option>

</select>

</div>


<div class="products" id="products"></div>


<section class="section" id="about">

<h2>About ÉLÉGANCE</h2>

<p>
ÉLÉGANCE is a modern Pakistani fashion store
bringing traditional Pakistani clothing together
with new-generation styles.

Our collection includes Lawn, Silk, Velvet,
3-Piece suits, Co-Ord sets, Kurta Shalwar,
Party Wear, Eid Wear and modern Western fashion.
</p>

</section>


<section class="section" id="delivery">

<h2>🏠 Home Delivery</h2>

<p>
Enter your details and our store will deliver
your selected clothing to your address.
</p>

<div class="form">

<input placeholder="Full Name">

<input placeholder="Phone Number">

<input type="email" placeholder="Email Address">

<input placeholder="City">

<textarea rows="4"
placeholder="Complete Delivery Address"></textarea>

<select>

<option>Home Delivery</option>
<option>Express Delivery</option>
<option>Same Day Delivery</option>

</select>

<button
class="purchase"
onclick="orderNow()">

🚚 Place Home Delivery Order

</button>

</div>

</section>


<section class="section" id="contact">

<h2>Contact Us</h2>

<p>
For orders, products and delivery information,
please contact our store.
</p>

<div class="form">

<input placeholder="Your Name">

<input placeholder="Phone Number">

<textarea rows="4"
placeholder="Your Message"></textarea>

<button
class="purchase"
onclick="sendMessage()">

Send Message

</button>

</div>

</section>


<footer>

© 2026 ÉLÉGANCE Pakistani Fashion Store

<br><br>

Lawn • Silk • Velvet • 3 Piece • Co-Ord •
Kurta • Shalwar Kameez • Eid • Party Wear

</footer>


<script>

/* =========================================
   48 MODERN PAKISTANI FASHION PRODUCTS
========================================= */

const products=[

/* WOMEN LAWN */

{
name:"Mint Pastel Embroidered Lawn 3 Piece",
cat:"3 Piece",
gender:"Women",
type:"Lawn",
price:9990,
sale:7990,
image:"https://images.unsplash.com/photo-1594633312681-425c7b97ccd1?auto=format&fit=crop&w=700&q=85"
},

{
name:"Lavender Floral Lawn 3 Piece",
cat:"3 Piece",
gender:"Women",
type:"Lawn",
price:8990,
sale:6990,
image:"https://images.unsplash.com/photo-1539008835657-9e8e9680c956?auto=format&fit=crop&w=700&q=85"
},

{
name:"Ivory Embroidered Lawn Suit",
cat:"Lawn",
gender:"Women",
type:"Lawn",
price:10990,
sale:8490,
image:"https://images.unsplash.com/photo-1581044777550-4cfa60707c03?auto=format&fit=crop&w=700&q=85"
},

{
name:"Dusty Pink Printed Lawn",
cat:"2 Piece",
gender:"Women",
type:"Lawn",
price:6990,
sale:5490,
image:"https://images.unsplash.com/photo-1566174053879-31528523f8ae?auto=format&fit=crop&w=700&q=85"
},

{
name:"Sage Green Lawn Collection",
cat:"3 Piece",
gender:"Women",
type:"Lawn",
price:9490,
sale:7490,
image:"https://images.unsplash.com/photo-1595777457583-95e059d581b8?auto=format&fit=crop&w=700&q=85"
},

{
name:"Peach Floral Lawn Suit",
cat:"3 Piece",
gender:"Women",
type:"Lawn",
price:8990,
sale:6790,
image:"https://images.unsplash.com/photo-1541101767792-f9b2b1c4f127?auto=format&fit=crop&w=700&q=85"
},

/* WOMEN MODERN */

{
name:"Modern Wide Leg Co-Ord Set",
cat:"Co-Ord",
gender:"Women",
type:"Western",
price:12990,
sale:9990,
image:"https://images.unsplash.com/photo-1594633312681-425c7b97ccd1?auto=format&fit=crop&w=700&q=85"
},

{
name:"Minimal Cream Co-Ord Outfit",
cat:"Co-Ord",
gender:"Women",
type:"Western",
price:11990,
sale:8990,
image:"https://images.unsplash.com/photo-1515886657613-9f3515b0c78f?auto=format&fit=crop&w=700&q=85"
},

{
name:"Oversized Blazer Women",
cat:"Western",
gender:"Women",
type:"Western",
price:14990,
sale:11990,
image:"https://images.unsplash.com/photo-1551488831-00ddcb6c6bd3?auto=format&fit=crop&w=700&q=85"
},

{
name:"Modern Black Wide Leg Set",
cat:"Western",
gender:"Women",
type:"Western",
price:13990,
sale:10990,
image:"https://images.unsplash.com/photo-1496747611176-843222e1e57c?auto=format&fit=crop&w=700&q=85"
},

/* WOMEN SILK / FORMAL */

{
name:"Luxury Silk Evening Suit",
cat:"Silk",
gender:"Women",
type:"Silk",
price:18990,
sale:14990,
image:"https://images.unsplash.com/photo-1539008835657-9e8e9680c956?auto=format&fit=crop&w=700&q=85"
},

{
name:"Champagne Silk Party Dress",
cat:"Party Wear",
gender:"Women",
type:"Silk",
price:21990,
sale:17990,
image:"https://images.unsplash.com/photo-1595777457583-95e059d581b8?auto=format&fit=crop&w=700&q=85"
},

{
name:"Emerald Velvet Formal Dress",
cat:"Velvet",
gender:"Women",
type:"Formal",
price:23990,
sale:18990,
image:"https://images.unsplash.com/photo-1585488435739-6c1e3a4f8f5e?auto=format&fit=crop&w=700&q=85"
},

{
name:"Royal Navy Velvet Suit",
cat:"Velvet",
gender:"Women",
type:"Formal",
price:22990,
sale:17990,
image:"https://images.unsplash.com/photo-1591369822096-ffd140ec948f?auto=format&fit=crop&w=700&q=85"
},

{
name:"Organza Embroidered Formal",
cat:"Formal",
gender:"Women",
type:"Formal",
price:25990,
sale:20990,
image:"https://images.unsplash.com/photo-1566174053879-31528523f8ae?auto=format&fit=crop&w=700&q=85"
},

{
name:"Mirror Work Festive Suit",
cat:"Eid",
gender:"Women",
type:"Party Wear",
price:19990,
sale:15990,
image:"https://images.unsplash.com/photo-1594633312681-425c7b97ccd1?auto=format&fit=crop&w=700&q=85"
},

/* ANARKALI / SHARARA / MAXI */

{
name:"Modern Anarkali Frock",
cat:"Party Wear",
gender:"Women",
type:"Formal",
price:18990,
sale:14990,
image:"https://images.unsplash.com/photo-1566174053879-31528523f8ae?auto=format&fit=crop&w=700&q=85"
},

{
name:"Pastel Sharara Set",
cat:"Eid",
gender:"Women",
type:"Party Wear",
price:21990,
sale:16990,
image:"https://images.unsplash.com/photo-1539008835657-9e8e9680c956?auto=format&fit=crop&w=700&q=85"
},

{
name:"Royal Farshi Shalwar Suit",
cat:"Eid",
gender:"Women",
type:"Formal",
price:24990,
sale:19990,
image:"https://images.unsplash.com/photo-1595777457583-95e059d581b8?auto=format&fit=crop&w=700&q=85"
},

{
name:"Flowy Kaftan Maxi",
cat:"Party Wear",
gender:"Women",
type:"Western",
price:17990,
sale:13990,
image:"https://images.unsplash.com/photo-1515886657613-9f3515b0c78f?auto=format&fit=crop&w=700&q=85"
},

{
name:"Asymmetric Modern Kurti",
cat:"Western",
gender:"Women",
type:"Western",
price:8990,
sale:6990,
image:"https://images.unsplash.com/photo-1485968579580-b6d095142e6e?auto=format&fit=crop&w=700&q=85"
},

{
name:"Long Modest Everyday Kurti",
cat:"Women",
gender:"Women",
type:"Western",
price:6990,
sale:4990,
image:"https://images.unsplash.com/photo-1490481651871-ab68de25d43d?auto=format&fit=crop&w=700&q=85"
},

/* MEN */

{
name:"Classic White Shalwar Kameez",
cat:"Shalwar Kameez",
gender:"Men",
type:"Men",
price:7990,
sale:5990,
image:"https://images.unsplash.com/photo-1610652492500-ded49ceeb378?auto=format&fit=crop&w=700&q=85"
},

{
name:"Premium Black Shalwar Kameez",
cat:"Shalwar Kameez",
gender:"Men",
type:"Men",
price:8990,
sale:6990,
image:"https://images.unsplash.com/photo-1617127365659-c47fa864d8bc?auto=format&fit=crop&w=700&q=85"
},

{
name:"Linen Kurta Pajama",
cat:"Kurta",
gender:"Men",
type:"Men",
price:6990,
sale:5490,
image:"https://images.unsplash.com/photo-1598808503746-f34c53b9323e?auto=format&fit=crop&w=700&q=85"
},

{
name:"Premium Silk Kurta",
cat:"Silk",
gender:"Men",
type:"Silk",
price:9990,
sale:7490,
image:"https://images.unsplash.com/photo-1610652492500-ded49ceeb378?auto=format&fit=crop&w=700&q=85"
},

{
name:"Eid White Kurta",
cat:"Eid",
gender:"Men",
type:"Men",
price:7990,
sale:5990,
image:"https://images.unsplash.com/photo-1594938298603-c8148c4dae35?auto=format&fit=crop&w=700&q=85"
},

{
name:"Designer Navy Kurta",
cat:"Kurta",
gender:"Men",
type:"Men",
price:8990,
sale:6990,
image:"https://images.unsplash.com/photo-1598808503746-f34c53b9323e?auto=format&fit=crop&w=700&q=85"
},

{
name:"Kurta With Embroidered Waistcoat",
cat:"Eid",
gender:"Men",
type:"Formal",
price:13990,
sale:10990,
image:"https://images.unsplash.com/photo-1555069519-127aadedf1ee?auto=format&fit=crop&w=700&q=85"
},

{
name:"Royal Black Waistcoat Set",
cat:"Formal",
gender:"Men",
type:"Formal",
price:14990,
sale:11990,
image:"https://images.unsplash.com/photo-1507679799987-c73779587ccf?auto=format&fit=crop&w=700&q=85"
},

{
name:"Modern Three Piece Suit",
cat:"3 Piece",
gender:"Men",
type:"Formal",
price:24990,
sale:19990,
image:"https://images.unsplash.com/photo-1507679799987-c73779587ccf?auto=format&fit=crop&w=700&q=85"
},

{
name:"Luxury Four Piece Suit",
cat:"4 Piece",
gender:"Men",
type:"Formal",
price:29990,
sale:23990,
image:"https://images.unsplash.com/photo-1594938298603-c8148c4dae35?auto=format&fit=crop&w=700&q=85"
},

{
name:"Italian Style Navy Suit",
cat:"Formal",
gender:"Men",
type:"Formal",
price:27990,
sale:21990,
image:"https://images.unsplash.com/photo-1555069519-127aadedf1ee?auto=format&fit=crop&w=700&q=85"
},

{
name:"Modern Slim Fit Suit",
cat:"Formal",
gender:"Men",
type:"Formal",
price:25990,
sale:19990,
image:"https://images.unsplash.com/photo-1617127365659-c47fa864d8bc?auto=format&fit=crop&w=700&q=85"
},

{
name:"Premium Wedding Prince Coat",
cat:"Party Wear",
gender:"Men",
type:"Formal",
price:29990,
sale:23990,
image:"https://images.unsplash.com/photo-1507679799987-c73779587ccf?auto=format&fit=crop&w=700&q=85"
},

{
name:"Velvet Prince Coat",
cat:"Velvet",
gender:"Men",
type:"Formal",
price:24990,
sale:19990,
image:"https://images.unsplash.com/photo-1598808503746-f34c53b9323e?auto=format&fit=crop&w=700&q=85"
},

{
name:"Wedding Black Sherwani",
cat:"Party Wear",
gender:"Men",
type:"Formal",
price:32990,
sale:26990,
image:"https://images.unsplash.com/photo-1507679799987-c73779587ccf?auto=format&fit=crop&w=700&q=85"
},

{
name:"Modern Casual Shirt",
cat:"Men",
gender:"Men",
type:"Men",
price:4990,
sale:3990,
image:"https://images.unsplash.com/photo-1603252110481-7ba873bf42ab?auto=format&fit=crop&w=700&q=85"
},

{
name:"Premium Casual Overshirt",
cat:"Men",
gender:"Men",
type:"Western",
price:5990,
sale:4490,
image:"https://images.unsplash.com/photo-1529139574466-a303027c1d8b?auto=format&fit=crop&w=700&q=85"
},

{
name:"Modern Polo Outfit",
cat:"Men",
gender:"Men",
type:"Western",
price:6490,
sale:4990,
image:"https://images.unsplash.com/photo-1516826957135-700dedea698c?auto=format&fit=crop&w=700&q=85"
},

{
name:"Smart Casual Blazer",
cat:"Formal",
gender:"Men",
type:"Western",
price:15990,
sale:12490,
image:"https://images.unsplash.com/photo-1555069519-127aadedf1ee?auto=format&fit=crop&w=700&q=85"
},

{
name:"Premium Linen Kurta",
cat:"Kurta",
gender:"Men",
type:"Men",
price:7990,
sale:5990,
image:"https://images.unsplash.com/photo-1610652492500-ded49ceeb378?auto=format&fit=crop&w=700&q=85"
},

{
name:"Eid Festive Kurta Set",
cat:"Eid",
gender:"Men",
type:"Party Wear",
price:10990,
sale:8490,
image:"https://images.unsplash.com/photo-1598808503746-f34c53b9323e?auto=format&fit=crop&w=700&q=85"
},

{
name:"Premium Cotton Kameez Shalwar",
cat:"Shalwar Kameez",
gender:"Men",
type:"Men",
price:6990,
sale:4990,
image:"https://images.unsplash.com/photo-1610652492500-ded49ceeb378?auto=format&fit=crop&w=700&q=85"
}

];


/* DISPLAY */

function displayProducts(list){

const box=document.getElementById("products");

if(list.length===0){

box.innerHTML=`
<div style="grid-column:1/-1;text-align:center;padding:60px">
<h2>No Products Found</h2>
<p>Try another search.</p>
</div>
`;

return;
}

box.innerHTML=list.map((p,index)=>`

<div class="card">

<div class="photo">

<img
src="${p.image}"
alt="${p.name}"
loading="lazy"
>

</div>

<div class="info">

<span class="badge">
${p.gender}
</span>

<h3>${p.name}</h3>

<div class="category">
${p.cat}
</div>

<div class="price">

$${p.sale}

<span class="old">
$${p.price}
</span>

</div>

<button
class="purchase"
onclick="purchase(${products.indexOf(p)})">

🛒 Purchase / Add To Cart

</button>

</div>

</div>

`).join("");

}


/* SEARCH */

function searchProducts(){

const text=
document.getElementById("search")
.value
.toLowerCase()
.trim();

const category=
document.getElementById("category")
.value;

const result=products.filter(p=>{

const searchMatch=

text==="" ||

p.name.toLowerCase().includes(text) ||

p.cat.toLowerCase().includes(text) ||

p.gender.toLowerCase().includes(text) ||

p.type.toLowerCase().includes(text);

const categoryMatch=

category==="all" ||

p.cat===category ||

p.gender===category ||

p.type===category;

return searchMatch && categoryMatch;

});

displayProducts(result);

}


/* ENTER SEARCH */

document.getElementById("search")
.addEventListener("keydown",e=>{

if(e.key==="Enter"){
searchProducts();
}

});


/* CART */

let cart=0;

function purchase(index){

cart++;

document.getElementById("cartCount")
.innerText=cart;

alert(
products[index].name+
" added to your cart!"
);

}


/* NAVIGATION */

function shop(){

window.scrollTo({
top:document.querySelector(".shopTools").offsetTop-80,
behavior:"smooth"
});

}

function about(){

document.getElementById("about")
.scrollIntoView({behavior:"smooth"});

}

function delivery(){

document.getElementById("delivery")
.scrollIntoView({behavior:"smooth"});

}

function contact(){

document.getElementById("contact")
.scrollIntoView({behavior:"smooth"});

}

function orderNow(){

alert(
"Your home delivery request has been received!"
);

}

function sendMessage(){

alert(
"Thank you! Your message has been received."
);

}


/* START */

displayProducts(products);
</script>
</body>
</html>

