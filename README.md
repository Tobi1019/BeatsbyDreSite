# Beats by Dre Website

This project is a responsive Beats by Dre website built using HTML, CSS, and JavaScript. The website includes interactive features such as a navigation menu, scroll-based animations, and dynamic content highlighting. This README provides an overview of the functionalities and the structure of the code.

## Table of Contents

- [Features](#features)
  - [Navigation Menu Interaction](#navigation-menu-interaction)
  - [Removing Menu on Link Click](#removing-menu-on-link-click)
  - [Changing Header Background on Scroll](#changing-header-background-on-scroll)
  - [Displaying Scroll-to-Top Button](#displaying-scroll-to-top-button)
  - [Highlighting Active Section Links](#highlighting-active-section-links)
  - [Scroll Reveal Animations](#scroll-reveal-animations)
- [Usage](#usage)
- [Installation](#installation)
- [Code Structure](#code-structure)
- [Contributing](#contributing)
- [License](#license)

## Features

### Navigation Menu Interaction

- **navMenu**: The navigation menu element.
- **navToggle**: The button that toggles the visibility of the navigation menu.
- **navClose**: The button that closes the navigation menu.

```js
const navMenu = document.getElementById('nav-menu');
const navToggle = document.getElementById('nav-toggle');
const navClose = document.getElementById('nav-close');

if (navToggle) {
  navToggle.addEventListener('click', () => {
    navMenu.classList.add('show-menu');
  });
}

if (navClose) {
  navClose.addEventListener('click', () => {
    navMenu.classList.remove('show-menu');
  });
}
```

### Removing Menu on Link Click

- **navLink**: All navigation link elements.
- **linkAction**: Function to hide the navigation menu when a link is clicked.

```js
const navLink = document.querySelectorAll('.nav__link');

function linkAction() {
  navMenu.classList.remove('show-menu');
}

navLink.forEach(n => n.addEventListener('click', linkAction));
```

### Changing Header Background on Scroll

- **scrollHeader**: Function to change the header background when scrolling.

```js
function scrollHeader() {
  const header = document.getElementById('header');
  if (this.scrollY >= 50) header.classList.add('scroll-header'); 
  else header.classList.remove('scroll-header');
}

window.addEventListener('scroll', scrollHeader);
```

### Displaying Scroll-to-Top Button

- **scrollUp**: Function to display the scroll-to-top button based on scroll position.

```js
function scrollUp() {
  const scrollUp = document.getElementById('scroll-up');
  if (this.scrollY >= 200) scrollUp.classList.add('show-scroll'); 
  else scrollUp.classList.remove('show-scroll');
}

window.addEventListener('scroll', scrollUp);
```

### Highlighting Active Section Links

- **sections**: All sections with an ID attribute.
- **scrollActive**: Function to highlight the active section link.

```js
const sections = document.querySelectorAll('section[id]');

function scrollActive() {
  const scrollY = window.pageYOffset;

  sections.forEach(current => {
    const sectionHeight = current.offsetHeight;
    const sectionTop = current.offsetTop - 50;
    const sectionId = current.getAttribute('id');
    const navMenuLink = document.querySelector(`.nav__menu a[href*=${sectionId}]`);

    if (scrollY > sectionTop && scrollY <= sectionTop + sectionHeight) {
      navMenuLink.classList.add('active-link');
    } else {
      navMenuLink.classList.remove('active-link');
    }
  });
}

window.addEventListener('scroll', scrollActive);
```

### Scroll Reveal Animations

- **ScrollReveal**: Initialization and configuration for scroll animations.

```js
const sr = ScrollReveal({
  origin: 'top',
  distance: '30px',
  duration: 2000,
  reset: true
});

sr.reveal(`.home__data, .home__img, 
           .about__data, .about__img, 
           .services__content, .menu__content, 
           .app__data, .app__img, 
           .contact__data, .contact__button`, {
  interval: 200
});
```

## Usage

1. Clone the repository.
2. Open `index.html` in your web browser to view the website.
3. Interact with the navigation menu, scroll through the page to see the dynamic changes.

## Installation

No special installation steps are required. Ensure you have a modern web browser to view the HTML, CSS, and JavaScript content.

## Code Structure

- **index.html**: The main HTML file containing the structure of the webpage.
- **style.css**: The CSS file for styling the webpage.
- **script.js**: The JavaScript file for interactive features and animations.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request with your changes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.# BeatsbyDreSite
