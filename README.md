Here’s a basic implementation of the requirements for the ReactJS coding test:

### 3. **App Component Code**

```jsx
import React, { useState } from 'react';
import Calculator from './Calculator';

function App() {
  const [showCalculator, setShowCalculator] = useState(false);

  return (
    <div>
      <button onClick={() => setShowCalculator(!showCalculator)}>
        Calculator
      </button>
      {showCalculator && <Calculator />}
    </div>
  );
}

export default App;
```

### 4. **Calculator Component Code**

```jsx
import React, { useState } from 'react';

function Calculator() {
  const [num1, setNum1] = useState(0);
  const [num2, setNum2] = useState(0);
  const [result, setResult] = useState(null);

  const handleAdd = () => {
    setResult(parseFloat(num1) + parseFloat(num2));
  };

  const handleSubtract = () => {
    setResult(parseFloat(num1) - parseFloat(num2));
  };

  const handleMultiply = () => {
    setResult(parseFloat(num1) * parseFloat(num2));
  };

  return (
    <div>
      <input
        type="number"
        placeholder="Enter first number"
        value={num1}
        onChange={(e) => setNum1(e.target.value)}
      />
      <input
        type="number"
        placeholder="Enter second number"
        value={num2}
        onChange={(e) => setNum2(e.target.value)}
      />

      <div>
        <button onClick={handleAdd}>Add</button>
        <button onClick={handleSubtract}>Subtract</button>
        <button onClick={handleMultiply}>Multiply</button>
      </div>

      {result !== null && <h3>Result: {result}</h3>}
    </div>
  );
}

export default Calculator;
```

### Explanation:

1. **App Component**:
   - Contains a button labeled "Calculator".
   - When the button is clicked, it toggles the visibility of the `Calculator` component.
   
2. **Calculator Component**:
   - Accepts two numbers through input boxes.
   - Has buttons to perform addition, subtraction, and multiplication.
   - Displays the result below the buttons when any operation is clicked.

Let me know if you'd like any further modifications or explanations!



For this specific project, adding **CSS** or **Bootstrap** is optional, depending on how you want to style the components. If you're going for a simple layout, here are a few suggestions:

### **Option 1: Basic CSS (Optional)**

You can create a basic CSS file (`App.css` or `Calculator.css`) to style your components. This can include styling for buttons, inputs, and the overall layout. Here's an example:

#### **App.css**:

```css
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 20px;
}

button {
  margin: 10px;
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
}

input {
  margin: 5px;
  padding: 5px;
  width: 150px;
  font-size: 16px;
}

h3 {
  margin-top: 20px;
}
```

You can then import this CSS file in `App.js` or `Calculator.js` as:

```javascript
import './App.css';
```

### **Option 2: Bootstrap (Optional)**

If you prefer using **Bootstrap** for styling, you can add it easily:

1. Install Bootstrap in your project:
   ```bash
   npm install bootstrap
   ```

2. Import Bootstrap into your `index.js` or `App.js`:
   ```javascript
   import 'bootstrap/dist/css/bootstrap.min.css';
   ```

3. Modify the existing JSX code to use Bootstrap classes. For example:

#### **App.js with Bootstrap Classes**:

```jsx
import React, { useState } from 'react';
import Calculator from './Calculator';

function App() {
  const [showCalculator, setShowCalculator] = useState(false);

  return (
    <div className="container mt-3 text-center">
      <button className="btn btn-primary" onClick={() => setShowCalculator(!showCalculator)}>
        Calculator
      </button>
      {showCalculator && <Calculator />}
    </div>
  );
}

export default App;
```

#### **Calculator.js with Bootstrap Classes**:

```jsx
import React, { useState } from 'react';

function Calculator() {
  const [num1, setNum1] = useState(0);
  const [num2, setNum2] = useState(0);
  const [result, setResult] = useState(null);

  const handleAdd = () => {
    setResult(parseFloat(num1) + parseFloat(num2));
  };

  const handleSubtract = () => {
    setResult(parseFloat(num1) - parseFloat(num2));
  };

  const handleMultiply = () => {
    setResult(parseFloat(num1) * parseFloat(num2));
  };

  return (
    <div className="mt-4">
      <input
        type="number"
        className="form-control mb-2"
        placeholder="Enter first number"
        value={num1}
        onChange={(e) => setNum1(e.target.value)}
      />
      <input
        type="number"
        className="form-control mb-2"
        placeholder="Enter second number"
        value={num2}
        onChange={(e) => setNum2(e.target.value)}
      />

      <div>
        <button className="btn btn-success me-2" onClick={handleAdd}>Add</button>
        <button className="btn btn-warning me-2" onClick={handleSubtract}>Subtract</button>
        <button className="btn btn-danger" onClick={handleMultiply}>Multiply</button>
      </div>

      {result !== null && <h3 className="mt-3">Result: {result}</h3>}
    </div>
  );
}

export default Calculator;
```

### Key Points:
- **CSS** gives you more customization control, but you need to style everything manually.
- **Bootstrap** provides a quick way to add pre-built, responsive styles (buttons, inputs, margins, etc.).

Either approach works well, depending on your design preference. For a more modern and faster approach, you might prefer **Bootstrap**.
