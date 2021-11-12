# laravel-owncloud

## Install

Via Composer

``` bash
$ composer require fabrizio/laravel-owncloud
```

## Usage

Register the service provider in your app.php config file:

``` php
// config/app.php

'providers' => [
    ...
    League\Flysystem\OwnCloud\OwnCloudServiceProvider::class
    ...
];
```

Create a owncloud filesystem disk:

``` php
// config/filesystems.php

'disks' => [
	...
	'owncloud' => [
        'driver'   => 'owncloud',
        //example baseUri: 'https://cloud.mydomain.com/remote.php/dav/files/MyCustomUser/'
        'baseUri'  => 'webdav.url', 
        //example shareApi: 'https://cloud.mydomain.com/ocs/v1.php/apps/files_sharing/api/v1/shares'
        'shareApi'  => 'something like...ocs/v1.php/apps/files_sharing/api/v1/shares',
        'userName' => 'MyCustomUser',
        'password' => 'secret'
    ],
	...
];
```