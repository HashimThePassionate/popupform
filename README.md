# 🎨 **Popup Form with Validation and Icons** 
This project creates a **popup form** with **real-time validation**, **icons** for valid/invalid feedback, and an **orange theme**. The form includes **Title** and **Description** input fields, which are validated using **regex**. The user gets visual feedback via icons, and the form can be opened, closed, and submitted interactively.
> **Click To Look [Try Me](https://hashimthepassionate.github.io/popupform/)**

## 🚀 **Features**:
- **Popup Form**: Opens and closes with a button click, or by clicking outside the form.
- **Real-time Validation**: Inputs are validated as the user types, using **regex**.
- **Visual Feedback**: Icons (`✔` for valid, `✘` for invalid) show validation status.
- **Prevents Invalid Submission**: If the fields are not valid, the form cannot be submitted.

---

## 🖥️ **Code Structure**

### **1. HTML Code**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Popup Form</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <!-- Button to trigger the popup form -->
  <button id="openFormBtn" class="open-button">Open Form</button>

  <!-- The Popup Form -->
  <div id="popupForm" class="popup-form">
    <div class="form-container">
      <h2>Submit Your Info</h2>
      <span id="closeBtn" class="close-btn">&times;</span>
      <form id="popupFormContent">
        <label for="title">Title</label>
        <div class="input-container">
          <input type="text" id="title" name="title" placeholder="Enter title" required>
          <span class="icon" id="title-icon"></span> <!-- Icon for Title -->
        </div>
        
        <label for="description">Description</label>
        <div class="input-container">
          <textarea id="description" name="description" placeholder="Enter description" required></textarea>
          <span class="icon" id="description-icon"></span> <!-- Icon for Description -->
        </div>
        
        <button type="submit" class="submit-btn">Submit</button>
      </form>
    </div>
  </div>

  <script src="script.js"></script>
</body>
</html>
```

### 🔍 **HTML Explanation**:

#### **Trigger Button**:
- **`<button>`**: The button with `id="openFormBtn"` triggers the popup form to display. It is styled to match the overall orange theme of the form.

#### **Popup Form**:
- **`<div id="popupForm" class="popup-form">`**: This `div` contains the entire form and is initially hidden (`display: none`). It is centered and covers the entire screen when opened.
  
#### **Form Fields**:
- **`<input type="text" id="title">`**: The title field where the user enters a title. It includes a placeholder ("Enter title") and requires at least **3 alphanumeric characters** for validation.
- **`<textarea id="description">`**: The description field where the user enters a description. The validation rule requires at least **10 characters**.
- **`<span class="icon">`**: This `span` holds the **validation icons** (`✔` for valid and `✘` for invalid) for both the title and description fields.

#### **Close Button**:
- **`<span id="closeBtn" class="close-btn">`**: This `span` represents the close button (`×`) that users can click to close the form. The form can also be closed by clicking outside the form area.

#### **Submit Button**:
- **`<button type="submit" class="submit-btn">`**: The form's submit button styled with the same orange theme. It becomes clickable only when both fields pass the validation.

---

### **2. CSS Code**

```css
/* General Body Styling */
body {
  font-family: Arial, sans-serif;
  background-color: #f4f4f4;
  margin: 0;
  padding: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

/* Button to Open Popup */
.open-button {
  background-color: #FF7F50; /* Orange theme */
  color: white;
  padding: 10px 20px;
  border: none;
  cursor: pointer;
  font-size: 16px;
  border-radius: 5px;
}

/* Popup Form Background */
.popup-form {
  display: none; /* Hidden by default */
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5); /* Dim background */
  justify-content: center;
  align-items: center;
}

/* Popup Form Container */
.form-container {
  background-color: white;
  padding: 20px;
  border-radius: 10px;
  width: 400px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
  position: relative;
  box-sizing: border-box;
  overflow: hidden;
}

/* Close Button */
.close-btn {
  position: absolute;
  top: 10px;
  right: 20px;
  font-size: 24px;
  cursor: pointer;
  color: #FF7F50;
}

/* Input Container for Icons */
.input-container {
  position: relative;
}

.input-container .icon {
  position: absolute;
  right: 10px;
  top: 12px;
  font-size: 18px;
}

/* Valid and Invalid Icons */
.valid-icon {
  color: green;
}

.invalid-icon {
  color: red;
}

/* Form Elements Styling */
input[type="text"], textarea {
  width: 100%;
  padding: 10px;
  margin: 10px 0;
  border: 1px solid #ccc;
  border-radius: 5px;
  font-size: 16px;
  box-sizing: border-box; /* Prevent overflow */
  resize: none; /* Prevent textarea resize */
}

/* Focus Effect for Input Fields */
input[type="text"]:focus, textarea:focus {
  outline: 2px solid rgba(255, 127, 80, 0.5); /* Orange outline with 50% transparency */
  border-color: rgba(255, 127, 80, 0.5); /* Change border color on focus */
}

/* Submit Button */
.submit-btn {
  background-color: #FF7F50;
  color: white;
  border: none;
  padding: 10px;
  width: 100%;
  cursor: pointer;
  border-radius: 5px;
  font-size: 16px;
}

/* Submit Button Hover Effect */
.submit-btn:hover {
  background-color: #FF6347; /* Darker orange */
}
```

### 🔍 **CSS Explanation**:

#### **Styling Overview**:
- **Orange Theme**: The **orange color** (`#FF7F50`) is used consistently across the button, borders, and other elements for a modern look.
- **Centered Popup**: The form is centered using `display: flex; justify-content: center; align-items: center;` which keeps the form in the middle of the screen.

#### **Popup Background**:
- **Dimming the Background**: When the popup form is displayed, the rest of the screen gets a dim effect using **semi-transparent black** (`rgba(0, 0, 0, 0.5)`), giving the form focus.

#### **Form Styling**:
- **Input Field Styling**: The input fields and textarea have **rounded borders** with good padding and margin for space. Their width is set to **100%** to ensure they are fully expanded.

#### **Focus Effect**:
- **Focus Interaction**: When an input field is clicked, it shows an **orange outline** with 50% transparency, making the form more interactive and visually pleasing.

#### **Icons for Validation**:
- **Valid and Invalid States**: The icons for validation are styled using `.valid-icon` and `.invalid-icon`. **Green icons** show valid inputs (`✔`), and **red icons** indicate invalid inputs (`✘`).

---

### **3. JavaScript Code**

```javascript
// Get the elements
const openFormBtn = document.getElementById("openFormBtn");
const popupForm = document.getElementById("popupForm");
const closeBtn = document.getElementById("closeBtn");
const form = document.getElementById("popupFormContent");

const titleInput = document.getElementById("title");
const descriptionInput = document.getElementById("description");

const titleIcon = document.getElementById("title-icon");
const descriptionIcon = document.getElementById("description-icon");

// Open the form when the button is clicked
openFormBtn.addEventListener("click", () => {
  popupForm.style.display = "flex

"; // Show the form (flex makes it centered)
});

// Close the form when the close button is clicked
closeBtn.addEventListener("click", () => {
  popupForm.style.display = "none"; // Hide the form
});

// Close the form when clicking outside of the form container
window.addEventListener("click", (e) => {
  if (e.target === popupForm) {
    popupForm.style.display = "none"; // Hide the form
  }
});

// Validation logic
function validateInput(input, regex, icon) {
  if (regex.test(input.value)) {
    input.style.borderColor = "green";
    icon.textContent = "✔";  // Display valid icon
    icon.className = "icon valid-icon";
  } else {
    input.style.borderColor = "red";
    icon.textContent = "✘";  // Display invalid icon
    icon.className = "icon invalid-icon";
  }
}

// Title validation (at least 3 characters, alphanumeric)
titleInput.addEventListener("input", () => {
  const titleRegex = /^[a-zA-Z0-9 ]{3,}$/;  // Title must have at least 3 alphanumeric characters
  validateInput(titleInput, titleRegex, titleIcon);
});

// Description validation (at least 10 characters)
descriptionInput.addEventListener("input", () => {
  const descriptionRegex = /^.{10,}$/;  // Description must have at least 10 characters
  validateInput(descriptionInput, descriptionRegex, descriptionIcon);
});

// Prevent form submission if invalid
form.addEventListener("submit", (e) => {
  if (titleInput.value.length < 3 || descriptionInput.value.length < 10) {
    e.preventDefault(); // Prevent form submission if inputs are invalid
    alert("Please fill out the form correctly.");
  }
});
```

### 🔍 **JavaScript Explanation**:

#### **Open/Close Form**:
- **Open the Form**: When the `Open Form` button is clicked, the `popupForm` is shown by setting its `display` to `flex`.
- **Close the Form**: The form can be closed by either clicking the close button (`×`) or clicking outside the form's content area.

#### **Input Validation**:
- **Regex-Based Validation**:
  - **Title Validation**: The title must be at least **3 characters long** and **alphanumeric**. This is checked using the regex `/^[a-zA-Z0-9 ]{3,}$/`.
  - **Description Validation**: The description must be at least **10 characters long**. The regex `/^.{10,}$/` is used to ensure this.

#### **Real-Time Validation**:
- **Icons for Feedback**: As the user types, the form checks whether their input meets the regex criteria:
  - **Green Checkmark** (`✔`): Appears when the input is valid.
  - **Red Cross** (`✘`): Appears when the input is invalid.
  
#### **Preventing Invalid Submission**:
- **Blocking Submission**: If either the `Title` or `Description` fields are invalid, the form prevents submission and displays an alert.

---

## 💡 **Key Features**

1. **Modern Design**: The form uses an orange color theme with interactive elements and clear visual feedback.
2. **Real-Time Validation**: Uses **regex** to ensure that users provide valid input in both the `Title` and `Description` fields.
3. **Validation Icons**: Provides immediate visual feedback using icons (`✔` for valid, `✘` for invalid).
4. **User-Friendly Form Control**: The form can be easily opened, closed, and prevents invalid submissions.

---

## 🎉 **Conclusion**

This **popup form** provides a seamless user experience with real-time validation and visual feedback using regex and icons. It’s responsive, clean, and designed with interactivity in mind, making it a practical tool for modern web applications.
