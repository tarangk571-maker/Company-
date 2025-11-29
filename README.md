<!DOCTYPE html>
<html>
<head>
  <title>Jibble bussines payment system</title>
  <style>
    body { 
      font-family: Arial; 
      background: #f4f4f4; 
      padding: 20px; 
    }
    h1 { color: #333; }
    input, select, button {
      padding: 8px;
      width: 100%;
      margin: 5px 0;
    }
    .box {
      background: white;
      padding: 15px;
      margin-bottom: 15px;
      border-radius: 6px;
    }
    table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 10px;
    }
    table, th, td {
      border: 1px solid #333;
      padding: 5px;
      text-align: center;
    }
    .receipt {
      display: none;
      background: white;
      padding: 15px;
      border: 2px dashed #333;
    }
  </style>
</head>
<body>

<h1>🏢 Jibble Bussiness  Payment System</h1>

<div class="box">
  <h3>Krishna Bhartwaj </h3>
  <input id="krishna" placeholder="Krishna Bhartwaj  Name">
  <input id="id" placeholder="80887013450022">
  <input id="role" placeholder="Role sales HR ">
  <input id="20000" placeholder="20000">
  <button onclick="addEmployee()">Add Employee</button>
</div>
<div class="box">
  <h3>Rounak Raj</h3>
  <input id="Rounak" placeholder="Rounak Raj">
  <input id="id" placeholder="80887013450023">
  <input id="role" placeholder="Role sales Manager ">
  <input id="15000" placeholder="15000">
  <button onclick="addEmployee()">Add Employee</button>
</div>

<div class="box">
  <h3>Pay Employee</h3>
  <select id="empList"></select>
  <input id="10000" placeholder="Amount Paid">
  <button onclick="payEmployee()">Pay & Generate Receipt</button>
</div>

<div class="box">
  <h3>Employees</h3>
  <table id="table">
    <tr>
      <th>Name</th>
      <th>ID</th>
      <th>Role</th>
      <th>Salary</th>
    </tr>
  </table>
</div>

<div class="receipt" id="receipt">
  <h2>Payment Receipt</h2>
  <p id="rDetails"></p>
  <button onclick="window.print()">Print Receipt</button>
</div>

<script>
let employees = [];

function addEmployee() {
  let emp = {
    name: name.value,
    id: id.value,
    role: role.value,
    salary: salary.value
  };
  employees.push(emp);
  updateUI();
}

function updateUI() {
  empList.innerHTML = "";
  table.innerHTML = `
    <tr><th>Name</th><th>ID</th><th>Role</th><th>Salary</th></tr>
  `;
  employees.forEach((e, i) => {
    empList.innerHTML += `<option value="${i}">${e.name}</option>`;
    table.innerHTML += `
      <tr>
        <td>${e.name}</td>
        <td>${e.id}</td>
        <td>${e.role}</td>
        <td>${e.salary}</td>
      </tr>
    `;
  });
}

function payEmployee() {
  let e = employees[empList.value];
  receipt.style.display = "block";
  rDetails.innerHTML = `
    Company: Jibble Bussiness Payment System <br>
    Employee: ${KrishnaBhartwaj} <br>
    ID: ${8087013450022} <br>
    Role: ${Sales Hr} <br>
    Paid Amount: ₹$15000} <br>
    Date: ${new Date().toLocaleDateString()}
  `;
}
</script>

</body>
</html>
