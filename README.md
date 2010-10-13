MooSwipe
========

A MooTools port of Andreas Waltl's [jQuery TouchWipe](http://www.netcu.de/jquery-touchwipe-iphone-ipad-library).  Gives easy access to left and right swipe events for iOS and other touch devices.

License: MIT-style.

How to use
----------

	new MooSwipe(el, options);

- el: String id of the element, an element node, or any object with a toElement method.
- options: Options and events.

Typical usage:

	new MooSwipe('swipe-id', {
		onSwipeLeft: function() {
			// Code to execute on left swipe
		},
		onSwipeRight: function() {
			// Code to execute on right swipe
		},
		onSwipe: function(direction) {
			// Code to execute on any swipe
		}
	});

Options
-------

- tolerance (int): The number of pixels your finger must move to trigger a swipe event.  Defaults to 20.
- preventDefaults (bool): Prevent the default action during the touchMove event?  Defaults to true.

Example:

	new MooSwipe('swipe-id', {
		tolerance: 50,
		preventDefaults: false,
		onSwipeLeft: ...,
		onSwipeRight: ...,
		onSwipe: ...
	});

Events
------
- swipeLeft
- swipeRight
- swipe: passed a string indicating the direction, 'left' or 'right'

Event functions can be included in the MooSwipe initialization:

	new MooSwipe('swipe-id', {
		onSwipeLeft: function() { ... },
		onSwipeRight: function() { ... },
		onSwipe: function(direction) { ... }
	});

Or added afterwards:

	var swipe = new MooSwipe('swipe-id');
	swipe.addEvent('swipeLeft', function() { ... });
	swipe.addEvent('swipeRight', function() { ... });
	swipe.addEvent('swipe', function(direction) { ... });