<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>PAYEER TECH Admin</title>
<style>
  /* --- Global Styles --- */
  body {
    margin: 0;
    font-family: 'Segoe UI', sans-serif;
    background: #fff;
    color: #111;
  }

  header {
    background: #e53935;
    padding: 18px;
    text-align: center;
    font-size: 22px;
    font-weight: bold;
    color: #fff;
  }

  .container {
    padding: 15px;
  }

  .card {
    background: #f5f5f5;
    border-radius: 12px;
    padding: 15px;
    margin-bottom: 15px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
  }

  .card h3 {
    margin-top: 0;
    color: #e53935;
  }

  input, textarea, select {
    width: 100%;
    padding: 10px;
    margin-top: 8px;
    border-radius: 8px;
    border: 1px solid #ccc;
  }

  button {
    padding: 10px;
    margin-top: 10px;
    border: none;
    border-radius: 8px;
    cursor: pointer;
    font-weight: bold;
    color: #fff;
  }

  .approve { background: #4caf50; }
  .reject { background: #f44336; }
  .logout { background: #555; width: 100%; margin-top: 20px; }

  table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 10px;
  }

  table th, table td {
    border-bottom: 1px solid #ccc;
    padding: 8px;
    text-align: left;
  }

  /* --- Floating Menu --- */
  .floating-menu {
    position: fixed;
    bottom: 20px;
    right: 20px;
    display: flex;
    flex-direction: column;
  }

  .floating-menu button {
    margin-top: 10px;
    width: 50px;
    height: 50px;
    border-radius: 50%;
    font-size: 20px;
    padding: 0;
  }
</style>
</head>
<body>

<header>PAYEER TECH Admin</header>
<div class="container">

  <!-- Admin Login -->
  <div class="card" id="loginCard">
    <h3>Admin Login</h3>
    <input type="email" id="adminEmail" placeholder="Email">
    <input type="password" id="adminPassword" placeholder="Password">
    <button onclick="login()">Login</button>
    <p id="loginStatus"></p>
  </div>

  <!-- Dashboard -->
  <div id="dashboard" style="display:none">

    <!-- Post Announcement -->
    <div class="card">
      <h3>Post Announcement</h3>
      <textarea id="announcement" rows="3" placeholder="Message to users"></textarea>
      <button onclick="postAnnouncement()">Post</button>
    </div>

    <!-- Create Task -->
    <div class="card">
      <h3>Create Task</h3>
      <input id="taskTitle" placeholder="Task Title">
      <input id="taskAmount" value="1000" disabled>
      <button onclick="createTask()">Create Task</button>
    </div>

    <!-- Pending Tasks -->
    <div class="card">
      <h3>Pending Task Submissions</h3>
      <table>
        <tr><th>User ID</th><th>Task</th><th>Action</th></tr>
        <tr>
          <td>123456789</td>
          <td>Join Telegram Channel</td>
          <td>
            <button class="approve" onclick="approveTask()">Approve</button>
            <button class="reject" onclick="rejectTask()">Reject</button>
          </td>
        </tr>
      </table>
    </div>

    <!-- Withdrawals -->
    <div class="card">
      <h3>Withdrawal Requests</h3>
      <table>
        <tr><th>User</th><th>Amount</th><th>Bank</th><th>Action</th></tr>
        <tr>
          <td>123456789</td>
          <td>₦5000</td>
          <td>GTBank<br>0123456789<br>John Doe</td>
          <td>
            <button class="approve" onclick="approveWithdrawal()">Approve</button>
            <button class="reject" onclick="rejectWithdrawal()">Reject</button>
          </td>
        </tr>
      </table>
    </div>

    <button class="logout" onclick="logout()">Logout</button>
  </div>

</div>

<!-- Floating Menu -->
<div class="floating-menu">
  <button onclick="scrollToSection('dashboard')">📋</button>
  <button onclick="scrollToSection('announcement')">📢</button>
  <button onclick="scrollToSection('taskTitle')">💼</button>
</div>

<script>
  const ADMIN_EMAIL = "corneliuspam8736@gmail.com";
  const ADMIN_PASSWORD = "2001@pam";

  function login(){
    const email = document.getElementById('adminEmail').value;
    const pass = document.getElementById('adminPassword').value;
    if(email === ADMIN_EMAIL && pass === ADMIN_PASSWORD){
      document.getElementById('loginCard').style.display = 'none';
      document.getElementById('dashboard').style.display = 'block';
    } else {
      document.getElementById('loginStatus').innerText = "Invalid credentials";
    }
  }

  function postAnnouncement(){ alert("Announcement posted (mock)."); }
  function createTask(){ alert("Task created: ₦1000 (mock)."); }
  function approveTask(){ alert("Task approved."); }
  function rejectTask(){ alert("Task rejected."); }
  function approveWithdrawal(){ alert("Withdrawal approved."); }
  function rejectWithdrawal(){ alert("Withdrawal rejected."); }
  function logout(){ location.reload(); }

  function scrollToSection(id){ 
    document.getElementById(id).scrollIntoView({behavior:'smooth'}); 
  }
</script>

</body>
</html>
