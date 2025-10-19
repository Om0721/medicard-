# medicard-
Medicard is a new digital way of hospital services just like rent hospital equipment, book lab test,find medicine,, book doctor appointments,etc
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Medicart App</title>
<style>
/* MAIN PAGE CSS */
* { margin:0; padding:0; box-sizing:border-box; font-family:'Segoe UI', sans-serif;}
body {background: linear-gradient(to right, #e0f7fa, #fce4ec);}
nav {background-color:#00897b; display:flex; justify-content:space-between; align-items:center; padding:1rem 2rem; color:white;}
nav .logo {font-size:1.5rem; font-weight:bold;}
nav ul {list-style:none; display:flex; gap:1rem;}
nav ul li {cursor:pointer; padding:0.5rem 1rem; border-radius:4px; transition:background 0.3s;}
nav ul li:hover {background: rgba(255,255,255,0.2);}
.hero {padding:1rem 2rem; text-align:center; background:linear-gradient(to bottom, #f3e5f5, #e8f5e9);}
.hero h1 {font-size:2.5rem; margin-bottom:1rem; color:#00796b;}
.hero p {font-size:1.2rem; color:#555;}
.features {display:flex; justify-content:space-around; flex-wrap:wrap; padding:2rem; gap:2rem;}
.feature-card {background:white; width:280px; padding:1.5rem; border-radius:12px; box-shadow:0 4px 20px rgba(0,0,0,0.1); text-align:center; transition: transform 0.3s;}
.feature-card:hover {transform:translateY(-5px);}
.feature-card img {width:100%; height:160px; object-fit:cover; border-radius:10px; margin-bottom:1rem;}
.feature-card h3 {margin-bottom:0.5rem; color:#00695c;}
.feature-card p {color:#777;}
.feature-card button {margin-top:1rem; padding:0.5rem 1rem; background-color:#00897b; border:none; color:white; border-radius:5px; cursor:pointer;}
footer {background:#00897b; color:white; text-align:center; padding:1rem; margin-top:2rem;}

/* LOGIN CSS */
.login-container {max-width:400px; margin:5% auto; background:white; padding:2rem; border-radius:12px; box-shadow:0 10px 20px rgba(0,0,0,0.2); text-align:center;}
.login-container h2 {color:#45b649; margin-bottom:1.5rem;}
input[type="text"], input[type="password"] {width:90%; padding:0.7rem; margin:0.6rem 0; border:1px solid #ccc; border-radius:6px;}
.login-container button {background:#45b649; color:white; padding:0.7rem 1.5rem; border:none; border-radius:6px; font-size:1rem; cursor:pointer; margin-top:1rem;}
.login-container button:hover {background:#388e3c;}
.login-container .logo {width:80px; margin-bottom:1rem;}

/* APPOINTMENT CSS */
.container {max-width:500px; margin:2rem auto; background:white; padding:2rem; border-radius:12px; box-shadow:0 5px 25px rgba(0,0,0,0.1);}
h2 {text-align:center; color:#1976d2; margin-bottom:1rem;}
label {display:block; margin:1rem 0 0.5rem; font-weight:bold;}
input, select, button {width:100%; padding:0.8rem; margin-bottom:1rem; border-radius:6px; border:1px solid #ccc;}
button[type="submit"] {background-color:#1976d2; color:white; border:none; font-weight:bold; cursor:pointer;}
button[type="submit"]:hover {background-color:#0d47a1;}
.back-button {background-color:#e0e0e0; color:#333; border:none; padding:0.6rem 1rem; border-radius:6px; cursor:pointer; font-weight:bold;}
.back-button:hover {background-color:#bdbdbd;}
.success {margin-top:1rem; padding:1rem; background-color:#c8e6c9; border:1px solid #388e3c; color:#2e7d32; border-radius:6px; display:none;}

/* RENT CSS */
.equipment-grid {display:flex; flex-wrap:wrap; justify-content:center; gap:1rem;}
.equipment-item {width:220px; background:#f5f5f5; padding:1rem; border-radius:8px; box-shadow:0 2px 8px rgba(0,0,0,0.1); text-align:center;}
.equipment-item img {width:100%; height:200px; object-fit:cover; border-radius:6px;}
.equipment-item h3 {margin:0.8rem 0 0.4rem;}
.equipment-item button {background:#66bb6a; color:white; border:none; padding:0.5rem 1rem; border-radius:4px; cursor:pointer;}

/* LAB CSS */
.test-list {display:flex; flex-wrap:wrap; gap:3rem; justify-content:center;}
.test-item {background:white; padding:1rem; border-radius:10px; box-shadow:0 4px 10px rgba(0,0,0,0.1); width:250px; text-align:center;}
.test-item h3 {margin:0.5rem 0;}
.test-item button {margin-top:0.5rem; padding:0.5rem 1rem; background-color:#00897b; color:white; border:none; border-radius:5px; cursor:pointer;}
.test-item button:hover {background-color:#00695c;}

/* MEDIFIND CSS */
#commonMedicines {display:flex; flex-wrap:wrap; gap:10px; justify-content:center; margin-bottom:20px;}
#commonMedicines button {padding:8px 16px; font-size:14px; background:#00897b; color:white; border:none; border-radius:20px; cursor:pointer;}
#commonMedicines button:hover {background:#0066cc;}
.search-bar {display:flex; justify-content:center; margin-bottom:30px;}
.search-bar input {width:60%; padding:14px; font-size:16px; border:none; border-radius:10px 0 0 10px;}
.search-bar button {padding:14px 20px; font-size:16px; background:#007bff; color:white; border:none; border-radius:0 10px 10px 0; cursor:pointer;}
.medicine-list {display:grid; grid-template-columns:repeat(auto-fit,minmax(260px,1fr)); gap:20px;}
.card {background:rgba(255,255,255,0.85); backdrop-filter:blur(6px); border-radius:16px; padding:20px; box-shadow:0 6px 15px rgba(0,0,0,0.1); transition:0.3s;}
.card:hover {transform:scale(1.03);}
.card h3 {color:#003366; margin-bottom:10px;}
.card p {margin:5px 0;}
.call-btn {display:inline-block; margin-top:10px; background-color:#28a745; color:white; padding:10px 14px; border-radius:8px; text-decoration:none; font-weight:bold;}
.no-result {text-align:center; font-size:18px; color:#555;}

/* ADMIN DASH */
.admin-controls {display:flex; gap:10px; justify-content:flex-end; margin-bottom:10px;}
.admin-controls button {padding:8px 12px; border-radius:6px; border:none; cursor:pointer;}
.admin-controls .csv {background:#00796b; color:white;}
.admin-controls .logout {background:#c62828; color:white;}
.user-card {border:1px solid #ddd; border-radius:8px; padding:12px; margin-bottom:10px; background:white;}
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="logo">Medicart</div>
  <ul id="navLinks">
    <li onclick="showSection('homeSection')">Home</li>
    <li onclick="showSection('appointmentSection')">Book Appointment</li>
    <li onclick="showSection('rentSection')">Rent Equipment</li>
    <li onclick="showSection('labSection')">Lab Tests</li>
    <li onclick="showSection('mediFindSection')">MediFind</li>
   <li onclick="showSection('loginSection')" id="loginNav">Login/Register</li>
    <li onclick="showAdminLogin()">Admin Dashboard</li>
  </ul>
  <div id="userInfo" style="color:white; font-weight:bold; display:none;">
    <span id="usernameDisplay"></span>
    <button onclick="logout()" style="margin-left:10px; padding:3px 8px; border:none; border-radius:5px; cursor:pointer; background:#c62828; color:white;">Logout</button>
  </div>
</nav>

<!-- HOME SECTION -->
<section id="homeSection" class="hero">
  <h1>Welcome to Medicart Health Services</h1>
  <p>Your one-stop solution for medicine search, doctor appointments, and hospital equipment rentals.</p>
  <div class="features">
    <div class="feature-card">
      <img src="https://img.freepik.com/premium-psd/modern-hospital-bed-with-blue-linens-transparent-background_84443-29256.jpg" alt="Hospital Bed"/>
      <h3>Rent Hospital Equipment</h3>
      <p>Hospital beds, wheelchairs, oximeters, walkers and more.</p>
      <button onclick="showSection('rentSection')">Explore</button>
    </div>
    <div class="feature-card">
      <img src="https://img.freepik.com/free-vector/medicine-search-concept-illustration_114360-6336.jpg?w=740" alt="MediFinder"/>
      <h3>MediFinder</h3>
      <p>Check where a medicine is available and its price nearby.</p>
      <button onclick="showSection('mediFindSection')">Find</button>
    </div>
    <div class="feature-card">
      <img src="https://img.freepik.com/free-vector/online-doctor-appointment-booking-concept-illustration_1150-50261.jpg?w=740" alt="Doctor Appointment"/>
      <h3>Book Appointment</h3>
      <p>Book doctor appointments and get your queue number instantly.</p>
      <button onclick="showSection('appointmentSection')">Book Now</button>
    </div>
  </div>
</section>

<!-- USER LOGIN/REGISTER SECTION -->
<section id="loginSection" style="display:none;">
  <div class="login-container">
    <img src="https://cdn-icons-png.flaticon.com/512/4290/4290854.png" alt="Medicart Logo" class="logo">
    <h2>Login / Register - Medicart</h2>
    <input type="text" id="fullName" placeholder="Full Name (for Register only)" />
    <input type="text" id="username" placeholder="Mobile Number" />
    <input type="password" id="password" placeholder="Password" />
    <button onclick="registerUser()">Register</button>
    <button onclick="loginUser()">Login</button>
  </div>
</section>

<!-- APPOINTMENT SECTION -->
<section id="appointmentSection" style="display:none;">
  <div class="container">
    <h2>Book Doctor Appointment</h2>
    <label>Doctor:</label>
    <select id="doctor">
      <option>Dr. Sharma (Cardiologist)</option>
      <option>Dr. Patel (Dermatologist)</option>
      <option>Dr. Singh (General Physician)</option>
    </select>
    <label>Date:</label>
    <input type="date" id="appointmentDate" />
    <label>Time:</label>
    <input type="time" id="appointmentTime" />
    <button onclick="bookAppointment()">Book Appointment</button>
    <div class="success" id="appointmentSuccess">Appointment booked successfully!</div>
  </div>
</section>

<!-- RENT SECTION -->
<section id="rentSection" style="display:none;">
  <div class="container">
    <h2>Hospital Equipment Rent</h2>
    <div class="equipment-grid" id="equipmentGrid"></div>
  </div>
</section>

<!-- LAB TEST SECTION -->
<section id="labSection" style="display:none;">
  <div class="container">
    <h2>Book Lab Tests</h2>
    <div class="test-list" id="labTestsList"></div>
  </div>
</section>

<!-- MEDIFIND SECTION -->
<section id="mediFindSection" style="display:none;">
  <div class="container">
    <h2>Find Medicine</h2>
    <div id="commonMedicines"></div>
    <div class="search-bar">
      <input type="text" id="medicineSearch" placeholder="Search medicine..." />
      <button onclick="searchMedicine()">Search</button>
    </div>
    <div class="medicine-list" id="medicineList"></div>
    <div class="no-result" id="noResult" style="display:none;">No medicines found</div>
  </div>
</section>

<!-- ADMIN LOGIN SECTION -->
<section id="adminLoginSection" style="display:none;">
  <div class="login-container">
    <h2>Admin Login</h2>
    <input type="text" id="adminUsername" placeholder="Admin Username"/>
    <input type="password" id="adminPassword" placeholder="Admin Password"/>
    <button onclick="adminLogin()">Login as Admin</button>
  </div>
</section>

<!-- ADMIN DASHBOARD SECTION -->
<section id="adminDashboard" style="display:none;">
  <div class="container">
    <h2>Admin Dashboard - All User Reports</h2>
    <div class="admin-controls">
      <button class="csv" onclick="downloadAllUsersCSV()">Download All Users CSV</button>
      <button class="logout" onclick="adminLogout()">Logout Admin</button>
    </div>
    <div id="allUsersReport"></div>
  </div>
</section>

<footer>© 2025 Medicart. All Rights Reserved.</footer>

<script>
  // USERS
  let users = JSON.parse(localStorage.getItem('users')) || {};
  // normalize older users that might be stored as arrays or other shapes:
  // ensure every user entry is an object with fields: name, password, appointments, rent, lab
  Object.keys(users).forEach(u=>{
    const entry = users[u];
    if(typeof entry !== 'object' || entry === null){
      users[u] = { name: u, password: String(entry || ''), appointments:[], rent:[], lab:[] };
    } else {
      users[u].name = entry.name || u;
      users[u].password = entry.password || '';
      users[u].appointments = Array.isArray(entry.appointments)? entry.appointments : [];
      users[u].rent = Array.isArray(entry.rent)? entry.rent : [];
      users[u].lab = Array.isArray(entry.lab)? entry.lab : [];
    }
  });

  let currentUser = localStorage.getItem('currentUser') || null;

  // MEDICINES
  const medicines = [
    {name:"Paracetamol", price:30, phone:"1234567890"},
    {name:"Azithromycin", price:120, phone:"1234567891"},
    {name:"Vitamin C", price:50, phone:"1234567892"},
    {name:"Cough Syrup", price:80, phone:"1234567893"},
    {name:"Pain Relief Gel", price:100, phone:"1234567894"}
  ];
  const commonMeds = ["Paracetamol","Vitamin C","Cough Syrup"];

  // EQUIPMENT
  const equipment = [
    {name:"Hospital Bed", img:"https://img.freepik.com/premium-psd/modern-hospital-bed-with-blue-linens-transparent-background_84443-29256.jpg", price:200},
    {name:"Wheelchair", img:"chair.jpeg", price:150},
    {name:"Oximeter", img:"oxi.jpeg", price:80},
    {name:"Walker", img:"walker.jpeg", price:120}
  ];

  // LAB TESTS
  const labTests = [
    {name:"Blood Test", price:200, instructions:"Fasting required 8 hrs"},
    {name:"X-Ray", price:500, instructions:"Remove metal objects"},
    {name:"MRI Scan", price:3000, instructions:"Remove jewelry"},
    {name:"Covid Test", price:600, instructions:"Nasal swab sample"}
  ];

  // ADMIN CREDENTIALS
  const adminCredentials = {username:'admin', password:'admin123'};
  let isAdminLoggedIn = false;

  // SHOW SECTION
  function hideAllSections(){document.querySelectorAll('section').forEach(s=>s.style.display='none');}
  function showSection(id){hideAllSections(); document.getElementById(id).style.display='block';}

  function showAdminLogin(){hideAllSections(); document.getElementById('adminLoginSection').style.display='block';}

  // REGISTER
  function registerUser(){
    const n=document.getElementById('fullName').value.trim();
    const u=document.getElementById('username').value.trim();
    const p=document.getElementById('password').value.trim();
    if(!n || !u || !p){ alert("Enter valid Name, Mobile and Password"); return;}
    if(users[u]){ alert("User already exists"); return;}
    users[u]={name:n, password:p, appointments:[], rent:[], lab:[]};
    localStorage.setItem('users', JSON.stringify(users));
    alert("Registration successful");
    // clear fields
    document.getElementById('fullName').value='';
    document.getElementById('username').value='';
    document.getElementById('password').value='';
  }

  // LOGIN
  function loginUser(){
    const u=document.getElementById('username').value.trim();
    const p=document.getElementById('password').value.trim();
    if(users[u] && users[u].password===p){
      currentUser=u;
      localStorage.setItem('currentUser', u);
      alert("Login Successful");
      updateNavbar();
      showSection('homeSection');
      // clear login inputs
      document.getElementById('username').value='';
      document.getElementById('password').value='';
      document.getElementById('fullName').value='';
    } else { alert("Invalid credentials"); }
  }

  // LOGOUT
  function logout(){currentUser=null; localStorage.removeItem('currentUser'); alert("Logged out successfully"); updateNavbar(); showSection('homeSection');}

  // UPDATE NAVBAR
  function updateNavbar(){
    if(currentUser){
      document.getElementById('loginNav').style.display='none';
      document.getElementById('userInfo').style.display='flex';
      const displayName = (users[currentUser] && users[currentUser].name) ? users[currentUser].name : currentUser;
      document.getElementById('usernameDisplay').innerText=displayName;
    } else {
      document.getElementById('loginNav').style.display='block';
      document.getElementById('userInfo').style.display='none';
    }
  }
  updateNavbar();

  // APPOINTMENT BOOKING
  function bookAppointment(){
    if(!currentUser){ alert("Login first to book"); return;}
    const doctor=document.getElementById('doctor').value;
    const date=document.getElementById('appointmentDate').value;
    const time=document.getElementById('appointmentTime').value;
    if(!date){ alert("Select date"); return;}
    // ensure user exists
    users[currentUser] = users[currentUser] || {name: currentUser, password:'', appointments:[], rent:[], lab:[]};
    users[currentUser].appointments.push({doctor,date,time});
    localStorage.setItem('users', JSON.stringify(users));
    document.getElementById('appointmentSuccess').style.display='block';
    setTimeout(()=>document.getElementById('appointmentSuccess').style.display='none',3000);
    // clear date/time
    document.getElementById('appointmentDate').value='';
    document.getElementById('appointmentTime').value='';
  }

  // RENT
  const equipmentGrid=document.getElementById('equipmentGrid');
  equipment.forEach(eq=>{
    const div=document.createElement('div'); div.className='equipment-item';
    div.innerHTML=`<img src="${eq.img}" alt="${eq.name}"/><h3>${eq.name}</h3><p>₹${eq.price} / day</p><button onclick="rentEquipment('${eq.name}')">Rent</button>`;
    equipmentGrid.appendChild(div);
  });
  function rentEquipment(name){
    if(!currentUser){ alert("Login to rent"); return;}
    users[currentUser] = users[currentUser] || {name: currentUser, password:'', appointments:[], rent:[], lab:[]};
    users[currentUser].rent.push({name});
    localStorage.setItem('users', JSON.stringify(users));
    alert("Equipment rented successfully");
  }

  // LAB
  const labList=document.getElementById('labTestsList');
  labTests.forEach(test=>{
    const div=document.createElement('div'); div.className='test-item';
    div.innerHTML=`<h3>${test.name}</h3><p>Price: ₹${test.price}</p><p>Instructions: ${test.instructions}</p><button onclick="bookLabTest('${test.name}')">Book Test</button>`;
    labList.appendChild(div);
  });
  function bookLabTest(name){
    if(!currentUser){ alert("Login to book"); return;}
    users[currentUser] = users[currentUser] || {name: currentUser, password:'', appointments:[], rent:[], lab:[]};
    users[currentUser].lab.push({name});
    localStorage.setItem('users', JSON.stringify(users));
    alert("Lab test booked successfully");
  }

  // MEDIFIND
  const medDiv=document.getElementById('commonMedicines');
  commonMeds.forEach(med=>{
    const btn=document.createElement('button'); btn.innerText=med; btn.onclick=()=>searchMedicine(med);
    medDiv.appendChild(btn);
  });
  function searchMedicine(name){
    const searchValue=(name && typeof name === 'string')? name.toLowerCase() : document.getElementById('medicineSearch').value.trim().toLowerCase();
    const listDiv=document.getElementById('medicineList'); listDiv.innerHTML='';
    const results=medicines.filter(m=>m.name.toLowerCase().includes(searchValue));
    if(results.length===0){ document.getElementById('noResult').style.display='block'; return;} else{document.getElementById('noResult').style.display='none';}
    results.forEach(m=>{
      const card=document.createElement('div'); card.className='card';
      card.innerHTML=`<h3>${m.name}</h3><p>Price: ₹${m.price}</p><p>Contact: ${m.phone}</p><a href="tel:${m.phone}" class="call-btn">Call</a>`;
      listDiv.appendChild(card);
    });
  }

  // ADMIN LOGIN
  function adminLogin(){
    const u=document.getElementById('adminUsername').value.trim();
    const p=document.getElementById('adminPassword').value.trim();
    if(u===adminCredentials.username && p===adminCredentials.password){
      isAdminLoggedIn=true;
      hideAllSections();
      document.getElementById('adminDashboard').style.display='block';
      renderAllUsersReport();
      // clear admin fields
      document.getElementById('adminUsername').value='';
      document.getElementById('adminPassword').value='';
    } else { alert("Invalid admin credentials"); }
  }

  // RENDER ALL USERS
  function renderAllUsersReport(){
    const div=document.getElementById('allUsersReport'); div.innerHTML='';
    const keys = Object.keys(users);
    if(keys.length===0){ div.innerHTML="<p>No users registered yet.</p>"; return; }

    keys.forEach(username=>{
      const user = users[username] || {name: username, appointments:[], rent:[], lab:[]};
      const appointments = user.appointments && user.appointments.length ? user.appointments.map(a=>`${a.doctor} (${a.date} ${a.time||''})`).join(', ') : 'None';
      const rentals = user.rent && user.rent.length ? user.rent.map(r=>r.name).join(', ') : 'None';
      const labs = user.lab && user.lab.length ? user.lab.map(l=>l.name).join(', ') : 'None';

      const userHtml = document.createElement('div');
      userHtml.className = 'user-card';
      userHtml.innerHTML = `<h3>${escapeHtml(user.name)} (${escapeHtml(username)})</h3>
                            <p><b>Appointments:</b> ${escapeHtml(appointments)}</p>
                            <p><b>Rentals:</b> ${escapeHtml(rentals)}</p>
                            <p><b>Lab Tests:</b> ${escapeHtml(labs)}</p>`;
      div.appendChild(userHtml);
    });
  }

  // DOWNLOAD CSV FOR ALL USERS
  function downloadAllUsersCSV(){
    const keys = Object.keys(users);
    if(keys.length===0){ alert("No users to export"); return; }

    let csvContent = "data:text/csv;charset=utf-8,";
    csvContent += "Mobile,Name,Appointments,Rentals,Lab Tests\n";

    keys.forEach(username=>{
      const user = users[username] || {name: username, appointments:[], rent:[], lab:[]};
      const appointments = user.appointments && user.appointments.length ? user.appointments.map(a=>`${a.doctor} (${a.date} ${a.time||''})`).join('|') : 'None';
      const rentals = user.rent && user.rent.length ? user.rent.map(r=>r.name).join('|') : 'None';
      const labs = user.lab && user.lab.length ? user.lab.map(l=>l.name).join('|') : 'None';

      // Escape double quotes and wrap fields that may contain commas
      const line = `${escapeCsv(username)},"${escapeCsv(user.name)}","${escapeCsv(appointments)}","${escapeCsv(rentals)}","${escapeCsv(labs)}"\n`;
      csvContent += line;
    });

    const encodedUri = encodeURI(csvContent);
    const link = document.createElement("a");
    link.setAttribute("href", encodedUri);
    link.setAttribute("download", `all_users_report.csv`);
    document.body.appendChild(link);
    link.click();
    document.body.removeChild(link);
  }

  // ADMIN LOGOUT
  function adminLogout(){ isAdminLoggedIn=false; hideAllSections(); showAdminLogin(); }

  // small helpers
  function escapeCsv(text){
    if(text === null || text === undefined) return '';
    return String(text).replace(/"/g, '""');
  }
  function escapeHtml(text){
    if(text === null || text === undefined) return '';
    return String(text)
      .replace(/&/g, "&amp;")
      .replace(/</g, "&lt;")
      .replace(/>/g, "&gt;")
      .replace(/"/g, "&quot;")
      .replace(/'/g, "&#039;");
  }

  // initial rendering for equipment and lab already done above, ensure nav correct
  updateNavbar();
</script>

</body>
</html>
