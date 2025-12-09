# Tech Stack & Architecture

This application is built with a "Zero-Build" philosophy. It requires no bundlers (like Webpack or Vite) and runs directly in the browser.

### Core Technologies
1.  **Vanilla JavaScript (ES6+):** Handles all logic, state management, and routing.
2.  **Markdown-it:** A fast markdown parser to convert text files into HTML.
3.  **Highlight.js:** Provides syntax highlighting for code blocks.
4.  **CSS Variables:** For dynamic theming (White/Sepia/Dark modes).

### Code Demonstration
Below is an example of how the syntax highlighting is implemented in this app. Notice how the colors change based on the selected theme:

```javascript
// Example of the highlighting logic
const md = window.markdownit({
    html: true,
    highlight: function (str, lang) {
        if (lang && window.hljs.getLanguage(lang)) {
            try {
                return window.hljs.highlight(str, { language: lang }).value;
            } catch (__) {}
        }
        return '';
    }
});
