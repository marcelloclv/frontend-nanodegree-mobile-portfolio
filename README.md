## Website Performance Optimization portfolio project

### Setup

To setup this project, you just need to add all files to the server and open the pages on the browser

This project has been hosted and is accessible from the following addresses:

* <a href="http://marcellovalenca.com/tests/portfolio/index.html">Portfolio (`index.html`)</a>
* <a href="http://marcellovalenca.com/tests/portfolio/views/pizza.html">Pizzeria (`views/pizza.html`)</a>

### Optimizations

####Part 1: Optimizing PageSpeed Insights score for index.html

* Compressed `profilepic.jpg` - from 14KB to 2.17KB
* Compressed `pizzaria.jpg` - from 2.25MB to 37KB (normal) and 4KB (small). The small size is used in the Portfolio, and the normal size is used in the Pizzeria
* Removed web fonts css reference, as it had a huge impact on performance and was not important for the page's customization
* Added `media="screen"` for `style.css` and `media="print"` for `print.css` to avoid unnecessary loads
* Added async to `analytics.js`, as it is not necessary to the main functionalities of the page
* Changed server settings to compress all content using gzip

####Part 2: Optimizing Frames per Second in pizza.html

* Removed Forced Synchronous Layout problem inside `main.js` changing function `resizePizzas`. Time to resize pizzas is now less than 5 ms using the pizza size slider on the `views/pizza.html` page
* Removed Forced Synchronous Layout problem inside `main.js` changing function `updatePositions`. When scrolling, `views/pizza.html` now render with a consistent frame-rate at `60fps`

### To do

* Leverage browser caching - I did not manage to leverage browser caching on the server I am using to host the pages

## Original project specification

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
