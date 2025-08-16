# Frequently Asked Questions (FAQ)

Here are answers to some common questions about the Awesome Kartikey Light and Dark Mode project.

**Q1: How does the theme switching actually work?**

**A:** The theme switching mechanism combines CSS custom properties (variables) and JavaScript:
1.  **CSS:** The `style.css` file defines two sets of color variables. One set is defined within the `:root` selector (defaulting to the light theme), and another set is defined within the `[data-theme="dark"]` attribute selector for the dark theme. Styles throughout the CSS use these variables (e.g., `background-color: var(--background);`).
2.  **HTML:** The `index.html` file includes a checkbox input acting as the theme toggle switch.
3.  **JavaScript:** The `script.js` file listens for the `change` event on the checkbox.
    *   When toggled, JavaScript checks if the checkbox is checked (for dark mode) or unchecked (for light mode).
    *   It then sets the `data-theme` attribute on the root `<html>` element (`document.documentElement`) to either `'dark'` or `'light'`.
    *   This attribute change causes the browser to apply the corresponding set of CSS variables defined in the stylesheet.
    *   JavaScript also updates specific element styles directly (like `nav` and `textBox` backgrounds for semi-transparent effects), changes the toggle icon (sun/moon) and text, and updates image sources to match the theme.

**Q2: How is my theme preference saved? Why does it stay the same when I reopen the page?**

**A:** Your theme preference ('light' or 'dark') is saved in your browser's **`localStorage`**.
*   When you toggle the theme switch, the JavaScript writes the selected theme (`'light'` or `'dark'`) to `localStorage` under the key `'theme'`.
*   When the page first loads, the script checks if a value exists for the `'theme'` key in `localStorage`.
*   If a theme preference is found, the script applies that theme immediately (sets the toggle state, applies the `data-theme` attribute, updates elements) so you see your last chosen theme.
*   `localStorage` persists even after you close the browser window or tab, making the choice "sticky".

**Q3: What technologies were used to build this?**

**A:** This project uses fundamental front-end web technologies:
*   **HTML5:** For the structure and content.
*   **CSS3:** For styling, layout, and defining the light/dark themes using custom properties.
*   **Vanilla JavaScript:** For the theme switching logic, updating the DOM, and interacting with `localStorage`.
*   **Font Awesome:** Used for the sun and moon icons in the theme switcher.

**Q4: Can I customize the colors used in the themes?**

**A:** Yes! Customization is easy thanks to CSS custom properties.
1.  Open the `style.css` file.
2.  Locate the `:root { ... }` block for the light theme colors and the `[data-theme="dark"] { ... }` block for the dark theme colors.
3.  Modify the color values associated with variables like `--primary-color`, `--background`, `--on-background`, etc., to your desired colors.
4.  Save the file and refresh the page to see your changes.

**Q5: Why are there different images for light and dark modes (e.g., `undraw_proud_coder_light.svg` and `undraw_proud_coder_dark.svg`)?**

**A:** Using separate image assets tailored for light and dark backgrounds enhances the visual consistency and user experience of each theme. Illustrations designed for a light background might look out of place or have poor contrast on a dark background, and vice-versa. The JavaScript dynamically switches the `src` attribute of the image elements to load the appropriate version (`_light.svg` or `_dark.svg`) when the theme changes.

**Q6: How can I apply the theme switching to new elements I add to the page?**

**A:**
1.  **CSS:** Style your new elements using the existing CSS custom properties (e.g., `color: var(--on-background); background-color: var(--background);`). Ensure the styles properly adapt when the variables change.
2.  **JavaScript (If needed):** If the element requires specific, theme-dependent changes not handled purely by CSS variables (like changing an image source or a complex background style), you'll need to modify `script.js`:
    *   Get a reference to your new element(s).
    *   Update the `applyTheme` function to include logic that modifies your new element(s) based on the `isDarkMode` flag.