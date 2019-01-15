# brunch-config.js


        // See http://brunch.io for documentation.
            exports.files = {
            javascripts: {
    joinTo: {
      'js/app.js': /^app/,
      'js/vendor.js': /^node_modules/
    },
            },
                        stylesheets: {
    joinTo: {
      'css/app.css': /^app/,
      'css/vendor.css': /^node_modules/
    }
        }
                };

        exports.plugins = {
    sass: {
    options: {
      // Je demande à Brunch de prendre connaissance du répertoire ci-dessous
      includePaths: ['node_modules/font-awesome/scss']
    }
        },
    copycat: {
    'fonts': ['node_modules/font-awesome/fonts']
    },
    browserSync: {
    files: ['*']
    },
    cleancss: {
    ignored: /app\.css/
    }
    };

    exports.npm = {
    styles: {
    'normalize.css': ['normalize.css']
    },
    globals: {
      '$': 'jquery',
     'jQuery': 'jquery'
    }
    };

    exports.modules = {
    autoRequire: {
    'js/app.js': ['app']
    }
        };

    exports.watcher = {
    usePolling: true,
    awaitWriteFinish: true
    };