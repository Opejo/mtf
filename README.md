<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>MTfy - Africa's Super App</title>
<script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>
<style>
*{box-sizing:border-box}body{margin:0;background:#000;color:#fff;font-family:system-ui;padding-bottom:70px}
/* 2. TOP BAR - SKY BLUE */
.top{position:fixed;top:0;left:0;right:0;display:flex;justify-content:space-between;align-items:center;padding:10px 12px;background:#00BFFF;z-index:50}
.logo{font-weight:900;font-size:22px;color:#fff}.logo span{color:#000}
.topIcons{display:flex;gap:8px;align-items:center}
.topIcons button{background:#fff;border:0;width:38px;height:38px;border-radius:50%;font-size:18px;cursor:pointer;color:#000;font-weight:800}
.topIcons button.active{background:#000;color:#fff}
/* Feed */
#feed{height:100vh;overflow-y:scroll;scroll-snap-type:y mandatory}
.post{height:100vh;scroll-snap-align:start;position:relative;display:flex;align-items:flex-end;justify-content:center;background:#000}
.post video{position:absolute;inset:0;width:100%;height:100%;object-fit:cover;background:#000}
/* 7. NO BROWN - WHITE TEXT ON BLACK GRADIENT */
.info{position:relative;z-index:2;padding:20px 70px 110px 16px;width:100%;background:linear-gradient(transparent,rgba(0,0,0,.9));color:#fff}
.user{font-weight:800;color:#fff}.cap{margin:6px 0;color:#fff}
.actions{position:absolute;right:12px;bottom:150px;z-index:3;display:flex;flex-direction:column;gap:12px;align-items:center}
.likeBtn,.cmtBtn{background:#fff;border:0;width:52px;height:52px;border-radius:50%;font-size:22px;color:#000}
.likeBtn.liked{background:#ff2d55;color:#fff}
/* Pages */
.page{padding:70px 16px 20px;display:none;background:#000;color:#fff;min-height:100vh}
.page.active{display:block}
.page input,.page select,.page textarea{width:100%;padding:14px;margin:8px 0;border-radius:10px;border:0;font-size:16px;background:#fff;color:#000}
.page button{width:100%;padding:14px;background:#fff;color:#000;border:0;border-radius:10px;font-size:17px;font-weight:800;margin-top:8px}
.page button.primary{background:#00BFFF;color:#fff}
.page h2{color:#fff}
/* Login */
.loginBox{padding:80px 20px;text-align:center;background:#000;color:#fff;min-height:100vh}
.loginBox input,.loginBox select{width:100%;padding:14px;margin:8px 0;border-radius:10px;border:0;font-size:16px;background:#fff;color:#000}
.loginBox button{width:100%;padding:14px;background:#00BFFF;color:#fff;border:0;border-radius:10px;font-size:18px;font-weight:800}
.row{display:flex;gap:8px}.row select{width:35%}.row input{width:65%}
.profilePreview{width:90px;height:90px;border-radius:50%;object-fit:cover;background:#333;display:block;margin:10px auto;border:3px solid #fff}
/* 4. HAMBURGER - PURE WHITE */
.drawer{position:fixed;top:0;left:-85%;width:85%;height:100%;background:#fff;color:#000;z-index:100;transition:0.3s;padding:20px;overflow-y:auto;box-shadow:5px 0 20px rgba(0,0,0,.5)}
.drawer.open{left:0}
.drawer h3{margin-top:0;color:#000}.drawer a,.drawer button{display:block;width:100%;text-align:left;padding:12px;background:#f2f2f2;border:0;border-radius:10px;margin:6px 0;font-size:16px;color:#000;text-decoration:none;font-weight:600}
.overlay{position:fixed;inset:0;background:rgba(0,0,0,.5);display:none;z-index:90}.overlay.show{display:block}
/* News Cards */
.newsCard{background:#fff;color:#000;border-radius:14px;padding:14px;margin:10px 0;display:flex;gap:10px;align-items:center;text-decoration:none}
.newsCard b{font-size:16px}.newsCard span{font-size:13px;color:#555}
.newsCard .icon{font-size:30px}
/* Games */
.gameCard{background:#fff;color:#000;border-radius:14px;padding:16px;margin:10px 0}
.gameCard button{background:#00BFFF;color:#fff;border:0;padding:10px;border-radius:8px;width:100%;font-weight:800}
/* Bottom */
.bottom{position:fixed;bottom:0;left:0;right:0;display:flex;justify-content:space-around;background:#111;padding:10px 0;border-top:1px solid #333;z-index:60}
.bottom button{background:none;border:0;color:#fff;font-size:22px}.bottom button.active{color:#00BFFF}
/* Tutorial */
.tutorial{position:fixed;inset:0;background:rgba(0,0,0,.92);z-index:200;display:none;padding:30px 20px;text-align:center;overflow-y:auto}
.tutorial.show{display:block}
.tutorial button{background:#00BFFF;color:#fff;border:0;padding:14px;border-radius:10px;width:100%;font-weight:800;margin-top:12px}
.step{background:#fff;color:#000;border-radius:12px;padding:14px;margin:10px 0;text-align:left}
</style>
</head>
<body>

<!-- TOP BAR SKY BLUE -->
<div class="top">
  <div class="logo">MTfy<span>•</span></div>
  <div class="topIcons">
    <button onclick="showPage('feed')" id="topHome" title="Home">🏠</button>
    <button onclick="showPage('news')" id="topNews" title="News">📰</button>
    <button onclick="showPage('games')" id="topGames" title="Games">🎮</button>
    <button onclick="openDrawer()" title="Menu">☰</button>
    <button onclick="showPage('settings')" id="topSettings" title="Settings">⚙️</button>
  </div>
</div>

<!-- HAMBURGER DRAWER PURE WHITE -->
<div class="overlay" id="overlay" onclick="closeDrawer()"></div>
<div class="drawer" id="drawer">
  <h3>MTfy Menu ☰</h3>
  <p id="drawerUser" style="color:#555">Guest</p>
  <button onclick="showPage('feed');closeDrawer()">🏠 Home Feed</button>
  <button onclick="showPage('news');closeDrawer()">📰 African News</button>
  <button onclick="showPage('games');closeDrawer()">🎮 Games</button>
  <button onclick="showPage('upload');closeDrawer()">➕ Upload Video</button>
  <button onclick="showPage('profile');closeDrawer()">👤 My Profile</button>
  <button onclick="showPage('settings');closeDrawer()">⚙️ Settings & Language</button>
  <button onclick="showTutorial();closeDrawer()">❓ How To Use MTfy - Tutorial</button>
  <button onclick="logout()">🚪 Logout</button>
  <p style="font-size:12px;color:#888;text-align:center;margin-top:20px">MTfy v2.0 • Made in Uganda 🇺🇬<br>Africa's Super App</p>
</div>

<!-- LOGIN -->
<div id="loginPage" class="loginBox">
<h1>MTfy 🇺🇬🇳🇬🇰🇪</h1><p style="color:#fff">Africa's Super App - TikTok + News + Games</p>
<img id="previewImg" class="profilePreview" src="https://via.placeholder.com/90?text=👤">
<label style="font-size:14px">Profile Photo</label>
<input type="file" id="profileFile" accept="image/*" onchange="previewProfile(this)">
<input id="fullname" placeholder="Full Names e.g. Opejo Benjamin">
<input id="user" placeholder="Username e.g. benjamin_ug">
<!-- 6. COUNTRY CODE, NO DEMO NUMBER -->
<div class="row">
<select id="countryCode">
<option value="+256">🇺🇬 +256 Uganda</option>
<option value="+254">🇰🇪 +254 Kenya</option>
<option value="+234">🇳🇬 +234 Nigeria</option>
<option value="+233">🇬🇭 +233 Ghana</option>
<option value="+27">🇿🇦 +27 South Africa</option>
<option value="+255">🇹🇿 +255 Tanzania</option>
<option value="+250">🇷🇼 +250 Rwanda</option>
<option value="+256">🇺🇬 +256</option>
<option value="+20">🇪🇬 +20 Egypt</option>
<option value="+212">🇲🇦 +212 Morocco</option>
<option value="+251">🇪🇹 +251 Ethiopia</option>
<option value="+263">🇿🇼 +263 Zimbabwe</option>
<option value="+260">🇿🇲 +260 Zambia</option>
<option value="+1">🇺🇸 +1 USA</option>
<option value="+44">🇬🇧 +44 UK</option>
</select>
<input id="phone" placeholder="Phone number" inputmode="numeric">
</div>
<button onclick="login()">Join MTfy →</button>
<p id="msg"></p>
<button onclick="showTutorial()" style="background:#fff;color:#000;margin-top:10px">📖 How To Use MTfy? Watch Tutorial</button>
</div>

<!-- FEED -->
<div id="feed" style="display:none"></div>

<!-- NEWS PAGE -->
<div id="newsPage" class="page">
<h2>📰 Top News in Africa</h2>
<p style="color:#ccc">Tap to read - MTfy sends you to the outlet, we don't copy their news.</p>
<a class="newsCard" href="https://www.bbc.com/africa" target="_blank"><span class="icon">🌍</span><div><b>BBC Africa</b><br><span>Breaking news across Africa</span></div><span>→</span></a>
<a class="newsCard" href="https://www.aljazeera.com/africa/" target="_blank"><span class="icon">📺</span><div><b>Al Jazeera Africa</b><br><span>Africa in-depth</span></div><span>→</span></a>
<a class="newsCard" href="https://www.monitor.co.ug" target="_blank"><span class="icon">🇺🇬</span><div><b>Daily Monitor - Uganda</b><br><span>Uganda's top newspaper</span></div><span>→</span></a>
<a class="newsCard" href="https://www.ntv.co.ug" target="_blank"><span class="icon">📡</span><div><b>NTV Uganda</b><br><span>News & Videos</span></div><span>→</span></a>
<a class="newsCard" href="https://www.newvision.co.ug" target="_blank"><span class="icon">📰</span><div><b>New Vision - Uganda</b><br><span>Uganda news</span></div><span>→</span></a>
<a class="newsCard" href="https://www.citizen.digital" target="_blank"><span class="icon">🇰🇪</span><div><b>Citizen Digital - Kenya</b><br><span>Kenya breaking news</span></div><span>→</span></a>
<a class="newsCard" href="https://punchng.com" target="_blank"><span class="icon">🇳🇬</span><div><b>Punch - Nigeria</b><br><span>Nigeria's most read</span></div><span>→</span></a>
<a class="newsCard" href="https://www.theeastafrican.co.ke" target="_blank"><span class="icon">🌍</span><div><b>The East African</b><br><span>East Africa region</span></div><span>→</span></a>
<a class="newsCard" href="https://www.sabcnews.com" target="_blank"><span class="icon">🇿🇦</span><div><b>SABC News - South Africa</b><br><span>South Africa</span></div><span>→</span></a>
<a class="newsCard" href="https://www.ghanaweb.com" target="_blank"><span class="icon">🇬🇭</span><div><b>GhanaWeb</b><br><span>Ghana news</span></div><span>→</span></a>
</div>

<!-- GAMES PAGE -->
<div id="gamesPage" class="page">
<h2>🎮 MTfy Games</h2>
<div class="gameCard"><h3>🔥 Tap Challenge</h3><p>Score: <b id="tapScore">0</b></p><button onclick="tapGame()">TAP ME! 👆</button></div>
<div class="gameCard"><h3>🎲 Guess The Number (1-10)</h3><p id="guessMsg">I'm thinking of a number...</p><input id="guessInput" type="number" placeholder="1-10"><button onclick="guessGame()">Guess</button></div>
<div class="gameCard"><h3>🧠 Quick Maths</h3><p id="mathQ">5 + 3 = ?</p><input id="mathAns" type="number" placeholder="Answer"><button onclick="mathGame()">Check</button><p id="mathMsg"></p></div>
<div class="gameCard"><h3>🌍 More Games Coming</h3><p>Ludo, Football Quiz, Memory Game - coming in MTfy v3.0</p></div>
</div>

<!-- UPLOAD -->
<div id="uploadPage" class="page">
<h2>Upload Video 🎥</h2>
<input type="file" id="videoFile" accept="video/*">
<textarea id="caption" placeholder="Caption... #Kampala #MTfy"></textarea>
<button class="primary" onclick="uploadVideo()">Post Video →</button><p id="upMsg"></p>
</div>

<!-- PROFILE -->
<div id="profilePage" class="page">
<img id="profilePageImg" class="profilePreview" src="https://via.placeholder.com/90?text=👤">
<h2 id="profileName">Profile</h2><p id="profileInfo"></p>
<button onclick="showPage('upload')">➕ Upload New Video</button>
<button onclick="logout()">🚪 Logout</button>
</div>

<!-- SETTINGS -->
<div id="settingsPage" class="page">
<h2>⚙️ Settings</h2>
<label>🌍 Choose Language</label>
<select id="langSelect" onchange="changeLang(this.value)">
<option value="en">English</option>
<option value="sw">Kiswahili - Swahili</option>
<option value="lg">Luganda - Uganda</option>
<option value="yo">Yoruba - Nigeria</option>
<option value="ha">Hausa - Nigeria / Niger</option>
<option value="ig">Igbo - Nigeria</option>
<option value="am">Amharic - Ethiopia</option>
<option value="zu">Zulu - South Africa</option>
<option value="xh">Xhosa - South Africa</option>
<option value="fr">Français - French</option>
<option value="ar">Arabic - العربية</option>
<option value="so">Somali - Somalia</option>
<option value="tw">Twi - Ghana</option>
<option value="rw">Kinyarwanda - Rwanda</option>
</select>
<p id="langMsg" style="color:#00BFFF"></p>
<label>👤 Account</label>
<button onclick="logout()">🚪 Logout</button>
<button onclick="loginAgain()">🔑 Login / Switch Account</button>
<button onclick="showTutorial()">📖 Tutorial - How To Navigate</button>
<p style="font-size:12px;color:#aaa">MTfy v2.0 • Language is saved on your phone.</p>
</div>

<!-- BOTTOM NAV -->
<div class="bottom" id="bottomNav" style="display:none">
<button onclick="showPage('feed')" id="btnFeed" class="active">🏠<br><span style="font-size:11px">Home</span></button>
<button onclick="showPage('news')" id="btnNews">📰<br><span style="font-size:11px">News</span></button>
<button onclick="showPage('games')" id="btnGames">🎮<br><span style="font-size:11px">Games</span></button>
<button onclick="showPage('upload')" id="btnUpload">➕<br><span style="font-size:11px">Upload</span></button>
<button onclick="showPage('profile')" id="btnProfile">👤<br><span style="font-size:11px">Me</span></button>
</div>

<!-- TUTORIAL -->
<div class="tutorial" id="tutorial">
<h1>Welcome to MTfy! 🇺🇬</h1><p>Africa's Super App - How To Navigate</p>
<div class="step"><b>1. Top Sky Blue Bar:</b><br>🏠 Home = Videos<br>📰 News = Top African news<br>🎮 Games = Play games<br>☰ Menu = White menu<br>⚙️ Settings = Language + Logout</div>
<div class="step"><b>2. Swipe Up:</b><br>Like TikTok, swipe up to see next video. Tap ❤️ to like, 💬 to comment.</div>
<div class="step"><b>3. Upload:</b><br>Tap ➕ at bottom → Choose video → Add caption → Post. Your video shows for everyone!</div>
<div class="step"><b>4. News:</b><br>Tap 📰 → Choose BBC, NTV, Monitor → Read full story on their site. MTfy does NOT copy news.</div>
<div class="step"><b>5. Games:</b><br>Tap 🎮 → Play Tap Challenge, Guess Number, Maths. More games soon.</div>
<div class="step"><b>6. Settings:</b><br>Tap ⚙️ → Choose your language: Luganda, Swahili, Yoruba, Hausa, etc. + Logout.</div>
<div class="step"><b>7. Profile:</b><br>Tap 👤 → See your Full Name, Username, Phone, Photo.</div>
<button onclick="closeTutorial()">Got It! Start Using MTfy →</button>
</div>

<script>
const SUPABASE_URL = "https://nzmwvowbonbhhwtnxbpv.supabase.co";
const SUPABASE_KEY = "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Im56bXd2b3dwYm9oYmh3dG5xYnBvIiwicm9sZSI6ImFub24iLCJpYXQiOjE3OTU3NzQ5OTksImV4cCI6MjExMTM1MDk5OX0.ogOSrStaF_FlK9htWZ6N53tU3rF5sUsUoemQlwz_2Bs";
const supabaseClient = supabase.createClient(SUPABASE_URL, SUPABASE_KEY);
let currentUser = localStorage.getItem('mtfy_user') || '';
let profilePicData = localStorage.getItem('mtfy_pic') || '';

function openDrawer(){ document.getElementById('drawer').classList.add('open'); document.getElementById('overlay').classList.add('show'); document.getElementById('drawerUser').innerText = currentUser ? "@"+currentUser+" • "+(localStorage.getItem('mtfy_name')||"") : "Guest - Please Login"; }
function closeDrawer(){ document.getElementById('drawer').classList.remove('open'); document.getElementById('overlay').classList.remove('show'); }
function showTutorial(){ document.getElementById('tutorial').classList.add('show'); }
function closeTutorial(){ document.getElementById('tutorial').classList.remove('show'); localStorage.setItem('mtfy_seen_tutorial','1'); }
function previewProfile(input){ const f=input.files[0]; if(!f) return; const r=new FileReader(); r.onload=e=>{ profilePicData=e.target.result; document.getElementById('previewImg').src=profilePicData; }; r.readAsDataURL(f); }

function showFeedUI(){
  document.getElementById('loginPage').style.display='none';
  document.getElementById('bottomNav').style.display='flex';
  document.getElementById('profileName').innerText="@"+currentUser;
  document.getElementById('profileInfo').innerText="Name: "+(localStorage.getItem('mtfy_name')||currentUser)+"\nPhone: "+(localStorage.getItem('mtfy_fullphone')||"");
  if(profilePicData) document.getElementById('profilePageImg').src=profilePicData;
}
function showPage(p){
  closeDrawer();
  // hide all
  document.getElementById('feed').style.display='none';
  ['newsPage','gamesPage','uploadPage','profilePage','settingsPage'].forEach(id=>document.getElementById(id).classList.remove('active'));
  document.querySelectorAll('.topIcons button').forEach(b=>b.classList.remove('active'));
  document.querySelectorAll('.bottom button').forEach(b=>b.classList.remove('active'));
  if(p==='feed'){ document.getElementById('feed').style.display='block'; document.getElementById('topHome').classList.add('active'); document.getElementById('btnFeed').classList.add('active'); loadFeed(); }
  if(p==='news'){ document.getElementById('newsPage').classList.add('active'); document.getElementById('topNews').classList.add('active'); document.getElementById('btnNews').classList.add('active'); }
  if(p==='games'){ document.getElementById('gamesPage').classList.add('active'); document.getElementById('topGames').classList.add('active'); document.getElementById('btnGames').classList.add('active'); }
  if(p==='upload'){ document.getElementById('uploadPage').classList.add('active'); document.getElementById('btnUpload').classList.add('active'); }
  if(p==='profile'){ document.getElementById('profilePage').classList.add('active'); document.getElementById('btnProfile').classList.add('active'); }
  if(p==='settings'){ document.getElementById('settingsPage').classList.add('active'); document.getElementById('topSettings').classList.add('active'); }
}
async function login(){
  const name=document.getElementById('fullname').value.trim();
  const username=document.getElementById('user').value.trim();
  const code=document.getElementById('countryCode').value;
  const phone=document.getElementById('phone').value.trim();
  if(!name||!username||!phone){document.getElementById('msg').innerText="Fill Full Name + Username + Phone";return;}
  const fullPhone=code+phone;
  localStorage.setItem('mtfy_user',username); localStorage.setItem('mtfy_name',name); localStorage.setItem('mtfy_fullphone',fullPhone); if(profilePicData) localStorage.setItem('mtfy_pic',profilePicData);
  currentUser=username; document.getElementById('msg').innerText="Joining...";
  try{ await supabaseClient.from('profiles').insert([{full_name:name,username:username,phone:fullPhone}]); }catch(e){ console.log(e); }
  showFeedUI(); showPage('feed'); if(!localStorage.getItem('mtfy_seen_tutorial')) showTutorial();
}
async function loadFeed(){
  try{
    const {data,error}=await supabaseClient.from('posts').select('*').order('created_at',{ascending:false});
    if(error) throw error; if(!data||data.length===0) throw new Error("empty");
    renderFeed(data);
  }catch(e){
    renderFeed([{id:'demo1',username:'mtfy',caption:'Welcome to MTfy v2! 🇺🇬 Tap ➕ to post YOUR video! Top = News & Games',video_url:'https://interactive-examples.mdn.mozilla.net/media/cc0-videos/flower.mp4',likes_count:13}]);
  }
}
function renderFeed(data){
  const feed=document.getElementById('feed'); feed.innerHTML='';
  data.forEach(p=>{
    const div=document.createElement('div'); div.className='post';
    div.innerHTML=`<video src="${p.video_url}" loop muted autoplay playsinline controls preload="metadata"></video>
    <div class="info"><div class="user">@${p.username||'mtfy'}</div><div class="cap">${p.caption||''}</div></div>
    <div class="actions"><button class="likeBtn" onclick="likePost('${p.id}',this,${p.likes_count||0})">❤️</button><span id="c-${p.id}" style="color:#fff">${p.likes_count||0}</span>
    <button class="cmtBtn" onclick="alert('Comments coming in v3 - For now like & share!')">💬</button>
    <button class="cmtBtn" onclick="sharePost()">↗️</button></div>`;
    feed.appendChild(div);
  });
}
async function likePost(id,btn,count){ if(btn.classList.contains('liked')) return; btn.classList.add('liked'); document.getElementById('c-'+id).innerText=count+1; try{ if(!id.startsWith('demo')) await supabaseClient.from('posts').update({likes_count:count+1}).eq('id',id); }catch(e){} }
async function uploadVideo(){
  const file=document.getElementById('videoFile').files[0]; const caption=document.getElementById('caption').value;
  <!-- PART 2 - PASTE AFTER PART 1 -->
Select a video first";return;}
  document.getElementById('upMsg').innerText="Uploading...";
  try{
    const fileName=Date.now()+"_"+file.name.replace(/\s/g,'_');
    const {error:upErr}=await supabaseClient.storage.from('videos').upload(fileName,file);
    if(upErr) throw upErr;
    const {data:urlData}=supabaseClient.storage.from('videos').getPublicUrl(fileName);
    const {error}=await supabaseClient.from('posts').insert([{username:currentUser,caption:caption,video_url:urlData.publicUrl,likes_count:0}]);
    if(error) throw error;
    document.getElementById('upMsg').innerText="✅ Posted!";
    showPage('feed');
  }catch(e){ document.getElementById('upMsg').innerText="Upload failed: "+e.message; }
}
function sharePost(){
  if(navigator.share){ navigator.share({title:'MTfy',text:'Watch on MTfy - Africa\'s Super App',url:location.href}); }
  else{ alert("Link copied! Share on WhatsApp"); }
}
function logout(){ localStorage.removeItem('mtfy_user'); location.reload(); }
function loginAgain(){ localStorage.removeItem('mtfy_user'); location.reload(); }

// --- GAMES ---
let tap=0;
function tapGame(){ tap++; document.getElementById('tapScore').innerText=tap; }
let secret=Math.floor(Math.random()*10)+1;
function guessGame(){
  const g=parseInt(document.getElementById('guessInput').value);
  document.getElementById('guessMsg').innerText = g===secret ? "🎉 Correct! New number..." : g<secret ? "Too low ⬆️" : "Too high ⬇️";
  if(g===secret) secret=Math.floor(Math.random()*10)+1;
}
let a=5,b=3;
function mathGame(){
  const ans=parseInt(document.getElementById('mathAns').value);
  if(ans===a+b){ document.getElementById('mathMsg').innerText="✅ Correct!"; a=Math.floor(Math.random()*10); b=Math.floor(Math.random()*10); document.getElementById('mathQ').innerText=a+" + "+b+" = ?"; }
  else document.getElementById('mathMsg').innerText="❌ Try again!";
}

// --- LANGUAGE ---
function changeLang(v){
  const names={en:"English",sw:"Kiswahili",lg:"Luganda",yo:"Yoruba",ha:"Hausa",ig:"Igbo",am:"Amharic",zu:"Zulu",xh:"Xhosa",fr:"Français",ar:"Arabic",so:"Somali",tw:"Twi",rw:"Kinyarwanda"};
  localStorage.setItem('mtfy_lang',v);
  document.getElementById('langMsg').innerText="✅ Language set to "+names[v];
  document.getElementById('langSelect').value=v;
}

// --- START APP ---
if(localStorage.getItem('mtfy_lang')) document.getElementById('langSelect').value=localStorage.getItem('mtfy_lang');
if(profilePicData) document.getElementById('previewImg').src=profilePicData;
if(currentUser){ showFeedUI(); showPage('feed'); }
</script>
</body>
</html>
