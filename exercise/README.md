# Refactoring Exercise

You'll be choosing a module in your project and refactoring it following the 1-6 steps of how to refactor a module.

If you didn't bring your own project code to work on, or just prefer to do a pre-made exercise, you can do the sample button module in the `/buttons-exercise` folder [/buttons-exercise](https://github.com/jina/refactoring/tree/master/exercise/buttons-exercise).





## Instructions

### Compiling

We recommend just using the Sass command line compilation for this project. You can do it in each folder separately so you can see the differences in your output along the way. CodeKit or similar is also recommended. If you need help with compilation just yell—or ask a tablemate!

## Recommendations

We highly recommend copying files at certain steps so you can see your progress later and remember what you did! Whether you save them out at certain states to a new folder, or copy and rename files, that's up to you.

## Steps to Refactor

1. Extract partial
2. Find repeating patterns
3. Create/extract base class/extend
4. Apply Nesting 
5. Edit HTML Classes
6. Apply Variables
7. Create Mixins

#### Step 1: Extract Partial.

Find all the different places in your CSS that you have code for this module.

Create a new `.scss` file—lets call it `[MODULENAME]-original.scss` and dump all that CSS into it. Import that from your manifest.

I'm choosing to add `-original` to this file so that later I can make a `[MODULENAME].scss` file and import that, and then switch them on/off to make sure my new code is doing the same stuff as the old code.

Now check and make sure you didn't break anything! Sometimes import order can cause specificity problems, so it's worth taking some time to look at all the places you know this module exists on your site/app to see if it's still working. Yes, that's tedious, but it'll save you a lot of headache later.

#### Step 2: Find Repeating Patterns

Look for repeating patterns or problems in the CSS file:

* selector duplication that implies an inheritance relationship
* repeating patterns relating to the colors, typography, or iconography
* complex nesting or selector chaining
* a CSS class that can function as a consistent base class
* plain ol' duplicated CSS of any type
* states (active, disabled, etc) that should be combined
* IDs or classes for JavaScript that may also have styles

#### Step 3: Create or Extract Base Class/Extend

Now create your new `[MODULENAME].scss` file so that we can copy over clean CSS into it without getting lost in the old code. This also helps us make sure we didn't lose anything—and we can toggle the old and new CSS on and off to see if everything looks OK.

**Extracting Base Class**

First, extract a base class. Determine what a shared class name might be and copy over all the repeated styles that you might want all buttons to share.

> "I decided to call it `.feedback` because all of the class names in use described a type of user feedback and this class was not in use already." — Chris Eppstein, Digg refactor post

For now we're going to add that base class to some/all of the places this module exists in our HTML. This is a test step, to make sure everything applies OK. We'll clean this up even more going forward.

**Creating an Extend**

If that's looking good, let's change our base class from a class to a placeholder extend.

If you have individual classes (for example, generic button base class versus unique button classes), apply the `@extend %[MODULE]` on all of them. Compile and check it out—should be exactly the same.

Be sure to compare the output between when you did it with a CSS class and placeholder extend!

**Adding Unique Styles**

You can now add unique styles to each module that requires it—colors, backgrounds, icons text colors, etc, to each class so that they look the same as they did before. 

#### Step 4: Apply Nesting

Figure out what you can nest inside the parent `%MODULE`—or under each individual button class. For clickable elements, `:hover` and `:active` states should be pretty obvious. Anything else?

For some modules, you may need to _remove_ nesting—if you're editing Sass, perhaps things are nested in so far you want to refactor that **out**.

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

Now we're going to actually clean up any HTML that we need to.

We have made a lot of good progress toward reusability and modularity, so even if the classes of the actual individual modules are all inconsistent, we have done a lot. But some good search-and-replace can get us to a modular setup that will help in the future, when we want to add even more of the same module.

**Naming Conventions**

Determine what naming convention works best for this module. Do you want to use BEM, or a primary/secondary/tertiary setup, semantic names, or something else you prefer? Write out the naming convention and then create classes for it. 

> Refactoring Tip! Don't remove the old class names from your CSS or HTML quite yet! You can comment them out in the CSS so they don't apply, but leave them for your reference until you're sure that the new ones are working appropriately!

Now edit the HTML of the buttons to use the new classes; make sure you make any other HTML edits that might be necessary while you're at it! Add the new classes into your CSS and you should have some much prettier code now. Be sure to check your output!

**Unique IDs or Classes**

If your module has individual class names/IDs that might have been used in JavaScript to make them work or track events on click, you probably don't want to get rid of those altogether.

You have a couple options:

* remove the old CSS classes from the CSS but leave them in the HTML so that the JavaScript still works on them (easiest but ugly classes still exist)
* make the old CSS classes into IDs and edit the JavaScript to use IDs instead of classes, if it's doing that (medium difficultly)
* refactor the IDs into a consistent naming scheme and edit the JavaScript (preferred, but most difficult)

Now you can remove the old class names from your CSS.


#### Step 6: Apply Variables

Now that we know our refactored class names, how our `%extend` is working, and the unique styles are applied, let's do a pass to see what those unique styles—colors, backgrounds, icons, fonts, etc—actually are.

Your module may just use existing variables from `colors.scss` or your grid or what not. 

It might also be worthwhile to create variables strictly for your module.

For example, if you have a button module with classes `.button-primary`, `.button-secondary`, etc, you might want to make variables like so:

    // Primary Buttons (Submit)
    $button_primary_background: $turquoise;
    $button_primary_color: lighten($button_primary_background,45%);

    // Secondary Buttons (Edit)
    $button_secondary_background: $purple;
    $button_secondary_color: lighten($button_secondary_background,45%);

Or you could apply grid, typography, or sizing variables, depending on what your module is.

Now go back and apply those variables!

Now is a good time to fix up things like inconsistent background colors or hover colors, highlighting, borders, etc. Visual errors are much easier to fix up now, when you can automate how they change.

**Check your Output**

Be sure to check your output and make sure everything is working!

I'm willing to bet you didn't save yourself that many lines of code from the original—so it's not a huge reduction in CSS file size—but the maintainability, class naming consistency, readability, and future-proofing of the code is drastically improved.

If everything looks good, congrats, you can stop here! Or you can take it one step Sassier and make a mixin to do some of the more repetive work.

#### Step 7: Create Mixins

In this—optional—step we're going to take all the redundant code in our unique classes and make a mixin to do the hard work for us. Some modules really benefit from this; in others, there's really no point. You have to determine for yourself if it's valuable to you.

If you're rewriting CSS properties for multiple unique versions of a module—such as color, background-color, borders or box-shadows, hover states, etc—you might want to make a mixin, so you can change all those styles in _one line_?

Create a mixin with arguments for any of the properties we want to change on the fly. Be sure to name them clearly!

Then replace your unique styles with an `@include` that contains the style values you want.

**Output Size**

When adding a mixin or an extend, I like to go back and see if it's saving me code.

Check on your old output and your new. In some cases you'll save yourself tons of lines of CSS by using a mixin (compared to adding more CSS or unique lines) but sometimes you won't. Make sure your mixin is valuable to you!

## Good Job!
