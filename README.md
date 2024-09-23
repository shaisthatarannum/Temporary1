// src/components/Login.js
import React, { useState, useEffect } from 'react';
import { useNavigate } from 'react-router-dom';
import './Login.css';

const Login = () => {
  const [username, setUsername] = useState('');
  const [phoneNumber, setPhoneNumber] = useState('');
  const [numPersons, setNumPersons] = useState('');
  const [isButtonEnabled, setIsButtonEnabled] = useState(false);
  const [error, setError] = useState('');

  const navigate = useNavigate();

  useEffect(() => {
    // Enable button only if all fields are filled
    setIsButtonEnabled(username && phoneNumber && numPersons);
  }, [username, phoneNumber, numPersons]);

  const handleSubmit = (e) => {
    e.preventDefault();
    if (validateForm()) {
      // Redirect to the payment success page
      navigate('/payment-success');
    }
  };

  const validateForm = () => {
    if (!username || !phoneNumber || !numPersons) {
      setError('Please fill in all fields.');
      return false;
    }
    if (!/^\d{10}$/.test(phoneNumber)) {
      setError('Please enter a valid 10-digit phone number.');
      return false;
    }
    if (isNaN(numPersons) || numPersons <= 0) {
      setError('Please enter a valid number of persons.');
      return false;
    }
    setError('');
    return true;
  };

  return (
    <div className="login-container">
      <h2>Restaurant Login</h2>
      <form onSubmit={handleSubmit}>
        <div className="form-group">
          <label>Username:</label>
          <input
            type="text"
            value={username}
            onChange={(e) => setUsername(e.target.value)}
            placeholder="Enter your username"
          />
        </div>
        <div className="form-group">
          <label>Phone Number:</label>
          <input
            type="text"
            value={phoneNumber}
            onChange={(e) => setPhoneNumber(e.target.value)}
            placeholder="Enter your phone number"
          />
        </div>
        <div className="form-group">
          <label>Number of Persons:</label>
          <input
            type="number"
            value={numPersons}
            onChange={(e) => setNumPersons(e.target.value)}
            placeholder="Enter number of persons"
            min="1"
          />
        </div>
        {error && <p className="error-message">{error}</p>}
        <button type="submit" disabled={!isButtonEnabled}>
          Proceed to Payment
        </button>
      </form>
    </div>
  );
};

export default Login;
