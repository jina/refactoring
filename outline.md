# OUTLINE

* Introduction
* Refactoring
  * What is it?
    * changing the structure of existing code without changing its behavior
  * Why do we do it?
    * because we never write code perfectly the first time
    * clarity, maintainability, efficiency, DRY
    * you have new requirements
    * the design or UI needs to change
    * code smell
  * general compromise and getting everyone on the same page
    * understanding principles of why you are doing a certain way
  * systems, not pages
 * Using Sass to refactor
   * why it's valuable
     * allows us to make modules
     * separation of concerns
     * importing individual files
     * variables, functions
     * writing DRYer code than pure CSS
* CYA: Installing and starting with Sass
  * gem
  * codekit
  * libsass
  * foundation
  * compass
  * changing .css to .scss
* CYA: Refactoring variables
  * colors
  * typography
* CYA: abstracting variables
  * variable naming conventions
  * levels of abstraction
    * theming
    * keeping functions/helpers out of style code
* CYA: Import files
  * breaking code out into files
  * importing files w/o changing import order
* CYA: Commenting
  * commenting files
  * commenting imports
  * commenting sections
  * documentation/instructions
  * /* versus // comments
* CYA: Modules
  * systems, not pages
  * how to determine WHAT modules you have
    * going thru old html and css and determining what is the same and what is different
    * which need a parent to have a style change under (namespacing)
  * WHERE they are and which should be the same
    * where do you put new modules
    * how do you group and organize them?
* CYA: Steps to refactor a module
  * once you have determined what goes into a module
  * 1) Extract partial
  * 2) Find repeating patterns
  * 3) Create/extract base class
  * 4) Apply nesting
  * 5) Create mixins/extends
  * determining the size of a refactor
* CYA: class naming refactoring in both HTML and CSS
  * elements -> classnames
* CYA: naming conventions
  * whatever you do, be consistent
    * .section, .section-item, .section-item-individualthingy
  * OOCSS
  * BEM
  * SMACSS
  * pros and cons of naming convention standards
  * how to iterate on naming conventions and change them
  * organizing properties (alpha, properties, camelcase vs underscore vs dash, etc)
* CYA: living style guides
  * docco, kss, etc, an overview of what they are
  * vs manual creation
  * show example of comments in sass file w/ relevant HTML & generate one)
* CYA: testing
  * how to test for changes/things that are broken after a refactor
  * diffux, phantom
  * keeping refactors small so they don't break things
* CYA: what's right for my project
  * how to tell what works for you...
    * naming conventions - why one would work better than another FOR your project
    * organization of files/folders
    * using elements vs classnames, BEM, OOCSS, etc
    * using frameworks or not