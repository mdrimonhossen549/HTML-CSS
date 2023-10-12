<!DOCTYPE html>
<html>
<head>
    <title>Login/Logout Form</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
        }

        .form-container {
            background: #fff;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.3);
            padding: 20px;
            max-width: 350px;
            width: 100%;
        }

        .form-container h2 {
            text-align: center;
        }

        .form-group {
            margin: 15px 0;
        }

        .form-group label {
            display: block;
            font-weight: 600;
        }

        .form-group input[type="text"],
        .form-group input[type="password"] {
            width: 100%;
            padding: 10px;
            margin-top: 5px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        .form-group button {
            width: 100%;
            background: #007BFF;
            border: none;
            color: #fff;
            padding: 10px;
            border-radius: 4px;
            cursor: pointer;
        }

        .logout-button {
            background: #dc3545;
        }

        .message {
            text-align: center;
            margin-top: 15px;
        }
    </style>
</head>
<body>
    <div class="form-container">
        <h2>Login Form</h2>
        <div id="login-form">
            <div class="form-group">
                <label for="username">Username:</label>
                <input type="text" id="username" required>
            </div>
            <div class="form-group">
                <label for="password">Password:</label>
                <input type="password" id="password" required>
            </div>
            <button id="login-button">Login</button>
        </div>
        <div id="logout-form" style="display: none;">
            <p class="message" id="welcome-message"></p>
            <button id="logout-button" class="logout-button">Logout</button>
        </div>
    </div>

    <script>
        const loginForm = document.getElementById("login-form");
        const logoutForm = document.getElementById("logout-form");
        const usernameInput = document.getElementById("username");
        const passwordInput = document.getElementById("password");
        const loginButton = document.getElementById("login-button");
        const logoutButton = document.getElementById("logout-button");
        const welcomeMessage = document.getElementById("welcome-message");

        loginButton.addEventListener("click", () => {
            const username = usernameInput.value;
            if (username) {
                loginForm.style.display = "none";
                logoutForm.style.display = "block";
                welcomeMessage.textContent = `Welcome, ${username}!`;
            }
        });

        logoutButton.addEventListener("click", () => {
            loginForm.style.display = "block";
            logoutForm.style.display = "none";
            usernameInput.value = "";
            passwordInput.value = "";
        });
    </script>
</body>
</html>
