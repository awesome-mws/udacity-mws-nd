# Accessible & Responsive Web Apps (due August 6th)

## 1. Why Responsive:

1.  Quiz 8
> Hold Down (Ctrl + Shift + M) -- toggle device toolbar. Then go the drop-down menu and then (Edit...). Then (Add Custom Device).

## 2. Starting Small:

1. Defining the Viewport
> His chrome book is 2560pixel width. However, when he opens the viewport width he gets only 1280px. WHY? because not all pixels are created equally ?!

2. Pixels, pixels and moar pixels!
> Hardware Pixels vs Device Independent Pixel -- DIP will always take the same amount of display on the screen regardless of the pixel density of the display. The 1280px DIPs scales up to 2560px HP. So you should always include the ViewPort Meta.

3. Pixelation
> mobile device pixels that found on the specs are the HP.

4. Calculating DPR
>With one dip for every two hardware pixels, the device pixel ratio is 2!

5. What's the difference?
> The viewport and the device pixel ratio are both likely causes for the differences between devices.

6. Calculating CSS Pixels
> Divide 1920px by 2 and you will get the answer :)

7. How wide is the viewport?
> to solve the quiz divide the pixels by the DPR number.

8. Setting the Viewport
>  initial-scale=1.0 means that the ratio between the DIP and CSS pixels is 1:1

9. Setting the Viewport
> To pass the quiz add `<meta name="viewport" content="width=device-width, initial-scale=1.0">` to the header of the site.

10. Large Fixed Width Elements
> Never used fixed width or absolute positions. You should use relative positions

11. Max-width on elements
> Setting a Max width of 100% should avoid overflow for most elemetns.

12. Relative Sizes
`max-width` overrides `width` so if you have them both then the max width will overrides the styles

13. Tap Target Sizes
> Human fingers are at least 40 CSS pixels. So it is safer to give your buttons a Height and width of 48px.

14. Tap Targets
> `min-width: 48px; min-height: 48px;`

15. Start Small
> When you start small there might be no need to re-design your website for larger screens. Also, you need to prioritize what is important for you.

16. Project Part 1 [Inspect Styles](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/)
> The Full answer of this quiz is in lesson `17`



## 3. Building Up

1. Lesson Intro

2. Basic Media Query Intro
> Media Query are used to apply styles depending on device characterstics 

3. Adding a Basic Media Query [Useful Link](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)

4. Adding a basic media query 2
> when you use `min-width:500px` it means that if the viewport is less than 500px then there will be no styles applied. It is like saying (apply these styles only if my width is bigger than 500px.) or ( don't apply these styles unless my width is bigger than 500px.)

5. Next Step Media Queries
> Developers usually use max-width and min-width media queries because you can't make mistakes with them. . Max-width styles get apllied when the screen is smaller than the width the has been specified.


6.Which styles are applied?
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

7.Breakpoints
> That you can changes the entire layout of your page.

8. Breakpoints Pt. II
> To see the screen resolution on the window you need to open devtools. In that lessons you don't see the devtools open bbecause he openned the devtools in a separate window. 

9.Number of Breakpoints
>  2 for medium.com and 2 for the course example.

10.Picking Breakpoints
> Use your content as a guide to pick your breakpoints.

11.Picking Breakpoints 2

12.Pick a Breakpoint

13.Complex Media Queries

14.What Styles Are Applied? [Guide](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
```css
@media screen and ( max-width:400px)
@media screen and ( min-width:301px) and ( max-width:600px)
@media screen and ( min-width:601px)
@media screen and ( min-width:961px)
```
15.Grids[guide](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Basic_Concepts_of_Grid_Layout)
> Bootstrap and 960

16.Flexbox Intro

17.Flex Item
> using the order you can shage the order to whatever you want.

18.Deconstructing a Flexbox Layout

19.Deconstructing a Flexbox Layout

20.Deconstructing a Flexbox Layout(quiz)
> just remember that three coulmns width will be 33.33% because it will give you around 99.99% almost 100%.


## 4. Common Responsive Patterns
Walk through the most popular responsive layout patterns and learn the tools needed to implement them in your own designs.

## 5. Optimizations
Learn how to optimize images, tables, and fonts to make for the best responsive layouts.

## 6. Getting Up and Running
Sam Dutton, the developer advocate at Google, explains the importance of getting responsive images right and helps you set up mobile developer tools.

## 7. Units, Formats, Environments
Optimize images to display beautifully on all screen sizes. Learn about the difference between Raster vs Vector images, responsive CSS units, and setting up optimization tools.

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
