<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Home</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }
        nav {
            background-color: #333;
            overflow: hidden;
        }
        nav a {
            float: left;
            display: block;
            color: white;
            text-align: center;
            padding: 14px 16px;
            text-decoration: none;
        }
        nav a:hover {
            background-color: #ddd;
            color: black;
        }
        .container {
            margin-top: 50px;
        }
    </style>
</head>
<body>
    <nav>
        <a href="home.html">Home</a>
        <span id="authOption"></span>
    </nav>

    <div class="container">
        <h1>This is the Home Page</h1>
    </div>

    <script>
        // Check if user is logged in
        window.onload = function() {
            const authOption = document.getElementById("authOption");
            const isLoggedIn = localStorage.getItem("loggedIn");

            if (isLoggedIn === "true") {
                authOption.innerHTML = '<a href="logout.html">Logout</a>';
            } else {
                authOption.innerHTML = '<a href="login.html">Login</a> | <a href="signup.html">Signup</a>';
            }
        };
    </script>
</body>
</html>
