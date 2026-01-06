<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>PAYEER TECH – Admin Panel</title>
  <style>
    body { margin: 0; font-family: Arial, sans-serif; background: #000; color: #fff; }
    header { background: #111; padding: 15px; text-align: center; font-size: 22px; font-weight: bold; color: #e53935; }
    .container { padding: 15px; }
    .card { background: #111; border-radius: 10px; padding: 15px; margin-bottom: 20px; }
    h3 { margin-top: 0; color: #4caf50; }
    input, textarea { width: 100%; padding: 10px; margin-top: 8px; border-radius: 6px; border: none; }
    textarea { resize: none; }
    button { width: 100%; padding: 12px; margin-top: 10px; border: none; border-radius: 8px; background: #e53935; color: #fff; font-size: 16px; cursor: pointer; }
    table { width: 100%; border-collapse: collapse; margin-top: 10px; }
    table th, table td { border-bottom: 1px solid #333; padding: 8px; text-align: left; }
    .approve { background: #4caf50; }
    .reject { background: #777; }
    .logout { background: #444; margin-top: 30px; }
  </style>
</head>
<body>

<header>PAYEER TECH – ADMIN PANEL</header>

<div class="container">

  <!-- ADMIN LOGIN -->
  <div class="card" id="loginCard">
    <h3>Admin Login</h3>
    <input id="adminPassword" type="password" placeholder="Admin Password" />
    <button onclick="adminLogin()">Login</button>
    <p id="loginStatus"></p>
  </div>

  <!-- DASHBOARD -->
  <div id="dashboard" style="display:none;">

    <!-- POST ANNOUNCEMENT -->
    <div class="card">
      <h3>Post Announcement</h3>
      <textarea id="announcement" rows="3" placeholder="Admin message shown to users"></textarea>
      <button onclick="postAnnouncement()">Post Announcement</button>
    </div>

    <!-- CREATE TASK -->
    <div class="card">
      <h3>Create Task</h3>
      <input id="taskTitle" placeholder="Task Title" />
      <input id="taskAmount" value="1000" disabled />
      <button onclick="createTask()">Create Task</button>
    </div>

    <!-- TASK SUBMISSIONS -->
    <div class="card">
      <h3>Pending Task Submissions</h3>
      <table>
        <tr><th>User ID</th><th>Task</th><th>Action</th></tr>
        <tr>
          <td>123456789</td>
          <td>Join Telegram Channel</td>
          <td><button class="approve" onclick="approveTask()">Approve</button></td>
        </tr>
      </table>
    </div>

    <!-- WITHDRAWAL REQUESTS -->
    <div class="card">
      <h3>Withdrawal Requests</h3>
      <table>
        <tr><th>User</th><th>Amount</th><th>Bank Details</th><th>Action</th></tr>
        <tr>
          <td>123456789</td>
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
  const ADMIN_PASS = 'admin123'; // CHANGE THIS before real use

  function adminLogin() {
    const pass = document.getElementById('adminPassword').value;
    if (pass === ADMIN_PASS) {
      document.getElementById('loginCard').style.display = 'none';
      document.getElementById('dashboard').style.display = 'block';
    } else {
      document.getElementById('loginStatus').innerText = 'Invalid admin password';
    }
  }

  function postAnnouncement() {
    alert('Announcement sent to users (connect backend API here)');
  }

  function createTask() {
    alert('Task created (₦1000) - connect backend API to save task');
  }

  function approveTask() {
    alert('Task approved. ₦1000 added to user balance - backend required');
  }

  function approveWithdrawal() {
    alert('Withdrawal approved. Pay user manually or via backend API');
  }

  function logout() {
    location.reload();
  }
</script>

</body>
</html>
