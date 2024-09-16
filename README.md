document.getElementById("signupForm").onsubmit = function(event) {
    // Prevent the default form submission
    event.preventDefault();

    // Get the input values
    const username = document.getElementById("username").value;
    const password = document.getElementById("password").value;
    const errorMsg = document.getElementById("errorMsg");

    // Clear any previous error message
    errorMsg.textContent = "";

    // Check if both fields are filled
    if (!username) {
        errorMsg.textContent = "Please enter a username.";
        return; // Stop the form from submitting
    } else if (!password) {
        errorMsg.textContent = "Please enter a password.";
        return; // Stop the form from submitting
    }

    // Store the username and password in localStorage (for demo purposes, not secure)
    try {
        localStorage.setItem("username", username);
        localStorage.setItem("password", password);
        localStorage.setItem("loggedIn", "true");

        // Redirect to home page after successful signup
        alert("Signup successful! Redirecting to home page...");
        window.location.href = "home.html"; // Redirect to home page
    } catch (e) {
        console.error("Error saving data to localStorage:", e);
        errorMsg.textContent = "Error signing up. Please try again.";
    }
};
