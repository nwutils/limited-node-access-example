# limited-node-access-example

Example of a project with an iframe that has limited access to Node.js in NW.js


**Two possible approaches:**

* `window.postMessage` ([MDN](https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage)) - Allows communication between a page and a pop-up it spawned, or between a page and an iframe embedded within it.
* Running a local webserver with custom routes that can be hit by any page. This has the security vulnerability of other applications running on the system being able to hit these routes too. So depending on what actions the routes perfom this could be bad, or not a big deal.
  * When embedding a page in an iframe for example, the URL used could have a one-time unique generated security token.
  * `<iframe src="http://locahost:8080/page.html?token=123456789abcdef0"></iframe>`
  * Then both the parent and the child would know the one-time token, and the custom routes would only execute if the matching token was passed in. Increasing difficulty for attack vectors.

Pull Requests welcome to demo these approaches.
