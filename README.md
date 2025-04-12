

Theme Creator
This project provides a flexible theming system using SCSS. It can be integrated into any project, whether you're using React, Angular, Vue, or no framework at all.
Features
Responsive Design: Easily create responsive layouts with configurable breakpoints.
Utility Classes: Use a wide range of utility classes for common CSS properties.
Customizable Themes: Adjust SCSS variables to create custom themes.
Dynamic Theme Switching: Switch themes dynamically using CSS classes.
Installation
1.
Clone the Repository: Clone the repository to your local machine.
git clone https://github.com/yourusername/theme-creator.git
cd theme-creator
2.
Install Dependencies: Run npm install to install the necessary dependencies.
Usage
Without a Framework
1.
Compile SCSS: Use a tool like Sass to compile the SCSS files into CSS.
npx sass src/styles/main.scss dist/styles.css
2.
Include CSS: Add the compiled CSS file to your HTML.
<link rel="stylesheet" href="dist/styles.css">
Apply
3.
Toggle Themes: Use JavaScript to toggle theme classes on the <body> or a main container.
<button onclick="document.body.classList.toggle('dark-theme')">Toggle Theme</button>
Apply
React
1.
Compile SCSS: Use a tool like Sass to compile the SCSS files into CSS.
npx sass src/styles/main.scss src/styles.css
2.
Import CSS: Import the compiled CSS file in your React component.
import './styles.css';
Apply
3.
Toggle Themes: Use state to manage theme classes.
import React, { useState } from 'react';
import './styles.css';

function App() {
  const [theme, setTheme] = useState('default-theme');

  const toggleTheme = () => {
    setTheme(theme === 'default-theme' ? 'dark-theme' : 'default-theme');
  };

  return (
    <div className={theme}>
      <button onClick={toggleTheme}>Toggle Theme</button>
    </div>
  );
}

export default App;
Apply
Angular
1.
Compile SCSS: Use a tool like Sass to compile the SCSS files into CSS.
npx sass src/styles/main.scss src/styles.css
2.
Include CSS: Add the compiled CSS file to your angular.json.
"styles": [
  "src/styles.css"
]
Apply
3.
Toggle Themes: Use Angular's binding to toggle theme classes.
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  template: `
    <div [ngClass]="theme">
      <button (click)="toggleTheme()">Toggle Theme</button>
    </div>
  `,
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  theme = 'default-theme';

  toggleTheme() {
    this.theme = this.theme === 'default-theme' ? 'dark-theme' : 'default-theme';
  }
}
Apply
Vue
1.
Compile SCSS: Use a tool like Sass to compile the SCSS files into CSS.
npx sass src/styles/main.scss src/styles.css
2.
Import CSS: Import the compiled CSS file in your Vue component.
import './styles.css';
Apply
3.
Toggle Themes: Use Vue's data binding to manage theme classes.
<template>
  <div :class="theme">
    <button @click="toggleTheme">Toggle Theme</button>
  </div>
</template>

<script>
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
</script>

<style src="./styles.css"></style>
Apply
Creating a New Theme
1.
Create a New Theme File: In the src/styles/themes directory, create a new SCSS file for your theme.
File: /path/to/your/project/src/styles/themes/_new-theme.scss
$new-theme: (
  primary-color: #ff6347,
  secondary-color: #4682b4,
  font-family: 'Courier New, monospace',
  base-font-size: 16px,
  base-line-height: 1.5,
  spacing-unit: 8px
);

.new-theme {
  @include theme-variables($new-theme);

  // Theme-specific utilities
  .text-primary {
    color: map-get($new-theme, primary-color);
  }

  .bg-primary {
    background-color: map-get($new-theme, primary-color);
  }
}
Apply
2.
Import the New Theme: Add the new theme to your main.scss file.
File: /path/to/your/project/src/styles/main.scss
@import 'theme-mixin';
@import 'themes/default-theme';
@import 'themes/dark-theme';
@import 'themes/new-theme'; // Import your new theme here

// ... existing code
Apply
3.
Rebuild the Project: Run npx sass src/styles/main.scss src/styles.css to compile the new theme into your CSS.
4.
Use the New Theme: Apply the new theme class in your HTML or component.
<div class="new-theme">
  <p class="text-primary">This text uses the primary color of the new theme.</p>
</div>
Apply
License
This project is licensed under the MIT License.
This README provides a comprehensive guide for using the theme creator project across different environments and explains how to create and integrate new themes. Adjust the instructions as needed to fit your specific project setup.