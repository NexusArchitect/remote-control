# Remote Slide
Remote Slide is a tool to control your HTML5 presentation slides remotely

## The goal
The idea of Remote Slide is provide a way to control the slides of a HTML5 presentantion, remotely.
Your phone is your remote control!

## Dependencies
* [nodejs](http://nodejs.org)
* [socket.io](http://socket.io)
* A modern Web Browser with WebSockets support [can i use](http://caniuse.com/#search=websockets) in your desktop
* A modern Web Browser with WebSockets support [can i use](http://caniuse.com/#search=websockets) in your phone

## How it works
Remote Slide is based on [WebSockets](https://developer.mozilla.org/en-US/docs/WebSockets), so you may have a good and modern browser, like Firefox, Chrome or Opera.
The phone send a message through WebSockets to the server.
The server receive the message as an action that must be executed, like 'next' or 'previous'.
This action are emited to the HTML5 presentation.

## How to install
For while, you need to install manually :(

First, if you don't have node, you must to install. Google it, if you don't know how.
Intall sockt.io:
```cli
npm install socket.io
```

## How to use
Run app.js:
```cli
node app.js
```
The server will be available at port 81 [http:localhost:81](http:localhost:81), but you can change if you want.

Now, you need to add 2 JavaScript libraries to your HTML5 presentation:
```html
<script src="http://localhost:81/socket.io/socket.io.js"></script>
<script src="path/to/remote-slide.js"></script>
```

You're almost ready to start the presentation!
Add this code to your presentation file
```javascript
var remote = new RemoteSlide();
remote.connect('http://localhost:81');
remote.on('next', function() {
	// Your method to move to the next slide
});

remote.on('previous', function() {
	// Your method to move to the previous slide
});
```
