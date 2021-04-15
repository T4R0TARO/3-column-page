# Frontend Mentor - 3-column preview card component solution

This is a solution to the [3-column preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/3column-preview-card-component-pH92eAR2-). 

![Screenshot from 2021-04-14 17-18-01](/home/tarotaro/Pictures/Screenshot from 2021-04-14 17-18-01.png)

![Screenshot from 2021-04-14 17-18-15](/home/tarotaro/Pictures/Screenshot from 2021-04-14 17-18-15.png)

![Screenshot from 2021-04-14 17-18-18](/home/tarotaro/Pictures/Screenshot from 2021-04-14 17-18-18.png)

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover states for interactive elements

### Screenshots

**Mobile-Layout:**

![image-20210414171253381](/home/tarotaro/.config/Typora/typora-user-images/image-20210414171253381.png)

**Desktop Layout:** 

![Screenshot from 2021-04-14 17-24-00](/home/tarotaro/Pictures/Screenshot from 2021-04-14 17-24-00.png)

**Active state :hover**

### ![Screenshot from 2021-04-14 16-25-31](/home/tarotaro/Pictures/Screenshot from 2021-04-14 16-25-31.png)



### Links

- Solution URL: [Add solution URL here](https://your-solution-url.com)
- Live Site URL: [Add live site URL here](https://your-live-site-url.com)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- Mobile-first workflow

### What I learned

Deeper understanding of the box-model, how to organize my container elements, and the row/column pseudo-class.  I start off the project by organizing my html as much as I can before styling with CSS. The design ask for 3 section separated equally both in mobile and in landscape. I organize my html to prepare it for the  pseudo-class row and column with the goal of making a 3-column layout for the design. I create <section> to act as the main parent container and give it the " row ". 

Next create the first card and the first column of the row. The <div> container is given the class = "sedan_card column" and the elements within the card container is organized in a header/body/footer style with each piece of content in the design is contained within div element to target it for positioning.

```html
<body>
  <section class="main_section row">
    <div class="sedan_card column">
      <div class="card_content">
        <div class="card_img">
          <img src="images/icon-sedans.svg" alt="">
        </div>
        <div class="card_text">
          <h2 class="card_title">SEDANS</h2>
          <p>Choose a sedan for its affordability and excellent fuel economy. Ideal for cruising in the city or on your next road trip.</p>
          <div class="card_button">
            <button class="sed_btn">Learn More</button>
          </div>
        </div>
      </div>
    </div>
```
The design requested that each section have a different color background and buttons when the cursor hovers over the element. Each card element is specifically targeted by it's class name and using custom properties for the color variables. This is where I implanted flex-box and gave the main section a flex-direction: column rule so that the content will be displayed vertically for mobile-use since I want to practice the mobile-first approach. 


````css
/* MAIN CARD STYLES */
.main_section {
    display: flex;
    flex-direction: column;  
}
.card_img {
    margin-bottom: 3rem;
}
.card_content {
    margin: 50px;
}
.sedan_card {
    background: var(--sedan-bkg-color);
}
.suv_card {
    background: var(--suv-bkg-color);
}
.luxury_card {
    background: var(--lux-bkg-color);
}
````

Each button element is targeted by their class name and given the :hover that will change the text to white and the background of the button will be the same with the background of the card giving it a transparent effect whenever the cursor hovers over the element. 

````css
/* BUTTON STYLES */
/* :hover will give transparent effect */

button {
    padding: 20px 50px;
    border-radius: 2.25rem;
    border: none;
}
.sed_btn {
    color: var(--sedan-bkg-color)
}
.sed_btn:hover {
    border: 2px #fff solid;
    color: #fff;
}
.suv_btn {
    color: var(--suv-bkg-color)
}
.suv_btn:hover {
    border: 2px #fff solid;
    color: #fff;
}
.lux_btn {
    color: var(--lux-bkg-color)
}
.lux_btn:hover {
    border: 2px #fff solid;
    color: #fff;
}
````

**Media query:**

````css
/* This media query will
    * Change mobile styles to desktop styles
    * Increase card_text elements
    * Increase img size
    * Increase button size
    * Implement desktop styles when the browser is at least 800px
*/

@media screen and (min-width: 800px) {
    .main_section {
        display: flex;
        flex-direction: row;
        height: 100vh;
    }

    .column {
        width: 33.33%;
    }

    img {
        height: 50px;
        width: auto;
    }

    .card_text {
        max-width: 17.7rem;
    }
    
    h2 {
        font-size: 3.5rem;
    }
    
    p {
        font-size: 19px;
        margin-bottom: 8rem;
    }
}
````



**Continued Development:** I am currently learning the basics of CSS gird. I will remake this project implementing Grid concepts. :muscle: :dango:

### Useful resources

- https://www.w3schools.com/howto/howto_css_two_columns.asp- This helped me understand the multi-column layout
- https://developer.mozilla.org/en-US/docs/Web/CSS/:hover- This helped me understand button elements and :hover
- https://getbootstrap.com/docs/5.0/components/buttons/- This helped me further understand the button element 

## Author

- Website - [Add your name here](https://www.your-site.com)
- Frontend Mentor - [@T4R0TARO](https://www.frontendmentor.io/profile/yourusername)
- Twitter - [@taro_code ](https://www.twitter.com/yourusername)


