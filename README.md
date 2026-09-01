<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ALURAIBRARY - Digital Library Adjumani</title>
<style>
body{font-family:Arial,sans-serif;margin:0;background:#f5f7fa}
header{background:#0d3b66;color:white;padding:20px;text-align:center}
header h1{margin:0;letter-spacing:2px}
.search{margin:20px auto;max-width:600px;text-align:center}
.search input{width:80%;padding:12px;border-radius:25px;border:1px solid #ccc}
.grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(180px,1fr));gap:20px;padding:20px;max-width:1000px;margin:auto}
.card{background:white;border-radius:10px;padding:15px;box-shadow:0 2px 8px rgba(0,0,0,0.1);text-align:center}
.card h3{font-size:16px;color:#0d3b66}
.card a{background:#0d3b66;color:white;padding:8px 15px;border-radius:20px;text-decoration:none;display:inline-block;margin-top:10px}
</style>
</head>
<body>
<header>
<h1>ALURAIBRARY</h1>
<p>Digital Library for our Community - Adjumani, Uganda</p>
</header>
<div class="search">
<input type="text" id="searchBox" onkeyup="searchBook()" placeholder="Search books by title...">
</div>
<div class="grid" id="bookGrid">
<div class="card"><h3>Primary Science Book</h3><p>P5-P7</p><a href="#">Read / Download</a></div>
<div class="card"><h3>English Grammar</h3><p>All Classes</p><a href="#">Read / Download</a></div>
<div class="card"><h3>Mathematics Revision</h3><p>P7 & S4</p><a href="#">Read / Download</a></div>
<div class="card"><h3>History of Uganda</h3><p>Secondary</p><a href="#">Read / Download</a></div>
<div class="card"><h3>Agriculture Guide</h3><p>Community</p><a href="#">Read / Download</a></div>
<div class="card"><h3>Health Education</h3><p>Community</p><a href="#">Read / Download</a></div>
</div>
<script>
function searchBook(){
let input=document.getElementById('searchBox').value.toLowerCase();
let cards=document.getElementsByClassName('card');
for(let i=0;i<cards.length;i++){
let title=cards[i].getElementsByTagName('h3')[0].innerText.toLowerCase();
cards[i].style.display=title.includes(input)?"":"none";
}
}
</script>
</body>
</html>
