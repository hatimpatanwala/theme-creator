<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Theme Creator - README</title>
  <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
  <style>
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      margin: 2rem;
      line-height: 1.6;
      background: #f9f9f9;
      color: #333;
    }
    h1, h2, h3 {
      color: #2c3e50;
    }
    h1 { font-size: 2.5rem; }
    h2 { font-size: 2rem; margin-top: 2rem; }
    h3 { font-size: 1.5rem; margin-top: 1.5rem; }
    code {
      background: #eee;
      padding: 2px 6px;
      border-radius: 4px;
      font-family: monospace;
    }
    pre {
      background: #2d2d2d;
      color: #f8f8f2;
      padding: 1rem;
      border-radius: 5px;
      overflow-x: auto;
    }
    ul {
      margin: 1rem 0;
      padding-left: 1.5rem;
    }
    li {
      margin-bottom: 0.5rem;
    }
    a {
      color: #3498db;
    }
    .icon {
      margin-right: 0.5rem;
      color: #3498db;
    }
  </style>
</head>
<body>

<h1><i class="fas fa-paint-brush icon"></i>Theme Creator</h1>
<p>This project provides a flexible theming system using SCSS. It can be integrated into any project, whether you're using React, Angular, Vue, or no framework at all.</p>

<h2><i class="fas fa-star icon"></i>Features</h2>
<ul>
  <li><strong>Responsive Design:</strong> Easily create responsive layouts with configurable breakpoints.</li>
  <li><strong>Utility Classes:</strong> Use a wide range of utility classes for common CSS properties.</li>
  <li><strong>Customizable Themes:</strong> Adjust SCSS variables to create custom themes.</li>
  <li><strong>Dynamic Theme Switching:</strong> Switch themes dynamically using CSS classes.</li>
</ul>

<h2><i class="fas fa-download icon"></i>Installation</h2>
<h3>1. Clone the Repository</h3>
<pre><code>git clone https://github.com/yourusername/theme-creator.git
cd theme-creator</code></pre>

<h3>2. Install Dependencies</h3>
<pre><code>npm install</code></pre>

<h2><i class="fas fa-play icon"></i>Usage</h2>

<h3>Without a Framework</h3>
<pre><code>npx sass src/styles/main.scss dist/styles.css</code></pre>

<pre><code>&lt;link rel="stylesheet" href="dist/styles.css"&gt;</code></pre>

<pre><code>&lt;button onclick="document.body.classList.toggle('dark-theme')"&gt;Toggle Theme&lt;/button&gt;</code></pre>

<h3>React</h3>
<pre><code>npx sass src/styles/main.scss src/styles.css</code></pre>

<pre><code>import './styles.css';</code></pre>

<pre><code>import React, { useState } from 'react';
import './styles.css';

function App() {
  const [theme, setTheme] = useState('default-theme');

  const toggleTheme = () => {
    setTheme(theme === 'default-theme' ? 'dark-theme' : 'default-theme');
  };

  return (
    &lt;div className={theme}&gt;
      &lt;button onClick={toggleTheme}&gt;Toggle Theme&lt;/button&gt;
    &lt;/div&gt;
  );
}

export default App;</code></pre>

<h3>Angular</h3>
<pre><code>npx sass src/styles/main.scss src/styles.css</code></pre>

<pre><code>"styles": [
  "src/styles.css"
]</code></pre>

<pre><code>import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  template: `
    &lt;div [ngClass]="theme"&gt;
      &lt;button (click)="toggleTheme()"&gt;Toggle Theme&lt;/button&gt;
    &lt;/div&gt;
  `,
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  theme = 'default-theme';

  toggleTheme() {
    this.theme = this.theme === 'default-theme' ? 'dark-theme' : 'default-theme';
  }
}</code></pre>

<h3>Vue</h3>
<pre><code>npx sass src/styles/main.scss src/styles.css</code></pre>

<pre><code>import './styles.css';</code></pre>

<pre><code>&lt;template&gt;
  &lt;div :class="theme"&gt;
    &lt;button @click="toggleTheme"&gt;Toggle Theme&lt;/button&gt;
  &lt;/div&gt;
&lt;/template&gt;

&lt;script&gt;
export default {
  data() {
    return {
      theme: 'default-theme'
    };
  },
  methods: {
    toggleTheme() {
      this.theme = this.theme === 'default-theme' ? 'dark-theme' : 'default-theme';
    }
  }
};
&lt;/script&gt;

&lt;style src="./styles.css"&gt;&lt;/style&gt;</code></pre>

<h2><i class="fas fa-magic icon"></i>Creating a New Theme</h2>
<h3>1. Create a New Theme File</h3>
<pre><code>$new-theme: (
  primary-color: #ff6347,
  secondary-color: #4682b4,
  font-family: 'Courier New, monospace',
  base-font-size: 16px,
  base-line-height: 1.5,
  spacing-unit: 8px
);

.new-theme {
@include theme-variables($new-theme);

.text-primary {
color: map-get($new-theme, primary-color);
}

.bg-primary {
background-color: map-get($new-theme, primary-color);
}
}</code></pre>

<h3>2. Import the New Theme</h3>
<pre><code>@import 'theme-mixin';
@import 'themes/default-theme';
@import 'themes/dark-theme';
@import 'themes/new-theme';</code></pre>

<h3>3. Rebuild the Project</h3>
<pre><code>npx sass src/styles/main.scss src/styles.css</code></pre>

<h3>4. Use the New Theme</h3>
<pre><code>&lt;div class="new-theme"&gt;
  &lt;p class="text-primary"&gt;This text uses the primary color of the new theme.&lt;/p&gt;
&lt;/div&gt;</code></pre>

<h2><i class="fas fa-balance-scale icon"></i>License</h2>
<p>This project is licensed under the MIT License.</p>

</body>
</html>
