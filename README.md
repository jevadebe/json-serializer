# Json Serializer for PHP

[![Build Status](https://travis-ci.org/zumba/json-serializer.png)](https://travis-ci.org/zumba/json-serializer)

This is a library to serialize PHP variables into JSON format. You can even serialize objects.
This library also come with a method to unserialize the JSON formatted, converting the data back
to their original objects.

*Json Serializer requires PHP >= 5.4*

## Example

```php

class MyCustomClass {
	public $isItAwesome = true;
	protected $nice = 'very!';
}

$instance = new MyCustomClass();

$serializer = new Zumba\Util\JsonSerializer();
$json = $serializer->serialize($instance);
// $json will contain the content {"@type":"MyCustomClass","isItAwesome":true,"nice":"very!"}

$restoredInstance = $serializer->unserialize($json);
// $restoredInstance will be an instance of MyCustomClass
```