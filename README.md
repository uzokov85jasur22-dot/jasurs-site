<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<title>Jasur Site</title>

<style>
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: linear-gradient(120deg, #000428, #004e92);
  color: white;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

.box {
  background: rgba(0,0,0,0.7);
  padding: 35px;
  border-radius: 25px;
  text-align: center;
  box-shadow: 0 0 40px cyan;
}

.hidden { display: none; }

input {
  padding: 12px;
  border-radius: 12px;
  border: none;
  margin-top: 15px;
  font-size: 16px;
  text-align: center;
}

button {
  margin-top: 15px;
  padding: 12px 25px;
  border: none;
  border-radius: 20px;
  background: cyan;
  color: black;
  font-size: 16px;
  cursor: pointer;
}
</style>
</head>

<body>

<!-- START -->
<div class="box" id="start">
  <h1>👋 Привет, Jasur</h1>
  <button onclick="startSite()">Начать</button>
</div>

<!-- LOGIN -->
<div class="box hidden" id="login">
  <h2>Введите пароль</h2>
  <input type="password" id="password" placeholder="Пароль">
  <br>
  <button onclick="checkPassword()">Войти</button>
</div>

<!-- MAIN -->
<div class="box hidden" id="main">
  <h2>🚀 Меню</h2>

  <button onclick="openSite('https://www.youtube.com','Открываю YouTube')">YouTube</button>
  <button onclick="openSite('https://web.telegram.org','Открываю Telegram')">Telegram</button>
  <button onclick="openSite('https://chat.openai.com','Открываю ChatGPT')">ChatGPT</button>
  <button onclick="openSite('https://www.pinterest.com','Открываю Pinterest')">Pinterest</button>
</div>

<script>
function say(text) {
  const msg = new SpeechSynthesisUtterance(text);
  msg.lang = "ru-RU";
  speechSynthesis.speak(msg);
}

function startSite() {
  say("Добро пожаловать, Жасур");
  start.classList.add("hidden");
  login.classList.remove("hidden");
}

function checkPassword() {
  const pass = password.value;
  if (pass === "8522") {
    say("Пароль верный. Добро пожаловать");
    login.classList.add("hidden");
    main.classList.remove("hidden");
  } else {
    say("Неверный пароль");
  }
}

function openSite(url, text) {
  say(text);
  window.open(url, "_blank");
}
</script>

</body>
</html>
