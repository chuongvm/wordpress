Officience Product RSS (test)

Requirement:
- PHP 8.1+
- MySQL 5.x
- Wordpress 6.x (The version being tested is 6.4.1)
- WooCommerce plugin (The version being tested is 8.3.0)
- "WP Mail SMTP" plugin and setting SMTP for email send

Installing:

1. WooCommerce setting:
    - Product:
        + Currency: Euro
        + Number of decimals: 2
    - Payment: Choose at least 1 payment method. For example "Cash on delivery"

2. Download "officience-product-rss.zip" file and install the "Officience Product RSS" plugin

3. Cronjob setting:
    + In your wp-config.php file, add the following line:
        define('DISABLE_WP_CRON', true);
    + In command line (Macos/Linux), type 
        crontab -e
    to open cronjob file and add following line (please replace {your_domain} with your actual value):
        */10 * * * * /usr/local/bin/wget -q -O - "{your_domain}/wp-cron.php?doing_wp_cron"
    + Save cronjob file

Enjoy it !
