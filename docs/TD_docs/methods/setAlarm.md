---
title: setAlarm
description: Returns Ok after specified amount of the time passed
---
## Method: setAlarm  
[Back to methods index](index.md)


Returns Ok after specified amount of the time passed

### Params:

| Name     |    Type       | Required | Description |
|----------|:-------------:|:--------:|------------:|
|seconds|[double](../types/double.md) | Yes|Number of seconds before that function returns|


### Return type: [Ok](../types/Ok.md)

### Example:


```
$MadelineProto = new \danog\MadelineProto\API();
if (isset($token)) {
    $this->bot_login($token);
}
if (isset($number)) {
    $sentCode = $MadelineProto->phone_login($number);
    echo 'Enter the code you received: ';
    $code = '';
    for ($x = 0; $x < $sentCode['type']['length']; $x++) {
        $code .= fgetc(STDIN);
    }
    $MadelineProto->complete_phone_login($code);
}

$Ok = $MadelineProto->setAlarm(['seconds' => double, ]);
```

Or, if you're into Lua:

```
Ok = setAlarm({seconds=double, })
```

