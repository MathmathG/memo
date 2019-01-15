# Install Brunch exemple de mealmeet

- aller dans le reportoir du theme en question
- En LDC "brunch new content/themes/mealmeet"
- copier coller dans package.json  :


{

    "name": "brunch-app",
    "description": "Brunch.io application",
    "private": true,
    "author": "Brunch",
    "version": "0.0.1",
    "repository": "",
    "scripts": {
    "start": "brunch watch --server",
    "build": "brunch build --production"
    },
    "dependencies": {
    "font-awesome": "^4.7.0",
    "jquery": "^3.3.1",
    "jquery.scrollex": "^0.2.1",
    "normalize.css": "^8.0.1",
    "rellax": "^1.6.2"
    },
    "devDependencies": {
    "browser-sync-brunch": "0.0.9",
    "brunch": "^2.10.16",
    "clean-css-brunch": "^2.10.0",
    "copycat-brunch": "^1.1.0",
    "pleeease-brunch": "^3.0.0",
    "sass-brunch": "git+ssh://git@github.com/christopheOclock/sass-brunch.git",
    "uglify-js-brunch": "^2.10.0"
    }

- npm update
- npm install --save-dev browser-sync-brunch
- pour installer des dépendances en LDC :

npm install --save normalize.css jquery font-awesome jquery.scrollex

- et pour des dépendance de dev rajouter dev apres save soit :  
  npm install --save-dev browser-sync-brunch

