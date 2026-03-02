# Heatwave-App-prototypes-
EVS topic HTML file for search engines verification 
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>HeatShield Dashboard</title>
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<style>
body{margin:0;font-family:Segoe UI;background:#f4f6fb;color:#333}
.menuBtn{position:fixed;top:15px;left:15px;background:#111827;color:#fff;padding:10px 14px;border-radius:8px;cursor:pointer;z-index:1000;box-shadow:0 4px 8px rgba(0,0,0,0.2)}
.sidebar{position:fixed;left:-260px;top:0;bottom:0;width:260px;background:#111827;color:#fff;padding:20px;transition:.3s;overflow-y:auto}
.sidebar h2{margin-top:0;font-size:24px;text-align:center;}
.sidebar .menu-item{padding:12px 10px;margin:6px 0;border-radius:8px;cursor:pointer;display:flex;align-items:center;gap:10px;transition:0.3s}
.sidebar .menu-item:hover{background:#1f2937}
.sidebar .submenu{display:none;flex-direction:column;margin-left:15px;}
.sidebar.open{left:0}
.topbar{margin-left:0;padding:15px;display:flex;justify-content:flex-end;background:#fff;box-shadow:0 2px 6px rgba(0,0,0,.1)}
.search{padding:10px;border-radius:8px;border:1px solid #ddd;width:260px}
.content{margin-left:0;padding:60px 30px 30px 30px;transition:.3s}
.sidebar.open ~ .content{margin-left:260px;transition:.3s}
.section{margin-bottom:35px;display:none}
.cards{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:18px}
.card{background:linear-gradient(135deg,#ffffff,#f9fafc);padding:20px;border-radius:14px;box-shadow:0 6px 14px rgba(0,0,0,.08);transition:0.3s;cursor:pointer}
.card:hover{transform:translateY(-5px);box-shadow:0 10px 20px rgba(0,0,0,0.15)}
.loginPopup{position:fixed;inset:0;background:rgba(0,0,0,.5);display:none;justify-content:center;align-items:center;z-index:2000}
.loginBox{background:#fff;padding:30px;border-radius:14px;width:320px}
input,textarea,select{width:100%;padding:10px;margin:8px 0;border-radius:8px;border:1px solid #ddd}
button{padding:10px;border:none;border-radius:8px;background:#111827;color:#fff;cursor:pointer}
button:hover{background:#1f2937;transition:0.3s}
.small{font-size:12px;color:#666;margin-top:8px}
</style>
</head>
<body>

<!-- MENU BUTTON -->
<div class="menuBtn" onclick="toggleMenu()">☰ Menu</div>

<!-- SIDEBAR -->
<div class="sidebar" id="sidebar">
<h2>🔥 HeatShield</h2>

<div class="menu-item" onclick="toggleSubmenu('dashSub')">🏠 Dashboard</div>
<div id="dashSub" class="submenu">
  <div onclick="showSection('dashboard')">Overview</div>
</div>

<div class="menu-item" onclick="toggleSubmenu('mapSub')">🗺️ Map & AQI</div>
<div id="mapSub" class="submenu">
  <div onclick="showSection('map')">City Map</div>
  <div onclick="showSection('aqiInfo')">About AQI</div>
</div>

<div class="menu-item" onclick="toggleSubmenu('graphsSub')">📊 Graphs</div>
<div id="graphsSub" class="submenu">
  <div onclick="showSection('graphs')">Temperature Trend</div>
  <div onclick="showSection('aqiGraph')">AQI Trend</div>
</div>

<div class="menu-item" onclick="toggleSubmenu('inventorySub')">📦 Inventory</div>
<div id="inventorySub" class="submenu">
  <div onclick="showSection('inventory')">Inventory Details</div>
  <div onclick="showSection('inventoryInfo')">Why Inventory Matters</div>
</div>

<div class="menu-item" onclick="toggleSubmenu('reportsSub')">📝 Reports</div>
<div id="reportsSub" class="submenu">
  <div onclick="showSection('reports')">Official Reports</div>
  <div onclick="showSection('alertsInfo')">Heatwave Alerts Info</div>
</div>

<div class="menu-item" onclick="toggleSubmenu('solutionsSub')">💡 Solutions</div>
<div id="solutionsSub" class="submenu">
  <div onclick="showSection('solutions')">Tips & Steps</div>
  <div onclick="showSection('whySolutions')">Why These Work</div>
</div>

<div class="menu-item" onclick="toggleSubmenu('forecastSub')">🤖 AI Forecast</div>
<div id="forecastSub" class="submenu">
  <div onclick="showSection('forecast')">7-Day Forecast</div>
  <div onclick="showSection('forecastInfo')">About Forecasting</div>
</div>

<div class="menu-item" onclick="toggleSubmenu('feedbackSub')">💬 Feedback</div>
<div id="feedbackSub" class="submenu">
  <div onclick="showSection('feedback')">Submit Feedback</div>
</div>

<div class="menu-item" onclick="toggleSubmenu('foundersSub')">👤 Founders</div>
<div id="foundersSub" class="submenu">
  <div onclick="showSection('founders')">Team Members</div>
</div>

</div>

<!-- TOPBAR -->
<div class="topbar">
<input class="search" placeholder="Search…">
</div>

<!-- CONTENT -->
<div class="content">

<!-- DASHBOARD -->
<div class="section" id="dashboard">
  <div class="card" style="text-align:center; background:#ffefef; padding:40px;">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3e/Shield_icon.svg/512px-Shield_icon.svg.png" alt="Heat Shield Logo" style="width:120px; height:120px; object-fit:contain; margin-bottom:20px;">
    <h1 style="font-weight:bold; font-size:42px; margin-bottom:15px; letter-spacing:2px;">HEAT SHIELD 🛡️</h1>
    <p style="font-size:18px; color:#555; max-width:750px; margin:auto; line-height:1.5;">
      Stay safe from heatwaves with real-time alerts, AQI tracking, and personalized solutions.
    </p>
  </div>
</div>

<!-- MAP -->
<div class="section" id="map">
<h3>City Heat & AQI Map</h3>
<div class="card">
<iframe width="100%" height="300" src="https://maps.google.com/maps?q=mumbai&t=&z=13&ie=UTF8&iwloc=&output=embed"></iframe>
</div>
<p style="font-size:16px; color:#444; margin-top:15px;">
  This map shows real‑time temperature and air quality index (AQI) across your city. Monitor heatwave zones and air pollution levels at a glance.
</p>
</div>

<!-- AQI Info -->
<div class="section" id="aqiInfo">
<h3>About Air Quality Index (AQI)</h3>
<div class="card">
<p>AQI is a number used to communicate how clean or polluted the air is. It helps you understand the health impacts of air quality:</p>
<ul style="text-align:left;">
<li><strong>0–50:</strong> Good — Air pollution poses little or no risk.</li>
<li><strong>51–100:</strong> Moderate — Acceptable air quality.</li>
<li><strong>101–150:</strong> Unhealthy for sensitive groups.</li>
<li><strong>151–200:</strong> Unhealthy — Everyone may begin to experience health effects.</li>
<li><strong>201+ :</strong> Very Unhealthy / Hazardous.</li>
</ul>
</div>
</div>

<!-- GRAPHS -->
<div class="section" id="graphs">
<h3>Weekly Temperature Trend</h3>
<canvas id="chart"></canvas>
</div>

<div class="section" id="aqiGraph">
<h3>Weekly AQI Trend</h3>
<canvas id="aqiChart"></canvas>
</div>

<!-- Inventory -->
<div class="section" id="inventory">
<h3>Inventory Details</h3>
<div class="cards">
<div class="card">💊 Medicines: Available</div>
<div class="card">❄ Cooling Devices: 12 Units</div>
<div class="card">💧 Water Bottles: 200 L</div>
<div class="card">🛠 Emergency Kits: Ready</div>
</div>
</div>

<div class="section" id="inventoryInfo">
<h3>Why Inventory Matters</h3>
<div class="card">
<p>During heatwaves, essential supplies like water, medicines, cooling devices, and emergency kits help reduce risks like dehydration, heat exhaustion, and medical emergencies. A well‑stocked inventory is vital for personal safety and community support.</p>
</div>
</div>

<!-- Reports -->
<div class="section" id="reports">
<h3>Official Heatwave Reports</h3>
<div class="card">
<p>Weather and health agencies monitor heatwave conditions and issue alerts to help protect communities. These reports include temperature forecasts, AQI levels, and safety recommendations.</p>
</div>
</div>

<div class="section" id="alertsInfo">
<h3>Heatwave Alerts Information</h3>
<div class="card">
<p>Heatwave alerts are warnings issued when extreme heat conditions are expected. They help people prepare by recommending hydration, staying cool, and limiting outdoor exposure.</p>
</div>
</div>

<!-- Solutions -->
<div class="section" id="solutions">
<h3>Heatwave Tips & Steps</h3>
<div class="cards">
<div class="card">💧 Hydration Reminder: Drink water often.</div>
<div class="card">❄ Cooling Tips: Seek cool/shaded areas.</div>
<div class="card">⚡ Emergency Steps: Call authorities if needed.</div>
</div>
</div>

<div class="section" id="whySolutions">
<h3>Why These Tips Work</h3>
<div class="card">
<p>Hydration prevents heat exhaustion, cooling helps regulate body temperature, and knowing emergency steps ensures quick, safe actions during extreme heat events.</p>
</div>
</div>

<!-- AI Forecast -->
<div class="section" id="forecast">
<h3>7‑Day Forecast</h3>
<div class="card">
<ul style="text-align:left;">
<li>Mon: 39°C — Moderate</li>
<li>Tue: 40°C — Moderate</li>
<li>Wed: 42°C — High</li>
<li>Thu: 41°C — Moderate</li>
<li>Fri: 43°C — High</li>
<li>Sat: 44°C — Very High</li>
<li>Sun: 42°C — High</li>
</ul>
</div>
</div>

<div class="section" id="forecastInfo">
<h3>About Forecasting</h3>
<div class="card">
<p>Heatwave forecasting uses weather models to predict temperature trends. Advanced AI tools improve accuracy by analyzing historical and real‑time data.</p>
</div>
</div>

<!-- Founders -->
<div class="section" id="founders">
<h3>Founders & Contributors</h3>
<div class="cards">
<div class="card">Vedant Pawar</div>
<div class="card">Pooja Gupta</div>
<div class="card">Piyush Dhawale</div>
<div class="card">Shreyas Gaikwad</div>
<div class="card">Prasenjit Gaikwad</div>
<div class="card">Viraj Punna</div>
<div class="card">AI Assistance — ChatGPT</div>
</div>
</div>

<!-- Feedback / Questions & Suggestions -->
<div class="section" id="feedback">
<h3>Submit Questions & Suggestions</h3>
<div class="card">
<form id="feedbackForm">
    <input type="text" id="fbName" placeholder="Your Name" required>
    <input type="email" id="fbEmail" placeholder="Your Email" required>
    <textarea id="fbMessage" placeholder="Your Question or Suggestion" rows="4" required></textarea>
    <button type="submit">Submit</button>
</form>
<div class="small">Your questions and suggestions will appear below once submitted.</div>
</div>

<div class="card" style="margin-top:20px;">
<h4>Submitted Questions & Suggestions:</h4>
<div id="submittedFeedback"></div>
</div>
</div>

<!-- LOGIN POPUP -->
<div class="loginPopup" id="loginPopup">
<div class="loginBox">
<h3>Login (Optional)</h3>
<input placeholder="Username">
<input type="password" placeholder="Password">
<button onclick="closeLogin()">Continue</button>
</div>
</div>

<script>
// Sidebar toggle
function toggleMenu(){document.getElementById("sidebar").classList.toggle("open");}

// Show section
function showSection(id){
  document.querySelectorAll('.section').forEach(sec=>sec.style.display='none');
  document.getElementById(id).style.display='block';
}

// Toggle submenu
function toggleSubmenu(id){
  const submenu=document.getElementById(id);
  submenu.style.display = submenu.style.display === 'flex' ? 'none' : 'flex';
}

// Open Dashboard by default
showSection('dashboard');

// Login popup
setTimeout(()=>{document.getElementById("loginPopup").style.display="flex";},8000);
function closeLogin(){document.getElementById("loginPopup").style.display="none";}

// Charts
const ctx=document.getElementById('chart')?.getContext('2d');
if(ctx){
new Chart(ctx,{type:'line',data:{labels:["Mon","Tue","Wed","Thu","Fri","Sat","Sun"],datasets:[{label:"Temperature (°C)",data:[36,37,39,40,41,42,41],borderColor:'#ff6e7f',backgroundColor:'rgba(255,110,127,0.2)',fill:true,tension:0.4}]}});
}

const ctxAQI=document.getElementById('aqiChart')?.getContext('2d');
if(ctxAQI){
new Chart(ctxAQI,{type:'bar',data:{labels:["Mon","Tue","Wed","Thu","Fri","Sat","Sun"],datasets:[{label:"AQI",data:[45,55,70,60,80,65,50],backgroundColor:'rgba(54,162,235,0.6)'}]}});
}

// Feedback form submission
const feedbackForm = document.getElementById('feedbackForm');
const submittedFeedback = document.getElementById('submittedFeedback');

feedbackForm.addEventListener('submit', function(e){
    e.preventDefault();
    const name = document.getElementById('fbName').value.trim();
    const email = document.getElementById('fbEmail').value.trim();
    const message = document.getElementById('fbMessage').value.trim();

    if(name && email && message){
        const item = document.createElement('div');
        item.style.borderBottom = "1px solid #eee";
        item.style.padding = "10px 0";
        item.innerHTML = `<strong>${name} (${email})</strong><p>${message}</p>`;
        submittedFeedback.appendChild(item);

        feedbackForm.reset();
    }
});
</script>
</body>
</html>
