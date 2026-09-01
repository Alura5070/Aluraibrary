<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ALURAIBRARY - Digital Library</title>
<style>
body{font-family:Arial,sans-serif;margin:0;background:#f5f7fa}
header{background:#0d3b66;color:white;padding:30px 20px;text-align:center}
header h1{margin:0;letter-spacing:3px;font-size:32px}
header p{opacity:0.9;margin-top:5px}
.search{margin:25px auto;max-width:650px;text-align:center;padding:0 15px}
.search input{width:85%;padding:14px 20px;border-radius:30px;border:1px solid #ccc;font-size:16px}
.filters{text-align:center;margin-bottom:10px}
.filters button{margin:5px;padding:8px 18px;border-radius:20px;border:1px solid #0d3b66;background:white;color:#0d3b66;cursor:pointer}
.filters button.active,.filters button:hover{background:#0d3b66;color:white}
.grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(200px,1fr));gap:20px;padding:20px;max-width:1100px;margin:auto}
.card{background:white;border-radius:12px;padding:20px;box-shadow:0 3px 10px rgba(0,0,0,0.08);text-align:center;transition:0.2s}
.card:hover{transform:translateY(-3px)}
.card .tag{display:inline-block;font-size:11px;padding:4px 10px;border-radius:20px;background:#eef3ff;color:#0d3b66;margin-bottom:10px;font-weight:bold;letter-spacing:1px}
.card h3{font-size:17px;color:#222;margin:10px 0}
.card a{background:#0d3b66;color:white;padding:9px 18px;border-radius:25px;text-decoration:none;display:inline-block;margin-top:12px;font-size:14px}
footer{text-align:center;padding:30px;color:#777;margin-top:30px}
</style>
</head>
<body>
<header>
<h1>ALURAIBRARY</h1>
<p>Open Digital Library - Tororo City</p>
</header>

<div class="search">
<input type="text" id="searchBox" onkeyup="filterBooks()" placeholder="Search books, authors, topics...">
</div>

<div class="filters">
<button class="active" onclick="filterCategory('ALL',this)">ALL</button>
<button onclick="filterCategory('PHILOSOPHY',this)">Philosophy</button>
<button onclick="filterCategory('SCIENCE',this)">Science</button>
<button onclick="filterCategory('TECHNOLOGY',this)">Technology</button>
<button onclick="filterCategory('ECONOMICS',this)">Economics</button>
<button onclick="filterCategory('MATHEMATICS',this)">Mathematics</button>
</div>

<div class="grid" id="bookGrid">
<div class="card" data-cat="PHILOSOPHY"><span class="tag">PHILOSOPHY</span><h3>Meditations - Alfred's Meditations</h3><a href="#">Read / Download</a></div>
<div class="card" data-cat="PHILOSOPHY"><span class="tag">PHILOSOPHY</span><h3>The Art of Thinking Clearly</h3><a href="#">Read / Download</a></div>
<div class="card" data-cat="SCIENCE"><span class="tag">SCIENCE</span><h3>A Brief History of Time</h3><a href="#">Read / Download</a></div>
<div class="card" data-cat="SCIENCE"><span class="tag">SCIENCE</span><h3>The Selfish Gene</h3><a href="#">Read / Download</a></div>
<div class="card" data-cat="TECHNOLOGY"><span class="tag">TECHNOLOGY</span><h3>Introduction to Artificial Intelligence</h3><a href="#">Read / Download</a></div>
<div class="card" data-cat="TECHNOLOGY"><span class="tag">TECHNOLOGY</span><h3>Clean Code - Programming</h3><a href="#">Read / Download</a></div>
<div class="card" data-cat="ECONOMICS"><span class="tag">ECONOMICS</span><h3>Principles of Economics</h3><a href="#">Read / Download</a></div>
<div class="card" data-cat="ECONOMICS"><span class="tag">ECONOMICS</span><h3>Wealth of Nations</h3><a href="#">Read / Download</a></div>
<div class="card" data-cat="MATHEMATICS"><span class="tag">MATHEMATICS</span><h3>Calculus Made Easy</h3><a href="#">Read / Download</a></div>
<div class="card" data-cat="MATHEMATICS"><span class="tag">MATHEMATICS</span><h3>Mathematical Thinking</h3><a href="#">Read / Download</a></div>
</div>

<footer>ALURAIBRARY © 2026 - Tororo City - Open Knowledge for All</footer>

<script>
let currentCat='ALL';
function filterBooks(){
let q=document.getElementById('searchBox').value.toLowerCase();
let cards=document.getElementsByClassName('card');
for(let c of cards){
let txt=c.innerText.toLowerCase();
let catMatch=currentCat==='ALL' || c.dataset.cat===currentCat;
c.style.display=(txt.includes(q) && catMatch)?'':'none';
}
}
function filterCategory(cat,btn){
currentCat=cat;
document.querySelectorAll('.filters button').forEach(b=>b.classList.remove('active'));
btn.classList.add('active');
filterBooks();
}
</script>
</body>
</html>
