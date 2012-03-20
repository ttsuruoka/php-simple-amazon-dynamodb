What is SimpleAmazon
====================

A simple PHP interface to Amazon Web Services API.

How to use
----------

### AWS Security Token Service

```php
<?php
$sts = new SimpleAmazonSTS(AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY);
$r = $sts->call('GetSessionToken', array('DurationSeconds' => 3600));

echo $r['GetSessionTokenResult']['Credentials']['AccessKeyId'];
echo $r['GetSessionTokenResult']['Credentials']['SecretAccessKey'];
echo $r['GetSessionTokenResult']['Credentials']['SessionToken'];
```

### Amazon DynamoDB

```php
<?php
$db = new SimpleAmazonDynamoDB(STS_ACCESS_KEY_ID, STS_SECRET_ACCESS_KEY, STS_SESSION_TOKEN);
$r = $db->call('ListTables');

var_dump($r['TableNames']);
```

Requirements
------------

 * PHP >= 5.2.0
 * extensions: curl, json

Developer Documentation
-----------------------

### AWS Security Token Service

* [API Reference](http://docs.amazonwebservices.com/STS/latest/APIReference/)

### Amazon DynamoDB

* [Operations in Amazon DynamoDB](http://docs.amazonwebservices.com/amazondynamodb/latest/developerguide/operationlist.html)

License
-------

The MIT License

Copyright (c) 2012 Tatsuya Tsuruoka

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
