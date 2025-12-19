
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

- View the optimal layout for the site depending on their device's screen size

### Screenshot

![](./images/Screenshot%20(350).png)

### Links

- Solution URL: [https://github.com/keerthana769/Four-Card-Feature-Section/]
- Live Site URL: [https://keerthana769.github.io/Four-Card-Feature-Section/]

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- SASS (SCSS preprocessor)
- Flexbox
- CSS Grid
- Mobile-first workflow

### What I learned

1. **Inspecting box-shadow & colors in Figma**

  - Some properties in Figma are linked to styles, so to view their exact values you need to unlink the style by clicking the link icon, open the property settings to inspect the values, and then undo the change, colors can also be easily converted from HEX to RGB directly in Figma.
  - Applying 50% opacity in CSS
    ```css
    box-shadow: 0px 15px 30px -11px rgba(131, 166, 210, 0.5);
    ```

2. **Understanding responsive values**

  - Responsive values avoid fixed px everywhere and use relative units instead.
  - Common units:
    - rem → scales with root font size ( spacing)
    - em → scales with parent
    - % → relative to parent size
    - vw / vh → relative to screen size
    - clamp() → best for fonts 
  - Converting pixels to rem
    1rem = 16px (default browser size)
    px ÷ 16 = rem
  - Use rem for: Font sizes, Padding / margin, Gaps, Border radius
  - Keep px for: Borders (1px), Fine shadows, Icons (when needed)
  - Container width → max-width + width: 100%

3. **Avoid over-precise rem values**

  - If `font-size: 1.3333333333rem`; Round to 2–3 decimal places, `font-size: 1.33rem;`

4. **rem vs body font-size**

  - rem is based on the html font-size, NOT body.
  - Changing this does not affect rem, it effects em, text size inside body, percentages based on body:
    ```css
    body {
      font-size: 15px;
    }
    ```
  - Only this changes rem:
    ```css
    html {
      font-size: 15px;
    }
    ```
  - Best practice
    ```css
    html {
      font-size: 100%; /* 16px */
    }

5. **Understanding padding-inline**

  - padding-inline adds spacing inside the box on the left and right. This makes layouts more future-proof and accessible.
  - Automatically adapts to writing direction:
    LTR → left ↔ right
    RTL → right ↔ left

6. **Grid centering techniques**

  - Center the grid inside its parent
    ```css
    .grid {
      display: grid;
      place-content: center;
    }
    ```
  - Center items inside grid cells
    ```css
    .grid {
      display: grid;
      place-items: center;
    }
    ```
  - Center a single grid item
    ```css
    .item {
      place-self: center;
    }
    ```
  - Grid → place-items (items), place-content (container)

7. **Fixing unexpected heading sizes**

  - The Figma file initially caused confusion because it only showed desktop font size for headings and didn’t provide separate values for mobile, which led me to use an incorrect heading size; after inspecting the design more carefully in Figma, I identified the correct font size and adjusted it accordingly.

8. **Grid vs Flex**

  - Grid for layout, Flex for alignment inside

9. **Tablet & Desktop Learnings**

  - order works in Grid and Flex. It changes visual order only, not DOM order
    ```css
    .item {
      order: -1;
    }
    ```
  - `order: 0;` default value
  - Positive - Moves later
  - Negative - Moves earlier
  - Screen readers follow HTML order
  - Use order only for small responsive tweaks
  - Safe responsive reordering
    ```css
    .item {
      order: 0;
    }

    @media (min-width: 768px) {
      .featured {
        order: -1;
      }
    }
    ```
  - order changes what you see, not what the browser reads
  - If two items must share the same row vertically → That row must be split


### Continued development

I plan to continue improving my use of semantic HTML and clean CSS, while also refining how I write Sass by making better use of mixins and other Sass features. I will focus on reducing repetition, removing unnecessary code, and keeping the styles more readable and maintainable.

### Useful resources

- [Resource 1](https://sass-lang.com/guide/) - Helped to write sass.

## Author

- Frontend Mentor - [@keerthana769](https://www.frontendmentor.io/profile/keerthana769)
- LinkedIn - [@keerthana-gurram](https://www.linkedin.com/in/keerthana-gurram/)
