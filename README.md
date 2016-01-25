# optimizing portfolio page.
As web applications become increasingly interactive and accessed on a variety of devices there are a variety of opportunities in
which performance issues can hinder the user experience. This project presents a number of those 
performance issues and provides an opportunity to showcase your skills in identifying and optimizing web applications.
This is the link of the portfolio page https://cdn.rawgit.com/Nooria/udportfolio-optimize.github.io/master/index.html

**In this project I optimize few things to achieves a target PageSpeed score:**

- Added media query for print.css.
- Removed link to google web font since I found it was not necessary.
- Resized and Compressed pizzeria_115px.jpg and profilepic.jpg images for the front page.
- Inlined the style.css code.
- Added async attribute for analytics.js since this is not needed for
rendering.
- Reduced the number of pizzas in main.js to 24 so render at a time.
- In ```function changeSliderLabel(size) {
      switch(size) {
      case "1":
      document.querySelector("#pizzaSize").innerHTML = "Small";
      return;
      case "2":
      document.querySelector("#pizzaSize").innerHTML = "Medium";
      return;
      case "3":
      document.querySelector("#pizzaSize").innerHTML = "Large";
      return;
      default;
      console.log("bug in changeSliderLabel");
      }
     }
      changeSliderLabel(size);
      function determineDx (elem, size) {
      var oldwidth = elem.offsetWidth;
      var windowwidth = document.querySelector("#randomPizzas").offsetWidth;``` 
Change all the ```document.querySelector``` to ```document.getElementById()``` so the Web API call will be faster.
Reference
https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById

- In  ``` var dx = determineDx(document.querySelectorAll(".randomPizzaContainer")[i], size);``` change the 
```document.querySelectorAll()``` to ```document.getElementsByClassName()``` 
so the Web API call will be faster. References
https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByClassNamehttps://github.com/udacity/fend-office-hours/tree/master/Web%20Optimization/Effective%20Optimizations%20for%2060%20FPS

- ```document.querySelectorAll(".randomPizzaContainer")[i].style.width = newwidth;```
I create a local variable to save document.getElementsByClassName('randomPizzaContainer') outside the loop (e.g. var container = document.getElementsByClassName('randomPizzaContainer')), so the DOM is not explicitly touched in every iteration!

/** Outside the for statement/loop*/
var container =  document.getElementsByClassName('randomPizzaContainer');
var dx = determineDx(container[0], size);
var newwidth = (container[0].offsetWidth + dx) + 'px';
// Other Statements;

/** Inside the for statement/loop*/
for (/** expressions */) {
    container[i].style.width = newwidth;
}
- ```  var items = document.querySelectorAll('.mover');``` change it to ```document.getElementsByClassName()``` so the Web API call will be faster. References
https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByClassNamehttps://github.com/udacity/fend-office-hours/tree/master/Web%20Optimization/Effective%20Optimizations%20for%2060%20FPS
