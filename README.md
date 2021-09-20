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

I started with getting a general picture of what pages I'd need by checking other Norwegian politician party sites, mostly arbeiderpartiet.no and hoyre.no. And kept these sites close so I could reference back to them when needed.

After getting a general picture of how the sites are set up, I decided to make some sketches in figma, where I pasted the requirements and set up a list of the general pages I'd need like:

- Landing page
- About the party page
- Join the party
- Blog
- What the party wants
- What we have already done / accomplished
- Members of the party

## **The start**

After getting a general list, I started sketching out the landing page, I decided pretty early that I wanted it to have a video background, and tried to find some resources on the web explaining how this is accomplished, found a youtube video where he basically attaches it to a container which he gives the position absolute, so you can place other content on top of it.

This is the approach I chose to go for, what I found challenging here was editing the video so the content I would add on top wouldn't become unreadable. So I tried first to create a secondary image that I would place over it, but the attempt failed. I then resulted in trying to add a color with an alpha code, so it would become see through, but was not satisfied with how it looked. Eventually I just turned down the opacity and for some reason it looked pretty good so I decided to run with it.

All while working on the landing page I kept iterating design ideas, this is how I ended up landing on having a transparent nav, which originally was not my idea (wanted to have one with a white background, but it looked really bad on the landing page).

Once the video and content was placed, I noticed the box with the heading and paragraph looked a bit empty on the right, so decided to add some media icon links to fill the space and make it more appealing.

The approach I took on the video was

once I had a

### **Built with**

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- Mobile first workflow

### **What I learned**

I realized that text can be a bit tricky to have match up in a way so it doesn't push other content out of its placement, if it didn't match up the buttons wouldn't end up properly aligned.

I also tried to find a way to reduce the code I've used on the hover effects:

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
