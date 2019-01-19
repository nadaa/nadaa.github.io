---
published: false
---
Understanding how browsers work can enhance frontend development, it is also critical part to speedup page loading and applying optimization techniques.
Browsers are compilers, they are built using c++. They are compilers as they can understand the language of webpage and represent it in different forms(e. DOM tree, cssDom). Most browsers by default can process html and images, with a posibility to install extension to accomidate other data types.

Browsers regardless of their types(firefox, chrome, opera, IE,..) combine vaious layers as shown bellow:
![](https://www.html5rocks.com/en/tutorials/internals/howbrowserswork/layers.png)

## Components
 - user interface : the starting point when the user requesting a web resource by the url.
 - Browser Engin :
 - Rendering Engine:
 - Networking:
 - UI backend:
 - Javascript interpreter:
 - Data persistence:
 


How Rendering Engine works

Parsing html

## Workflow
- traverse html
- divide it into tokens
- tokens are converted to nodes
- connecting nodes construct the DOM(document object model)
