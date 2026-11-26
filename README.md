<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MTfy Uganda - Make It Finally 🇺🇬</title>
<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:Arial,sans-serif}
body{background:#FFD700;color:#111;padding-bottom:90px}
.header{background:#111;padding:16px;text-align:center;position:sticky;top:0;z-index:10;border-bottom:4px solid #FFD700}
.logo{font-size:36px;font-weight:900;color:#FFD700}.logo span{color:#fff}
.tag{font-size:13px;color:#FFD700;margin-top:4px;font-weight:bold}
.sub{font-size:11px;color:#ccc;margin-top:2px}
.langs{display:flex;gap:6px;justify-content:center;margin-top:10px;flex-wrap:wrap}
.langs button{background:#222;color:#FFD700;border:1px solid #FFD700;padding:7px 12px;border-radius:20px;font-size:12px;font-weight:bold}
.langs button.active{background:#FFD700;color:#111}
.card{margin:12px;background:#fff;border-radius:16px;overflow:hidden;border:2px solid #111;box-shadow:0 4px 10px rgba(0,0,0,0.2)}
.video{height:260px;background:linear-gradient(135deg,#FFD700,#FF8C00,#B8860B);display:flex;align-items:center;justify-content:center;font-size:70px}
.info{padding:14px}
.user{font-weight:bold;font-size:15px}.user small{color:#B8860B}
.caption{margin:8px 0;color:#333;font-size:14px;line-height:1.4}
.actions{display:flex;gap:12px;padding-top:10px;border-top:1px solid #FFD700;font-size:14px;font-weight:bold}
.actions span{cursor:pointer;background:#FFF8DC;padding:6px 10px;border-radius:20px;border:1px solid #FFD700}
.btn{display:block;margin:15px;background:#111;color:#FFD700;text-align:center;padding:16px;border-radius:30px;font-weight:bold;text-decoration:none;font-size:16px;border:2px solid #111}
.bottom{position:fixed;bottom:0;left:0;right:0;background:#111;display:flex;justify-content:space-around;padding:14px;border-top:4px solid #FFD700;font-size:12px;color:#fff;text-align:center}
.bottom div{cursor:pointer}
.bottom div.active{color:#FFD700}
.login{background:#fff;margin:15px;padding:22px;border-radius:16px;text-align:center;border:2px solid #111}
.login input{width:100%;padding:13px;margin:8px 0;border-radius:10px;border:2px solid #FFD700;background:#FFF8DC;color:#111;font-size:14px}
.login button{width:100%;padding:14px;background:#111;border:none;color:#FFD700;border-radius:30px;font-weight:bold;margin-top:10px;font-size:15px}
.pageBox{background:#fff;margin:15px;padding:22px;border-radius:16px;border:2px solid #111;text-align:center}
.pageBox button{padding:12px 22px;background:#111;color:#FFD700;border:none;border-radius:20px;font-weight:bold;margin:8px}
</style>
</head>
<body>
<div class="header">
<div class="logo">MT<span>fy</span> 🇺🇬</div>
<div class="tag">MTfy Uganda - Make It Finally</div>
<div class="sub">Ateso • Acholi • Luganda • Kiswahili • English | Made in Uganda for Uganda</div>
<div class="langs">
<button class="active" onclick="setLang(this)">English</button>
<button onclick="setLang(this)">Ateso</button>
<button onclick="setLang(this)">Acholi</button>
<button onclick="setLang(this)">Luganda</button>
<button onclick="setLang(this)">Kiswahili</button>
</div>
</div>

<div id="homePage">
<div class="login">
<h2>Welcome to MTfy Uganda 🔥</h2>
<p style="color:#666;font-size:13px;margin:8px 0">Login to watch & upload - Apai! Oli Otya? Ber!</p>
<input placeholder="Phone: 0770123456" value="0770123456">
<input placeholder="OTP Code" value="1234">
<button onclick="alert('Welcome to MTfy Uganda! Apai! You are in! 🇺🇬')">LOGIN WITH OTP →</button>
<p style="font-size:11px;color:#888;margin-top:8px">Demo: Use 0770123456 / 1234</p>
</div>

<div class="card"><div class="video">🎥</div><div class="info"><div class="user">@ateso_star <small>• Soroti • Ateso</small></div><div class="caption">Apai! My first dance in Ateso! Make It Finally! 🇺🇬 #MTfyUganda #Soroti</div><div class="actions"><span onclick="like(this)">❤️ 12.4K</span><span onclick="alert('Link copied! Share MTfy Uganda: https://opejo.github.io/mtf/')">↗️ Share</span><span onclick="follow(this)">➕ Follow</span></div></div></div>

<div class="card"><div class="video" style="background:linear-gradient(135deg,#FFD700,#FF4500,#8B0000)">🎤</div><div class="info"><div class="user">@acholi_queen <small>• Gulu • Acholi</small></div><div class="caption">Acholi traditional dance! Ber! Who can dance better? #MTfyUganda #Gulu</div><div class="actions"><span onclick="like(this)">❤️ 8.9K</span><span onclick="alert('Link copied! Share MTfy Uganda')">↗️ Share</span><span onclick="follow(this)">➕ Follow</span></div></div></div>

<div class="card"><div class="video" style="background:linear-gradient(135deg,#FFD700,#32CD32,#006400)">🍲</div><div class="info"><div class="user">@kampala_food <small>• Kampala • Luganda</small></div><div class="caption">How to cook Luwombo! Oli Otya? Best food in Kampala! #MTfyUganda</div><div class="actions"><span onclick="like(this)">❤️ 25K</span><span onclick="alert('Link copied! Share MTfy Uganda')">↗️ Share</span><span onclick="follow(this)">➕ Follow</span></div></div></div>

<a class="btn" href="#" onclick="showPage('upload');return false;">＋ UPLOAD YOUR VIDEO - MAKE IT FINALLY</a>
</div>

<div id="discoverPage" class="pageBox" style="display:none">
<h2>🔍 Discover - MTfy Uganda</h2>
<p style="color:#666;margin:10px">Trending in Uganda today</p>
<p>🔥 #MTfyUganda #SorotiDance #AcholiDance #Luwombo</p><br>
<p>🎥 Soroti Dance Challenge - 50K views</p>
<p>🎤 Gulu Music - 30K views</p>
<p>🍲 Kampala Food - 25K views</p>
<button onclick="showPage('home')">← Back to Home</button>
</div>

<div id="uploadPage" class="pageBox" style="display:none">
<h2>＋ Upload Video</h2>
<p style="color:#666;margin:10px">Record in Ateso, Acholi, Luganda or English</p>
<button onclick="alert('Camera opening... Record and Make It Finally!')">🎥 RECORD VIDEO</button>
<button onclick="alert('Choose video from your phone gallery')">📁 Choose From Gallery</button><br>
<button onclick="showPage('home')">← Back</button>
</div>

<div id="inboxPage" class="pageBox" style="display:none">
<h2>💬 Inbox</h2>
<p>👤 @ateso_star: Apai! Loved your video! ❤️</p><br>
<p>👤 @acholi_queen: Ber! Let's collab?</p><br>
<p>👤 MTfy Uganda: Welcome! 🇺🇬 Karibu!</p><br>
<button onclick="showPage('home')">← Back to Home</button>
</div>

<div id="mePage" class="pageBox" style="display:none">
<h2>👤 @opejo_benjamin</h2>
<p style="color:#666">Soroti, Uganda 🇺🇬 | Founder of MTfy Uganda</p>
<p>0 Following • 0 Followers • 0 Likes</p><br>
<p>Your videos will show here after you upload!</p>
<button onclick="showPage('home')">← Back to Home</button>
</div>

<div class="bottom">
<div id="nav-home" class="active" onclick="showPage('home')">🏠<br>Home</div>
<div id="nav-discover" onclick="showPage('discover')">🔍<br>Discover</div>
<div id="nav-upload" onclick="showPage('upload')">＋<br>Upload</div>
<div id="nav-inbox" onclick="showPage('inbox')">💬<br>Inbox</div>
<div id="nav-me" onclick="showPage('me')">👤<br>Me</div>
</div>

<script>
function setLang(btn){document.querySelectorAll('.langs button').forEach(b=>b.classList.remove('active'));btn.classList.add('active');alert('MTfy Uganda language: '+btn.innerText+' - Apai!');}
function like(el){el.innerText='❤️ Liked!';alert('❤️ You liked this video on MTfy Uganda!');}
function follow(el){el.innerText='✓ Following';alert('You are now following!');}
function showPage(page){
  ['homePage','discoverPage','uploadPage','inboxPage','mePage'].forEach(id=>{document.getElementById(id).style.display='none'});
  document.querySelectorAll('.bottom div').forEach(d=>d.classList.remove('active'));
  if(page==='home'){document.getElementById('homePage').style.display='block';document.getElementById('nav-home').classList.add('active');}
  else{document.getElementById(page+'Page').style.display='block';document.getElementById('nav-'+page).classList.add('active');}
  window.scrollTo(0,0);
}
</script>
</body>
</html>
