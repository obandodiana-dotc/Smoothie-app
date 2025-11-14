🥤 Smoothie Central | Ordering Interface with Nutritional Explorer 
Here is the complete professional README for your project, provided in a single Markdown code block as requested, with all content translated to English.

Markdown

# 🥤 Smoothie Central | Ordering Interface with Nutritional Explorer

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)

---

## 🌟 Project Description

**Smoothie Central** is an interactive and modern user interface, designed as a Single-Page Application (SPA-like), simulating the ordering experience for a futuristic smoothie shop.

The project stands out for its **Cyber-Tech Dark Mode** aesthetic (primary neon colors on a dark background) and its **bilingual functionality (Spanish/English)** supporting both static and dynamic content. The application not only allows users to select and customize products but also features an **Interactive Nutritional Explorer** to view the simulated health impact profile of each ingredient.

### Key Features

* **Multilingual Support (ES/EN):** Dynamic translation of the entire UI, including product names, cart texts, form labels, and descriptions.
* **Nutritional Explorer:** An interactive panel that displays simulated impact metrics (Energy, Immunity, Recovery, Digestion) for any clicked ingredient.
* **Advanced Customization Modal:** Allows users to add **Boosters** (with extra charge) and remove ingredients from pre-built smoothies, or create recipes from scratch (**BYO** - Build Your Own).
* **Floating Cart Widget:** A persistent widget displaying the item count and total purchase price in real-time.
* **Responsive Design:** Utilizes Tailwind CSS for optimal viewing on both mobile and desktop devices.

---

## 🐛 Implemented Fixes (Translation Enhancements)

The initial version of the code contained critical flaws in dynamic translation management, particularly in elements updated outside the page's initial render. The following fixes were implemented to ensure a complete bilingual experience:

1.  **Data Panel Translation Failure:**
    * **Problem:** When switching the language, the selected ingredient's name and the metrics (`Energy`, `Digestion`, etc.) in the explorer panel remained in the previous language.
    * **Solution:** The `updateUI()` function was modified to check if an ingredient was selected and, if so, force a re-render of the `DataPanel` with the updated translations.

2.  **Customization Modal Translation Failure:**
    * **Problem:** The names of the **Boosters** inside the modal did not update when switching languages if the modal had been previously opened.
    * **Solution:** Logic was added to `updateUI()` to **close and reopen the customization modal** if it was active, forcing the re-execution of `openCustomizationModal()` and thus the re-rendering of all option chips (fruits, boosters, and removals) with the correct language.

---

## 🛠️ Technologies Used

This project was built using standard, modern web development tools for a pure front-end approach.

| Technology | Purpose |
| :--- | :--- |
| **HTML5** | Base structure of the application. |
| **Vanilla JavaScript** | All application logic (state management, DOM manipulation, cart logic, translations). |
| **Tailwind CSS** | Utility-first CSS framework for fast styling and responsive design. |
| **Custom CSS** | Implementation of the **Cyber-Tech Dark Mode** theme (neon colors, glow effects, and *glassmorphism*). |
| **Font Awesome** | Icon library to enhance the user interface. |

---

## 🚀 Installation and Usage

Since the project is contained entirely within a single HTML file, usage is extremely simple.

1.  **Download the file:** Obtain the HTML file (e.g., `fritas.html`).
2.  **Open the file:** Simply double-click the HTML file to open it in your browser.
3.  **Nutritional Explorer:** Use the top section to click on ingredients and view their simulated profiles.
4.  **Ordering:** Click the "Add and Customize" button on any smoothie to modify its recipe before adding it to the cart.
5.  **Language Switch:** Use the **`[EN/ES]`** button in the upper right corner to toggle languages.

---

## ⚙️ Code Structure (JavaScript)

The JavaScript code follows a modular structure within the HTML `<script>` tag for organization and clarity:

1.  **Language Management (`T()`):** Functions and the `translations` object for internationalization.
2.  **Database:** Definition of data structures (`PRODUCTS`, `BOOSTERS`, etc.) with bilingual support.
3.  **Explorer Logic:** Functions for managing unique ingredients, rendering the list, and the data panel.
4.  **Cart Logic:** Utility functions for updating the cart view and formatting item names.
5.  **Modal Management:** Functions to open/close modals and handle option selection (chips).
6.  **UI Update (`updateUI()`):** The central function executed on load and every language change to re-render all dynamic parts.
7.  **Initialization:** `DOMContentLoaded` detection for initial setup.
