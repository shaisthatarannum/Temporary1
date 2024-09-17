import React, { useState } from "react";

const ColorSliders = () => {
  const [red, setRed] = useState(0);
  const [green, setGreen] = useState(0);
  const [blue, setBlue] = useState(0);

  const handleRedChange = (e) => setRed(e.target.value);
  const handleGreenChange = (e) => setGreen(e.target.value);
  const handleBlueChange = (e) => setBlue(e.target.value);

  const backgroundColor = `rgb(${red}, ${green}, ${blue})`;

  return (
    <div style={{ backgroundColor, height: "100vh", padding: "20px" }}>
      <div>
        <label>Red: {red}</label>
        <input
          type="range"
          min="0"
          max="255"
          value={red}
          onChange={handleRedChange}
        />
      </div>
      <div>
        <label>Green: {green}</label>
        <input
          type="range"
          min="0"
          max="255"
          value={green}
          onChange={handleGreenChange}
        />
      </div>
      <div>
        <label>Blue: {blue}</label>
        <input
          type="range"
          min="0"
          max="255"
          value={blue}
          onChange={handleBlueChange}
        />
      </div>
    </div>
  );
};

export default ColorSliders;





import React from "react";
import ColorSliders from "./ColorSliders"; // Import the ColorSliders component

function App() {
  return (
    <div>
      <ColorSliders /> {/* Render the ColorSliders component */}
    </div>
  );
}

export default App;
