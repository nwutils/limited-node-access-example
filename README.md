# limited-node-access-example

Example of a project with an iframe that has limited access to Node.js in NW.js


Two possible approaches:

* `window.postMessage` ([MDN](https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage)) - Allows communication between a page and a pop-up it spawned, or between a page and an iframe embedded within it.
* Running a local webserver with custom routes that can be hit by any page. This has the security vulnerability of of other applications running on the system being able to hit these routes too. So depending on what actions the routes perfom this could be bad, or not a big deal.
