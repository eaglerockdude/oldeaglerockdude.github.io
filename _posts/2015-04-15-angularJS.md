---
layout: post
title: angularJS
category: angular
---

<div class="message">
  <cite> "It's tax day..my printer ran out of ink as usual...oh yes...angular!..." </cite>
</div>

I have delved some with Handlebars, Mustache..well...I get them confused..they all have the mustaches right?  Sometimes I think
somewhere in the GIT universe there is this one giant repo from which everything is forked.  Until I find it I will continue looking at
trees in the forest.

I have changed gears to so speak.  So many javascript things of interest to learn, but Angular to me looks the most promising right now.
I will keep notes here on what i learn about angular and javascript.

The starting point if setting up angular:

{% highlight javascript linenos %}

// MODULE  definition
var angularApp = angular.module('angularApp', []);

// CONTROLLER definition
angularApp.controller('mainController', ['$scope', function ($scope) {

}]);

{% endhighlight %}

## Terminology
- ng-app  (directive attaches application module to the page )

- ng-controller   (directive attaches a controller function to the page)

- ng-show = "attribute" (directive)

- ng-hide = "attribute"  (directive)

- ng-repeat = "product in store.products"  (example only but gives us an EACH method for an array)

###Expressions:

Statements or conditions in between {{ }}..for example, a boolean field that evaluates to true or false.

- AngularJS expressions are written inside double braces: {{ expression }}.
- AngularJS expressions binds data to HTML the same way as the ng-bind directive.
- AngularJS will "output" data exactly where the expression is written.
- AngularJS expressions are much like JavaScript expressions: They can contain literals, operators, and variables.

> We are living in the future
> so our present it our past.
