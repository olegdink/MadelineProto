---
title: getCommonChats
description: Returns list of common chats with an other given user. Chats are sorted by their type and creation date
---
## Method: getCommonChats  
[Back to methods index](index.md)


Returns list of common chats with an other given user. Chats are sorted by their type and creation date

### Params:

| Name     |    Type       | Required | Description |
|----------|:-------------:|:--------:|------------:|
|user\_id|[int](../types/int.md) | Yes|User identifier|
|offset\_chat\_id|[long](../types/long.md) | Yes|Chat identifier to return chats from, use 0 for the first request|
|limit|[int](../types/int.md) | Yes|Maximum number of chats to be returned, up to 100|


### Return type: [Chats](../types/Chats.md)

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

$Chats = $MadelineProto->getCommonChats(['user_id' => int, 'offset_chat_id' => long, 'limit' => int, ]);
```

Or, if you're into Lua:

```
Chats = getCommonChats({user_id=int, offset_chat_id=long, limit=int, })
```

