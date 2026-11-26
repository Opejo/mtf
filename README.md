<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MTfy Uganda - Make It Finally 🇺🇬</title>
<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:Arial,sans-serif}
body{background:#C9A227;color:#111;padding-bottom:90px}
.header{background:#5C3317;padding:8px 10px;text-align:center;position:sticky;top:0;z-index:10;border-bottom:3px solid #8B6508}
.logo{font-size:22px;font-weight:900;color:#FFD700;line-height:1}.logo span{color:#fff}
.tag{font-size:10px;color:#FFD700;margin-top:2px;font-weight:bold}
.sub{font-size:9px;color:#E8DCC0;margin-top:1px}
.langs{display:flex;gap:4px;justify-content:center;margin-top:6px;flex-wrap:wrap}
.langs button{background:#3B2108;color:#FFD700;border:1px solid #C9A227;padding:4px 8px;border-radius:12px;font-size:10px;font-weight:bold}
.langs button.active{background:#C9A227;color:#3B2108}
.card{margin:10px;background:#fff;border-radius:14px;overflow:hidden;border:2px solid #5C3317}
.video{height:240px;background:linear-gradient(135deg,#C9A227,#8B6508,#5C3317);display:flex;align-items:center;justify-content:center;font-size:60px}
.info{padding:12px}.user{font-weight:bold;font-size:14px}.user small{color:#8B6508}
.caption{margin:6px 0;color:#333;font-size:13px;line-height:1.4}
.actions{display:flex;gap:8px;padding-top:8px;border-top:1px solid #C9A227;font-size:13px;font-weight:bold}
.actions span{cursor:pointer;background:#FFF8DC;padding:5px 9px;border-radius:20px;border:1px solid #C9A227}
.btn{display:block;margin:12px;background:#5C3317;color:#FFD700;text-align:center;padding:14px;border-radius:30px;font-weight:bold;text-decoration:none;font-size:15px}
.bottom{position:fixed;bottom:0;left:0;right:0;background:#5C3317;display:flex;justify-content:space-around;padding:10px;border-top:3px solid #C9A227;font-size:11px;color:#fff;text-align:center}
.bottom div{cursor:pointer}.bottom div.active{color:#FFD700}
.login{background:#fff;margin:12px;padding:18px;border-radius:14px;text-align:center;border:2px solid #5C3317}
.login input{width:100%;padding:11px;margin:6px 0;border-radius:10px;border:2px solid #C9A227;background:#FFF8DC;color:#111}
.login button{width:100%;padding:12px;background:#5C3317;border:none;color:#FFD700;border-radius:30px;font-weight:bold}
.pageBox{background:#fff;margin:12px;padding:18px;border-radius:14px;border:2px solid #5C3317;text-align:center}
.pageBox button{padding:11px 18px;background:#5C3317;color:#FFD700;border:none;border-radius:20px;font-weight:bold;margin:6px}
#preview{width:100%;max-height:300px;border-radius:12px;margin-top:10px;display:none}
</style>
</head>
<body>
<div class="header">
<div class="logo">MT<span>fy</span> 🇺🇬</div>
<div class="tag">MTfy Uganda - Make It Finally</div>
<div class="sub">Ateso • Acholi • Luganda • Kiswahili • English</div>
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
<h2 style="font-size:18px">Welcome to MTfy Uganda 🔥</h2>
<p style="color:#666;font-size:12px;margin:6px 0">Login to watch & upload</p>
<input placeholder="Phone: 0770123456" value="0770123456">
<input placeholder="OTP Code" value="1234">
<button onclick="alert('Welcome to MTfy Uganda! Apai! You are in! 🇺🇬')">LOGIN WITH OTP →</button>
</div>
<div class="card"><div class="video">🎥</div><div class="info"><div class="user">@ateso_star <small>• Soroti • Ateso</small></div><div class="caption">Apai! My first dance in Ateso! Make It Finally! 🇺🇬 #MTfyUganda</div><div class="actions"><span onclick="like(this)">❤️ 12.4K</span><span onclick="alert('Link copied! https://opejo.github.io/mtf/')">↗️ Share</span><span onclick="follow(this)">➕ Follow</span></div></div></div>
<div class="card"><div class="video">🎤</div><div class="info"><div class="user">@acholi_queen <small>• Gulu • Acholi</small></div><div class="caption">Acholi traditional dance! Ber! #MTfyUganda</div><div class="actions"><span onclick="like(this)">❤️ 8.9K</span><span onclick="alert('Link copied!')">↗️ Share</span><span onclick="follow(this)">➕ Follow</span></div></div></div>
<div class="card"><div class="video">🍲</div><div class="info"><div class="user">@kampala_food <small>• Kampala • Luganda</small></div><div class="caption">How to cook Luwombo! Oli Otya? #MTfyUganda</div><div class="actions"><span onclick="like(this)">❤️ 25K</span><span onclick="alert('Link copied!')">↗️ Share</span><span onclick="follow(this)">➕ Follow</span></div></div></div>
<a class="btn" href="#" onclick="showPage('upload');return false;">＋ UPLOAD YOUR VIDEO</a>
</div>

<div id="discoverPage" class="pageBox" style="display:none">
<h2>🔍 Discover</h2><p style="color:#666;margin:10px">Trending in Uganda</p><p>🔥 #MTfyUganda #SorotiDance #AcholiDance</p><br><button onclick="showPage('home')">← Back</button>
</div>

<div id="uploadPage" class="pageBox" style="display:none">
<h2>＋ Upload Video</h2>
<p style="color:#666;margin:10px">This will REALLY open your phone now</p>
<input type="file" id="fileInput" accept="video/*,image/*" style="display:none" onchange="previewFile(this)">
<button onclick="document.getElementById('fileInput').click()">📁 CHOOSE FROM GALLERY</button><br>
<input type="file" id="cameraInput" accept="video/*,image/*" capture="environment" style="display:none" onchange="previewFile(this)">
<button onclick="document.getElementById('cameraInput').click()">🎥 OPEN CAMERA TO RECORD</button>
<video id="preview" controls></video>
<img id="previewImg" style="width:100%;border-radius:12px;margin-top:10px;display:none">
<p id="uploadStatus" style="color:#5C3317;font-weight:bold;margin-top:10px"></p>
<button onclick="postVideo()">✅ POST TO MTfy UGANDA</button><br>
<button onclick="showPage('home')">← Back</button>
</div>

<div id="inboxPage" class="pageBox" style="display:none">
<h2>💬 Inbox</h2><p>👤 @ateso_star: Apai! Loved your video! ❤️</p><br><p>👤 MTfy Uganda: Welcome! 🇺🇬</p><br><button onclick="showPage('home')">← Back</button>
</div>

<div id="mePage" class="pageBox" style="display:none">
<h2>👤 @opejo_benjamin</h2><p>Soroti, Uganda 🇺🇬 | Founder of MTfy Uganda</p><br><button onclick="showPage('home')">← Back</button>
</div>

<div class="bottom">
<div id="nav-home" class="active" onclick="showPage('home')">🏠<br>Home</div>
<div id="nav-discover" onclick="showPage('discover')">🔍<br>Discover</div>
<div id="nav-upload" onclick="showPage('upload')">＋<br>Upload</div>
<div id="nav-inbox" onclick="showPage('inbox')">💬<br>Inbox</div>
<div id="nav-me" onclick="showPage('me')">👤<br>Me</div>
</div>

<script>
function setLang(btn){document.querySelectorAll('.langs button').forEach(b=>b.classList.remove('active'));btn.classList.add('active');alert('MTfy Uganda: '+btn.innerText);}
function like(el){el.innerText='❤️ Liked!';}
function follow(el){el.innerText='✓ Following';}
function showPage(page){
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
  document.getElementById('uploadStatus').innerText='✅ Selected: '+file.name+' - Ready to post!';
}
function postVideo(){
  var status=document.getElementById('uploadStatus');
  if(!status.innerText){alert('Please choose a video first! Tap CHOOSE FROM GALLERY'); return;}
  alert('🎉 Your video is posted on MTfy Uganda! Make It Finally! (Demo - saved on your phone, will show to everyone after we connect cloud)');
  showPage('home');
}
</script>
</body>
</html>
