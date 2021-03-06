---
title: getUserFull
description: Returns full information about a user by its identifier
---
## Method: getUserFull  
[Back to methods index](index.md)


Returns full information about a user by its identifier

### Params:

| Name     |    Type       | Required | Description |
|----------|:-------------:|:--------:|------------:|
|user\_id|[int](../types/int.md) | Yes|User identifier|


### Return type: [UserFull](../types/UserFull.md)

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

$UserFull = $MadelineProto->getUserFull(['user_id' => int, ]);
```

Or, if you're into Lua:

```
UserFull = getUserFull({user_id=int, })
```

