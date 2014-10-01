# Schedule

## Timeline

_9am to 10am_
* Introduction
  * introduce ourselves
  * send out digital survey, get responses http://bit.ly/cya-refactoring
  * Q&A: get to know attendees, where they are in their project, what they want to learn
  * update response states in slides?
_10am to 10:45am_
* Refactoring Overview
  * Clarity, Maintainability, Efficiency, DRY
  * why we do and don't refactor
  * getting everyone on the same page
  * why Sass helps us refactor
  * making refactoring a regular part of your workflow
* Installation and Apps
  * gem
  * codekit
  * foundation
  * libsass
    * nodesass
    * a note on feature parity
  * grunt and gulp
  * choosing .scss or .sass syntax
* Importing
  * create a manifest
  * break up existing files and import w/o altering existing output
  * reorg/regroup files
* Creating variables
  * colors, type
  * ???
* Variable abstraction
  * patterns
  * abstracted name options
  * creating simple themes
  * named media queries
* Organize Files and Folders
  * creating config files
    * [show examples of config options: simple, medium, Dale Sande style]
_10:45am to 11am_
* BREAK
_11am to 11:30am_
* Creating Modules
  * systems, not pages -- but what if you have existing code
  * how to determine what kinds of modules you HAVE
  * namespacing
    * & parent
    * state classes
    * placeholders
* Refactoring a Module
  * Extract partial
  * Find repeating patterns
  * Create/extract base class
  * Apply nesting
  * Create mixins/extends
  * determining the size of a module refactor 
  * refactoring HTML/CSS
    * elements -> classnames
_11:30am to 12:30pm_
* WORK TIME
  * spend ~1hr looking for a module in their code, starting a refactor on it
  * TODO: have an example for those who don't have project code
* BREAK
_12:30pm to 1pm_
* Naming Conventions
  * OOCSS
  * BEM
  * SMACSS
  * pros/cons and iterating on conventions
  * organizing properties
* Living Style Guides
  * options
  * how to create them
  * show examples
* Documentation & Commenting
  * commenting files, sections
  * inline comment documentation
  * comment types
* Testing
  * diffux, wraith
  * true
  * keeping refactors small
