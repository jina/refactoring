|- sass/
|--- application.sass    // manifest, imports config, components, modules, frameworks
|--- config.sass         // imports actual config file, helpers, colors, typography, themes
|--- config/
|------ _config.sass
|------ _helpers.sass    // includes mixins, testing functions, css3, js is- states
|------ _colors.sass
|------ _typography.sass // webfonts and type declarations
|--- components.sass     // imports icons, buttons, UI elements, page components
|--- components/
|------ page.sass        // general page/body
|------ header.sass
|------ footer.sass
|------ buttons.sass
|------ icons.sass
|------ nav.sass
|------ forms.sass
|--- modules.sass        // imports page content and semantic HTML
|--- modules/
|------ [your page content files]
|--- vendor.sass         // imports CSS from third party or JS libs
