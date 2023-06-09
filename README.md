# Frontend Mentor - Workit landing page solution

This is a solution to the [Workit landing page challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/workit-landing-page-2fYnyle5lu). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued Development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)


## Overview

### The challenge

Users should be able to:

- View the optimal layout for the interface depending on their device's screen size
- See hover and focus states for all interactive elements on the page

### Screenshot

![](./Screenshot%20Workit%20landing%20page.png)

### Links

- Github Repo URL: [Workit Repo](https://github.com/amyspencerproject/workit-landing-page)
- Live Site URL: [Workit Landing Page](https://amyspencerproject.github.io/workit-landing-page/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- CSS Grid
- Mobile-first workflow


### What I learned
- Having a hard time figuring out how many columns and rows to use for header grid container. There is a difference between having implicit and explicit grid. Pretty sure I would like the former which means using `minmax()` and `repeat()`

- There is a big difference between underlining a word `text-decoration: underline #44FFA1;` and using a border to underline the element that the word resides in `border-bottom: solid 0.25rem #44FFA1;`. Using a border comes closer to the design comp for this challenge. It also looks better with the larger stand out text because the spacing between the word and the line is larger and the thickness of the border can be precisely controlled.
- This challenge has curved lines at the bottom of two sections. I attempted to make this effect with SVG but I was soon going down a rabbit hole that would not get me to the finish line of completing this challenge. Went with using border-radius with a much wider width so the edge appears more subltly curved. The edge is certaily not as clean as if I did SVG.
- Button vs anchor link: Here is a response from FEM discord server from Chamu to another developer doing this same challange
![](./btn-vs-anchor-screenshot.png)
- Even though fonts were available in this challenge as files in the assets (ie .ttt) both font-families were available on Google fonts. I haven't used `@font-face ` for ages and probably should review that at some point.
- I used an ordered list for the benefits which are numbered 1 - 3. The numbers have quite a bit of style applied to them and it was not as simple as using the default numbers that come with `<ol>`. The biggest styling issue was getting rid of the period after the number which is the default setting. I found a partial solution in [Stack Overflow](https://stackoverflow.com/questions/28490537/how-to-remove-dot-from-css-list-styledecimal). This along with using `counter()` got me to a more malleable numbering scheme.
- I used flex on the list numbers to get them centered horizontally and vertically. Until this centering was applied I could not get the border to be a perfect circle of a resonalbe size.
- Pseudo-element (double colons `::`)is a keyword added to a selector that lets you style a specific part of the selected element(s). For example, `::before` is the first child of the selected element. It is often used to add cosmetic content to an element with the content property.
- Pseudo-class (single colon `:`) is a keyword added to a selector that specifies a special state of the selected element(s). For example, `:hover` can be used to select a button when a user's pointer hovers over the button and this selected button can then be styled.
- Stuggled with the mobile phone image and the z-indexing. Learned that the z-index of a child is trapped by the z-index of the parent. Pulled the image out of the hero section and gave it a hero-image-wrapper to get the layout correct while also being able to set the z-index to put the image above the other divs.
- Used `<span>` with `display: block` in the `h1` header title to force a line break with out using `<br />`
- Using negative values with positioning does not work well. The left spiral pattern in the header was set to -35% and it kept dissapearing as the screen size was increased. Here is the explaination that I got from FEM Discord:

  Giving it a left: -35% is basically telling it to be anchored 35% of the viewport (the parent is 100% of the viewport), but in the opposite direction. As the viewport grows, that value grows, moving it further and further from the left edge. If you want it to stick to the same place relative to the viewport, try using pixels or rems instead of a % value. 

  If you want it to be somewhat responsive, like the one on the right side, try something like right: 80% instead.

- Careful when setting a z-index value for larger container element such as `<main>`. I set `<main>` to `z-index: -1`. A mouse hover will not register since the mouse can "see" anything in the negative. I chased this issue for more than an hour before realizing that I had set `<main>` to `z-index: -1` while wrestling with the mobile phone positioning. It was just fine to set `<main>` to `z-index: 1` and then just adjust all the other elements to one z-level higher.

- Used proper `<svg>` elements for the social icons instead of linking the files as images. Doing this allowed for an active hover state for the icons. This was a first for me. 

- CSS Nesting is not supported by Mozilla-Firefox or Opera! I didn't realize I was using something so new and unsupported. The curved borders are not visible in these browsers because the background color and curved border are child elements nested within the container parent element. In the example below the parent has a white background and the child has the dark curved background.

![](./nested-css-example.png)

My challenge solution screenshot which is generated by FrontEnd Mentor looks terrible!
![](./screenshot-solution-compare.png)

- Decided to change everything about how I created curved borders. Went back to the stradegy of having a round border radius with a width of 150% so it will stretch long into a lovely curve. The border-radius is set to 50% so making a circle and this is applied at 100% to only the bottom-left and bottom-right of the div.
  ```
  border-radius: 50% / 0 0 100% 100%;
  width: 150%;
  ```

### Continued Development

I am fairly happy with my final submission on this challenge. If I were starting again I would try to incorporate the calc() css function to control the sizing of the hero image. I am very timid with setting a height for anything but with responsive images you need to at some point. Using auto and calc() can make the responsivemess much smoother. Additionally I would have like to start using [CSS Custom Properties](https://css-tricks.com/a-complete-guide-to-custom-properties/) or at a minimum use [BEM](https://css-tricks.com/bem-101/) naming conventions. This will make my code and stylings easier to understand both for others and more importantly to future self. 

### Useful resources

- [Stack Overflow-Curved Bottom](https://stackoverflow.com/questions/17040709/can-i-create-a-div-with-a-curved-bottom) - This was a good discussion on different ways to get curved bottoms on elements.
- [CSS Counter()](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles/Using_CSS_counters#list_item_counters) - CSS allows for a good deal of control over counting for lists.
- [Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements) vs [Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
- [Responsive Curved Header](https://codepen.io/soi/pen/OJXarwz) - Codepen example of a curved header but it uses nesting CSS and therefore has serious browser compatibility issues!
- [CSS Positioning](https://css-tricks.com/absolute-relative-fixed-positioining-how-do-they-differ/#:~:text=This%20is%20a%20very%20powerful,right%20to%20set%20the%20location.) - this article has very clear descriptions of different types of positioning and when to use them.
- [CSS Parent-Child Positioning](https://css-tricks.com/absolute-positioning-inside-relative-positioning/) - Reminder to set the parent element to relative.
- [Non-rectangular Headers](https://css-tricks.com/creating-non-rectangular-headers/)
- [4 reasons Z-index isn't working](https://coder-coder.com/z-index-isnt-working/) - very clear article on reasons why the z-index mysteriously isn't working.
- [Linebreak w/o the `<br />` tag](https://www.geeksforgeeks.org/how-to-break-line-without-using-br-tag-in-html-css/) - clever way to avoid `<br />` with a `<span>'
- [Hover fill change to SVGs](https://stackoverflow.com/questions/19157122/css-change-fill-color-on-hover-svg-path) - pretty straight forward

## Author

- Website - [Amy Spencer](https://spencerproject.com/)
- Frontend Mentor - [@amyspencerproject](https://www.frontendmentor.io/profile/amyspencerproject)
- Linkedin - [amyspencercodes](https://www.linkedin.com/in/amyspencercodes/)
