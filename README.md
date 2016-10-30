Running the application:
1. Visit: callahan417.github.io/frontend-nanodegree-mobile-portfolio
2. Click on links to visit the various project pages.
3. On the Pizzeria page:
    a. Scroll up and down to animate the background pizzas.
    b. Click or slide the pizza size slider to change the size of the foreground pizzas.

Optimization of index.html (and related CSS and JavaScript):
1. Added a media query for print.css
2. Removed unnecessary css from style.css
3. Used smaller versions of profilepic.jpg and pizzeria.jpg in img elements.
4. Added async attribute to Google Analytics script tag.
5. Moved inline script to external JavaScript file and added async attribute to tag.
6. Inlined Google Font css in index.html
7. Minified style.css and inlined in index.html.
8. Minified index.html

Optimization of Pizzeria page scrolling:
1. Calculated and used only the 5 phase values (stored in phases array) needed to reposition the pizzas. Calculations were moved outside of the loop in function updatePositions.
2. Modified loop in sliding-pizza-creating function to create pizzas only if the element top is less than the height of the viewport. 24 pizzas are created on my laptop.
3. Added "backface-visibility: hidden" to css class 'mover'.
4. Modified loop in updatePositions function to change pizza position only if it will be visible on the screen (i.e. within the viewport).
5. Used style.transform and translateX to change position of pizzas instead of style.left in function updatePositions.
6. Made 'items' a global variable and moved its assignment out of updatePositions and into anonymous function called when DOM is loaded. Used getElementsByClassName instead of querySelectorAll to query DOM.
7. Used requestAnimationFrame to invoke function updatePositions. Only called requestAnimationFrame if it was not already requested (i.e. with "animating" global boolean variable).

Optimization of pizza re-sizing:
1. Deleted function determineDx.
2. Used switch statement at beginning of function resizePizzas to set the variable newWidth to 25%, 33.33%, or 50% (for small, medium, and large pizzas, respectively).
3. Set the width of each pizza element to the value of newWidth.
4. Outside of the for loop, used getElementsByClassName to create an array of all DOM elements with the class "randomPizzaContainer".




## Website Performance Optimization portfolio project

Your challenge, if you wish to accept it (and we sure hope you will), is to optimize this online portfolio for speed! In particular, optimize the critical rendering path and make this page render as quickly as possible by applying the techniques you've picked up in the [Critical Rendering Path course](https://www.udacity.com/course/ud884).

To get started, check out the repository and inspect the code.

### Getting started

####Part 1: Optimize PageSpeed Insights score for index.html

Some useful tips to help you get started:

1. Check out the repository
1. To inspect the site on your phone, you can run a local server

  ```bash
  $> cd /path/to/your-project-folder
  $> python -m SimpleHTTPServer 8080
  ```

1. Open a browser and visit localhost:8080
1. Download and install [ngrok](https://ngrok.com/) to the top-level of your project directory to make your local server accessible remotely.

  ``` bash
  $> cd /path/to/your-project-folder
  $> ./ngrok http 8080
  ```

1. Copy the public URL ngrok gives you and try running it through PageSpeed Insights! Optional: [More on integrating ngrok, Grunt and PageSpeed.](http://www.jamescryer.com/2014/06/12/grunt-pagespeed-and-ngrok-locally-testing/)

Profile, optimize, measure... and then lather, rinse, and repeat. Good luck!

####Part 2: Optimize Frames per Second in pizza.html

To optimize views/pizza.html, you will need to modify views/js/main.js until your frames per second rate is 60 fps or higher. You will find instructive comments in main.js.

You might find the FPS Counter/HUD Display useful in Chrome developer tools described here: [Chrome Dev Tools tips-and-tricks](https://developer.chrome.com/devtools/docs/tips-and-tricks).

### Optimization Tips and Tricks
* [Optimizing Performance](https://developers.google.com/web/fundamentals/performance/ "web performance")
* [Analyzing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/analyzing-crp.html "analyzing crp")
* [Optimizing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/optimizing-critical-rendering-path.html "optimize the crp!")
* [Avoiding Rendering Blocking CSS](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css.html "render blocking css")
* [Optimizing JavaScript](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/adding-interactivity-with-javascript.html "javascript")
* [Measuring with Navigation Timing](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/measure-crp.html "nav timing api"). We didn't cover the Navigation Timing API in the first two lessons but it's an incredibly useful tool for automated page profiling. I highly recommend reading.
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/eliminate-downloads.html">The fewer the downloads, the better</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer.html">Reduce the size of text</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization.html">Optimize images</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching.html">HTTP caching</a>

### Customization with Bootstrap
The portfolio was built on Twitter's <a href="http://getbootstrap.com/">Bootstrap</a> framework. All custom styles are in `dist/css/portfolio.css` in the portfolio repo.

* <a href="http://getbootstrap.com/css/">Bootstrap's CSS Classes</a>
* <a href="http://getbootstrap.com/components/">Bootstrap's Components</a>
