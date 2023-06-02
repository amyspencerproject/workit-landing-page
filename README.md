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
  - [Useful resources](#useful-resources)
- [Author](#author)


## Overview

### The challenge

Users should be able to:

- View the optimal layout for the interface depending on their device's screen size
- See hover and focus states for all interactive elements on the page

### Screenshot

![](./screenshot.jpg)

Add a screenshot of your solution. The easiest way to do this is to use Firefox to view your project, right-click the page and select "Take a Screenshot". You can choose either a full-height screenshot or a cropped one based on how long the page is. If it's very long, it might be best to crop it.

Alternatively, you can use a tool like [FireShot](https://getfireshot.com/) to take the screenshot. FireShot has a free option, so you don't need to purchase it. 

Then crop/optimize/edit your image however you like, add it to your project, and update the file path in the image above.



### Links

- Repo URL: [Add solution URL here](https://your-solution-url.com)
- Live Site URL: [Add live site URL here](https://your-live-site-url.com)

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


### Useful resources

- [Stack Overflow-Curved Bottom](https://stackoverflow.com/questions/17040709/can-i-create-a-div-with-a-curved-bottom) - This was a good discussion on different ways to get curved bottoms on elements.
- [CSS Counter()](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles/Using_CSS_counters#list_item_counters) - CSS allows for a good deal of control over counting for lists.
- [Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements) vs [Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
- [Responsive Curved Header](https://codepen.io/soi/pen/OJXarwz) - Codepen example of a curved header!
- [Non-rectangular Headers](https://css-tricks.com/creating-non-rectangular-headers/)


## Author

- Website - [Amy Spencer](https://spencerproject.com/)
- Frontend Mentor - [@amyspencerproject](https://www.frontendmentor.io/profile/amyspencerproject)
- Linkedin - [amyspencercodes](https://www.linkedin.com/in/amyspencercodes/)
