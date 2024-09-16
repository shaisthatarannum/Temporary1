gejen

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 100px;
        }
    </style>
</head>
<body>
    <h1>Login Page</h1>
    <div id="loginMessage"></div>

    <script>
        // Simulate login by storing in localStorage
        localStorage.setItem("loggedIn", "true");
        document.getElementById("loginMessage").innerHTML = "<h2>Successfully logged in</h2>";
        
        // Redirect to home after 2 seconds
        setTimeout(function() {
            window.location.href = "home.html";
        }, 2000);
    </script>
</body>
</html>






logout
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Logout</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 100px;
        }
    </style>
</head>
<body>
    <h1>Logout Page</h1>
    <div id="logoutMessage"></div>

    <script>
        // Simulate logout by removing login status from localStorage
        localStorage.setItem("loggedIn", "false");
        document.getElementById("logoutMessage").innerHTML = "<h2>Successfully logged out</h2>";

        // Redirect to home after 2 seconds
        setTimeout(function() {
            window.location.href = "home.html";
        }, 2000);
    </script>
</body>
</html>



