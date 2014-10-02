+ css/

| - [project name].scss

| + dependencies/     # variables, mixins, functions (nothing compiles yet)
|   |--- _color.scss
|   |--- _typography.scss
|   |--- _layout.scss            # responsive grid settings
|   |--- _motion.scss            # keyframes, durations, etc.
|   |--- …

| + base/             # Plain old semantic HTML elements (no classes/IDs yet)
|   |--- _site.scss              # a, html, body, selection
|   |--- _text-inline.scss       # a, b, strong, abbr, etc.
|   |--- _text-block.scss        # h1, h2, p, blockquote, etc.
|   |--- _lists.scss
|   |--- _tables.css
|   |--- _forms.scss
|   |--- _media.scss             # img, svg, audio, video, etc.
|   |--- _code.scss              # pre, code, var, etc.
|   |--- …

| + components/       # modular, reusable UI components
|   |--- _buttons.scss           # hello world of Sass ;)
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
|   |--- _themes.scss             # background & foreground pairings
|   |--- _layout-float.scss       # clearfix, float columns
|   |--- _layout-table.scss       # display: table layouts
|   |--- _visibility.scss
|   |--- …

| + tools/            # design & debugging utilities (conditionally imported)
|   |--- _show-grids.scss         # baseline & vertical grid
|   |--- _diagnostic.scss         # highlight problem elements
|   |--- …

| + responsive/       # media queries
|   |--- [various media queries for responsive layout]
|   |--- _high-definition.scss    # print & retina
|   |--- _print.scss
