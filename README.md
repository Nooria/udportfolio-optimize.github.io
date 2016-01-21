# optimizing portfolio page.
As web applications become increasingly interactive and accessed on a variety of devices there are a variety of opportunities in
which performance issues can hinder the user experience. This project presents a number of those 
performance issues and provides an opportunity to showcase your skills in identifying and optimizing web applications.

**In this project I optimize few things to achieves a target PageSpeed score:**

- Added media query for print.css.
- Removed link to google web font since I found it was not necessary.
- Created a smaller pizzeria_115px.jpg for the front page.
- Inlined the style.css code.
- Added async attribute for analytics.js since this is not needed for
rendering.
- Reduced the number of pizzas in main.js to 20 so render at a time.
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
      default:
      console.log("bug in changeSliderLabel");
      }
     }
      changeSliderLabel(size);
      function determineDx (elem, size) {
      var oldwidth = elem.offsetWidth;
      var windowwidth = document.querySelector("#randomPizzas").offsetWidth;``` 
Change all the ```document.querySelector``` to ```document.getElementById()``` so the Web API call will be faster.

- In  ``` var dx = determineDx(document.querySelectorAll(".randomPizzaContainer")[i], size);``` change the 
```document.querySelectorAll()``` to ```document.getElementsByClassName()``` 
so the so the Web API call will be faster.

