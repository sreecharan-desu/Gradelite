# Gradelite Documentation

Generated on: 2025-04-02 16:51:54

## Overview

This documentation covers 3 files from the Gradelite codebase.

## Table of Contents

### Root

- [index.html](#index-html)
- [script.js](#script-js)
- [style.css](#style-css)

## File Documentation

### Root

<a id='index-html'></a>

#### index.html

*Path: index.html*

1. **Purpose:** This HTML file defines the structure and content of the GradeLite web page, providing a user interface for GPA calculation based on selected criteria. It serves as the entry point for the application.

2. **Key Functionality:**

- **Structure:** Uses standard HTML elements (`<table>`, `<form>`, `<select>`, `<input>`, etc.) to create the page layout, including a navigation bar, criteria selection form, subject grade input table, and a footer.
- **Form Handling:** The `<form>` element collects user input (branch, year, semester) via `<select>` dropdowns.  The `onclick="validate()"` event on the submit button triggers the `validate()` function in `script.js`.
- **Dynamic Content:**  Placeholders like `<p id="Subject1"></p>` and dynamically generated table rows are used to display subject names based on user selections. The `id` attributes are used by `script.js` to populate these elements.
- **GPA Calculation Trigger:** The "Calculate" button with `onclick="calc_gpa()"` triggers the GPA calculation function in `script.js`.
- **Result Display:** The `<p id="result"></p>` and `<p id="mobile-result"></p>` elements are used to display the calculated GPA, targeting different screen sizes.
- **External Resources:** Links to external CSS (Bootstrap, Font Awesome) and JavaScript (Bootstrap, Confetti library) are included for styling and dynamic effects.

3. **Dependencies and Relationships:**

- **Imports & Usage:** Depends on `bootstrap.css`, `style.css`, `script.js`, `wish.js`, Bootstrap (JS and CSS), Font Awesome, and a confetti library.
- **Code Relationships:** This file is the main HTML file and is rendered by the browser.  It interacts directly with `script.js` for dynamic content updates and GPA calculation.  `style.css` provides the styling, and `wish.js` likely adds birthday-related functionality (not included in the provided code).

4. **Usage Example:** The user interacts with the form elements, selects their branch, year, and semester, and then clicks "Submit."  `script.js` then populates the subject table. The user enters their grades, clicks "Calculate," and the GPA is displayed in the designated area.

5. **Technical Notes:**

- The use of external libraries (Bootstrap, Font Awesome) simplifies styling and adds responsiveness.
- The structure is relatively simple but could benefit from more semantic HTML5 elements (e.g., `<nav>`, `<main>`, `<aside>`) for improved accessibility and maintainability.
- Inline event handlers (`onclick`) are used, which can be less maintainable than event listeners in JavaScript.

---

<a id='script-js'></a>

#### script.js

*Path: script.js*

1. **Purpose:** This JavaScript file provides the dynamic functionality for the GradeLite web page. It handles user input validation, dynamically updates the subject list based on selected criteria, calculates the GPA, and triggers confetti effects.

2. **Key Functionality:**

- **`validate()`:**
    - Parameters: None
    - Return Type: None
    - Implementation:  Reads values from the branch, year, and semester selection dropdowns.  Updates the `<h2>` element with the selected criteria and displays the subject table.  Hides specific table rows based on the chosen branch, year, and semester. Sets subject names and associated credit values.
- **`calc_gpa()`:**
    - Parameters: None
    - Return Type: None
    - Implementation: Reads grade values from subject dropdowns. Calculates the GPA based on selected grades and predefined credit values. Displays the calculated GPA in the "result" and "mobile-result" elements. Calls `generateEffect()` if the GPA is 9 or higher.
- **`generateEffect()`:**
    - Parameters: None
    - Return Type: None
    - Implementation: Uses the `canvas-confetti` library to create a confetti effect.  Uses `requestAnimationFrame` for smooth animation.

3. **Dependencies and Relationships:**

- **Imports & Usage:** Depends on `index.html` and the `canvas-confetti` library.
- **Code Relationships:** Directly manipulates elements within `index.html` to update content and display results.  Responds to user interactions defined in `index.html` (e.g., `onclick` events).

4. **Usage Example:** Called when the user clicks "Submit" (calls `validate()`) and "Calculate" (calls `calc_gpa()`).

5. **Technical Notes:**

- The code uses global variables extensively, which can lead to maintainability issues. Encapsulating logic within objects or modules would improve code organization.
- The subject and credit information is hardcoded within the `validate()` function, making it difficult to update or extend.  A more data-driven approach (e.g., using JSON or an external data source) would be more flexible.
- Error handling is minimal.  The code assumes valid input and doesn't handle potential errors (e.g., non-numeric input in grade selections).

---

<a id='style-css'></a>

#### style.css

*Path: style.css*

1. **Purpose:** This CSS file provides the styling for the GradeLite web page. It defines the visual appearance of elements, including layout, colors, fonts, and responsiveness.

2. **Key Functionality:**

- **Styling:** Uses CSS selectors to style various elements (body, navbar, form elements, tables, result display, footer).
- **Layout:**  Uses basic layout techniques (margins, padding, display properties) to arrange elements on the page.
- **Responsiveness:** Includes a media query for `max-width: 900px` to adapt the layout and styling for smaller screens.
- **External Fonts:** Imports the 'Cabin Condensed' font from Google Fonts.

3. **Dependencies and Relationships:**

- **Imports & Usage:** Imported by `index.html`.
- **Code Relationships:**  Provides the visual styles for the HTML structure defined in `index.html`.

4. **Usage Example:**  Styles all elements within `index.html` according to the defined rules.

5. **Technical Notes:**

- The CSS is generally well-organized but could benefit from a more structured approach (e.g., using a CSS preprocessor or methodology like BEM) for larger projects.
- The media query handles basic responsiveness, but more breakpoints might be needed for a truly responsive design across various devices.
- Some styles are repeated within the media query, which could be optimized.


The files work together to create a functional web page: `index.html` provides the structure, `script.js` adds dynamic behavior, and `style.css` handles the visual presentation.  The key interaction points are the `onclick` events in `index.html` that trigger functions in `script.js`.  The JavaScript code then manipulates the DOM of `index.html` to update content and display results, all while being styled by `style.css`.  The dependencies are clearly defined through the `<link>` and `<script>` tags in `index.html`.

---

