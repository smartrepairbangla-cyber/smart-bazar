# smart-bazar
<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Smart Bazar</title>
<style>
*{box-sizing:border-box}
body{margin:0;font-family:Arial,sans-serif;background:#f5f6fa;color:#222}
header{background:#087b45;color:white;padding:18px 5%;display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap}
header h1{margin:0}
nav{display:flex;gap:18px;align-items:center}
nav a{color:white;text-decoration:none}
.search{padding:20px 5%;display:flex;gap:8px}
.search input{flex:1;padding:13px;border:1px solid #ddd;border-radius:8px}
button{background:#087b45;color:white;border:0;padding:12px 18px;border-radius:8px;cursor:pointer}
.banner{margin:10px 5%;padding:35px 20px;background:#dff5e9;border-radius:14px;text-align:center}
main{padding:10px 5%}
.categories,.products{display:grid;grid-template-columns:repeat(auto-fit,minmax(145px,1fr));gap:15px}
.category,.card{background:white;padding:18px;border-radius:12px;text-align:center;box-shadow:0 2px 8px #00000010}
.category{font-size:17px}
.card img{width:100%;height:145px;object-fit:contain}
.card h3{font-size:16px}
.price{color:#087b45;font-weight:bold;font-size:18px}
.ai{position:fixed;bottom:18px;right:18px;border-radius:30px}
footer{text-align:center;background:#173d2c;color:white;padding:25px;margin-top:30px}
</style>
</head>
<body>
<header>
<h1>🛒 Smart Bazar</h1>
<nav>
<a href="#">হোম</a>
<a href="#categories">ক্যাটাগরি</a>
<a href="#products">পণ্য</a>
<a href="#cart">কার্ট 🛍️</a>
</nav>
</header>

<div class="search">
<input id="search" placeholder="আপনার পছন্দের পণ্য খুঁজুন...">
<button onclick="searchProducts()">খুঁজুন</button>
</div>

<section class="banner">
<h2>Smart Bazar-এ স্বাগতম!</h2>
<p>আপনার পছন্দের সব পণ্য এক জায়গায়</p>
<button onclick="document.getElementById('products').scrollIntoView()">এখনই কেনাকাটা করুন</button>
</section>

<main>
<h2 id="categories">পণ্যের ক্যাটাগরি</h2>
<div class="categories">
<div class="category">📱 ইলেকট্রনিক্স</div>
<div class="category">👕 ফ্যাশন</div>
<div class="category">🏠 ঘর ও রান্নাঘর</div>
<div class="category">💄 সৌন্দর্য</div>
</div>

<h2 id="products">জনপ্রিয় পণ্য</h2>
<div class="products" id="productList">
<div class="card" data-name="Samsung Mobile">
<img src="https://placehold.co/300x300?text=Samsung+Mobile" alt="Samsung Mobile">
<h3>Samsung Mobile</h3>
<p class="price">৳১৫,০০০</p>
<button onclick="addCart('Samsung Mobile')">কার্টে যোগ করুন</button>
</div>
<div class="card" data-name="T-Shirt">
<img src="https://placehold.co/300x300?text=T-Shirt" alt="T-Shirt">
<h3>T-Shirt</h3>
<p class="price">৳৫০০</p>
<button onclick="addCart('T-Shirt')">কার্টে যোগ করুন</button>
</div>
</div>

<h2 id="cart">আপনার কার্ট</h2>
<p id="cartItems">এখনো কোনো পণ্য যোগ হয়নি।</p>
</main>

<button class="ai" onclick="alert('Smart Bazar AI শিগগিরই চালু হবে!')">🤖 Smart Bazar AI</button>

<footer>
<h3>Smart Bazar</h3>
<p>আপনার অনলাইন শপিংয়ের বিশ্বস্ত ঠিকানা</p>
</footer>

<script>
let cart=[];
function addCart(name){
cart.push(name);
document.getElementById('cartItems').textContent=cart.join(', ');
}
function searchProducts(){
let q=document.getElementById('search').value.toLowerCase();
document.querySelectorAll('.card').forEach(card=>{
card.style.display=card.dataset.name.toLowerCase().includes(q)?'block':'none';
});
}
</script>
</body>
</html>
