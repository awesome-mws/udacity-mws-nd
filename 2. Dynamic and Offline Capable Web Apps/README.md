# Dynamic & Offline Capable Web Apps (due June 5th)

## 1. Ajax with XHR

1. Course Intro: You request a data async and then deal with it.

2. Client Server Demonstration

3. Ajax Definition & Examples

![](./img/1.3.PNG)

4. APIs

> Application Programming Interface

5. Create An Async Request with XHR

6. The XHR Object

7. XHR's .open() method

```javascript
asyncRequestObject.open();
//it takes a number of parameters but the most important are its first two: the HTTP method URL to send the request
// If we want to asynchronously request the homepage from the popular high-res image site, Unsplash, we'd use a GET request and provide the URL:
const asyncRequestObject = new XMLHttpRequest();
asyncRequestObject.open('GET', 'https://unsplash.com');
```
> Passing false as the third option makes the XHR request become a synchronous one. This will cause the JavaScript engine to pause and wait until the request is returned before continuing - this "pause and wait" is also called "blocking". This is a terrible idea and completely defeats the purpose for having an asynchronous behavior. Make sure you never set your XHR objects this way! Instead, either pass true as the 3rd argument or leave it blank (which makes it default to true).'

8. XHR's .send() method

![](./img/1.8.gif)

> To handle the successful response of an XHR request, we set the onload property on the object to a function that will handle it: As with onload, if onerror isn't set and an error occurs, that error will just fail silently and your code (and your user!) won't have any idea what's wrong or any way to recover."

```javascript
function handleSuccess () {
    // in the function, the `this` value is the XHR object
    // this.responseText holds the response from the server

    console.log( this.responseText ); // the HTML of https://unsplash.com/
}
asyncRequestObject.onload = handleSuccess;

function handleError () {
    // in the function, the `this` value is the XHR object
    console.log( 'An error occurred 😞' );
}

asyncRequestObject.onerror = handleError;
```

9. A Full Request

```javascript
function handleSuccess () { 
  console.log( this.responseText ); 
// the HTML of https://unsplash.com/}
function handleError () { 
  console.log( 'An error occurred \uD83D\uDE1E' );
}
const asyncRequestObject = new XMLHttpRequest();
asyncRequestObject.open('GET', 'https://unsplash.com');
asyncRequestObject.onload = handleSuccess;
asyncRequestObject.onerror = handleError;
asyncRequestObject.send();

// tweak the function to handle the response
function handleSuccess () {
const data = JSON.parse( this.responseText ); // convert data from JSON to a JavaScript object
console.log( data );
}
asyncRequestObject.onload = handleSuccess;
```

10. Project Initial Walkthrough

11. Setting a Request Header

![](./img/1.11.PNG)

```javascript 
const searchedForText = 'hippos';
const unsplashRequest = new XMLHttpRequest();

unsplashRequest.open('GET', `https://api.unsplash.com/search/photos?page=1&query=${searchedForText}`);
unsplashRequest.onload = addImage;
unsplashRequest.setRequestHeader('Authorization', 'Client-ID <your-client-id>');
unsplashRequest.send();

function addImage(){
}
```

12. Project Final Walkthrough

13. XHR Recap

```
To Send An Async Request
create an XHR object with the XMLHttpRequest constructor function
use the .open() method - set the HTTP method and the URL of the resource to be fetched
set the .onload property - set this to a function that will run upon a successful fetch
set the .onerror property - set this to a function that will run when an error occurs
use the .send() method - send the request
To Use The Response
use the .responseText property - holds the text of the async request's response
```

14. XHR Outro


## 2. Ajax with jQuery
In this lesson, you'll compare using XHR with using jQuery's Ajax method. You'll send and receive data using jQuery's Ajax methods and learn how jQuery's Ajax works under the hood.

1. The jQuery Library & Ajax

2. jQuery's `ajax()` Method

> $.ajax({
    url: 'http://swapi.co/api/people/1/'
});

![](./img/2.2.gif)

3. Handling The Returned Data

> If you recall from setting up an XHR object, the response was handled by a function. It's the same thing with the .ajax() method. We can chain on to .ajax() with a .done() method. We pass the .done() method a function that will run with the Ajax call is done!

```javascript
function handleResponse(data) {
    console.log('the ajax request has finished!');
    console.log(data);
}
$.ajax({
    url: 'http://swapi.co/api/people/1/'
}).done(handleResponse);
```

> Let's convert the existing, plain XHR call with jQuery's .ajax(). This is what the app currently has:

```javascript
const imgRequest = new XMLHttpRequest();
imgRequest.onload = addImage;
imgRequest.open('GET', `https://api.unsplash.com/search/photos?page=1&query=${searchedForText}`);
imgRequest.setRequestHeader('Authorization', 'Client-ID <your-client-id-here>');
imgRequest.send();

$.ajax({
    url: `https://api.unsplash.com/search/photos?page=1&query=${searchedForText}`
}).done(addImage);
```

> QUIZ: The correct answer is option 4. A header is added to the request by passing a headers object as a property. Each key in the headers object is the name of the header, and the value is what will be used as the value for the header.


4. Cleaning up the Success Callback

```javascript
function addImage() {
    const data = JSON.parse(this.responseText);
    const firstImage = data.results[0];

    responseContainer.insertAdjacentHTML('afterbegin', `<figure>
            <img src="${firstImage.urls.small}" alt="${searchedForText}">
            <figcaption>${searchedForText} by ${firstImage.user.name}</figcaption>
        </figure>`
    );
}
//We just need to change the first three lines:

function addImage(images) {
    const firstImage = images.results[0];

    responseContainer.insertAdjacentHTML('afterbegin', `<figure>
            <img src="${firstImage.urls.small}" alt="${searchedForText}">
            <figcaption>${searchedForText} by ${firstImage.user.name}</figcaption>
        </figure>`
    );
}
```
5. Code Walkthrough

6. Peek inside $.ajax()

![](./img/2.6.gif)

7. Review the Call Stack

> Look at jQuery's code and especially the jQuery.ajaxSettings.xhr function, we can see that the code is return new window.XMLHttpRequest();. So this code will return a new XHR object every time it's called (which happens every time $.ajax() is run!

![](./img/2.7.gif)

> jQuery uses a for…in loop to iterate over the data in the headers object. This can be seen on lines 9094-9096.

8. Walkthrough of .ajaxTransport

9. jQuery's Other Async Methods

![](./img/2.9.gif)

![](./img/2.9.1.gif)

10. Async with jQuery Outro

## 3. Ajax with Fetch
In this lesson, you'll use JavaScript Promises to create a fetch request and handle the returned data asynchronously. You'll also learn how to handle errors for failed requests.

1. Ajax call with the Fetch API

2. What is Fetch

> the new Fetch API utilizes Promises under the hood. If you've got a handle on how Promises work, then give yourself a pat on the back then skip down to the next section. If the word "Promises" makes you feel a little queasy and unsure of your life's future, don't panic! Breathe! Then head over to our short course on JavaScript Promises to level up your JavaScript muscles.

3. Write the Fetch Request

> The correct answers are options 2 and 3. The Fetch request takes the URL to the requested resource as the first argument, but the second argument is a configuration object. One of the options to this config object is a headers property.
One of the new additions that rode along on the coattails of Fetch is a new Headers constructor function. The headers property of a Fetch request's configuration object can either be a plain object of headers to include, or it can be a Headers object that's been built up with headers.

![](./img/3.3.gif)

> The correct answer is that the GET HTTP method is used for a Fetch request.

4. Handle The Response

![](./img/3.4.gif)
> The answer is none of the above, actually. Check below for where you can find the actual data!

5. The Response Object

> The correct answer is .blob(). .blob() will extract the image body from the response.

[article 1](https://davidwalsh.name/fetch)
[article 2](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch#Making_fetch_requests)


6. ES6 Arrow Function

![](./img/3.6.gif)

7. Display Content & Handling Errors

```javascript
fetch(`https://api.unsplash.com/search/photos?page=1&query=${searchedForText}`, {
    headers: {
        Authorization: 'Client-ID abc123'
    }
}).then(response => response.json())
.then(addImage)
.catch(e => requestError(e, 'image'));

function addImage(data) {
    debugger;
}

function requestError(e, part) {
    console.log(e);
    responseContainer.insertAdjacentHTML('beforeend', `<p class="network-warning">Oh no! There was an error making a request for the ${part}.</p>`);
}
```

8. Project Wrap-up

9. Fetch Outro

10. Course Outro

## 4. Syntax

## 5. Functions

## 6. Built-ins

## 7. Professional Developer-fu
With this massive improvement, not all browsers are able to support this new version of JavaScript. In this lesson, you'll learn about using polyfills and transpiling your ES6 JavaScript code to ES5.

## 8. IndexedDB and Caching

## 9. Introducing Web Tooling and Automation
Learn how automation and tooling can make you more productive as a developer and allow you to work more faster and more efficiently.

1. Course Intro

2. Cost Effectiveness

3. Common Sense

4.On to the course!

## 10. Productive Editing
Use keyboard shortcuts and code editor extensions to speed up your development process and help to avoid repetitive typing tasks.

## 11. Powerful Builds
Leverage the power of build tools like Gulp and Grunt to automate the process of converting your development code into streamlined production-ready code.

## 12. Expressive Live Editing
Learn how to set up your environment for live editing. Live editing will cause any connected browser to automatically reload if you change any file it's watching in your project.

## 13. How to Prevent Disasters
Learn how to use tooling to be a safety net for you as you're coding. Use it to automatically check the code you write and automatically run tests.

## 14. Awesome Optimizations
Learn how to use tooling to optimize your apps for production use. You'll learn how to concatenate, minify, and optimize your code.

## 15. Web Tooling and Automation Conclusion
You're on your way to tooling greatness. In this lesson, you'll learn about tooling to scaffold entire projects.

## PROJECT - Restaurant Reviews App — Stage 2
Build off of your existing Restaurant Reviews app to create a fully-featured app that communicates with a backend server and handles asynchronous requests.
