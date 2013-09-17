## Paths

    /
      app/
        assets/
      vendor/
      public/
      config.coffee

## Config

    files:
      javascripts:   # or 'stylesheets' or 'templates'
        order:
          before: [ 'normalize.css' ]
          after:  [ 'helpers.css' ]

        joinTo: 'app.js'
        joinTo:
          'js/app.js':    /^app/
          'js/vendor.js': /^vendor/
        pluginHelpers: 'js/vendor.js'

    paths:
      public: 'public'                       # where to compile
      watched: ['app','test','vendor']       # what to monitor

    modules:
      wrapper: 'amd'
      definition: 'amd'
      nameCleaner: (path) -> path.replace /^app\//, ''

    # brunch b --apply production
    overrides:
      production:
        optimize: true
        sourceMaps: false
        plugins: autoReload: enabled: false

## Plugins

    plugins:
      uglify:
        mangle: true
        compress:
          global_defs:
            DEBUG: false

## Stuff

  * uglify-js-brunch
  * stylus-brunch
  * coffee-script-brunch

## References

  * https://github.com/brunch/brunch/blob/master/docs/config.md