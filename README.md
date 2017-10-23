# Mailer
PHP Class for sending email.

# Install
## With [Composer](https://getcomposer.org/)
1. Run in console:
    ```text
    php composer.phar require ddrv/mailer
    php composer.phar install
    ```
1. Include autoload file
    ```php
    require_once('vendor/autoload.php');
    ```
## Manually install
1. Download [Archive](https://github.com/ddrv/mailer/archive/master.zip)
1. Unzip archive to /path/to/libraries/
1. Include files
    ```php
    require_once('/path/to/libraries/mailer/src/Mailer.php');
    ```

#Usage

```php
/**
 * Inititalization Mailer class. 
 */
$mailer = new \Ddrv\Mailer\Mailer();

/**
 * If need use SMTP server, setting it
 */
$mailer->smtp('smtp.host.name',25,'from@host.name','password for from', 'http://host.name');

/**
 * Set sender from@host.name as Site Administrator
 */
$mailer->sender('from@host.name','Site Administrator');

/**
 * Set subject of mail
 */
$mailer->subject('Subject of mail');

/**
 * Add text of mail in HTML format
 */
$mailer->body('<p>Simple text</p>');

/**
 * In need adding attachment from string, run
 */
$mailer->attachFromString('content','attach1.txt');

/**
 * In need adding attachment from file, run
 */
$mailer->attachFromFile('/path/to/file','attach2.txt');

/**
 * Add addresses
 */
$mailer->addAddress('address1@host.name', 'My best Friend');
$mailer->addAddress('address2@host.name', 'My second Friend');

/**
 * If error, remove address
 */
$mailer->removeAddress('address2@host.name');

/**
 * Send email to addresses
 */
$mailer->send();
```