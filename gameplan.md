
# Refactoring Gameplan Doc:

## Goal

Every attendee leaves with a game plan of how they would refactor their app. What are my next steps, order of operations,  potential tools to look into.


## Survey/Questionnaire

_Before the workshop starts, send out this as a digital poll; we can use survey responses for how much in depth we go, and also general information._

http://bit.ly/cya-refactoring



## Handout for Attendees


[ ] I am already using Sass in my project
[ ] I am not using Sass and need to install it with: _______________

I am using... 
    [ ] .css and I need to convert it to [ ] .scss [ ] .sass.
    [ ] .scss and I like it.
    [ ] .scss and I want to convert it to [ ] .sass.
    [ ] .sass because I hate brackets

To import my Sass files I need to
    [ ] create an application.scss manifest file
    [ ] break up my existing files and import them
    [ ] make sure I don't alter my existing CSS output order
    [ ] reorganize/regroup my files/folders

I need to make variables and helpers for...
    [ ] Colors
    [ ] Typography
    [ ] CSS3
    [ ] Clearfix/Floats
    [ ] Grids
    [ ] Buttons
    [ ] I need to create other variables for: _________________________________
    [ ] I'm using Compass, Bourbon, Foundation, Bootstrap, etc

    I have
        [ ] a zillion color/type declarations and need to create variables and do an intensive find-and-replace
        [ ] some defined variables that aren't consistently used
        [ ] a defined config/variables stylesheet that needs updating
        [ ] well-organized variables/helpers that need better documentation

I need to have more abstraction because I need...
    [ ] to have variables names that are more robust
    [ ] to be able to create themes
    [ ] lots of UI states via JavaScript
    [ ] to have an easily editable settings/configuration file
    [ ] to keep my functions/helpers out of my styles
    [ ] more consistent responsive mixins

    I'll probably abstract my variables with a naming convention like
        [ ] primary/secondary/tertiary
        [ ] module-based e.g button-*, header-*, font-*
        [ ] color schemed

    [ ] I need to make a settings/config file.
        Notes on a good setup:  ____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________

My CSS is [ ] in one gigantic CSS file [ ] in page-based files [ ] in invididual modules but could be better [ ] perfect.

    I need to break out the following into individual Sass files:
      [ ] vendor and third party libraries
      [ ] frameworks like Foundation or Bootstrap
        [ ] I am or plan to use something like Bower
      [ ] configuration or settings
      [ ] variables like colors, type, themes
      [ ] grids
      [ ] helpers and mixins
      [ ] tools and testing mixins
      [ ] IE or responsive styles, if you keep them seperate
      [ ] global base/body styles
      [ ] reusable components - icons, buttons, avatars, comments
      [ ] styled components — reusable components styled for individual pages
      [ ] one-off components that are only used on one page/area

      I have styles that need to be called separately from the manifest import, because they're...
        [ ] responsive stylesheets
        [ ] IE or browser-specific
        [ ] for modernizr or fallback related
        [ ] themes for certain sites or sections

[ ] It is time for a break.

My CSS is organized into modules [ ] by individual files/groups of files [ ] by pages and need to be broken down [ ] in my imagination [ ] in someone else's imagination [ ] not even a little bit.

    Modules my project needs:  ______________________________________________________________________________________________________________________________________________________________________________________________________

    [ ] I need to break big files up into smaller ones
    [ ] I need to group modules by type/folder more clearly
    [ ] I need to better namespace modules so the styles don't conflict
    [ ] I need to update, comment, or organize my import/manifest file
    [ ] I have modules but they're getting messy and need updating

Choose a module that you know of—like buttons, or a profile avatar, or a comment block. Whether it exists as a module/file or just in your imagination, document how you might follow the steps to refactor it.

    Module: ___________________________________________________________________

    1) Extract partial ___________________________________________________________________________________________________________________________________
    2) Find repeating patterns ________________________________________________
    ___________________________________________________________________________
    3) Create/extract base class ______________________________________________
    ___________________________________________________________________________
    4) Apply nesting __________________________________________________________
    ___________________________________________________________________________
    5) Create mixins/extends __________________________________________________
    ___________________________________________________________________________

[ ] I have a headache right now.

My project's naming conventions... 
    [ ] are consistent, and it uses...
            [ ] and they're even documented!
        [ ] BEM
        [ ] OOCSS
        [ ] whatever my framework was using
        [ ] something I made up but at least we use it consistently
        [ ] something someone else made up and I hate it
    [ ] exist, but are confusing, inconsistent, or don't fit with the project
    [ ] what's a naming convention?
        [ ] I need to pick a naming convention and...
            [ ] apply it to existing code as I refactor
            [ ] write new code with it as we delete old code
            [ ] beat my coworkers over the head with it til they give in
            The naming convention that best fits my project might be: _________

I have this much documentation:
    [ ] zero
    [ ] a little bit
        [ ] as code comments in my app
        [ ] as an external wiki/document
    [ ] lots, but it's all old and outdated
    [ ] my documentation is flawless

    I need more comment documentation [ ] per file [ ] in my manifest/import [ ] for a config/settings file [ ] individual modules [ ] how to use mixins, helpers or frameworks.

My project needs [ ] a code standards doc [ ] a static style guide or how-to [ ] a living style guide [ ] a designer.

I can best define my styles and how to use them...
    [ ] in modules, by writing instructional documentation
    [ ] visually, with images in a static doc, as my styles don't often change or I have designers creating this
    [ ] in a living style guide, because I change styles in the code more often than a designer changes mockups

A visual testing tool would be [ ] a useful addition to my project [ ] total overkill but really awesome [ ] neat but that involves command line crap, right?

    I might try to install [ ] Wraith [ ] DiffUX [ ] something else.

    
