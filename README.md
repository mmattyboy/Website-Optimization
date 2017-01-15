Describe all steps to run app.
Summarize optimizations made to index.html and views/js/main.js
In order to access the not yet live website of the pizzeria and course developer (index.html) by Cameron Pitman, the user must acquire download of any web browser and the access to the internet. 

In the pizzeria website, Cameron offers pizza for order and delivery. The user may choose any toppings they would like to be added to the pizza.

The optimization in index.html include the compression and inlining the styles in css styles, this allows the browser to skip rendering the CSSOM. Furthermore, a compression website was used to compress images into small sizes. The pizza picture was also resized to 100 x 100. Instead of getting pictures from a website, it was downloaded into the img file and compressed in size. 

The optimization for pizza.html involve changes in main.js. The javascript file was what affected the jank when a timeline was loaded in developer tools. Specifically, the function updatePostion (Line 522) was causing a force layout. The reason for this cause was the scrollTop property. This value is changed whenever scrolling occurs. In the case of a for loop, it causes the change in layout everytime. To fix the bottleneck, a variable was declared outside of the for loop and the variable was then assigned to the pizza mover. Throughout the docment, the selectors can be specific by using getElementByID or getElementsByClassName instead of querySelector for improvement. Next, the improvement to scroll fps was on the last eventListener (Line 552). There were much less than 200 pizzas on the screen at each given moment during scrolling. The for loop specifies a value of i < 200 (for 200 pizzas). This caused the slow in fps. For the fix, it was found that the total number of pizzas can be determined by using the screen.height / scrolling row height(s) * col.

In another function in main.js, the changePizzaSizes was also causeing a lower fps due to the unnecessary function, determineDx() and sizeSwitcher. The fix was to change the pizza sizes directly by assigning it to a % value based on which size was selected on the slider.

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
