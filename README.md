# Awesome Kartikey Light and Dark Mode

A simple demonstration project showcasing how to implement a light and dark theme switcher for a website using HTML, CSS (with custom properties), and JavaScript. The user's theme preference is saved using `localStorage`.

## Features

- **Theme Switching:** Easily toggle between light and dark modes using a dedicated switch.
- **Persistence:** Remembers the user's selected theme across browser sessions using `localStorage`.
- **Dynamic Content Updates:** Updates CSS variables, text, icons (Font Awesome), and images dynamically based on the selected theme.
- **Clean Structure:** Follows standard web development practices with separate HTML, CSS, and JavaScript files.
- **CSS Custom Properties:** Leverages CSS variables for efficient and maintainable theme management.
- **Smooth Scrolling:** Implements smooth scrolling for anchor links.

## Tech Stack

- **HTML5:** For the basic structure and content of the webpage.
- **CSS3:** For styling, layout, and theme definitions using custom properties.
  - Font Imports (Google Fonts: Comfortaa, Kaushan Script, Oswald)
  - Font Awesome (for icons)
- **JavaScript (Vanilla):** For handling theme switching logic, DOM manipulation, and interacting with `localStorage`.

## Setup Instructions

1.  **Clone the repository:**

    ```bash
    git clone https://github.com/awesome-kartikey/light-and-dark-mode.git
    ```

2.  **Navigate to the project directory:**

    ```bash
    cd light-and-dark-mode
    ```

3.  **Open the `index.html` file:**
    Simply open the `index.html` file in your web browser. No complex build steps or server is required.

    - On macOS: `open index.html`
    - On Windows: `start index.html`
    - On Linux: `xdg-open index.html`

    Or, right-click the file in your file explorer and choose "Open with" your preferred browser.

## Usage

1.  Open the `index.html` file in your browser.
2.  Locate the theme switch toggle, usually in the top-right corner.
3.  Click the toggle switch to change between "Light Mode" and "Dark Mode".
4.  Observe how the page elements (background, text, navigation, buttons, images, icons) adapt to the selected theme.
5.  Close and reopen the page; the previously selected theme should be automatically applied.
