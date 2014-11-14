# Translator Component - Mendo Framework

The Mendo Translator component aids in building multilingual applications.

## Creating the Translator

```php
$translator = new Translator();
```

## Adding a Translation File

```php
$translator->addTranslationFile(__DIR__.'./translations/fr/messages.php', 'fr');
```

At the moment, only PHP arrays are supported.

## Adding a Directory of Translation Files

```php
$translator->addTranslationFile(__DIR__.'./translations/nl', 'nl');
```

The directory will be searched recursively for translations files.

## Adding an Array of Translations

```php
$translator->addTranslationArray(['First name' => 'Vorname'], 'de');
```

## Translate a Message

```php
$translator->setDefaultLanguage('fr'); // You can set a default language

$translator->translate('First name'); // No language specified, using def. lang "fr" and returns "Prénom"

$translator->translate('First name', null, 'nl'); // Returns "Voornaam"

$translator->translate('First name', null, 'it'); // No Italian translations provided, returns "First name"

$translator->translate('User %1 created', 'John'); // returns "Utilisateur John créé"

$translator->translate('User %1 %2 created', ['John', 'Smith']); // returns "Utilisateur John Smith créé"
```

## Installation

You can install Mendo Translator using the dependency management tool [Composer](https://getcomposer.org/).
Run the *require* command to resolve and download the dependencies:

```
composer require mendoframework/translate
```