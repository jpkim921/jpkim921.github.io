---
layout: post
title:      "Responsive Navabr"
date:       2020-01-18 21:58:40 -0500
permalink:  responsive_navabr
---


This is a quick blog about creating a responsive navigation bar that's designed with mobile first in mind. This means that we are going to create a site for smaller screens like a mobile phone where the nav bar adjusts appropriately to an increasing screen size. When on a smaller screen, the menu is hidden 'behind' the menu icon. On a larger screen the nav links are presented on the nav bar. Below is a wireframe for a visual illustration of what I put together. This is the first time that I'm using [draw.io](https://www.draw.io/), which is an online diagram building application.


![alt text](https://github.com/jpkim921/images/blob/master/responsive-navbar-wireframe-accent%20copy.png?raw=true?raw=true?raw=true "Click navigation hamburger")


The first step was to put the HTML elements of the navbar together.

``` html
<div class="container">
  <nav>
    <img id="menu-icon" onclick=toggleMenu() src="https://i.ya-webdesign.com/images/3-bar-menu-png-1.png" alt="">
    <div id="nav-links" class="hidden">
      <a href="#" class="nav-link">Home</a>
      <a href="#" class="nav-link">About</a>
      <a href="#" class="nav-link">Contact</a>
    </div>
  </nav>
  <div class="main-content">
    <div class="hero-image-placeholder">

    </div>
  </div>
</div>
```

Nothing complicated here but there are two things to note:

- the menu is initially 'hidden' (remember it's designed for a small screen first)
- the `onclick` attribute on the hamburger icon

What makes the nav bar responsive is the media query.  Media queries change the CSS allowing the design to adapt and adjust when it hits a breakpoint. My initial thought was the '@media' was going to be confusing.  However after working with it I realized it was a lot easier than I anticipated. You just write the css for the element you want to change once the breakpoint is met. In this case, the nav links are hidden until a user clicks the icon. That will toggle the display property of the `<div>` holding the nav links from `display: none` to `display: block`. When the screen size is increased to more than 600px, the icon will disappear and the nav links will appear in the nav bar.

Aside from the media query, the other important part in making this happen is javascript. Javascipt allows the `toggleMenu()` function to trigger the `onclick` event.


```javascript

const toggleMenu = () => {
  // console.log('clicked')
  const menu = document.getElementById('nav-links')
  // console.log(menu.classList[0])
  
  if (menu.classList[0] == 'hidden'){
    menu.classList.remove('hidden')
  } else {
    menu.classList += 'hidden'
  }
}

```

When a user clicks on the icon, javascript will grab `<div>` with the id of `nav-links` and check to see if it has the `'hidden'` class. If it does, `.remove('hidden')` or else add (`+='hidden'`).


This project is actually my second attempt. In the first attempt, instead of using a click event, I tried to toggle the menu by hovering over the icon. Although it worked, there was an issue that if I hid the menu and resized the screen, the menu and icon remained hidden.

There are a few changes I would like to make in the future. The first is to redo the hamburger icon. Instead of linking an image, I may just try to create the icon with HTML/CSS. I would also like to try adding a small animation to the menu and have it slide down or pop out from the icon.  This would make it more appealing and excitable for the user. 

There are many ways to do this, but hopefully this effort gives insight to those reading this.

Please take a look and play with the browser window size to see it in action - [Responsive Navbar on Codepen]( https://codepen.io/jpkim921/pen/OJPovew ).



