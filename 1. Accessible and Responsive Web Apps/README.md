# Accessible & Responsive Web Apps (due August 6th)

## 1. Why Responsive:

1.  Quiz 8
> Hold Down **Ctrl+Shift+M** (toggles device toolbar). Then from the drop-down menu select **Edit/Add Custom Device**.

## 2. Starting Small:

1. Defining the Viewport
> His screen is 2560px wide. However, when he opens the viewport width it shows 1280px. <br />
> **WHY?** Because not all pixels are created equal.

2. Pixels, pixels and more pixels!
> **Hardware Pixels vs. Device-Independent Pixels** <br />
> DIP will always take the same amount of display on the screen regardless of the pixel density of the display. The 1280px DIPs scales up to 2560px HP. So you should always include the *viewport* meta tag in your pages.

3. Pixelation
> Mobile device pixels that found on the specs are the HP.

4. Calculating DPR
> With one DIP for every two hardware pixels, the device pixel ratio is 2.

5. What's the difference?
> The viewport and the device pixel ratio are both likely causes for the differences between devices.

6. Calculating CSS pixels
> Divide 1920px by 2 and you will get the answer. :)

7. How wide is the viewport?
> To solve the quiz divide the pixels by the DPR number.

8. Setting the Viewport
>  **initial-scale=1.0** means that the ratio between the DIP and CSS pixels is 1:1.

9. Setting the Viewport
> To pass the quiz add `<meta name="viewport" content="width=device-width, initial-scale=1.0">` to the header of the site.

10. Large Fixed Width Elements
> Using fixed width or absolute positions is not recommended. You should use relative positions.

11. Max-width on elements
> Setting a `max-width` of 100% should avoid overflow for most elements.

12. Relative Sizes
`max-width` overrides `width` so if you have them both then the max width will overrides the styles.

13. Tap Target Sizes
> Human fingers are at least 40 CSS pixels. So it is safer to give your buttons a Height and width of 48px.

14. Tap Targets
> `min-width: 48px; min-height: 48px;`

15. Start Small
> Starting small (eg. mobile first) might remove the need to re-design your website for larger screens.

16. Project Part 1 [Inspect Styles](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/)
> The full answer of this quiz is in lesson `17`.

## 3. Building Up

1. Lesson Intro

2. Basic Media Query Intro
> Media queries are used to apply styles depending on device characterstics.

3. Adding a basic media query
> [Using Media Queries [MDN]](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)

4. Adding a basic media query 2
> `min-width:500px` means that the MQ will be triggered and styles applied only if the *viewport* is bigger than 500px.

5. Next Step Media Queries
> Developers usually use max-width and min-width media queries because they are relatively error-proof. Max-width styles get applied when the *viewport* is smaller than the specified width.


6. Which styles are applied?
> Remove what is there and change it with this code.
```css
body {
    background-color: green;
}

@media screen and (min-width: 600px) {
    body {
        background-color: blue;
    }
}

@media screen and (max-width: 400px) {
    body {
        background-color: red;
    }
}
```

7. Breakpoints
> Predefined widths at which majors layout changes happen. For example, swapping the main navigation for a burger one or other hidden version suitable for smaller screens.

8. Breakpoints Pt. II
> To see the screen resolution of the window you need to open DevTools. In that lessons you don't see the devtools open because he opened the DevTools in a separate window. 

9. Number of Breakpoints
> 2 for medium.com and 2 for the course example.

10. Picking Breakpoints
> Use your content as a guide to pick your breakpoints.

11. Picking Breakpoints 2

12. Pick a Breakpoint

13. Complex Media Queries

14. What Styles Are Applied? [Guide](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
```css
@media screen and ( max-width:400px)
@media screen and ( min-width:301px) and ( max-width:600px)
@media screen and ( min-width:601px)
@media screen and ( min-width:961px)
```
15. Grids [Helpful Guide](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Basic_Concepts_of_Grid_Layout)
> Bootstrap and 960

16. Flexbox Intro

17. Flex Item
> Using the order you can change the order to whatever you want.

18. Deconstructing a Flexbox Layout

19. Deconstructing a Flexbox Layout

20. Deconstructing a Flexbox Layout(quiz)
> Three columns width will be 33.33% because it will give you around 99.99%, almost 100%.


## 4. Common Responsive Patterns
Walk through the most popular responsive layout patterns and learn the tools needed to implement them in your own designs.

1. Intro to Patterns
> There are 4 patterns: Mostly Fluid, Column Drop, Layout Shifter, Off Canvas 

2. Pattern - Column Drop

3. Pattern - Mostly Fluid

4. Mostly Fluid Part 1(quiz)

5. Mostly Fluid Part 2(quiz)
> The red is 33 and not 25.

6. Combining Fluid Layouts

7. Pattern - Layout Shifter

8. Which is Which?

9. Pattern - Off Canvas

10. Off Canvas Visualization

11. Project Part 2

## 5. Optimizations
Learn how to optimize images, tables, and fonts to make for the best responsive layouts.

1.Lesson Intro

2. Images
> You could have a high quality image as well as a smaller one.

3. Tables
> Hiddedn Colums / No More Tables / Contained Tables

4. Responsive Tables - Hidden Columns
> The drawback of this approach is that you hide content from the users.

5. Hide Some Columns [helpful link](https://www.thoughtco.com/display-none-vs-visibility-hidden-3466884)
> @media screen and (max-width:499px){ .gametime { display:none } } 

6. Responsive Tables - No More Tables
> This technique show all the data the users want to see
![](https://github.com/awesome-mws/udacity-mws-nd/blob/master/1.%20Accessible%20and%20Responsive%20Web%20Apps/img/5.6%20-%201.PNG)
![](https://github.com/awesome-mws/udacity-mws-nd/blob/master/1.%20Accessible%20and%20Responsive%20Web%20Apps/img/5.6%20-%202.PNG)

7. Responsive Tables - Contained Scrolling
![](https://github.com/awesome-mws/udacity-mws-nd/blob/master/1.%20Accessible%20and%20Responsive%20Web%20Apps/img/5.7.PNG)

8. Fonts
![](https://github.com/awesome-mws/udacity-mws-nd/blob/master/1.%20Accessible%20and%20Responsive%20Web%20Apps/img/5.8.PNG)

9.Minor Breakpoints
> Like changing the icons size or making the font a bit bigger.

10.Project.

## 6. Getting Up and Running
Sam Dutton, the developer advocate at Google, explains the importance of getting responsive images right and helps you set up mobile developer tools.

1. Course Introduction

2. Why Responsive Images?
> They shoud work no matter the screen size is.

3. Intro to Project

4. Setting up Your Environment

5. Setup for mobile [Helpful Link](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/?hl=en)

6. Using dev tools on mobile 

7. Mobile tools for iOS [Helpful Link](https://github.com/google/ios-webkit-debug-proxy)

8. Lesson Wrap Up

## 7. Units, Formats, Environments
Optimize images to display beautifully on all screen sizes. Learn about the difference between Raster vs Vector images, responsive CSS units, and setting up optimization tools.

1. Sizing Intro
> Make sure the recording icon is red. Then disable the cache. Then Hit F5.

#### To manipulate an element in the DOM. CLick on that element. (In your console) type $0. If the console is not showing below your element tab then go the _horizontal three dots_ and click on show console drawer. 

[Edit DOM](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/edit-dom)
[Firefox DOM_Property_Viewer](https://developer.mozilla.org/en-US/docs/Tools/DOM_Property_Viewer)
[Chrome DOM_Property_Viewer](https://developers.google.com/web/tools/chrome-devtools/console/command-line-reference?utm_source=dcc&utm_medium=redirect&utm_campaign=2016q3#selector_1)

> In Chrome: You can see all the _DOM Properties_ for a certain element by using **console.dir($0)**

```javascript
// For checking the width of the img
$0.naturalwidth
```
2. All about Bits and Pixels
![](https://github.com/awesome-mws/udacity-mws-nd/blob/master/1.%20Accessible%20and%20Responsive%20Web%20Apps/img/7.2.PNG)


3. Requests and Revenue
![](https://github.com/awesome-mws/udacity-mws-nd/blob/master/1.%20Accessible%20and%20Responsive%20Web%20Apps/img/7.3.PNG)


4. Relative Sizing [Calc](https://developer.mozilla.org/en-US/docs/Web/CSS/calc)

![](https://github.com/awesome-mws/udacity-mws-nd/blob/master/1.%20Accessible%20and%20Responsive%20Web%20Apps/img/7.4.1.PNG)

![](https://github.com/awesome-mws/udacity-mws-nd/blob/master/1.%20Accessible%20and%20Responsive%20Web%20Apps/img/7.4.2.PNG)


5. IMPORTANT! Udacity Front End Feedback Extension

6. calc()
> Note: There MUST be a space on each side of the + and - operators. (A space is not required around * and / as the problem is an ambiguity around negation.) For example: calc(100px - 10%) will work. calc(100px-10%) will not.

```css
margin-right: 10px;
width: calc((100% - 20px)/3);

/* This means that there is no margin right after the last img */
img:last-of-type{
margin-right: 0;
}
```
7. Landscape and Portrait
> Don't assume the view-port will always stay the same. The screen orientation can rotate and miss up your calculation

8.Less Well Known CSS Units
> vh and vw. viewport height and viewport width. vmin and vmax

9. Raster and Vector
[vector-vs-raster-what-do-i-use](https://designshack.net/articles/layouts/vector-vs-raster-what-do-i-use/)

10. Rastor or Vector ?
> Vector images can be scaled infinitely, which means that it'll be sharp and clear even on a 50m banner

11. Raster and Vector Identification
> SVG are vectors. JPG and PNG are Raster

12. File formats
> Use svg because it is really small and fast.

13. Spot the Differences 

14. Spot the Differences 2
> Compression ratio is different

15. Image Compression [pagespeed](https://developers.google.com/speed/pagespeed/insights/)

16. Project Part 1
[imagemagick](http://www.imagemagick.org/script/index.php)
[grunt-is-not-weird](https://24ways.org/2013/grunt-is-not-weird-and-hard/)
[srcset-with-grunt](https://addyosmani.com/blog/generate-multi-resolution-images-for-srcset-with-grunt/)
[grunt-responsive-images](https://github.com/andismith/grunt-responsive-images)

```javascript 
// Download imagemagick for your OS https://www.imagemagick.org/script/download.php
// cd to the project folder then type
npm install
npm install -g grunt

// inside the grunt file type 
width: 1600,
suffix: '_large_2x',
quality: 30

// ready!set!responsiveimages!
```

> If the grunt tool didn't work for you. This website can be helpful (http://compressimage.toolur.com)

## 8. Images with Markup
Dive deep into image alternatives like CSS and icon fonts and learn common strategies to alleviate latency.

## 9. Full Responsiveness
Learn to use the srcset attribute and the picture element to choose images of the right size for your application for every viewing context.

## 10. Accessibility Overview
Explore the diversity of different users experience with websites and applications. Learn about using screen readers practically and recognize the challenge of building web experiences for all users.

## 11. Focus
Manage focus - the location on a page that receives input from the keyboard. Discover how some users navigate website entirely with the keyboard, and how to optimize their experience.

## 12. Semantics Basics
Dive into the differences between visual UI and semantically designed accessible UI. Add semantic elements to HTML to create a user interface that works for everyone.

## 13. Navigating Content
Implement effective semantic navigation using headings, link text and landmarks.

## 14. ARIA
Sometimes an HTML element may not have a role or value assigned semantically. In this lesson, you'll use ARIA attributes to provide context for screen readers.

## 15. Style
Incorporate CSS styling into your accessible web design and use accessible colour schemes to improve accessibility.

## 16. The Benefits of Offline First

## 17. Introducing the Service Worker

## PROJECT - Restaurant Reviews App — Stage 1
In this real-world case study, given the front-end code for a static Restaurant Reviews App, revise the site to be responsive and achieve accessibility standards.
