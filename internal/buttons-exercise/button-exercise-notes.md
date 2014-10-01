# Button Refactoring Exercise Notes

### Steps to Refactor

1. Extract partial
2. Find repeating patterns
3. Create/extract base class/extend
4. Apply Nesting 
5. Edit HTML Classes
6. Apply Variables
7. Create Mixins

## Step 1: Extract Partial.

### Can you make a list of some of the things that are wrong with the CSS/HTML?

Visual issues:

* Save's drop-shadow is grey, not colored
* Sign Up has wider letterspacing
* Edit/Edit hover are different font weights
* Edit button and Cancel link change to not bold on hover
* Delete has no hover state

CSS issues:

* Some rgba, some hex value colors
* Classnames have no consistent naming convention
* Save button has 2 color values
* Inconsistent capitalization in both HTML and CSS
* Inconsistent margin/spacing
* Edit buttons use height/width (and are different), use border-box
* Other buttons use padding to create size
* only Sign Up uses line-height for size
* Inconsistent selector ordering
* Did I mention the redundancy?
