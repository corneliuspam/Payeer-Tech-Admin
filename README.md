<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>PAYEER TECH Admin Panel</title>
<link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" rel="stylesheet">
<style>
  body{margin:0;font-family:Segoe UI,sans-serif;background:#f5f5f5;color:#333;}
  header{background:#2196f3;padding:20px;text-align:center;font-size:28px;font-weight:bold;color:#fff;box-shadow:0 2px 10px rgba(0,0,0,.2);}
  .container{display:flex;flex-wrap:wrap;padding:20px;gap:20px;}
  .card{background:#fff;padding:20px;border-radius:16px;flex:1 1 400px;box-shadow:0 0 15px rgba(0,0,0,.1);}
  h3{color:#f44336;margin-top:0;font-size:22px;}
  input, textarea, select{width:100%;padding:12px;margin-top:10px;border-radius:10px;border:1px solid #ccc;font-size:16px;}
  textarea{resize:none;}
  button{padding:14px;width:100%;border:none;border-radius:12px;background:#4caf50;color:#fff;font-size:16px;margin-top:12px;cursor:pointer;}
  table{width:100%;border-collapse:collapse;margin-top:12px;}
  th, td{border-bottom:1px solid #ddd;padding:10px;text-align:left;font-size:14px;}
  .approve{background:#2196f3;}
  .reject{background:#f44336;}
  .logout{background:#9e9e9e;margin-top:25px;}
  .section-title{display:flex;justify-content:space-between;align-items:center;margin-bottom:12px;font-size:20px;}
  @media(max-width:900px){.container{flex-direction:column;}}
</style>
</head>
<body>

<header>PAYEER TECH Admin Panel</header>
<div class="container">

  <!-- ADMIN LOGIN -->
  <div class="card" id="loginCard">
    <h3>Admin Login</h3>
    <input id="adminEmail" type="email" placeholder="Enter Gmail" />
    <input id="adminPassword" type="password" placeholder="Enter Password" />
    <button onclick="adminLogin()">Login</button>
    <p id="loginStatus" style="color:red;"></p>
  </div>

  <!-- DASHBOARD -->
  <div id="dashboard" style="display:none;flex:1 1 100%;">

    <!-- ANNOUNCEMENTS -->
    <div class="card">
      <div class="section-title"><h3>Post Announcement</h3></div>
      <textarea id="announcement" rows="3" placeholder="Message for all users"></textarea>
      <button onclick="postAnnouncement()">Send Announcement</button>
    </div>

    <!-- CREATE TASK -->
    <div class="card">
      <div class="section-title"><h3>Create Task</h3></div>
      <input id="taskTitle" placeholder="Task Title" />
      <input id="taskAmount" value="1000" disabled />
      <button onclick="createTask()">Create Task</button>
    </div>

    <!-- PENDING TASK SUBMISSIONS -->
    <div class="card">
      <div class="section-title"><h3>Pending Task Submissions</h3></div>
      <table>
        <tr><th>User ID</th><th>Task</th><th>Action</th></tr>
        <tr>
          <td>123456</td>
          <td>Join Telegram Channel</td>
          <td><button class="approve" onclick="approveTask()">Approve</button></td>
        </tr>
      </table>
    </div>

    <!-- WITHDRAWAL REQUESTS -->
    <div class="card">
      <div class="section-title"><h3>Withdrawal Requests</h3></div>
      <table>
        <tr><th>User</th><th>Amount</th><th>Bank</th><th>Action</th></tr>
        <tr>
          <td>123456</td>
          <td>₦5000</td>
          <td>GTBank<br>0123456789<br>John Doe</td>
          <td><button class="approve" onclick="approveWithdrawal()">Approve</button></td>
        </tr>
      </table>
    </div>

    <button class="logout" onclick="logout()">Logout</button>
  </div>
</div>

<script>
const ADMIN_EMAIL='youremail@gmail.com';
const ADMIN_PASS='2001@pam';

function adminLogin(){
  const email=document.getElementById('adminEmail').value;
  const pass=document.getElementById('adminPassword').value;
  if(email===ADMIN_EMAIL && pass===ADMIN_PASS){
    document.getElementById('loginCard').style.display='none';
    document.getElementById('dashboard').style.display='flex';
  } else {
    document.getElementById('loginStatus').innerText='Invalid email or password';
  }
}

function postAnnouncement(){alert('Announcement sent (connect backend)');}
function createTask(){alert('Task created (₦1000)');}
function approveTask(){alert('Task approved. Balance updated');}
function approveWithdrawal(){alert('Withdrawal approved');}
function logout(){location.reload();}
</script>

</body>
</html>
