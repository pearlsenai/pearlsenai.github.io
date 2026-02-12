<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>H-ID System</title>
<style>
body {
    background:#0a0a0a;
    color:#00ffcc;
    font-family: monospace;
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
}
.box {
    border:2px solid #00ffcc;
    padding:20px;
    width:300px;
    text-align:center;
}
input {
    width:90%;
    margin:6px 0;
    padding:6px;
    background:black;
    color:#00ffcc;
    border:1px solid #00ffcc;
}
button {
    margin-top:10px;
    padding:6px 12px;
    background:black;
    color:#00ffcc;
    border:1px solid #00ffcc;
    cursor:pointer;
}
.hidden { display:none; }
.log { font-size:12px; color:#aaa; }
</style>
</head>
<body>

<div class="box" id="loginBox">
    <h2>LOGIN</h2>
    <input id="user" placeholder="Username">
    <input id="pass" type="password" placeholder="Password">
    <button onclick="login()">ENTER</button>
    <div class="log" id="loginMsg"></div>
</div>

<div class="box hidden" id="systemBox">
    <h2>ACCESS GRANTED</h2>
    <input id="hid" placeholder="ENTER H-ID">
    <br>
    <button onclick="start()">START</button>
    <button onclick="disable()">DISABLE</button>
    <div class="log" id="systemLog"></div>
</div>

<script>
function login() {
    const u = document.getElementById("user").value.trim();
    const p = document.getElementById("pass").value.trim();

    if (u === "monkey" && p === "S-355") {
        loginBox.classList.add("hidden");
        systemBox.classList.remove("hidden");
    } else {
        loginMsg.textContent = "ACCESS DENIED";
    }
}

function start() {
    const hid = document.getElementById("hid").value || "UNKNOWN";
    systemLog.textContent = "[SYSTEM] H-ID " + hid + " STARTED";
}

function disable() {
    const hid = document.getElementById("hid").value || "UNKNOWN";
    systemLog.textContent = "[SYSTEM] H-ID " + hid + " DISABLED";
}
</script>

</body>
</html>
