# Frontend Mentor - QR code component solution

This is a solution to the [QR code component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/qr-code-component-iux_sIO_H).

## Table of contents

- [Overview](#overview)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My Process](#my-process)
  - [Built with](#built-with)
  - [HTML](#html)
  - [CSS](#css)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview
### Screenshot
![Screenshot of desktop solution](/01-qr-code-component/images/qr-desktop.png)

### Links
- [Solution code](https://github.com/ahanlixu/fm-challenges/tree/master/01-qr-code-component)
- [Live site](https://ahanlixu.github.io/fm-challenges/01-qr-code-component/)

## My Process
### Built with

- HTML5
  - Semantic elements
- CSS
  - Custom properties
  - Flexbox

### HTML
#### Semantic elements
I used `<article>` for the card, as it's a self-contained piece of content. I used `<h1>` for "Improve your front-end skills by building projects," as it was the only text that could really be considered heading-level.

### CSS
#### CSS reset
First, I used a CSS reset to give me a clean slate to work with—I went with Josh W. Comeau's version. I linked the reset in the `<head>` of my HTML, above the link to my main CSS file.

#### Custom font
The style guide provided a link to the Google Fonts page for Outfit, so I followed the link and grabbed the embed code for the font there. This code also went into the `<head>`.

#### Custom properties
Taking the color values from the given style guide, I made custom properties to make it easier for me to use those colors throughout the CSS. I declared these custom properties at the top of my CSS file, using the `:root` selector. Whenever I needed to use one of these custom colors, I used the `var()` function.

#### Flexbox
For the layout, I used flexbox. I applied `display: flex;` to the `<body>` to be able to center the card on the page. I also applied `display: flex;` to the card `<article>` to be able to center the content inside the card.

#### The font smoothing rabbit hole
While working on the font styling, I noticed that all of my text would show up a bit bolder in the browser even though I used 400 and 700 weight as specified in the style guide. I wondered if it had something to do with the browser itself (I use Firefox on MacOS), so I tried viewing the page using a different browser. Sure enough, the text looked like the correct weight on Safari and Chrome. So why did it look weird in Firefox?

![Browser comparison](/01-qr-code-component/images/qr-comp.png)

After much Googling, I learned that it had to do with font smoothing. From what I understood: in MacOS, browsers apply smoothing on text. In particular, *subpixel* rendering is applied by default. However, subpixel rendering thickens the text quite a bit. To avoid this, we can change the font smoothing flavor from subpixel rendering to pixel-level antialiasing by adding these two lines in the CSS:

```
-webkit-font-smoothing: antialiased;
-moz-osx-font-smoothing: grayscale;
```

`-webkit-font-smoothing: antialiased;` was already included in the CSS reset I used, which is why Safari and Chrome looked fine when I tested them; if it wasn't included, the text would have looked thicker on those browsers too.`-moz-osx-font-smoothing: grayscale;` is Firefox's analog for it; once I added it, my text looked like the correct weight in Firefox.

There are arguments for and against using antialiasing over subpixel rendering for font smoothing; I'm still a bit on the fence, I think. Feel free to chime in with your thoughts!

### Continued development

With this being my first challenge, I mainly just focused on copying the design as closely as I could and as quickly as I could. If I were to revisit this, I would work on making it responsive.

### Useful resources

- [Josh W. Comeau's Custom CSS Reset](https://www.joshwcomeau.com/css/custom-css-reset/) - Not exactly a "true" reset since it doesn't wipe out *everything*, but it cleans up enough of the funky stuff while keeping some useful default styles.
- [CSS Custom Properties Cheatsheet](https://www.freecodecamp.org/news/css-customs-properties-cheatsheet-c86778541f7d/) - A quick reference for how to declare and use custom properties.
- [How To Load and Use Custom Fonts with CSS](https://www.digitalocean.com/community/tutorials/how-to-load-and-use-custom-fonts-with-css#finding-and-loading-a-font-file-from-a-hosted-service) - A tutorial with two methods for loading custom fonts.
- [Flexbox Zombies](https://mastery.games/post/flexboxzombies2/) - A game that teaches flexbox. This is how I personally learned how to use flexbox! I played it about a year ago and I still remembered enough to apply flexbox in this challenge without needing to look up reference, which I think is a testament to how effective this game is.
- A bunch of articles about font smoothing:
  - [font-smooth](https://developer.mozilla.org/en-US/docs/Web/CSS/font-smooth)
  - [Font Smoothing](https://ui.dev/rwd/articles/font-smoothing)
  - [Laissez-Faire Font Smoothing and Anti-Aliasing](https://www.zachleat.com/web/font-smooth/)
  - [Please Stop "Fixing" Font Smoothing](https://usabilitypost.com/2012/11/05/stop-fixing-font-smoothing/)
  - [Font smoothing (from Josh Comeau's CSS reset)](https://www.joshwcomeau.com/css/custom-css-reset/#four-font-smoothing-5)
- [MDN Web Docs](https://developer.mozilla.org/en-US/) - My go-to HTML and CSS (and JS) reference.

## Author
Hi, I'm Angela! I'm a designer with a background in engineering. I'm working toward a career in frontend development and/or UX engineering.

- Website - [Angela Xu](https://angelahxu.com/)
- Frontend Mentor - [@ahanlixu](https://www.frontendmentor.io/profile/ahanlixu)

Thanks for reading my (very verbose) solution writeup! 👋