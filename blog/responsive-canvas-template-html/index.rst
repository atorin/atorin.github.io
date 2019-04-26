.. title: A responsive html template for drawing on a canvas
.. slug: responsive-canvas-template-html
.. date: 2019-04-26 15:00:00 UTC+01:00
.. tags: html, canvas, template
.. category: 
.. link: 
.. description: "How to build a responsive drawing canvas in html"
.. type: text

I recently built a `handwriting recognition system
<https://screebo.herokuapp.com>`_ that works in the browser. As you might
imagine, the main component of the page, beside the machine learning model in
the background, is the ability to draw a character in the browser. 

In order to do that, you need to use the `<canvas>` element in html. Long story
short, I created a `template
<https://github.com/atorin/templates/tree/master/html-js>`_ that you can freely
use and adapt to your needs.   

.. figure:: http://www.albertotorin.it/blog-files/canvas.gif
   :alt: Drawing a smile in a canvas
   :width: 344 px
   :align: center


.. TEASER_END

There are many helpful resources out there, but none that I could find had a
complete template that worked both on desktop and mobile. 

Implementing a drawing element in your html page is not difficult. Of course,
you need a bit of JavaScript magic to dynamically change the page, but it's
just a few lines of code. Here are the main ingredients:

- a `<canvas>` element: as the name suggests, this is where the drawing will be
  happening;
  
- a few event listeners that check for the main mouse events (mouse down, mouse
  move, mouse up) and touch screen events;

- a call back function that determines the position of the mouse and draws a
  line when the mouse moves inside the canvas while the user is clicking;

- a button to clear the drawing. 

As you can see, it is not much work, but it's always nice to start from a
template instead of a blank page. So, feel free to use the `template I created
<https://github.com/atorin/templates/tree/master/html-js>`_ and please submit
pull requests if you find bugs! 

Some useful resources
=====================

- The `official documentation page on canvas
  <https://www.w3schools.com/html/html5_canvas.asp>`_

- Dealing with `touch events in a canvas
  <http://bencentra.com/code/2014/12/05/html5-canvas-touch-events.html>`_
