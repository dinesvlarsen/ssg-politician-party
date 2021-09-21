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

- It is possible to change all occurrences across multiple files by doing ctrl + shift + H, which got super handy when I wanted to refactor the footer on nav, since those elements have been copied and pasted across several files. Sadly I figured this out a bit late.

- With css different css selectors you don't really need classes to get to elements anymore.

- Need to pay more attention to when I code, and how it formats, even tho I used prettier to format, it can format things weirdly if I don't pay attention.

- CSS grid is incredibly useful and powerful when used correctly.

- I should definitely learn to be at 100% zoom when working in figma or other design programs, because a lot of the pictures and planned sizes was way too big when I implemented them in real practice.

- Need to pay attention to when I abandon a way of styling or style, so I don't end up with useless css that doesn't do anything.

### Continued development

On my future projects and this one, I want to implement responsiveness, cause it kind of bugs me that this site cant be viewed on any device too small.

I also want to get more aquatinted with CSS Grid, so I can pull it out without having to spend to much time looking up what the difference properties I can use are.

## Author

- Twitter - [@Dinesvlarsen](https://twitter.com/Dinesvlarsen)

## Acknowledgments

Travesty Media - because of the youtube video I used to figure out how to add a full-screen video as a background.

Css-tricks.com - because of both their css grid and flexbox run down.
