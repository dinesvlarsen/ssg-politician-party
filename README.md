# ssg-politician-party

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

## Overview

### **The challenge**

Users should be able to:

- Should have three different pages/sections
- Should be able to navigate between the different pages/sections
- Should contain pictures and or other media

### **Screenshot**

#### **Landing Page**

![](assets\Screenshots\landing-page.png)

#### **About Page**

![](assets\Screenshots\about-ssg.png)

#### **Politicians Page**

![](assets\Screenshots\politicians-ssg.png)

### **Links**

- Live Site URL: [SSG Politician Party](https://dinesvlarsen.github.io/ssg-politician-party/)

## **My process**

I started with getting a general picture of what pages I'd need by checking other Norwegian politician party sites, mostly arbeiderpartiet.no and hoyre.no. And kept referencing back to them when needed.

After getting a general picture of how other political sites are set up, I decided to make some sketches in figma, where I pasted the requirements and set up a list of the general pages I'd need like:

- Landing page
- About the party page
- Join the party
- Blog
- What the party wants
- What we have already done / accomplished
- Members of the party

Once I had some sketches decided, I focused on adding html content, before I turned to styling. So on every page I would see what content was supposed to be on the page, create it, and then turn to styling.
I focused on one page at the time, so first I tackled the landing page, then I worked on the sign-up page etc. After working on the sign-up page for a bit I realized the css file will get really long, so I decided to branch out and make one css file for each page.

Also wanted to keep the same footer and nav, so made an universal stylesheet for those and copy pasted the html on each page I worked on.

### **Built with**

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Desktop first approach

### **What I learned**

- I learnt that to be able to use the position: relative property you need to add a unit behind it, I was adding values without specifying what unit I want. Resulting in the content not moving (kind of spent an awkward amount of time before I figured this out).

- Also learnt that you should avoid vertical-align, since it's a table styling property.

- You don't need .left .right classes, since wherever you are specifying this, you already know that there will be an order, so you can use css Pseudo-classes.

-

```css
#sedan button:hover {
	background-color: transparent;
	color: hsl(0, 0%, 95%);
}
#suv button:hover {
	background-color: transparent;
	color: hsl(0, 0%, 95%);
}

#luxury button:hover {
	background-color: transparent;
	color: hsl(0, 0%, 95%);
}
```

By applying these:

```css
main button:hover {
	background-color: transparent;
	color: hsl(0, 0%, 95%);
}

section button:hover {
	background-color: transparent;
	color: hsl(0, 0%, 95%);
}

section:last-child:hover {
	background-color: transparent;
	color: hsl(0, 0%, 95%);
}
```

But sadly none of them worked, and I'm not sure why.

Another redundancy I tried to eliminate was the border radiuses, which I've applied to the start first section and last section, instead of just getting it to work on the parent container:

```css
#sedan {
	background-color: hsl(31, 77%, 52%);
	border-radius: 10px 10px 0 0;
}

#luxury {
	background-color: hsl(179, 100%, 13%);
	border-radius: 0 0 10px 10px;
}
```

I tried to fix it by setting border-radius on the parent container and set the overflow property to hidden. And this works when the component is in its horizontal layout, but for some weird reason not in the vertical one.

```css
main {
	border-radius: 10px;
	overflow: hidden;
}
```

![](screenshots/overflow-hidden-not-working-on-mobile-view.png)

Not sure what causes this, but as I'm writing this I realize that only fixing this issue, will reduce a bit of code at least, so I've chosen to leave the border-radius and overflow on the main container, and apply an extra border radius to the luxury card section, which I then remove again when it enters the horizontal layout screen dimension.

```css
#luxury {
  border-radius: 0 0 10px 10px;

  @media only screen and (min-width: 857px) {

  #luxury {
    border-radius: 0;
  }
}
```

### Continued development

I thought I was spot on with the design, until I took a screenshot and placed it over the design I had in figma, and noticed some my parts are a lot bigger than the design. So I guess Id like to improve my attention to detail? I'm not sure how relevant having it pixel perfect is, and maybe in this day and age of having so many different screen sizes you can't really make it pixel perfect to the design?

I also want to continue to be conscious of semantics, I feel like I'm getting better with them, and tweaking and moving things with css is getting a lot simpler, so these little challenges are definitely working.

I've written this on every project, but I STILL want to learn CSS grid, haven't gotten around to it yet, probably because I'm getting so comfortable with flex-box, but I know flex-box is not the tool for layouts, and is mostly supposed to be used for alignment.

## Author

- Frontend Mentor - [@Dinesvlarsen](https://www.frontendmentor.io/profile/dinesvlarsen)
- Twitter - [@Dinesvlarsen](https://twitter.com/Dinesvlarsen)

## Acknowledgments

I got the tip of trying out overflow: hidden by @Kaleem420#9453 on the Jonas Schmedtmann discord server. So thanks for that🙏
