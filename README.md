# Decimal-to-Binary-Converter

You can run the converter in the link below:
https://fadliazharr.github.io/Decimal-to-Binary-Converter/
---

# Decimal to Binary Converter  

## Overview  

This project is a **Decimal to Binary Converter** built using **HTML, CSS, and JavaScript**. It allows users to enter a decimal number and instantly see its binary equivalent. Additionally, when the user enters `5`, a **call stack animation** visually explains how recursion is used in the conversion process.  

## Features  

- **Decimal to Binary Conversion:** Converts any non-negative integer to binary.  
- **Recursive Approach:** Uses recursion to compute binary values.  
- **Call Stack Animation:** When the input is `5`, an animation demonstrates how the function processes recursion step by step.  
- **User-Friendly Interface:** Styled with CSS for a clean and intuitive look.  

## How It Works  

1. **User Input:**  
   - The user enters a **decimal number** into the input field.  
   - Clicking the **"Convert" button** triggers the conversion process.  
   - Pressing **Enter** also triggers conversion.  

2. **Conversion Process:**  
   - The script uses a **recursive function** to calculate the binary representation.  
   - If the user enters `5`, a **step-by-step animation** shows how recursion breaks down the number.  
   - The final binary value is displayed inside the result box.  

3. **Validation Checks:**  
   - Ensures the input is a valid **non-negative integer**.  
   - Shows an **alert** if the input is invalid (negative numbers, empty input, or non-numeric values).  

## Code Explanation  

### `decimalToBinary(input)`  

This is a **recursive function** that converts a decimal number to binary:  

```js
const decimalToBinary = (input) => {
  if (input === 0 || input === 1) {
    return String(input); // Base case
  } else {
    return decimalToBinary(Math.floor(input / 2)) + (input % 2);
  }
};
```
- If `input` is **0 or 1**, it returns the number as a string (base case).  
- Otherwise, it **divides the number by 2**, recursively calls itself, and **appends the remainder**.  

### `showAnimation()`  

- If the user enters `5`, this function creates an **animated visual representation** of the call stack:  
  - It displays each function call as a separate **frame**.  
  - After a short delay, it **modifies the frame** to show what’s happening at that step.  
  - Finally, it removes the frame once that step **pops off the stack**.  

### Event Listeners  

- **Button Click:** Triggers conversion when the user clicks "Convert".  
- **Enter Key Press:** Allows conversion by pressing Enter.  

```js
convertBtn.addEventListener("click", checkUserInput);
numberInput.addEventListener("keydown", (e) => {
  if (e.key === "Enter") {
    checkUserInput();
  }
});
```


## Expected Output  

| Input  | Binary Output |
|--------|--------------|
| 2      | `10`         |
| 5      | `101` + Animation |
| 10     | `1010`       |
| 25     | `11001`      |

If the input is `5`, an **animation** will also appear, visually explaining how recursion works.  

## Technologies Used  

- **HTML** – Structure of the webpage.  
- **CSS** – Styling and layout.  
- **JavaScript** – Handles conversion logic and animations.  

