---
layout: post
title:      "Responsive Navabr"
date:       2020-01-19 02:58:39 +0000
permalink:  responsive_navabr
---


This is a quick blog about creating a responsive navigation bar that's designed with mobile first in mind. This means that we are going to create a site for smaller screens like a mobile phone and when the screen size increases, it adjusts appropriately. When on a smaller screen, the menu is hidden 'behind' the menu icon. Below is a wireframe for a visual illustration of what I put together. First time trying [draw.io](https://www.draw.io/), which is an online diagram building application.


![alt text](https://github.com/jpkim921/images/blob/master/responsive-navbar-wireframe-accent%20copy.png?raw=true?raw=true?raw=true "Click navigation hamburger")


First thing I did was add Bootstrap. It makes putting a website together faster and easier. But then I realized it wasn't really necessary.

Then what I did was put the HTML elements of the navbar together.

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
- the `onclick` attribute added to the hamburger icon


The main idea of this small project: to make it responsive, the CSS was written for a small screen size and to adapt to a larger screen, I used media queries to change the design when it hits a breakpoint. 

I thought it was confusing to use `@media` but after trying it, it wasn't that bad. You just change properties/write css for the element you want to change once the breakpoint is met.

I thought it was confusing to use `@media` but after trying it, it wasn't that bad. You just write css for the element you want to change once the breakpoint is met. In this case the menu links are hidden until a user clicks the icon. That will toggle the display property of the `<div>` holding the nav links from `display: none` to `display: block`. When the screen size is increased to more than 600px, the icon will disappear and the menu links will link up in the nav bar.

Aside from the media query, the other import part to make this happen was the javascript, which is the part that works `toggleMenu()` function tied to the `onclick` event.


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

When a user clicks on the icon, javascript will grab `<div>` with the id of `nav-links` and check to see if it has the `hidden` class. If it does, `.remove('hidden')` it or else add (`+='hidden'`) it.



This is actually my second attempt. The first time, instead of clicking, I tried the toggle the menu by hovering over the icon. It worked, but I ran into a problem where if I hide the menu, and then resize the screen, the menu and icon would still be hidden.

A few changes I would make is to redo the hamburger icon. Instead of linking an image, I may just try to create the icon with HTML/CSS. In addition to that I am interested in trying to add a small animation to the menu. Maybe have it slide down or pop out from the icon.

There is so many ways to do this, but hopefully the way I did it can help give some insight to some of you readin this.

Please take a look and play with the browser window size to see it in action - [Responsive Navbar on Codepen]( https://codepen.io/jpkim921/pen/OJPovew ).



