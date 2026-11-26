 <!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MTfy Uganda - Make It Finally 🇺🇬</title>
<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:Arial,sans-serif}
body{
background:
repeating-linear-gradient(115deg, rgba(255,255,255,0.25) 0px, rgba(255,255,255,0) 2px, rgba(0,0,0,0.15) 3px, rgba(0,0,0,0) 5px),
linear-gradient(135deg,#FFF7A8 0%, #FFD700 15%, #C9A227 30%, #8B6508 45%, #FFEC8B 55%, #D4AF37 65%, #B8860B 80%, #5C3317 100%);
background-attachment:fixed;
color:#111;padding-bottom:90px;min-height:100vh}
.header{background:#5C3317;padding:8px 10px;text-align:center;position:sticky;top:0;z-index:20;border-bottom:3px solid #FFD700;display:flex;align-items:center;justify-content:space-between}
.header-center{flex:1;text-align:center}
.logo{font-size:22px;font-weight:900;color:#FFD700;line-height:1}.logo span{color:#fff}
.tag{font-size:10px;color:#FFD700;margin-top:2px;font-weight:bold}
.sub{font-size:9px;color:#E8DCC0}
.hamburger{font-size:26px;color:#FFD700;cursor:pointer;padding:4px 10px;background:#3B2108;border:1px solid #FFD700;border-radius:8px}
.menu{position:fixed;top:58px;right:10px;background:#fff;border:2px solid #5C3317;border-radius:14px;width:220px;z-index:30;display:none;box-shadow:0 10px 25px rgba(0,0,0,0.4);overflow:hidden}
.menu a{display:block;padding:13px 16px;text-decoration:none;color:#111;border-bottom:1px solid #F0D060;font-weight:bold;font-size:14px}
.menu a:hover{background:#FFF7A8}
.menu .menu-head{background:#5C3317;color:#FFD700;padding:12px 16px;font-weight:900}
.langs{display:flex;gap:4px;justify-content:center;margin:8px 6px;flex-wrap:wrap}
.langs button{background:#3B2108;color:#FFD700;border:1px solid #FFD700;padding:4px 8px;border-radius:12px;font-size:10px;font-weight:bold}
.langs button.active{background:#FFD700;color:#3B2108}
.card{margin:10px;background:#fff;border-radius:14px;overflow:hidden;border:2px solid #5C3317}
.video{height:240px;background:linear-gradient(135deg,#FFD700,#B8860B,#5C3317);display:flex;align-items:center;justify-content:center;font-size:60px}
.info{padding:12px}.user{font-weight:bold}.user small{color:#8B6508}
.caption{margin:6px 0;color:#333;font-size:13px}
.actions{display:flex;gap:8px;padding-top:8px;border-top:1px solid #C9A227;font-size:13px;font-weight:bold}
.actions span{cursor:pointer;background:#FFF8DC;padding:5px 9px;border-radius:20px;border:1px solid #C9A227}
.btn{display:block;margin:12px;background:#5C3317;color:#FFD700;text-align:center;padding:14px;border-radius:30px;font-weight:bold;text-decoration:none}
.bottom{position:fixed;bottom:0;left:0;right:0;background:#5C3317;display:flex;justify-content:space-around;padding:10px;border-top:3px solid #FFD700;font-size:11px;color:#fff;text-align:center;z-index:20}
.bottom div{cursor:pointer}.bottom div.active{color:#FFD700}
.login{background:#fff;margin:12px;padding:18px;border-radius:14px;text-align:center;border:2px solid #5C3317}
.login input{width:100%;padding:11px;margin:6px 0;border-radius:10px;border:2px solid #C9A227;background:#FFF8DC}
.login button{width:100%;padding:12px;background:#5C3317;color:#FFD700;border:none;border-radius:30px;font-weight:bold}
.pageBox{background:#fff;margin:12px;padding:18px;border-radius:14px;border:2px solid #5C3317;text-align:center}
.pageBox button{padding:11px 18px;background:#5C3317;color:#FFD700;border:none;border-radius:20px;font-weight:bold;margin:6px}
</style>
</head>
<body>
<div class="header">
<div style="width:44px"></div>
<div class="header-center">
<div class="logo">MT<span>fy</span> 🇺🇬</div>
<div class="tag">MTfy Uganda - Make It Finally</div>
<div class="sub">Ateso • Acholi • Luganda • Kiswahili • English</div>
</div>
<div class="hamburger" onclick="toggleMenu()">☰</div>
</div>

<div id="sideMenu" class="menu">
<div class="menu-head">MTfy Uganda 🇺🇬</div>
<a href="#" onclick="goMenu('home')">🏠 Home</a>
<a href="#" onclick="goMenu('discover')">🔍 Discover</a>
<a href="#" onclick="goMenu('upload')">＋ Upload Video</a>
<a href="#" onclick="goMenu('inbox')">💬 Inbox</a>
<a href="#" onclick="goMenu('me')">👤 My Profile</a>
<a href="#" onclick="alert('Settings: Language, Notifications, Privacy - Coming soon!')">⚙️ Settings</a>
<a href="#" onclick="alert('MTfy Uganda - Made by Opejo Benjamin in Soroti, Uganda. Make It Finally! 🇺🇬')">ℹ️ About MTfy Uganda</a>
<a href="#" onclick="alert('You logged out. Apai, see you soon!')">🚪 Logout</a>
</div>

<div class="langs">
<button class="active" onclick="setLang(this)">English</button>
<button onclick="setLang(this)">Ateso</button>
<button onclick="setLang(this)">Acholi</button>
<button onclick="setLang(this)">Luganda</button>
<button onclick="setLang(this)">Kiswahili</button>
</div>

<div id="homePage">
<div class="login">
<h2 style="font-size:18px">Welcome to MTfy Uganda 🔥</h2>
<p style="color:#666;font-size:12px;margin:6px 0">Login to watch & upload</p>
<input placeholder="Phone: 0770123456" value="0770123456">
<input placeholder="OTP Code" value="1234">
<button onclick="alert('Welcome to MTfy Uganda! Apai!')">LOGIN WITH OTP →</button>
</div>
<div class="card"><div class="video">🎥</div><div class="info"><div class="user">@ateso_star <small>• Soroti • Ateso</small></div><div class="caption">Apai! My first dance in Ateso! 🇺🇬 #MTfyUganda</div><div class="actions"><span onclick="like(this)">❤️ 12.4K</span><span onclick="alert('Link copied!')">↗️ Share</span><span onclick="follow(this)">➕ Follow</span></div></div></div>
<div class="card"><div class="video">🎤</div><div class="info"><div class="user">@acholi_queen <small>• Gulu • Acholi</small></div><div class="caption">Acholi traditional dance! Ber! #MTfyUganda</div><div class="actions"><span onclick="like(this)">❤️ 8.9K</span><span onclick="alert('Link copied!')">↗️ Share</span><span onclick="follow(this)">➕ Follow</span></div></div></div>
<div class="card"><div class="video">🍲</div><div class="info"><div class="user">@kampala_food <small>• Kampala • Luganda</small></div><div class="caption">How to cook Luwombo! Oli Otya? #MTfyUganda</div><div class="actions"><span onclick="like(this)">❤️ 25K</span><span onclick="alert('Link copied!')">↗️ Share</span><span onclick="follow(this)">➕ Follow</span></div></div></div>
<a class="btn" href="#" onclick="showPage('upload');return false;">＋ UPLOAD YOUR VIDEO</a>
</div>

<div id="discoverPage" class="pageBox" style="display:none"><h2>🔍 Discover</h2><p style="color:#666;margin:10px">Trending in Uganda</p><p>🔥 #MTfyUganda #SorotiDance</p><br><button onclick="showPage('home')">← Back</button></div>
<div id="uploadPage" class="pageBox" style="display:none">
<h2>＋ Upload Video</h2><p style="color:#666;margin:10px">Real gallery & camera</p>
<input type="file" id="fileInput" accept="video/*,image/*" style="display:none" onchange="previewFile(this)">
<button onclick="document.getElementById('fileInput').click()">📁 CHOOSE FROM GALLERY</button><br>
<input type="file" id="cameraInput" accept="video/*,image/*" capture="environment" style="display:none" onchange="previewFile(this)">
<button onclick="document.getElementById('cameraInput').click()">🎥 OPEN CAMERA</button>
<video id="preview" controls style="width:100%;max-height:300px;border-radius:12px;margin-top:10px;display:none"></video>
<img id="previewImg" style="width:100%;border-radius:12px;margin-top:10px;display:none">
<p id="uploadStatus" style="color:#5C3317;font-weight:bold;margin-top:10px"></p>
<button onclick="postVideo()">✅ POST TO MTfy UGANDA</button><br><button onclick="showPage('home')">← Back</button>
</div>
<div id="inboxPage" class="pageBox" style="display:none"><h2>💬 Inbox</h2><p>👤 @ateso_star: Apai! Loved your video! ❤️</p><br><button onclick="showPage('home')">← Back</button></div>
<div id="mePage" class="pageBox" style="display:none"><h2>👤 @opejo_benjamin</h2><p>Soroti, Uganda 🇺🇬 | Founder of MTfy Uganda</p><br><button onclick="showPage('home')">← Back</button></div>

<div class="bottom">
<div id="nav-home" class="active" onclick="showPage('home')">🏠<br>Home</div>
<div id="nav-discover" onclick="showPage('discover')">🔍<br>Discover</div>
<div id="nav-upload" onclick="showPage('upload')">＋<br>Upload</div>
<div id="nav-inbox" onclick="showPage('inbox')">💬<br>Inbox</div>
<div id="nav-me" onclick="showPage('me')">👤<br>Me</div>
</div>

<script>
function toggleMenu(){var m=document.getElementById('sideMenu');m.style.display=(m.style.display==='block'?'none':'block');}
function goMenu(page){document.getElementById('sideMenu').style.display='none';showPage(page);}
function setLang(btn){document.querySelectorAll('.langs button').forEach(b=>b.classList.remove('active'));btn.classList.add('active');alert('MTfy Uganda: '+btn.innerText);}
function like(el){el.innerText='❤️ Liked!';}
function follow(el){el.innerText='✓ Following';}
function showPage(page){
  document.getElementById('sideMenu').style.display='none';
  ['homePage','discoverPage','uploadPage','inboxPage','mePage'].forEach(id=>document.getElementById(id).style.display='none');
  document.querySelectorAll('.bottom div').forEach(d=>d.classList.remove('active'));
  if(page==='home'){document.getElementById('homePage').style.display='block';document.getElementById('nav-home').classList.add('active');}
  else{document.getElementById(page+'Page').style.display='block';document.getElementById('nav-'+page).classList.add('active');}
  window.scrollTo(0,0);
}
function previewFile(input){
  var file=input.files[0]; if(!file) return;
  var url=URL.createObjectURL(file);
  var vid=document.getElementById('preview'); var img=document.getElementById('previewImg');
  if(file.type.startsWith('video')){vid.src=url; vid.style.display='block'; img.style.display='none';}
  else{img.src=url; img.style.display='block'; vid.style.display='none';}
  document.getElementById('uploadStatus').innerText='✅ Selected: '+file.name;
}
function postVideo(){
  if(!document.getElementById('uploadStatus').innerText){alert('Please choose a video first!'); return;}
  alert('🎉 Posted on MTfy Uganda!'); showPage('home');
}
document.addEventListener('click',function(e){
  if(!e.target.closest('.hamburger') && !e.target.closest('.menu')){document.getElementById('sideMenu').style.display='none';}
});
</script>
</body>
</html>
