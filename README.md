<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MTfy Uganda - Make It Finally 🇺🇬</title>
<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:Arial,sans-serif}
body{background:repeating-linear-gradient(115deg, rgba(255,255,255,0.25) 0px, rgba(255,255,255,0) 2px, rgba(0,0,0,0.15) 3px, rgba(0,0,0,0) 5px),linear-gradient(135deg,#FFF7A8 0%, #FFD700 15%, #C9A227 30%, #8B6508 45%, #FFEC8B 55%, #D4AF37 65%, #B8860B 80%, #5C3317 100%);background-attachment:fixed;color:#111;padding-bottom:90px;padding-top:96px;min-height:100vh}
.topbar{position:fixed;top:0;left:0;right:0;background:#5C3317;z-index:30;border-bottom:3px solid #FFD700;padding:6px 8px}
.topRow{display:flex;align-items:center;gap:8px}
.hamburger{font-size:24px;color:#FFD700;cursor:pointer;padding:5px 10px;background:#3B2108;border:1px solid #FFD700;border-radius:8px}
.brand{flex:1;text-align:center;color:#FFD700;font-weight:900;font-size:20px;line-height:1}.brand span{color:#fff}.brand small{display:block;font-size:9px;color:#E8DCC0}
.topIcons{display:flex;justify-content:space-around;background:#3B2108;border-radius:10px;margin-top:6px;padding:6px 2px}
.topIcons div{cursor:pointer;color:#fff;font-size:10px;text-align:center;flex:1;padding:3px}.topIcons div.active{color:#FFD700;background:#5C3317;border-radius:8px}.topIcons b{display:block;font-size:18px}
.menu{position:fixed;top:58px;left:10px;background:#fff;border:2px solid #5C3317;border-radius:14px;width:250px;z-index:40;display:none;box-shadow:0 10px 25px rgba(0,0,0,0.4);overflow:hidden;max-height:80vh;overflow-y:auto}
.menu a{display:block;padding:13px 16px;text-decoration:none;color:#111;border-bottom:1px solid #F0D060;font-weight:bold;font-size:14px}
.menu .menu-head{background:#5C3317;color:#FFD700;padding:14px 16px;font-weight:900;text-align:center}.menu .menu-head small{display:block;color:#E8DCC0;font-size:11px}
.langs{display:flex;gap:4px;justify-content:center;margin:8px 6px;flex-wrap:wrap}
.langs button{background:#3B2108;color:#FFD700;border:1px solid #FFD700;padding:4px 8px;border-radius:12px;font-size:10px;font-weight:bold}.langs button.active{background:#FFD700;color:#3B2108}
.card{margin:10px;background:#fff;border-radius:14px;overflow:hidden;border:2px solid #5C3317}
.video{height:220px;background:linear-gradient(135deg,#FFD700,#B8860B,#5C3317);display:flex;align-items:center;justify-content:center;font-size:55px}
.info{padding:12px}.user{font-weight:bold}.user small{color:#8B6508}.caption{margin:6px 0;color:#333;font-size:13px}
.actions{display:flex;gap:8px;padding-top:8px;border-top:1px solid #C9A227;font-size:13px;font-weight:bold}.actions span{cursor:pointer;background:#FFF8DC;padding:5px 9px;border-radius:20px;border:1px solid #C9A227}
.btn{display:block;margin:12px;background:#5C3317;color:#FFD700;text-align:center;padding:14px;border-radius:30px;font-weight:bold;text-decoration:none}
.bottom{position:fixed;bottom:0;left:0;right:0;background:#5C3317;display:flex;justify-content:space-around;padding:10px;border-top:3px solid #FFD700;font-size:10px;color:#fff;text-align:center;z-index:30}.bottom div{cursor:pointer;flex:1}.bottom div.active{color:#FFD700}
.pageBox{background:#fff;margin:12px;padding:18px;border-radius:14px;border:2px solid #5C3317;text-align:center}
.pageBox button{padding:11px 18px;background:#5C3317;color:#FFD700;border:none;border-radius:20px;font-weight:bold;margin:6px}
.pageBox input, .pageBox textarea{width:100%;padding:11px;margin:6px 0;border-radius:10px;border:2px solid #C9A227;background:#FFF8DC}
.shareBtn{display:block;padding:12px;margin:8px 0;border-radius:12px;color:#fff;font-weight:bold;text-decoration:none;text-align:center}
.chat{ text-align:left;background:#FFF8DC;padding:10px;border-radius:12px;margin:8px 0;border:1px solid #C9A227}
.gameCard{background:#FFF8DC;border:2px solid #C9A227;border-radius:12px;padding:12px;margin:10px 0}
.marketCard{background:#FFF8DC;border:2px solid #C9A227;border-radius:12px;padding:12px;margin:10px 0;text-align:left}
</style>
</head>
<body>

<!-- TOP BAR + HAMBURGER LEFT -->
<div class="topbar">
<div class="topRow">
<div class="hamburger" onclick="toggleMenu()">☰</div>
<div class="brand">MT<span>fy</span> 🇺🇬<small>MTfy Uganda - Make It Finally</small></div>
<div style="width:44px;text-align:right;font-size:22px;cursor:pointer" onclick="showPage('fans')">🔔</div>
</div>
<div class="topIcons">
<div id="t-me" onclick="showPage('me')"><b>👤</b>Me</div>
<div id="t-fans" onclick="showPage('fans')"><b>❤️</b>My Fans</div>
<div id="t-news" onclick="showPage('news')"><b>📰</b>News</div>
<div id="t-market" onclick="showPage('market')"><b>🛒</b>Market</div>
<div id="t-games" onclick="showPage('games')"><b>🎮</b>Games</div>
</div>
</div>

<!-- HAMBURGER MENU LEFT -->
<div id="sideMenu" class="menu">
<div class="menu-head">MTfy Uganda 🇺🇬<small>Ateso • Acholi • Luganda • English</small></div>
<a href="#" onclick="goMenu('home')">🏠 Home</a>
<a href="#" onclick="goMenu('me')">👤 My Profile - Me</a>
<a href="#" onclick="goMenu('fans')">❤️ My Fans</a>
<a href="#" onclick="goMenu('news')">📰 News</a>
<a href="#" onclick="goMenu('market')">🛒 Marketplace</a>
<a href="#" onclick="goMenu('games')">🎮 Games</a>
<a href="#" onclick="openPage('terms')">📜 Terms and Conditions</a>
<a href="#" onclick="openPage('privacy')">🔒 Privacy Policy</a>
<a href="#" onclick="openPage('ads')">📢 Ads - Promote Your Business</a>
<a href="#" onclick="openPage('admin')">💬 Admin Chat - Talk to Opejo</a>
<a href="#" onclick="openPage('settings')">⚙️ Settings</a>
<a href="#" onclick="openPage('share')">↗️ Share MTfy Uganda</a>
<a href="#" onclick="alert('Logged out. Apai, see you soon!')">🚪 Logout</a>
</div>

<div class="langs">
<button class="active" onclick="setLang(this)">English</button>
<button onclick="setLang(this)">Ateso</button>
<button onclick="setLang(this)">Acholi</button>
<button onclick="setLang(this)">Luganda</button>
<button onclick="setLang(this)">Kiswahili</button>
</div>

<!-- HOME -->
<div id="homePage">
<div class="pageBox"><h2 style="font-size:18px">Welcome to MTfy Uganda 🔥</h2><p style="color:#666;font-size:12px">Login to watch & upload</p><input placeholder="Phone: 0770123456" value="0770123456" style="width:100%;padding:11px;margin:6px 0;border-radius:10px;border:2px solid #C9A227;background:#FFF8DC"><input placeholder="OTP" value="1234" style="width:100%;padding:11px;margin:6px 0;border-radius:10px;border:2px solid #C9A227;background:#FFF8DC"><button onclick="alert('Welcome! Apai!')">LOGIN WITH OTP →</button></div>
<div class="card"><div class="video">🎥</div><div class="info"><div class="user">@ateso_star <small>• Soroti</small></div><div class="caption">Apai! My first dance! 🇺🇬 #MTfyUganda</div><div class="actions"><span onclick="like(this)">❤️ 12.4K</span><span onclick="openPage('share')">↗️ Share</span><span onclick="follow(this)">➕ Follow</span></div></div></div>
<div class="card"><div class="video">🎤</div><div class="info"><div class="user">@acholi_queen <small>• Gulu</small></div><div class="caption">Acholi dance! Ber! #MTfyUganda</div><div class="actions"><span onclick="like(this)">❤️ 8.9K</span><span onclick="openPage('share')">↗️ Share</span><span onclick="follow(this)">➕ Follow</span></div></div></div>
<a class="btn" href="#" onclick="showPage('upload');return false;">＋ UPLOAD YOUR VIDEO</a>
</div>

<!-- TOP PAGES -->
<div id="mePage" class="pageBox" style="display:none"><h2>👤 @opejo_benjamin</h2><p>Soroti, Uganda 🇺🇬 | Founder</p><p>0 Following • 1.2K Fans • 0 Likes</p><br><p>Tap My Fans to see who loves you!</p><button onclick="showPage('fans')">❤️ See My Fans</button><button onclick="showPage('home')">← Home</button></div>

<div id="fansPage" class="pageBox" style="display:none"><h2>❤️ My Fans - Meet Your Fans</h2><p style="color:#666">These fans love your videos! Chat with them = Retention!</p>
<div class="chat"><b>@ateso_star ❤️</b><br>Apai! Your dance is fire! When is next video?</div>
<div class="chat"><b>@acholi_queen ❤️</b><br>Ber! I followed you, follow back?</div>
<div class="chat"><b>@kampala_food ❤️</b><br>Oli Otya? Let's collab on Luwombo video!</div>
<input id="fanMsg" placeholder="Reply to your fans... Apai!"><button onclick="replyFan()">💬 SEND REPLY</button><button onclick="showPage('home')">← Home</button></div>

<div id="newsPage" class="pageBox" style="display:none"><h2>📰 MTfy News - Uganda</h2>
<div class="chat"><b>🇺🇬 Soroti:</b> MTfy Uganda launches! 1000 users in first week!</div>
<div class="chat"><b>⚽ Sports:</b> Uganda Cranes win! Fans celebrate in Kampala.</div>
<div class="chat"><b>🎵 Music:</b> New Acholi hit trending on MTfy!</div>
<div class="chat"><b>🌧️ Weather:</b> Rain in Soroti today, stay safe!</div>
<button onclick="alert('News updated! Come back every morning for fresh news = Retention!')">🔄 Refresh News</button><button onclick="showPage('home')">← Home</button></div>

<div id="marketPage" class="pageBox" style="display:none"><h2>🛒 Marketplace - Buy & Sell</h2><p style="color:#666">Sell to your fans! Buy from Uganda!</p>
<div class="marketCard">👕 <b>MTfy T-Shirt - UGX 30,000</b><br>Soroti • 📞 0770123456<br><button onclick="alert('Seller contacted! They will WhatsApp you!')">💬 Chat Seller</button></div>
<div class="marketCard">🍲 <b>Luwombo Ingredients - UGX 15,000</b><br>Kampala<br><button onclick="alert('Seller contacted!')">💬 Chat Seller</button></div>
<div class="marketCard">🎸 <b>Adungu Instrument - UGX 80,000</b><br>Gulu<br><button onclick="alert('Seller contacted!')">💬 Chat Seller</button></div>
<button onclick="alert('Your product listed! Your fans will see it!')">＋ SELL SOMETHING</button><button onclick="showPage('home')">← Home</button></div>

<div id="gamesPage" class="pageBox" style="display:none"><h2>🎮 Games - Play & Win!</h2><p style="color:#666">Play daily = Come back daily!</p>
<div class="gameCard"><b>🎲 Spin & Win</b><br>Daily free spin! Win up to UGX 5,000<br><button onclick="spinGame()">🎲 SPIN NOW</button><p id="spinResult"></p></div>
<div class="gameCard"><b>🧠 Uganda Quiz</b><br>What is capital of Uganda?<br><button onclick="alert('Correct! Kampala! You earned 100 points! 🎉')">A) Kampala</button><button onclick="alert('Wrong! Try again!')">B) Gulu</button><button onclick="alert('Wrong! Try again!')">C) Soroti</button></div>
<div class="gameCard"><b>🔢 Guess Number 1-10</b><br><button onclick="guessGame()">🎯 GUESS</button><p id="guessResult"></p></div>
<button onclick="showPage('home')">← Home</button></div>

<!-- BOTTOM PAGES -->
<div id="discoverPage" class="pageBox" style="display:none"><h2>🔍 Discover</h2><p>🔥 #MTfyUganda #SorotiDance</p><br><button onclick="showPage('home')">← Back</button></div>
<div id="uploadPage" class="pageBox" style="display:none"><h2>＋ Upload</h2>
<input type="file" id="fileInput" accept="video/*,image/*" style="display:none" onchange="previewFile(this)"><button onclick="document.getElementById('fileInput').click()">📁 GALLERY</button><br>
<input type="file" id="cameraInput" accept="video/*,image/*" capture="environment" style="display:none" onchange="previewFile(this)"><button onclick="document.getElementById('cameraInput').click()">🎥 CAMERA</button>
<video id="preview" controls style="width:100%;max-height:300px;display:none;border-radius:12px;margin-top:10px"></video><img id="previewImg" style="width:100%;display:none;border-radius:12px;margin-top:10px">
<p id="uploadStatus"></p><button onclick="postVideo()">✅ POST</button><br><button onclick="showPage('home')">← Back</button></div>
<div id="inboxPage" class="pageBox" style="display:none"><h2>💬 Inbox</h2><p>👤 @ateso_star: Apai! ❤️</p><br><button onclick="showPage('home')">← Back</button></div>
<div id="meetFansPage" class="pageBox" style="display:none"><h2>💬❤️ Meet Your Fans - LIVE Chat</h2><p style="color:#666">This is your FAN chat! Your fans are waiting!</p><div class="chat"><b>@soroti_boy:</b> Big fan! 🔥</div><div class="chat"><b>@gulu_girl:</b> Post more Acholi dance please!</div><input id="meetMsg" placeholder="Chat with your fans..."><button onclick="replyMeet()">💬 SEND TO FANS</button><button onclick="showPage('home')">← Home</button></div>

<!-- MENU PAGES -->
<div id="termsPage" class="pageBox" style="display:none"><h2>📜 Terms and Conditions</h2><p style="text-align:left;font-size:13px;line-height:1.6">1. MTfy Uganda is made by Opejo Benjamin in Soroti, Uganda.<br>2. Be respectful. No hate, no bad videos.<br>3. You own your videos. MTfy can show them to promote Uganda.<br>4. No selling fake things in Marketplace.<br>5. Be 13+ to use MTfy.<br>6. Make It Finally - but make it with love! 🇺🇬</p><button onclick="showPage('home')">← I Agree, Back Home</button></div>
<div id="privacyPage" class="pageBox" style="display:none"><h2>🔒 Privacy Policy</h2><p style="text-align:left;font-size:13px;line-height:1.6">• We only ask your phone number to login.<br>• We NEVER share your PIN, OTP or password.<br>• Your videos are public if you post them.<br>• Your private chats stay private.<br>• You can delete your account anytime - ask Admin Chat.<br>• MTfy Uganda respects Uganda Data Protection Law.</p><button onclick="showPage('home')">← Back</button></div>
<div id="adsPage" class="pageBox" style="display:none"><h2>📢 Ads - Promote With MTfy</h2><p>Reach 1000s in Soroti, Gulu, Kampala!</p><div class="marketCard"><b>🥉 Starter - UGX 20,000 / day</b><br>Your ad on Home page</div><div class="marketCard"><b>🥇 Pro - UGX 50,000 / day</b><br>Home + Discover + Top banner</div><button onclick="alert('Thank you! Admin will WhatsApp you to start your Ad!')">🚀 START MY AD</button><button onclick="showPage('home')">← Back</button></div>
<div id="adminPage" class="pageBox" style="display:none"><h2>💬 Admin Chat - Talk to Opejo</h2><p>Direct to Founder of MTfy Uganda!</p><div class="chat"><b>👤 Admin Opejo:</b> Apai! Welcome to MTfy! How can I help you today? 🇺🇬</div><input id="adminMsg" placeholder="Type to Admin..."><button onclick="replyAdmin()">💬 SEND TO ADMIN</button><button onclick="showPage('home')">← Back</button></div>
<div id="settingsPage" class="pageBox" style="display:none"><h2>⚙️ Settings</h2>
<p>Language: <button onclick="alert('Language changed!')">English ▼</button></p><p>Notifications: <button onclick="toggleSetting(this)">ON ✅</button></p><p>Dark Gold Mode: <button onclick="toggleSetting(this)">ON ✅</button></p><p>Auto-play Videos: <button onclick="toggleSetting(this)">OFF ❌</button></p><br><button onclick="showPage('home')">← Save & Back</button></div>
<div id="sharePage" class="pageBox" style="display:none"><h2>↗️ Share MTfy Uganda</h2><p>Help Uganda grow! Share to your friends!</p>
<a class="shareBtn" style="background:#25D366" href="https://wa.me/?text=Join%20MTfy%20Uganda%20-%20Make%20It%20Finally!%20https://opejo.github.io/mtf/" target="_blank">💬 Share on WhatsApp</a>
<a class="shareBtn" style="background:#1877F2" href="https://www.facebook.com/sharer/sharer.php?u=https://opejo.github.io/mtf/" target="_blank">📘 Share on Facebook</a>
<a class="shareBtn" style="background:#111" href="https://www.tiktok.com/" target="_blank">🎵 Share on TikTok - Copy Link</a>
<button onclick="copyLink()">🔗 Copy Link</button>
<button onclick="nativeShare()">↗️ Share to Any App (X, Instagram, SMS)</button>
<button onclick="showPage('home')">← Back</button></div>

<!-- BOTTOM BAR - ME REPLACED WITH MEET YOUR FANS -->
<div class="bottom">
<div id="nav-home" class="active" onclick="showPage('home')">🏠<br>Home</div>
<div id="nav-discover" onclick="showPage('discover')">🔍<br>Discover</div>
<div id="nav-upload" onclick="showPage('upload')">＋<br>Upload</div>
<div id="nav-inbox" onclick="showPage('inbox')">💬<br>Inbox</div>
<div id="nav-meetFans" onclick="showPage('meetFans')">💬❤️<br>Meet Fans</div>
</div>

<script>
function toggleMenu(){var m=document.getElementById('sideMenu');m.style.display=(m.style.display==='block'?'none':'block');}
function goMenu(p){document.getElementById('sideMenu').style.display='none';showPage(p);}
function openPage(p){document.getElementById('sideMenu').style.display='none';showPage(p);}
function setLang(btn){document.querySelectorAll('.langs button').forEach(b=>b.classList.remove('active'));btn.classList.add('active');alert('Language: '+btn.innerText);}
function like(el){el.innerText='❤️ Liked!';} function follow(el){el.innerText='✓ Following';}
function toggleSetting(btn){btn.innerText=(btn.innerText.includes('ON')?'OFF ❌':'ON ✅');}
function showPage(page){
  document.getElementById('sideMenu').style.display='none';
  var all=['homePage','mePage','fansPage','newsPage','marketPage','gamesPage','discoverPage','uploadPage','inboxPage','meetFansPage','termsPage','privacyPage','adsPage','adminPage','settingsPage','sharePage'];
  all.forEach(id=>document.getElementById(id).style.display='none');
  document.querySelectorAll('.bottom div').forEach(d=>d.classList.remove('active'));
  document.querySelectorAll('.topIcons div').forEach(d=>d.classList.remove('active'));
  var map={home:'homePage',me:'mePage',fans:'fansPage',news:'newsPage',market:'marketPage',games:'gamesPage',discover:'discoverPage',upload:'uploadPage',inbox:'inboxPage',meetFans:'meetFansPage',terms:'termsPage',privacy:'privacyPage',ads:'adsPage',admin:'adminPage',settings:'settingsPage',share:'sharePage'};
  document.getElementById(map[page]).style.display='block';
  var b=document.getElementById('nav-'+page); if(b) b.classList.add('active');
  var t=document.getElementById('t-'+page); if(t) t.classList.add('active');
  if(page==='meetFans') document.getElementById('nav-meetFans').classList.add('active');
  window.scrollTo(0,0);
}
function replyFan(){var v=document.getElementById('fanMsg').value; if(!v){alert('Type a reply first!');return;} alert('Sent to your fans: '+v+' ❤️'); document.getElementById('fanMsg').value='';}
function replyMeet(){var v=document.getElementById('meetMsg').value; if(!v){alert('Type a message!');return;} alert('Sent to ALL your fans: '+v+' 🎉'); document.getElementById('meetMsg').value='';}
function replyAdmin(){var v=document.getElementById('adminMsg').value; if(!v){alert('Type a message to Admin!');return;} alert('Sent to Admin Opejo! He will reply soon. ✅ Message: '+v); document.getElementById('adminMsg').value='';}
function spinGame(){var prizes=['UGX 500!','100 Points!','Try Again!','UGX 1,000!','Free Spin!']; var p=prizes[Math.floor(Math.random()*prizes.length)]; document.getElementById('spinResult').innerText='🎉 You won: '+p; alert('Spin result: '+p);}
function guessGame(){var n=prompt('Guess 1-10:'); if(!n) return; var win=Math.floor(Math.random()*10)+1; if(parseInt(n)===win){document.getElementById('guessResult').innerText='🎉 CORRECT! Number was '+win; alert('You WIN!');} else {document.getElementById('guessResult').innerText='Wrong! Number was '+win+' Try again!';}}
function previewFile(input){var f=input.files[0]; if(!f) return; var u=URL.createObjectURL(f); var v=document.getElementById('preview'); var im=document.getElementById('previewImg'); if(f.type.startsWith('video')){v.src=u;v.style.display='block';im.style.display='none';} else {im.src=u;im.style.display='block';v.style.display='none';} document.getElementById('uploadStatus').innerText='✅ Selected: '+f.name;}
function postVideo(){if(!document.getElementById('uploadStatus').innerText){alert('Choose video first!');return;} alert('🎉 Posted!'); showPage('home');}
function copyLink(){navigator.clipboard.writeText('https://opejo.github.io/mtf/'); alert('Link copied! Paste it on WhatsApp, Facebook, TikTok! https://opejo.github.io/mtf/');}
async function nativeShare(){var data={title:'MTfy Uganda',text:'Join MTfy Uganda - Make It Finally! 🇺🇬',url:'https://opejo.github.io/mtf/'}; if(navigator.share){try{await navigator.share(data);}catch(e){copyLink();}} else {copyLink();}}
document.addEventListener('click',function(e){if(!e.target.closest('.hamburger') && !e.target.closest('.menu')){d
