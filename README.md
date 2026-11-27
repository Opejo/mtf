<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MTfy Africa - Make It Finally</title>
<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:Arial,sans-serif}
body{background:linear-gradient(135deg,#FFF7A8,#FFD700,#C9A227,#FFEC8B,#D4AF37);background-attachment:fixed;color:#111;padding-bottom:95px;padding-top:102px}
.topbar{position:fixed;top:0;left:0;right:0;background:#fff;z-index:30;border-bottom:3px solid #FFD700;padding:6px 8px}
.topRow{display:flex;align-items:center;gap:8px}
.hamburger{font-size:24px;cursor:pointer;padding:5px 10px;background:#FFD700;border:1px solid #C9A227;border-radius:8px}
.brand{flex:1;text-align:center;font-weight:900;font-size:20px}.brand small{display:block;font-size:9px;color:#666;font-weight:normal}
.topIcons{display:flex;justify-content:space-around;background:#87CEEB;border-radius:10px;margin-top:6px;padding:6px 2px}
.topIcons div{cursor:pointer;font-size:10px;text-align:center;flex:1;padding:4px;font-weight:bold;border-radius:8px}.topIcons div.active{color:#fff;background:#111}
.menu{position:fixed;top:58px;left:10px;background:#fff;border:2px solid #FFD700;border-radius:14px;width:260px;z-index:40;display:none;box-shadow:0 10px 25px rgba(0,0,0,.4);max-height:82vh;overflow-y:auto}
.menu a{display:block;padding:13px 16px;text-decoration:none;color:#111;border-bottom:1px solid #EEE;font-weight:bold;font-size:14px}
.menuHead{background:#FFD700;padding:14px;text-align:center;font-weight:900}
.langs{display:flex;gap:4px;justify-content:center;margin:8px 6px;flex-wrap:wrap}
.langs button{background:#fff;border:1px solid #C9A227;padding:4px 8px;border-radius:12px;font-size:10px;font-weight:bold;cursor:pointer}.langs button.active{background:#FFD700}
.card{margin:10px;background:#fff;border-radius:14px;overflow:hidden;border:2px solid #FFD700}
.video{height:200px;background:linear-gradient(135deg,#87CEEB,#FFD700,#fff);display:flex;align-items:center;justify-content:center;font-size:55px}
.info{padding:12px}.caption{margin:6px 0;color:#333;font-size:13px}
.actions{display:flex;gap:8px;padding-top:8px;border-top:1px solid #FFD700;font-size:13px;font-weight:bold}.actions span{cursor:pointer;background:#FFF8DC;padding:5px 9px;border-radius:20px;border:1px solid #FFD700}
.btn{display:block;margin:12px;background:#fff;text-align:center;padding:14px;border-radius:30px;font-weight:bold;text-decoration:none;color:#111;border:2px solid #FFD700}
.bottom{position:fixed;bottom:0;left:0;right:0;background:#fff;display:flex;justify-content:space-around;padding:10px;border-top:3px solid #FFD700;font-size:10px;text-align:center;z-index:30}.bottom div{cursor:pointer;flex:1;font-weight:bold}.bottom div.active{color:#C9A227}
.pageBox{background:#fff;margin:12px;padding:18px;border-radius:14px;border:2px solid #FFD700;text-align:center}
.pageBox button{padding:11px 18px;background:#FFD700;border:1px solid #C9A227;border-radius:20px;font-weight:bold;margin:6px;cursor:pointer}
.pageBox input,.pageBox select{width:100%;padding:11px;margin:6px 0;border-radius:10px;border:2px solid #FFD700;background:#FFF8DC}
.chatBox{text-align:left;background:#FFF8DC;padding:10px;border-radius:12px;margin:8px 0;border:1px solid #FFD700;max-height:250px;overflow-y:auto}
.newsLink{display:block;background:#87CEEB;padding:12px;margin:8px 0;border-radius:10px;color:#111;font-weight:bold;text-decoration:none;text-align:left}
.football{height:180px;background:linear-gradient(#87CEEB,#7CFC00);border-radius:12px;position:relative;margin:10px 0;border:2px solid #111;overflow:hidden}
.keeper{position:absolute;top:60px;left:50%;transform:translateX(-50%);font-size:45px;transition:all .3s}
.ball{position:absolute;bottom:10px;left:50%;transform:translateX(-50%);font-size:35px;transition:all .4s}
.goal{position:absolute;top:20px;left:20%;right:20%;height:80px;border:3px solid #fff;border-bottom:none;text-align:center;color:#fff;font-weight:bold}
.tut{position:fixed;top:0;left:0;right:0;bottom:0;background:rgba(0,0,0,.7);z-index:100;display:none;align-items:center;justify-content:center;padding:20px}
.tutBox{background:#fff;padding:22px;border-radius:16px;max-width:360px;text-align:center;border:3px solid #FFD700}
</style>
</head>
<body>

<div class="topbar">
<div class="topRow">
<div class="hamburger" onclick="toggleMenu()">☰</div>
<div class="brand">MTfy 🌍<small>MTfy Africa - Make It Finally</small></div>
<div style="font-size:22px;cursor:pointer" onclick="showPage('fans')">🔔</div>
</div>
<div class="topIcons">
<div id="t-me" onclick="showPage('me')">👤<br>Me</div>
<div id="t-fans" onclick="showPage('fans')">❤️<br>My Fans</div>
<div id="t-news" onclick="showPage('news')">📰<br>News</div>
<div id="t-market" onclick="showPage('market')">🛒<br>Market</div>
<div id="t-games" onclick="showPage('games')">🎮<br>Games</div>
</div>
</div>

<div id="sideMenu" class="menu">
<div class="menuHead">MTfy Africa 🌍<br><small>For All Africa</small></div>
<a href="#" onclick="showPage('home');return false">🏠 Home</a>
<a href="#" onclick="showPage('me');return false">👤 My Profile</a>
<a href="#" onclick="showPage('fans');return false">❤️ My Fans</a>
<a href="#" onclick="showPage('news');return false">📰 News</a>
<a href="#" onclick="showPage('market');return false">🛒 Marketplace</a>
<a href="#" onclick="showPage('games');return false">🎮 Games</a>
<a href="#" onclick="showPage('terms');return false">📜 Terms and Conditions</a>
<a href="#" onclick="showPage('privacy');return false">🔒 Privacy Policy</a>
<a href="#" onclick="showPage('ads');return false">📢 Ads</a>
<a href="#" onclick="showPage('admin');return false">💬 Admin Chat</a>
<a href="#" onclick="showPage('settings');return false">⚙️ Settings</a>
<a href="#" onclick="showPage('share');return false">↗️ Share</a>
<a href="#" onclick="showPage('tutorial');return false">🎓 Tutorial</a>
<a href="#" onclick="doLogout();return false">🚪 Logout</a>
</div>

<div class="langs" id="langsRow">
<button class="active" onclick="setLang(this)">English</button><button onclick="setLang(this)">Swahili</button><button onclick="setLang(this)">Hausa</button><button onclick="setLang(this)">Yoruba</button><button onclick="setLang(this)">Igbo</button><button onclick="setLang(this)">Amharic</button><button onclick="setLang(this)">Zulu</button><button onclick="setLang(this)">French</button><button onclick="setLang(this)">Arabic</button><button onclick="setLang(this)">Ateso</button>
</div>

<div id="homePage">
<div class="pageBox" id="loginBox">
<h2>Welcome to MTfy Africa 🌍</h2>
<p style="font-size:12px;color:#666">Create FREE account</p>
<input id="fullName" placeholder="Full Names - e.g. Opejo Benjamin">
<input id="userName" placeholder="Username - e.g. @opejo_africa">
<div style="display:flex;gap:6px"><select id="countryCode" style="width:38%"><option value="+256">🇺🇬 +256 Uganda</option><option value="+234">🇳🇬 +234 Nigeria</option><option value="+254">🇰🇪 +254 Kenya</option><option value="+27">🇿🇦 +27 S. Africa</option><option value="+233">🇬🇭 +233 Ghana</option><option value="+251">🇪🇹 +251 Ethiopia</option><option value="+255">🇹🇿 +255 Tanzania</option><option value="+20">🇪🇬 +20 Egypt</option><option value="+212">🇲🇦 +212 Morocco</option></select><input id="phoneNum" placeholder="Phone - e.g. 770123456"></div>
<label style="font-size:12px;font-weight:bold">Profile Photo</label>
<input type="file" id="profilePicInput" accept="image/*" onchange="previewPhoto(this)">
<img id="profilePreview" style="width:80px;height:80px;border-radius:50%;display:none;object-fit:cover;margin:6px auto;border:2px solid gold">
<input id="otpInput" placeholder="OTP - use 1234">
<button onclick="doLogin()">✅ CREATE ACCOUNT & LOGIN</button>
<button onclick="skipLogin()" style="background:#87CEEB">⚡ ENTER WITHOUT LOGIN</button>
<p id="loginMsg" style="font-weight:bold;font-size:13px"></p>
</div>
<div class="pageBox" id="welcomeBox" style="display:none">
<h2>Welcome Back, <span id="welcomeName"></span>! 🌍</h2>
<img id="welcomePic" style="width:80px;height:80px;border-radius:50%;object-fit:cover;display:none">
<p><b id="welcomeUser"></b> • <span id="welcomePhone"></span></p>
<button onclick="doLogout()">🚪 Logout</button>
</div>
<div class="card"><div class="video">🎥</div><div class="info"><b>@lagos_star</b> • Lagos, Nigeria<div class="caption">Afrobeats! 🇳🇬 #MTfyAfrica</div><div class="actions"><span onclick="doLike(this)">❤️ <span class="likeCount">12400</span></span><span onclick="showPage('share')">↗️ Share</span><span onclick="doFollow(this)">➕ Follow</span></div></div></div>
<div class="card"><div class="video">🎤</div><div class="info"><b>@nairobi_food</b> • Nairobi, Kenya<div class="caption">Nyama Choma! 🇰🇪</div><div class="actions"><span onclick="doLike(this)">❤️ <span class="likeCount">25000</span></span><span onclick="showPage('share')">↗️ Share</span><span onclick="doFollow(this)">➕ Follow</span></div></div></div>
<div id="postedHere"></div>
<a class="btn" href="#" onclick="showPage('upload');return false">＋ UPLOAD YOUR VIDEO</a>
<button onclick="openTut()">🎓 Show Tutorial</button>
</div>

<div id="mePage" class="pageBox" style="display:none"><h2>👤 My Profile</h2><p id="meInfo">Login to see your profile!</p><img id="mePic" style="width:100px;height:100px;border-radius:50%;object-fit:cover;display:none"><br><button onclick="showPage('fans')">❤️ My Fans</button><button onclick="showPage('home')">← Home</button></div>
<div id="fansPage" class="pageBox" style="display:none"><h2>❤️ My Fans</h2><div class="chatBox" id="fansChat"><div><b>@lagos_star:</b> Big fan! 🔥</div></div><input id="fanMsg" placeholder="Reply to fans..."><button onclick="sendChat('fanMsg','fansChat')">💬 SEND - Appears Above!</button><button onclick="showPage('home')">← Home</button></div>
<div id="newsPage" class="pageBox" style="display:none"><h2>📰 Africa News - Real Links</h2>
<a class="newsLink" href="https://www.bbc.com/news/world/africa" target="_blank">🌍 BBC News Africa →</a>
<a class="newsLink" href="https://www.aljazeera.com/africa/" target="_blank">📺 Al Jazeera Africa →</a>
<a class="newsLink" href="https://www.africanews.com/" target="_blank">📰 Africanews →</a>
<a class="newsLink" href="https://nation.africa/" target="_blank">🇰🇪 Daily Nation →</a>
<a class="newsLink" href="https://punchng.com/" target="_blank">🇳🇬 Punch Nigeria →</a>
<a class="newsLink" href="https://www.news24.com/" target="_blank">🇿🇦 News24 →</a>
<button onclick="showPage('home')">← Home</button></div>
<div id="marketPage" class="pageBox" style="display:none"><h2>🛒 Marketplace Africa</h2><div id="marketList"><div style="background:#FFF8DC;padding:12px;border-radius:10px;margin:8px 0;text-align:left">👕 <b>MTfy T-Shirt - 30,000</b><br>Soroti, Uganda</div></div><input id="marketItem" placeholder="What to sell? e.g. Shoes 50k"><button onclick="listMarket()">＋ LIST - Appears Above!</button><button onclick="showPage('home')">← Home</button></div>
<div id="gamesPage" class="pageBox" style="display:none"><h2>🎮 Games - REAL Football!</h2>
<p>Score: <b id="footScore">0</b> | Missed: <b id="footMiss">0</b> | Round: <b id="footRound">1/5</b></p>
<div class="football"><div class="goal">GOAL</div><div class="keeper" id="keeper">🧤</div><div class="ball" id="ball">⚽</div></div>
<button onclick="shoot('left')">⬅️ LEFT</button><button onclick="shoot('center')">⬆️ CENTER</button><button onclick="shoot('right')">➡️ RIGHT</button>
<p id="footMsg" style="font-weight:bold"></p><button onclick="resetFoot()">🔄 Play Again</button><br><button onclick="showPage('home')">← Home</button></div>
<div id="discoverPage" class="pageBox" style="display:none"><h2>🔍 Discover Africa</h2><p>🔥 #MTfyAfrica #Lagos #Nairobi</p><button onclick="showPage('home')">← Back</button></div>
<div id="uploadPage" class="pageBox" style="display:none"><h2>＋ Upload</h2><input type="file" id="fileInput" accept="video/*,image/*" style="display:none" onchange="handleFile(this)"><button onclick="document.getElementById('fileInput').click()">📁 GALLERY - Opens Gallery!</button><br><input type="file" id="cameraInput" accept="video/*,image/*" capture="environment" style="display:none" onchange="handleFile(this)"><button onclick="document.getElementById('cameraInput').click()">🎥 CAMERA - Opens Camera!</button><video id="preview" controls style="width:100%;display:none;border-radius:12px;margin-top:10px"></video><img id="previewImg" style="width:100%;display:none;border-radius:12px;margin-top:10px"><p id="uploadStatus"></p><button onclick="doPost()">✅ POST - Shows on Home!</button><button onclick="showPage('home')">← Back</button></div>
<div id="inboxPage" class="pageBox" style="display:none"><h2>💬 Inbox</h2><div class="chatBox" id="inboxChat"><div><b>@lagos_star:</b> Hello!</div></div><input id="inboxMsg" placeholder="Reply..."><button onclick="sendChat('inboxMsg','inboxChat')">💬 SEND</button><button onclick="showPage('home')">← Home</button></div>
<div id="meetFansPage" class="pageBox" style="display:none"><h2>💬❤️ Meet Your Fans</h2><div class="chatBox" id="meetChat"><div><b>@fan:</b> Big fan! 🔥</div></div><input id="meetMsg" placeholder="Chat..."><button onclick="sendChat('meetMsg','meetChat')">💬 SEND TO FANS</button><button onclick="showPage('home')">← Home</button></div>
<div id="termsPage" class="pageBox" style="display:none"><h2>📜 Terms</h2><p style="text-align:left;line-height:1.6">1. MTfy Africa by Opejo Benjamin.<br>2. Be respectful. No hate.<br>3. You own your videos.<br>4. 13+ to use.</p><button onclick="showPage('home')">← I Agree</button></div>
<div id="privacyPage" class="pageBox" style="display:none"><h2>🔒 Privacy</h2><p style="text-align:left;line-height:1.6">• Only phone to login.<br>• NEVER share PIN/OTP.<br>• Private chats stay private.</p><button onclick="showPage('home')">← Back</button></div>
<div id="adsPage" class="pageBox" style="display:none"><h2>📢 Ads Africa</h2><p>🥉 $10/day • 🥇 $25/day</p><input id="adsName" placeholder="Business Name"><button onclick="doAds()">🚀 START AD - Saved!</button><p id="adsMsg"></p><button onclick="showPage('home')">← Back</button></div>
<div id="adminPage" class="pageBox" style="display:none"><h2>💬 Admin Chat - Opejo</h2><div class="chatBox" id="adminChatBox"><div><b>Admin Opejo:</b> Welcome! How can I help? 🌍</div></div><input id="adminMsg" placeholder="Type to Admin..."><button onclick="sendAdmin()">💬 SEND</button><button onclick="showPage('home')">← Back</button></div>
<div id="settingsPage" class="pageBox" style="display:none"><h2>⚙️ Settings</h2><p style="text-align:left"><b>🌍 Language:</b></p><select id="langSelect" onchange="document.getElementById('settingsMsg').textContent='✅ Language saved: '+this.value"><option>English</option><option>Swahili</option><option>Hausa</option><option>Yoruba</option><option>Igbo</option><option>Amharic</option><option>Zulu</option><option>Xhosa</option><option>Shona</option><option>Somali</option><option>Arabic</option><option>French</option><option>Portuguese</option><option>Ateso</option><option>Acholi</option><option>Luganda</option></select><p style="text-align:left"><b>🔔 Notifications:</b> <button onclick="toggleBtn(this)">ON ✅</button></p><p style="text-align:left"><b>▶️ Auto-play:</b> <button onclick="toggleBtn(this)">OFF ❌</button></p><button onclick="showPage('home')">🔐 LOGIN</button><button onclick="doLogout()">🚪 LOGOUT</button><p id="settingsMsg" style="color:green;font-weight:bold"></p><button onclick="showPage('home')">← Save & Back</button></div>
<div id="sharePage" class="pageBox" style="display:none"><h2>↗️ Share MTfy Africa</h2>
<a style="display:block;background:#25D366;color:#fff;padding:12px;border-radius:10px;margin:8px 0;font-weight:bold;text-decoration:none" href="https://wa.me/?text=Join%20MTfy%20Africa%20https://opejo.github.io/mtf/" target="_blank">💬 WhatsApp</a>
<a style="display:block;background:#1877F2;color:#fff;padding:12px;border-radius:10px;margin:8px 0;font-weight:bold;text-decoration:none" href="https://www.facebook.com/sharer/sharer.php?u=https://opejo.github.io/mtf/" target="_blank">📘 Facebook</a>
<a style="display:block;background:#111;color:#fff;padding:12px;border-radius:10px;margin:8px 0;font-weight:bold;text-decoration:none" href="https://www.tiktok.com/" target="_blank">🎵 TikTok</a>
<button onclick="copyLink()">🔗 Copy Link</button><button onclick="nativeShare()">↗️ Share to Any App</button><button onclick="showPage('home')">← Back</button></div>
<div id="tutorialPage" class="pageBox" style="display:none"><h2>🎓 Tutorial</h2><p style="text-align:left;line-height:1.7"><b>1. ☰ Top Left:</b> Menu<br><b>2. TOP Blue:</b> Me, Fans, News, Market, Games<br><b>3. BOTTOM White:</b> Home, Discover, Upload, Inbox, Meet Fans<br><b>4. ❤️ Like:</b> Number goes UP<br><b>5. 📁 Upload:</b> Gallery/Camera → Post<br><b>6. ⚽ Games:</b> Football Penalty<br><b>7. 📰 News:</b> Real news opens</p><button onclick="showPage('home')">✅ Got It!</button></div>

<div class="bottom">
<div id="nav-home" class="active" onclick="showPage('home')">🏠<br>Home</div>
<div id="nav-discover" onclick="showPage('discover')">🔍<br>Discover</div>
<div id="nav-upload" onclick="showPage('upload')">＋<br>Upload</div>
<div id="nav-inbox" onclick="showPage('inbox')">💬<br>Inbox</div>
<div id="nav-meetFans" onclick="showPage('meetFans')">💬❤️<br>Meet Fans</div>
</div>

<div id="tutPopup" class="tut"><div class="tutBox"><h2>🎓 Welcome to MTfy Africa! 🌍</h2><p id="tutText" style="margin:12px">Step 1/5: Tap ☰ top-left for Menu.</p><button onclick="tutNext()">Next →</button><button onclick="closeTut()">Skip Tutorial</button></div></div>

<script>
var tutStep=1, footScore=0, footMiss=0, footRound=1;
function showPage(p){var m={home:'homePage',me:'mePage',fans:'fansPage',news:'newsPage',market:'marketPage',games:'gamesPage',discover:'discoverPage',upload:'uploadPage',inbox:'inboxPage',meetFans:'meetFansPage',terms:'termsPage',privacy:'privacyPage',ads:'adsPage',admin:'adminPage',settings:'settingsPage',share:'sharePage',tutorial:'tutorialPage'};if(!m[p])return;var sm=document.getElementById('sideMenu');if(sm)sm.style.display='none';for(var k in m){var e=document.getElementById(m[k]);if(e)e.style.display='none';}document.getElementById(m[p]).style.display='block';var bs=document.querySelectorAll('.bottom div');for(var i=0;i<bs.length;i++)bs[i].classList.remove('active');var ts=document.querySelectorAll('.topIcons div');for(var j=0;j<ts.length;j++)ts[j].classList.remove('active');var b=document.getElementById('nav-'+p);if(b)b.classList.add('active');var t=document.getElementById('t-'+p);if(t)t.classList.add('active');window.scrollTo(0,0);}
function toggleMenu(){var m=document.getElementById('sideMenu');m.style.display=(m.style.display==='block'?'none':'block');}
function setLang(btn){var all=document.querySelectorAll('#langsRow button');for(var i=0;i<all.length;i++)all[i].classList.remove('active');btn.classList.add('active');var s=document.getElementById('settingsMsg');if(s)s.textContent='Language: '+btn.textContent;}
function closeTut(){document.getElementById('tutPopup').style.display='none';}
function openTut(){tutStep=1;document.getElementById('tutText').textContent='Step 1/5: Tap ☰ top-left for Menu.';document.getElementById('tutPopup').style.display='flex';}
function tutNext(){tutStep++;var texts={2:'Step 2/5: TOP Sky Blue = Me, Fans, News, Market, Games.',3:'Step 3/5: BOTTOM White = Home, Discover, Upload, Inbox, Meet Fans.',4:'Step 4/5: Like ❤️ number goes UP. Upload opens Gallery.',5:'Step 5/5: Play Football, Read News, Sell in Market. Ready!'};if(tutStep>5){closeTut();return;}document.getElementById('tutText').textContent=texts[tutStep];}
function doLike(el){var c=el.querySelector('.likeCount');if(!c)return;c.textContent=parseInt(c.textContent)+1;el.style.background='#FFD700';}
function doFollow(el){el.textContent='✓ Following';el.style.background='#87CEEB';}
function doLogin(){var n=document.getElementById('
