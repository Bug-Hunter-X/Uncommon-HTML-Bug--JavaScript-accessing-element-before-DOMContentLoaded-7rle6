# Uncommon HTML Bug: Premature JavaScript DOM Access

This repository demonstrates a common yet subtle bug in HTML where JavaScript attempts to manipulate a DOM element before the element is fully loaded into the DOM.  This often leads to a `TypeError: Cannot set property 'innerHTML' of null` error.

## Problem

The `bug.html` file contains a `<div>` element with the ID `myDiv`.  A JavaScript script attempts to change the `innerHTML` of this div.  However, the script executes *before* the browser has finished parsing and rendering the HTML, resulting in the `myDiv` element being `null` at the time of access.

## Solution

The `bugSolution.html` file fixes this issue by using the `DOMContentLoaded` event listener. This ensures that the JavaScript code executes only after the HTML document is fully parsed and the DOM is ready.