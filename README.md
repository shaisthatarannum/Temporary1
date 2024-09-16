<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Signup</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
        }
        form {
            display: inline-block;
            text-align: left;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 10px;
            background-color: #f9f9f9;
            width: 300px;
        }
        label {
            display: block;
            margin: 10px 0 5px;
        }
        input[type="text"], input[type="password"] {
            width: 100%;
            padding: 8px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        input[type="submit"] {
            width: 100%;
            padding: 10px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        input[type="submit"]:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <h1>Signup Page</h1>
    <form id="signupForm">
        <label for="username">Username:</label>
        <input type="text" id="username" required>

        <label for="password">Password:</label>
        <input type="password" id="password" required>

        <input type="submit" value="Sign Up">
    </form>

    <script>
        document.getElementById("signupForm").onsubmit = function(event) {
            event.preventDefault();

            const username = document.getElementById("username").value;
            const password = document.getElementById("password").value;

            if (username && password) {
                // Save user credentials in local storage (for demo purposes, not secure)
                localStorage.setItem("username", username);
                localStorage.setItem("password", password);
                localStorage.setItem("loggedIn", "true");

                // Redirect to home page
                window.location.href = "home.html";
            } else {
                alert("Please fill in all fields");
            }
        };
    </script>
</body>
</html>
