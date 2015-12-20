# Blizzard API PHP Client
API client for Blizzard API written in PHP. [Blizzard API Documentation](https://dev.battle.net/io-docs)

[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/LogansUA/blizzard-api-client/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/LogansUA/blizzard-api-client/?branch=master)
[![Build Status](https://scrutinizer-ci.com/g/LogansUA/blizzard-api-client/badges/build.png?b=master)](https://scrutinizer-ci.com/g/LogansUA/blizzard-api-client/build-status/master)
[![Latest Stable Version](https://poser.pugx.org/logansua/blizzard-api-client/v/stable)](https://packagist.org/packages/logansua/blizzard-api-client)
[![Total Downloads](https://poser.pugx.org/logansua/blizzard-api-client/downloads)](https://packagist.org/packages/logansua/blizzard-api-client)
[![License](https://poser.pugx.org/logansua/blizzard-api-client/license)](https://packagist.org/packages/logansua/blizzard-api-client)
[![Dependency Status](https://www.versioneye.com/user/projects/5503fd1a4a1064f144000002/badge.svg?style=flat)](https://www.versioneye.com/user/projects/5503fd1a4a1064f144000002)
[![SensioLabsInsight](https://insight.sensiolabs.com/projects/b103523d-7f46-4c74-94f9-cf41462b298a/mini.png)](https://insight.sensiolabs.com/projects/b103523d-7f46-4c74-94f9-cf41462b298a)

## Installation
### Method 1
```
php composer.phar require logansua/blizzard-api-client
```
This command requires you to have Composer installed globally, as explained
in the [Composer documentation](https://getcomposer.org/doc/00-intro.md).
### Method 2
```
git clone https://github.com/LogansUA/blizzard-api-client.git
```

## List of available API services
* World of Warcraft
* Diablo 3

## Example
* World of Warcraft

```PHP
require_once __DIR__.'/../vendor/autoload.php';

// Create a BlizzardClient with Blizzard application ApiKey
$client = new \BlizzardApi\BlizzardClient('apiKey', 'locale', 'region');

// Create API service and pass configured BlizzardClient in constructor
$wow = new \BlizzardApi\Service\WorldOfWarcraft($client);

// Use any of service method
$response = $wow->getGuild('test-realm', 'test-guild', [
    'fields' => 'achievements,challenge',
]);

// Show status code
var_dump($response->getStatusCode());

// Show headers
var_dump($response->getHeaders());

// Show response body
echo $response->getBody();
```
* Diablo 3

```PHP
require_once __DIR__.'/../vendor/autoload.php';

$client = new \BlizzardApi\BlizzardClient('apiKey', 'locale', 'region');

$diablo = new \BlizzardApi\Service\Diablo($client);

$response = $diablo->getItemDataById('Unique_Shoulder_103_x1');

// Show status code
var_dump($response->getStatusCode());

// Show headers
var_dump($response->getHeaders());

// Show response body
echo $response->getBody();
```

## License
This software is published under the [MIT License](https://github.com/LogansUA/blizzard-api-client/blob/master/LICENSE)
