<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MTfy Africa - Make It Finally 🌍</title>
<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:Arial,sans-serif}
body{background:repeating-linear-gradient(115deg, rgba(255,255,255,0.25) 0px, rgba(255,255,255,0) 2px, rgba(0,0,0,0.15) 3px, rgba(0,0,0,0) 5px),linear-gradient(135deg,#FFF7A8 0%, #FFD700 15%, #C9A227 30%, #8B6508 45%, #FFEC8B 55%, #D4AF37 65%, #B8860B 80%, #FFF8DC 100%);background-attachment:fixed;color:#111;padding-bottom:95px;padding-top:102px;min-height:100vh}
.topbar{position:fixed;top:0;left:0;right:0;background:#fff;z-index:30;border-bottom:3px solid #FFD700;padding:6px 8px}
.topRow{display:flex;align-items:center;gap:8px}
.hamburger{font-size:24px;color:#111;cursor:pointer;padding:5px 10px;background:#FFD700;border:1px solid #C9A227;border-radius:8px}
.brand{flex:1;text-align:center;color:#111;font-weight:900;font-size:20px;line-height:1}.brand span{color:#C9A227}.brand small{display:block;font-size:9px;color:#666}
.topIcons{display:flex;justify-content:space-around;background:#87CEEB;border-radius:10px;margin-top:6px;padding:6px 2px;border:1px solid #fff}
.topIcons div{cursor:pointer;color:#111;font-size:10px;text-align:center;flex:1;padding:4px;font-weight:bold}.topIcons div.active{color:#fff;background:#111;border-radius:8px}.topIcons b{display:block;font-size:18px}
.menu{position:fixed;top:58px;left:10px;background:#FFFFFF;border:2px solid #FFD700;border-radius:14px;width:260px;z-index:40;display:none;box-shadow:0 10px 25px rgba(0,0,0,0.4);overflow:hidden;max-height:82vh;overflow-y:auto}
.menu a{display:block;padding:13px 16px;text-decoration:none;color:#111;border-bottom:1px solid #EEE;font-weight:bold;font-size:14px;background:#fff}
.menu .menu-head{background:#FFD700;color:#111;padding:14px 16px;font-weight:900;text-align:center}
.langs{display:flex;gap:4px;justify-content:center;margin:8px 6px;flex-wrap:wrap}
.langs button{background:#fff;color:#111;border:1px solid #C9A227;padding:4px 8px;border-radius:12px;font-size:10px;font-weight:bold}.langs button.active{background:#FFD700;color:#111}
.card{margin:10px;background:#fff;border-radius:14px;overflow:hidden;border:2px solid #FFD700}
.video{height:220px;background:linear-gradient(135deg,#87CEEB,#FFD700,#fff);display:flex;align-items:center;justify-content:center;font-size:55px}
.info{padding:12px}.user{font-weight:bold}.user small{color:#888}.caption{margin:6px 0;color:#333;font-size:13px}
.actions{display:flex;gap:8px;padding-top:8px;border-top:1px solid #FFD700;font-size:13px;font-weight:bold}.actions span{cursor:pointer;background:#FFF8DC;padding:5px 9px;border-radius:20px;border:1px solid #FFD700}
.btn{display:block;margin:12px;background:#fff;color:#111;text-align:center;padding:14px;border-radius:30px;font-weight:bold;text-decoration:none;border:2px solid #FFD700}
.bottom{position:fixed;bottom:0;left:0;right:0;background:#fff;display:flex;justify-content:space-around;padding:10px;border-top:3px solid #FFD700;font-size:10px;color:#111;text-align:center;z-index:30}.bottom div{cursor:pointer;flex:1;font-weight:bold}.bottom div.active{color:#C9A227}
.pageBox{background:#fff;margin:12px;padding:18px;border-radius:14px;border:2px solid #FFD700;text-align:center}
.pageBox button{padding:11px 18px;background:#FFD700;color:#111;border:1px solid #C9A227;border-radius:20px;font-weight:bold;margin:6px}
.pageBox input, .pageBox select, .pageBox textarea{width:100%;padding:11px;margin:6px 0;border-radius:10px;border:2px solid #FFD700;background:#FFF8DC}
.chatBox{text-align:left;background:#FFF8DC;padding:10px;border-radius:12px;margin:8px 0;border:1px solid #FFD700;max-height:250px;overflow-y:auto}
.newsLink{display:block;background:#87CEEB;padding:12px;margin:8px 0;border-radius:10px;color:#111;font-weight:bold;text-decoration:none;text-align:left}
.football{height:180px;background:linear-gradient(#87CEEB,#7CFC00);border-radius:12px;position:relative;margin:10px 0;border:2px solid #111;overflow:hidden}
.keeper{position:absolute;top:60px;left:50%;transform:translateX(-50%);font-size:45px;transition:all 0.3s}
.ball{position:absolute;bottom:10px;left:50%;transform:translateX(-50%);font-size:35px;transition:all 0.4s}
.goal{position:absolute;top:20px;left:20%;right:20%;height:80px;border:3px solid #fff;border-bottom:none;text-align:center;color:#fff;font-weight:bold}
.tut{position:fixed;top:0;left:0;right:0;bottom:0;background:rgba(0,0,0,0.7);z-index:100;display:flex;align-items:center;justify-content:center;padding:20px}
.tutBox{background:#fff;padding:22px;border-radius:16px;max-width:360px;text-align:center;border:3px solid #FFD700}
</style>
</head>
<body>

<div class="topbar">
<div class="topRow">
<div class="hamburger" onclick="toggleMenu()">☰</div>
<div class="brand">MT<span>fy</span> 🌍<small>MTfy Africa - Make It Finally</small></div>
<div style="width:44px;text-align:right;font-size:22px;cursor:pointer" onclick="showPage('fans')">🔔 <span id="bellCount" style="font-size:12px;background:red;color:#fff;border-radius:50%;padding:2px 5px">3</span></div>
</div>
<div class="topIcons">
<div id="t-me" onclick="showPage('me')"><b>👤</b>Me</div>
<div id="t-fans" onclick="showPage('fans')"><b>❤️</b>My Fans</div>
<div id="t-news" onclick="showPage('news')"><b>📰</b>News</div>
<div id="t-market" onclick="showPage('market')"><b>🛒</b>Market</div>
<div id="t-games" onclick="showPage('games')"><b>🎮</b>Games</div>
</div>
</div>

<div id="sideMenu" class="menu">
<div class="menu-head">MTfy Africa 🌍<small>Make It Finally - For All Africa</small></div>
<a href="#" onclick="goMenu('home')">🏠 Home</a>
<a href="#" onclick="goMenu('me')">👤 My Profile - Me</a>
<a href="#" onclick="goMenu('fans')">❤️ My Fans</a>
<a href="#" onclick="goMenu('news')">📰 News</a>
<a href="#" onclick="goMenu('market')">🛒 Marketplace</a>
<a href="#" onclick="goMenu('games')">🎮 Games</a>
<a href="#" onclick="openPage('terms')">📜 Terms and Conditions</a>
<a href="#" onclick="openPage('privacy')">🔒 Privacy Policy</a>
<a href="#" onclick="openPage('ads')">📢 Ads</a>
<a href="#" onclick="openPage('admin')">💬 Admin Chat</a>
<a href="#" onclick="openPage('settings')">⚙️ Settings</a>
<a href="#" onclick="openPage('share')">↗️ Share</a>
<a href="#" onclick="openPage('tutorial')">🎓 Tutorial - How To Use App</a>
<a href="#" onclick="logoutUser()">🚪 Logout</a>
</div>

<div class="langs">
<button class="active" onclick="setLang(this)">English</button>
<button onclick="setLang(this)">Swahili</button>
<button onclick="setLang(this)">Hausa</button>
<button onclick="setLang(this)">Yoruba</button>
<button onclick="setLang(this)">Igbo</button>
<button onclick="setLang(this)">Amharic</button>
<button onclick="setLang(this)">Zulu</button>
<button onclick="setLang(this)">Ateso</button>
<button onclick="setLang(this)">Acholi</button>
<button onclick="setLang(this)">Luganda</button>
</div>

<!-- LOGIN / HOME -->
<div id="homePage">
<div class="pageBox" id="loginBox">
<h2>Welcome to MTfy Africa 🌍🔥</h2>
<p style="color:#666;font-size:12px">Create your FREE account - No demo number!</p>
<label style="text-align:left;display:block;font-size:12px;font-weight:bold">Full Names</label>
<input id="fullName" placeholder="e.g. Opejo Benjamin">
<label style="text-align:left;display:block;font-size:12px;font-weight:bold">Username</label>
<input id="userName" placeholder="e.g. @opejo_africa">
<label style="text-align:left;display:block;font-size:12px;font-weight:bold">Country Code + Phone</label>
<div style="display:flex;gap:6px"><select id="countryCode" style="width:35%"><option value="+256">🇺🇬 +256 Uganda</option><option value="+234">🇳🇬 +234 Nigeria</option><option value="+254">🇰🇪 +254 Kenya</option><option value="+27">🇿🇦 +27 South Africa</option><option value="+233">🇬🇭 +233 Ghana</option><option value="+251">🇪🇹 +251 Ethiopia</option><option value="+255">🇹🇿 +255 Tanzania</option><option value="+250">🇷🇼 +250 Rwanda</option><option value="+20">🇪🇬 +20 Egypt</option><option value="+212">🇲🇦 +212 Morocco</option></select><input id="phoneNum" placeholder="770123456" style="flex:1"></div>
<label style="text-align:left;display:block;font-size:12px;font-weight:bold">Profile Photo</label>
<input type="file" id="profilePicInput" accept="image/*" onchange="previewProfile(this)">
<img id="profilePreview" style="width:80px;height:80px;border-radius:50%;display:none;object-fit:cover;margin:6px auto;border:2px solid gold">
<label style="text-align:left;display:block;font-size:12px;font-weight:bold">OTP Code (we sent to your phone)</label>
<input id="otpInput" placeholder="Enter OTP - try 1234 for demo">
<button onclick="doLogin()">✅ CREATE ACCOUNT & LOGIN →</button>
<p id="loginMsg" style="font-size:12px;color:green;font-weight:bold"></p>
</div>

<div class="pageBox" id="welcomeBox" style="display:none">
<h2>Welcome Back, <span id="welcomeName">Friend</span>! 🌍</h2>
<p><img id="welcomePic" style="width:80px;height:80px;border-radius:50%;object-fit:cover;display:none"></p>
<p>Username: <b id="welcomeUser">@user</b> • <span id="welcomePhone"></span></p>
<button onclick="logoutUser()">🚪 Logout</button>
</div>

<div class="card"><div class="video">🎥</div><div class="info"><div class="user">@ateso_star <small>• Soroti, Uganda</small></div><div class="caption">Apai! Dance from Uganda! 🌍 #MTfyAfrica</div><div class="actions"><span onclick="like(this)">❤️ <span>12400</span></span><span onclick="openPage('share')">↗️ Share</span><span onclick="follow(this)">➕ Follow</span></div></div></div>
<div class="card"><div class="video">🎤</div><div class="info"><div class="user">@lagos_star <small>• Lagos, Nigeria</small></div><div class="caption">Afrobeats from Lagos! 🇳🇬 #MTfyAfrica</div><div class="actions"><span onclick="like(this)">❤️ <span>8900</span></span><span onclick="openPage('share')">↗️ Share</span><span onclick="follow(this)">➕ Follow</span></div></div></div>
<div class="card"><div class="video">🍲</div><div class="info"><div class="user">@nairobi_food <small>• Nairobi, Kenya</small></div><div class="caption">Nyama Choma! Karibu! 🇰🇪 #MTfyAfrica</div><div class="actions"><span onclick="like(this)">❤️ <span>25000</span></span><span onclick="openPage('share')">↗️ Share</span><span onclick="follow(this)">➕ Follow</span></div></div></div>
<a class="btn" href="#" onclick="showPage('upload');return false;">＋ UPLOAD YOUR VIDEO</a>
</div>

<div id="mePage" class="pageBox" style="display:none"><h2>👤 My Profile</h2><p id="meInfo">Login to see your profile!</p><img id="mePic" style="width:100px;height:100px;border-radius:50%;object-fit:cover;display:none"><br><button onclick="showPage('fans')">❤️ My Fans</button><button onclick="showPage('home')">← Home</button></div>
<div id="fansPage" class="pageBox" style="display:none"><h2>❤️ My Fans</h2><div class="chatBox" id="fansChat"><div><b>@lagos_star:</b> Big fan from Nigeria! 🔥</div><div><b>@nairobi_girl:</b> Love your videos!</div><div><b>@accra_boy:</b> Follow back please!</div></div><input id="fanMsg" placeholder="Reply to fans..."><button onclick="replyFan()">💬 SEND - It Will Appear Above!</button><button onclick="showPage('home')">← Home</button></div>

<div id="newsPage" class="pageBox" style="display:none"><h2>📰 Africa News - Real Links</h2><p style="color:#666">Tap any outlet - it REALLY opens!</p>
<a class="newsLink" href="https://www.bbc.com/news/world/africa" target="_blank">🌍 BBC News Africa →</a>
<a class="newsLink" href="https://www.aljazeera.com/africa/" target="_blank">📺 Al Jazeera Africa →</a>
<a class="newsLink" href="https://www.africanews.com/" target="_blank">📰 Africanews →</a>
<a class="newsLink" href="https://nation.africa/" target="_blank">🇰🇪 Daily Nation - Kenya →</a>
<a class="newsLink" href="https://punchng.com/" target="_blank">🇳🇬 Punch - Nigeria →</a>
<a class="newsLink" href="https://www.news24.com/" target="_blank">🇿🇦 News24 - South Africa →</a>
<a class="newsLink" href="https://www.monitor.co.ug/" target="_blank">🇺🇬 Daily Monitor - Uganda →</a>
<button onclick="showPage('home')">← Home</button></div>

<div id="marketPage" class="pageBox" style="display:none"><h2>🛒 Marketplace Africa</h2><div id="marketList"><div style="background:#FFF8DC;padding:12px;border-radius:10px;margin:8px 0;text-align:left">👕 <b>MTfy Africa T-Shirt - UGX 30,000</b><br>Soroti, Uganda<br><button onclick="alert('Seller will WhatsApp you!')">💬 Chat Seller</button></div></div><input id="marketItem" placeholder="What do you want to sell? e.g. Shoes 50k"><button onclick="addMarket()">＋ LIST MY PRODUCT - It Will Appear!</button><button onclick="showPage('home')">← Home</button></div>

<div id="gamesPage" class="pageBox" style="display:none"><h2>🎮 Games</h2>
<h3>⚽ REAL FOOTBALL - Penalty Shootout!</h3>
<p>Score: <b id="footScore">0</b> | Missed: <b id="footMiss">0</b> | Round: <b id="footRound">1/5</b></p>
<div class="football"><div class="goal">GOAL</div><div class="keeper" id="keeper">🧤</div><div class="ball" id="ball">⚽</div></div>
<p>Choose where to shoot:</p><button onclick="shoot('left')">⬅️ LEFT</button><button onclick="shoot('center')">⬆️ CENTER</button><button onclick="shoot('right')">➡️ RIGHT</button>
<p id="footMsg" style="font-weight:bold;margin-top:8px"></p>
<button onclick="resetFootball()">🔄 Play Again</button>
<h3 style="margin-top:15px">🎲 Spin & Win</h3><button onclick="spinGame()">🎲 SPIN NOW</button><p id="spinResult"></p>
<button onclick="showPage('home')">← Home</button></div>

<div id="discoverPage" class="pageBox" style="display:none"><h2>🔍 Discover Africa</h2><p>🔥 #MTfyAfrica #Lagos #Nairobi #Accra</p><button onclick="showPage('home')">← Back</button></div>
<div id="uploadPage" class="pageBox" style="display:none"><h2>＋ Upload</h2><input type="file" id="fileInput" accept="video/*,image/*" style="display:none" onchange="previewFile(this)"><button onclick="document.getElementById('fileInput').click()">📁 GALLERY</button><br><input type="file" id="cameraInput" accept="video/*,image/*" capture="environment" style="display:none" onchange="previewFile(this)"><button onclick="document.getElementById('cameraInput').click()">🎥 CAMERA</button><video id="preview" controls style="width:100%;display:none;border-radius:12px;margin-top:10px"></video><img id="previewImg" style="width:100%;display:none;border-radius:12px;margin-top:10px"><p id="uploadStatus"></p><button onclick="postVideo()">✅ POST - It Will Show On Home!</button><button onclick="showPage('home')">← Back</button></div>
<div id="inboxPage" class="pageBox" style="display:none"><h2>💬 Inbox</h2><div class="chatBox" id="inboxChat"><div><b>@lagos_star:</b> Hello from Lagos!</div></div><input id="inboxMsg" placeholder="Reply..."><button onclick="replyInbox()">💬 SEND</button><button onclick="showPage('home')">← Home</button></div>
<div id="meetFansPage" class="pageBox" style="display:none"><h2>💬❤️ Meet Your Fans - LIVE</h2><div class="chatBox" id="meetChat"><div><b>@soroti_boy:</b> Big fan! 🔥</div></div><input id="meetMsg" placeholder="Chat with fans..."><button onclick="replyMeet()">💬 SEND TO FANS</button><button onclick="showPage('home')">← Home</button></div>

<div id="termsPage" class="pageBox" style="display:none"><h2>📜 Terms - MTfy Africa</h2><p style="text-align:left;font-size:13px;line-height:1.6">1. MTfy Africa is by Opejo Benjamin, for all Africa.<br>2. Be respectful. No hate.<br>3. You own your videos.<br>4. 13+ to use.<br>5. Make It Finally with love! 🌍</p><button onclick="showPage('home')">← I Agree</button></div>
<div id="privacyPage" class="pageBox" style="display:none"><h2>🔒 Privacy Policy</h2><p style="text-align:left;font-size:13px;line-height:1.6">• Only phone number to login.<br>• NEVER share PIN/OTP.<br>• Private chats stay private.<br>• Delete account anytime via Admin Chat.</p><button onclick="showPage('home')">← Back</button></div>
<div id="adsPage" class="pageBox" style="display:none"><h2>📢 Ads Africa</h2><p>Reach ALL Africa!</p><p>🥉 Starter - $10/day • 🥇 Pro - $25/day</p><input id="adsName" placeholder="Your Business Name"><button onclick="startAd()">🚀 START MY AD - Saved!</button><p id="adsMsg"></p><button onclick="showPage('home')">← Back</button></div>
<div id="adminPage" class="pageBox" style="display:none"><h2>💬 Admin Chat - Opejo</h2><div class="chatBox" id="adminChatBox"><div><b>👤 Admin Opejo:</b> Welcome to MTfy Africa! How can I help? 🌍</div></div><input id="adminMsg" placeholder="Type to Admin..."><button onclick="replyAdmin()">💬 SEND - Admin Will Reply!</button><button onclick="showPage('home')">← Back</button></div>
<div id="settingsPage" class="pageBox" style="display:none"><h2>⚙️ Settings - REALLY WORKS</h2>
<p style="text-align:left"><b>🌍 Choose Language:</b></p><select id="langSelect" onchange="changeLang()"><option>English</option><option>Swahili - Kiswahili</option><option>Hausa</option><option>Yoruba</option><option>Igbo</option><option>Amharic - Ethiopia</option><option>Zulu - South Africa</option><option>Xhosa</option><option>Shona - Zimbabwe</option><option>Somali</option><option>Arabic - Egypt/Morocco</option><option>French - Senegal/Congo</option><option>Portuguese - Angola/Mozambique</option><option>Ateso - Uganda</option><option>Acholi - Uganda</option><option>Luganda - Uganda</option></select>
<p style="text-align:left"><b>🔔 Notifications:</b> <button id="notifBtn" onclick="toggleSetting(this)">ON ✅</button></p>
<p style="text-align:left"><b>▶️ Auto-play:</b> <button onclick="toggleSetting(this)">OFF ❌</button></p>
<p style="text-align:left"><b>👤 Account:</b></p><button onclick="showPage('home')">🔐 LOGIN</button><button onclick="logoutUser()">🚪 LOGOUT</button>
<p id="settingsMsg" style="color:green;font-weight:bold"></p><button onclick="showPage('home')">← Save & Back</button></div>
<div id="sharePage" class="pageBox" style="display:none"><h2>↗️ Share MTfy Africa</h2>
<a style="display:block;background:#25D366;color:#fff;padding:12px;border-radius:10px;margin:8px 0;font-weight:bold;text-decoration:none" href="https://wa.me/?text=Join%20MTfy%20Africa%20-%20Make%20It%20Finally!%20https://opejo.github.io/mtf/" target="_blank">💬 WhatsApp</a>
<a style="display:block;background:#1877F2;color:#fff;padding:12px;border-radius:10px;margin:8px 0;font-weight:bold;text-decoration:none" href="https://www.facebook.com/sharer/sharer.php?u=https://opejo.github.io/mtf/" target="_blank">📘 Facebook</a>
<a style="display:block;background:#111;color:#fff;padding:12px;border-radius:10px;margin:8px 0;font-weight:bold;text-decoration:none" href="https://www.tiktok.com/" target="_blank">🎵 TikTok</a>
<button onclick="copyLink()">🔗 Copy Link</button><button onclick="nativeShare()">↗️ Share to Any App</button><button onclick="showPage('home')">← Back</button></div>
<div id="tutorialPage" class="pageBox" style="display:none"><h2>🎓 Tutorial - How To Navigate</h2><p style="text-align:left;line-height:1.7"><b>1. ☰ Top Left:</b> Menu - Terms, Privacy, Ads, Admin, Settings, Share<br><b>2. TOP Blue Bar:</b> Me, My Fans, News, Market, Games<br><b>3. BOTTOM White Bar:</b> Home, Discover, Upload, Inbox, Meet Fans<br><b>4. ❤️ Like:</b> Tap heart, number goes UP for real<br><b>5. 📁 Upload:</b> Tap Upload → Gallery/Camera → Post<br><b>6. ⚽ Games:</b> Play Football Penalty, win points<br><b>7. 📰 News:</b> Tap outlet, real news opens<br><b>8. 🔐 Login:</b> Fill names, country code, phone, OTP</p><button onclick="showPage('home')">✅ Got It! Start Using MTfy!</button></div>

<div class="bottom">
<div id="nav-home" class="active" onclick="showPage('home')">🏠<br>Home</div>
<div id="nav-discover" onclick="showPage('discover')">🔍<br>Discover</div>
<div id="nav-upload" onclick="showPage('upload')">＋<br>Upload</div>
<div id="nav-inbox" onclick="showPage('inbox')">💬<br>Inbox</div>
<div id="nav-meetFans" onclick="showPage('meetFans')">💬❤️<br>Meet Fans</div>
</div>

<!-- TUTORIAL POPUP -->
<div id="tutPopu
