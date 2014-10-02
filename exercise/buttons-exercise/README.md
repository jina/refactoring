# Button Refactoring Exercise

"Buttons are the Sass community's Hello World." —Eric Suzanne (I think?) at SassConf last year

Well, it's true. They're easily refactorable, pretty much every site or app has some, and everyone understands their purpose. Plus, they can be as simple or complex as required, so there's a lot of room to play!

## Your Job

If you didn't bring your own project code to work on, or just prefer to do a pre-made exercise, your job is to refactor this button partial.



## Files and Folders

### /1-original-css-html

This folder contains some super-messy pure CSS and HTML of some buttons. There are a few types, and a disabled state button, but they have varying classnames and a lot of redundant and/or competing styles. (It was really painful to write this so badly on purpose!)

### /2-shared-scss-nesting

This folder has an empty `.scss` and `.html` file you. You'll do Steps 2, 3, & 4 in this folder and files. 

### /3-change-classes

Copy over what you have so far; in this folder you'll be editing the HTML! You'll do Step 4 here.

### /4-mixins-extends

Copy over the files you have from folder 3. This is a spot to continue to refactor or add Sass complexity; you'll do Step 5, Create Mixins here.



## Instructions

### Compiling

We recommend just using the Sass command line compilation for this project. You can do it in each folder separately so you can see the differences in your output along the way. CodeKit or similar is also recommended. If you need help with compilation just yell—or ask a tablemate!

### Steps to Refactor

1. Extract partial
2. Find repeating patterns
3. Create/extract base class/extend
4. Apply Nesting 
5. Edit HTML Classes
6. Apply Variables
7. Create Mixins

#### Step 1: Extract Partial.

If you are doing this in your own code, you'd have to find all the different places in your CSS that you had button code, and put them all into a file, and import that from your manifest. Then you want to check and make sure you didn't break anything! 

If you're doing this exercise, this step has already been done for you in folder `/1-original-css-html` by creating `buttons-original.scss` and dumping all the button CSS into it. (We don't have a manifest to import from in this exercise so we're just linking to the CSS file directly.)

I'm choosing to add `-original` to this file so that later I can make a `buttons.scss` file and import that, and then switch them on/off to make sure my new code is doing the same stuff as the old code.

There's some button HTML and some pretty ugly CSS. Poke around in it a little bit, see what's going on. Can you make a list of some of the things that are wrong with the CSS/HTML? Visually, where there are discrepancies, can you guess what was intended?

(We've grouped all the button HTML into one file for the purposes of this exercise, but in your own project that will not be the case.)


#### Step 2: Find Repeating Patterns

In folder `/2-shared-scss-nesting`, copy over the HTML. We won't touch that junk quite yet.

Look for repeating patterns or problems in the CSS file:

* selector duplication that implies an inheritance relationship
* repeating patterns relating to the colors, typography, or iconography
* complex nesting or selector chaining
* a CSS class that can function as a consistent base class
* plain ol' duplicated CSS of any type
* states (active, disabled, etc) that should be combined
* IDs or classes for JavaScript that may also have styles

#### Step 3: Create or Extract Base Class/Extend

We've created a blank `buttons.scss` file so that we can copy over clean CSS into it without getting lost in the old code. This also helps us make sure we didn't lose anything—and we can toggle the old and new CSS on and off to see if everything looks OK.

**Extracting Base Class**

First, extract a base class. Most likely it'll be `.button`. Copy over all the repeated styles that you might want all buttons to share.

> "I decided to call it `.feedback` because all of the class names in use described a type of user feedback and this class was not in use already." — Chris Eppstein, Digg refactor post

Compile your new file—now you'll probably have completely unstyled buttons. Time to mess with the HTML!

> Refactoring Tip! Delete or comment out the lines in the old styles once you remove them, to help you keep track. All that should be left are unique styles.

For now let's just add the base class to all the HTML buttons. We can clean this up even more going forward, but first let's make sure that our button styles are applying as we wanted them to.

**Creating an Extend**

If that's looking good, let's change our base class from a class to a placeholder extend.

Now you can take all the original different button classes and `@extend %button` on all of them. Remove class `button` from your HTML.

Compile and check it out—should be exactly the same.

Be sure to compare the output between when you did it with a CSS class and placeholder extend!

**Adding Unique Styles**

You can now add back in the unique styles to each individual button—applying colors, text colors, etc, to each class so that they look the same as they did before. 

#### Step 4: Apply Nesting

Figure out what you can nest inside the parent `%button`—or under each individual button class. `:hover` and `:active` states should be pretty obvious. Anything else?

Use the &#38; parent selector to nest, and don't forget you can do it three ways, depending on a) what output you want and b) what makes for the most understandable code:

    /* Output is: .feedback .test */
    .feedback {
        .test { }
    }

    /* Output is: .feedback .test */
    .text {
        .feedback & { }
    }

    /* Output is: .feedback.positive */
    .feedback {
        &.positive { }
    }


#### Step 5: Edit HTML Classes

Copy everything over into folder `/3-change-classes`. Now we're going to actually clean up that horrible HTML.

We have made a lot of good progress toward reusability and modularity, so even if the classes of the actual buttons are all inconsistent, we have done a lot. But some good search-and-replace can get us to a modular setup that will help in the future, when we want to add even more buttons.

**Naming Conventions**

Determine what naming convention works best for these buttons. Do you want to use BEM, or a primary/secondary/tertiary setup, or something else you prefer? Write out the naming convention and then create classes for it. 

Add in the unique styles again into the new classes. Now is a great time to make sure your hover, active, etc states are consistent—or exist! Be sure to nest those, if you need to.

> Refactoring Tip! Don't remove the old classnames from your CSS or HTML quite yet! You can comment them out in the CSS so they don't apply, but leave them for your reference until you're sure that the new ones are working appropriately!

Now edit the HTML of the buttons to use the new classes; make sure you make any other HTML edits that might be necessary while you're at it! Add the new classes into your CSS and you should have some much prettier code now. Be sure to check your output!

**Unique IDs or Classes**

Most likely, by looking at the HTML, we can see that the buttons had individual names that might have been used in JavaScript to make them work or track events on click. We probably don't want to get rid of those altogether.

You have a couple options:

* remove the old CSS classes from the CSS but leave them in the HTML so that the JavaScript still works on them (easiest but ugly classes still exist)
* make the old CSS classes into IDs and edit the JavaScript to use IDs instead of classes, if it's doing that (medium difficultly)
* refactor the IDs into a consistent naming scheme and edit the JavaScript (preferred, but most difficult)

Now you can remove the old class names from your CSS.


#### Step 6: Apply Variables

Now that we know our refactored classnames, how our `%extend` is working, and the unique styles are applied, let's do a pass to see what those unique styles—colors, backgrounds, icons, fonts, etc—actually are.

Assuming you already have some variables in a `colors.scss` file, you can go ahead and replace things like `#fff` with `$white`.

But now what about all the colors we have for the backgrounds, shadows, etc? How do we name these colors? `turquoise`, `turquoise-light`, `turquoise-dark`? Then we have a zillion variables for variations for the same color. Those names don't give us a lot of insight into what the colors are for. So let's take our variable naming one more level abstract.

Create variables strictly for the button colors and name them the same as our classes. For example, if my naming convention is primary/secondary:

    // Primary Buttons (Submit)
    $button_primary_background: $turquoise;
    $button_primary_color: lighten($button_primary_background,45%);

    // Secondary Buttons (Edit)
    $button_secondary_background: #993399;
    $button_secondary_color: rgb(213,121,204);

Now go back and apply those to the classes, rather than putting the hex colors directly in. You can do this for way more than colors! What about backgrounds, hover states, borders, shadows, or typography styles? Take it as far as makes sense for your buttons.

Now is a good time to fix up things like inconsistent background colors or hover colors, highlighting, borders, etc. Visual errors are much easier to fix up now, when you can automate how they change.

**Check your Output**

Be sure to check your output and make sure everything is working!

How many lines of code is your `.scss` file now? Compare to how many lines of code your original `.css` file was. I'm willing to bet you didn't save yourself that many lines of code from the original—so it's not a huge reduction in CSS file size—but the maintainability, class naming consistency, readability, and future-proofing of the code is drastically improved.

If everything looks good, congrats, you can stop here! Or you can take it one step Sassier and make a mixin to do some of the more repetitive work.

#### Step 7: Create Mixins

Copy everything over into folder `/4-mixins`.

In this—optional—step we're going to take all the redundant code in the unique button classes and make a mixin to do the hard work for us.

We're rewriting CSS properties for color, background-color, borders or box-shadows, text-shadows, and then possibly changing them again for hover states. What if we could do that in _one line_?

Create a mixin with arguments for any of the properties we want to change on the fly. Be sure to name them clearly!

Then replace your unique styles with an `@include` that contains the style values you want.

**Disabled State**

Let's assume any button can become disabled. Then we could apply a disabled class—without replacing the original classname—to any button and it would grey it out and make it not clickable.

Can you make your mixin check if the button has a disabled state? 

**Output Size for more Buttons**

When adding a mixin or an extend, I like to go back and see if it's saving me code.

Go back into the original folder with the original junky CSS and HTML. Make 5-6 more buttons. Give them each a unique class (`.button-1`, `.button-2` etc will suffice, as this is just a test) and then copy some CSS for each of them. How many more lines of code is that?

Now in your new mixin-ified Sass code, add 6 more buttons in your HTML. How many more lines of code is that in your output?

## Good Job!
