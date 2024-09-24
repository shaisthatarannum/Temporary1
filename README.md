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
