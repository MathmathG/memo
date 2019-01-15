# Memo install Custom Wordpress

- En LDC composer init.
- Exemple d'instalation *composer.json* :


{

    "name": "mathieu/profile",
    "authors": [
        {
            "name": "Mathmathg",
            "email": "gle.mathieu@gmail.com"
        }
    ],
    "repositories":[
      {
        "type": "composer",
        "url" :"https://wpackagist.org"
      }
    ],
    "require": {
      "johnpbloch/wordpress": "4.9.*",
      "wpackagist-theme/twentyseventeen":"1.6",
      "wpackagist-plugin/akismet":"4.0.7",
      "wpackagist-plugin/contact-form-7":"5.0.2"
    },
    "require-dev":{
      "wpackagist-plugin/what-the-file": "1.5.4",
      "wpackagist-plugin/simply-show-hooks":"1.2.1"
    },
    "extra":{
      "wordpress-install-dir": "wp",
      "installer-paths": {
            "content/plugins/{$name}/": ["type:wordpress-plugin"],
            "content/themes/{$name}/": ["type:wordpress-theme"]
        }
    }
}

- npm install et npm update.
- créer le fichier .gitignore
- Copier dans wp-content coller *"index.php"* et rajouter : 
  
  "/** Loads the WordPress Environment and Template */
require( dirname( __FILE__ ) . '/wp/wp-blog-header.php' );
"(le wp en plus).

- Dans créer le fichier wp-config.php et rajouter :



define('WP_DEBUG', true);

if (WP_DEBUG) {
	// J'affiche les erreurs
	define('WP_DEBUG_DISPLAY', true);

	// Je n'active pas le fichier de debug
	define('WP_DEBUG_LOG', true);

	// Bloquer l'installation des plugins & des thèmes
	define('DISALLOW_FILE_MODS', false);

	// Désactive l'éditeur de thème en ligne.
	define('DISALLOW_FILE_EDIT', true);

	// Télécharger directement les plugins/thèmes/langues/maj
	define('FS_METHOD', 'direct');

	// Je désactive les révisions en mode debug
	define('WP_POST_REVISIONS', false);

// Si WP_DEBUG == false (en gros si le site est en prod)
} else {
	// Bloquer l'installation des plugins & des thèmes
	define('DISALLOW_FILE_MODS', true);

	// Désactive l'éditeur de thème en ligne.
	define('DISALLOW_FILE_EDIT', true);

	// Je n'affiche pas les erreurs
	define('WP_DEBUG_DISPLAY', true);

	// J'active le fichier de debug
	define('WP_DEBUG_LOG', true);

	// Je limite le nombre de révisions à 10
	define('WP_POST_REVISIONS', '10');

}

- Ensuite config des url, base de donnée et salage.
- ajouter le fichier .htacess : 

RewriteEngine on

RewriteRule ^index\.php$ - [L]

RewriteCond %{REQUEST_FILENAME} !-f

RewriteCond %{REQUEST_FILENAME} !-d

RewriteRule . index.php [L]

- les droits en ligne de commande : 

sudo chown -R <user>:www-data .

sudo find . -type f -exec chmod 664 {} +

sudo find . -type d -exec chmod 775 {} +

