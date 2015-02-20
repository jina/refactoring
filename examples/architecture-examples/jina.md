```
+ css/

| - [project name].scss

| + dependencies/     # variables, mixins, functions (nothing compiles yet)
|   |--- _color.scss
|   |--- _typography.scss
|   |--- _layout.scss            # responsive grid settings
|   |--- _motion.scss            # keyframes, durations, etc.
|   |--- …

| + base/             # Plain old semantic HTML elements (no classes/IDs yet)
|   |--- _root.scss              # a, html, body, selection
|   |--- _type-elements.scss     # inline & block text elements
|   |--- _form-elements.scss
|   |--- _table-elements.css
|   |--- _embedded-media.scss    # img, svg, audio, video, etc.

| + components/       # modular, reusable UI components
|   |--- _buttons.scss           # hello world of Sass ;)
|   |--- _cards.scss
|   |--- _menus.scss
|   |--- _modals.scss
|   |--- _tabs.scss
|   |--- _tooltips.scss
|   |--- …

| + regions/          # page sections & regions
|   |--- _banner.scss
|   |--- _nav.scss
|   |--- _main.scss
|   |--- _complementary.scss
|   |--- _contentinfo.scss
|   |--- …

| + helpers/          # non-semantic layout helper classes & placeholders
|   |--- _color-themes.scss       # background & foreground pairings
|   |--- _layout-flex.scss        # clearfix, float columns
|   |--- _layout-float.scss       # clearfix, float columns
|   |--- _layout-table.scss       # display: table layouts
|   |--- _visibility.scss
|   |--- …

|---_print.scss
```
