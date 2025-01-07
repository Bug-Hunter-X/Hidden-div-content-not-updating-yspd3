# Uncommon HTML Bug: Hidden div content not updating
This repository demonstrates an uncommon bug in HTML where attempting to update the innerHTML of a div element after setting its display style to "none" does not reflect the changes when the element's display style is set back to its default.  The solution involves checking the display property before updating the content. 

## Bug Description
The primary issue lies in manipulating a hidden element's content.  Standard practice is to modify the content, and then adjust the visibility. Setting `display: none;` prevents the browser from rendering the content, which can cause unintended issues when trying to subsequently update that content.  Once the content is modified and then the `display` property is modified back to `block` or `inline`, the changes will not render unless the changes are done prior to setting the `display` property to `none`. 

## How to Reproduce
1. Clone this repository.
2. Open `bug.html` in a web browser.
3. Click the "Click Me" button.
4. Observe that the div content does not update even after the display property is set back to the default which will be `block`.

## Solution
The solution involves checking the display property before updating the content. If the element is hidden, it is made visible before modifying the content. Check the `bugSolution.html` file for the corrected code.