### What kind of tasks are normally handled in the back end, and which are more usually handled in the front end? Why?

**front-end** development is what is used to create the visual display that the end user of a website experiences.

The front end typically includes the HTML, CSS and JavaScript that creates pages, menus, buttons and everything else that forms the basis of what the user sees in his or her Web browser.

**Back-end** development is what makes the presentation of front-end development possible.


**As an example of how front-end and back-end systems work together**

 When a user visits the website and attempts to access a certain page, he or she will be asked to log in; that login information will be documented via a database lookup, and then the back-end application communicates with the front end to display the proper page to the use
![example](http://www.prudens.com/images/ebusfrontbackend2.gif)


<br>
<br>

## The pros and cons of each approach

##### So there you have it. Those are the main differences between server-side and client-side rendering. Only you the developer can decide which option is best for your website or application.
##### Below is a quick breakdown of the pros and cons for each approach:

#### Server-side pros:
* Search engines can crawl the site for better SEO.
2. The initial page load is faster.
3. Great for static sites.

#### Server-side cons:
* Frequent server requests.
2. An overall slow page rendering.
3. Full page reloads.
4. Non-rich site interactions.

#### Client-side pros:
* Rich site interactions
2. Fast website rendering after the initial load.
3. Great for web applications.
4. Robust selection of JavaScript libraries.

#### Client-side cons:
* Low SEO if not implemented correctly.
2. Initial load might require more time.
3. In most cases, requires an external library.


## Alternative back-end technologies
#### Which other technologies (programming languages and servers) might be used instead of Node on the back end?
* # PHP
**PHP** is maybe the most popular language for web development. It’s pre-installed in almost all hosting services. It has a syntax very similar to C and Java.

* # JAVA
like PHP,** JAVA** is one the “big boys” in the field of programming languages.solid and scalable , Java always trying to stay on top of the game.

* # Python
**Python** is a language that uses a simpler syntax than PHP. It’s designed to have a very readable code, and for that reason is very recommended to learn programming.

* # Ruby
<img src="https://www.layalina.com/site-images/sites/default/files/prod/article/e/7/216456/6d877355100832c0f6da7db9b9380df68fa9c940-200916081012.jpg?preset=v3.0_620XDYN&save-png=1&rnd=051915122014&croptop=1" alt="Ruby" height="200" width="200">

**Ruby** is designed to be a fun language. It has a focus on simplicity and productivity with an elegant syntax.
In Ruby everything is an object, and that’s interesting because it encourages to the programmer to think this way when developing.

### What are some of the pros and cons of using Node?

| Pros        | Cons           |
| ------------- |:-------------:|
| Uses JavaScript, which is easy to learn.      | Dealing with relational database is a pain if you are using Node. |
| Share the same piece of code with both server and client side.      | Every time using a callback end up with tons of nested callbacks.|
| npm, the Node packaged modules has already become huge, and still growing. | Unstable API: Node needs frequent changes to your codebase to keep things running on the latest version      |
|FAC team loves it :D | -

### Node environment vs Browser environment

Node and web browsers, both executes JavaScript, but Node does that in server side and browsers in client side. Node uses the same JavaScript engine which is the backbone of Chrome, but still we can find few differences between Node and Browser.

| Node          | Browser           |
|-------------  |-------------|
| Ofcourse Node doesn’t have “document” object also, cause it never have to render anything in a page.      | “document”, which is also another predefined global variable in browsers, has the html which is rendered. |
| Node has “global”, which is a predefined global object. It contains several functions that are not available in browsers, cause they are needed for server side works only.     | Browsers may have an object named “global”, but it will be the exact one as “window     |
| “require” object is predefined in Node which is used to include modules in the app.| Browsers don’t have “require” predefined. You may include it in your app for asynchronous file loading.|


### How to write a JavaScript package for both Node and the browser

  * vanilla JavaScript
  ``` JavaScript
  if (process.browser) {
  module.exports = function (string) {
    return btoa(string);
  };
} else {
  module.exports = function (string) {
    return Buffer.from(string, 'binary').toString('base64');
  };
}
  ```


   * [node-browser-resolve](https://github.com/defunctzombie/node-browser-resolve) is a specification for a ```browser``` field inside of ```package.json```, which can be used to define modules that should be swapped out when building for the browser.

  ``` json
  {

    "browser": {
      "./index.js": "./browser.js"
    }
  }

  ```

  And then separate the functions into two different files, index.js and browser.js:

  ``` JavaScript
  // index.js
  module.exports = function (string) {
    return Buffer.from(string, 'binary').toString('base64');
  };
  ```

  ``` JavaScript
  // browser.js
  module.exports = function (string) {
    return btoa(string);
  };
  ```
