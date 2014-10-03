```

+ scss/
|
| + base/                 # reset, typography, site-wide
|   |-- _index.scss       # imports for all base styles
|   |-- _base.scss        # base styles
|   |-- _normalize.scss   # normalize v3.0.1
|
| + layout/               # major components, e.g., header, footer etc.
|   |-- _index.scss       # imports for all layout styles
|
| + modules/              # minor components, e.g., buttons, widgets etc.
|   |-- _index.scss       # imports for all modules
|
| + states/               # js-based classes, alternative states
|   |-- _index.scss       # imports for all state styles
|   |-- _states.scss      # state rules
|   |-- _print.scss       # print styles
|   |-- _touch.scss       # touch styles
|
| + themes/               # (optional) separate theme files
|   |-- beccapurple.scss  # rename to appropriate theme name
|
| + utilities/            # non-CSS outputs (i.e. mixins, vars)
|   |-- _index.scss       # imports for all mixins + global project vars
|   |-- _fonts.scss       # font mixins
|   |-- _functions.scss   # ems to rems conversion, etc.
|   |-- _global.scss      # global variables
|   |-- _helpers.scss     # placeholder helper classes
|   |-- _mixins.scss      # media queries, CSS3, etc.
|   |-- _lib.scss         # imports for third party styles
|   |-- + lib/            # third party styles
|       | _pesticide.scss # CSS pesticide
|       | ...
|
|   + ie.scss             # IE specific Sass file
|   + styles.scss         # primary Sass file
|   + _shame.scss         # because hacks happen
|
+ .htaccess               # Apache server configs
+ config.rb               # Compass configuration file
+ crossdomain.xml         # cross-domain requests
+ docs/                   # SassDoc generated documentation
+ deploy.rb               # Capistrano configuration file
+ Gruntfile.js            # Grunt configuration & tasks
+ package.json            # Grunt metadata & dependencies
```
