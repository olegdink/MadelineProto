---
title: messages.getCommonChats
description: messages.getCommonChats parameters, return type and example
---
## Method: messages.getCommonChats  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|:-------------:|---------:|
|user\_id|[InputUser](../types/InputUser.md) | Yes|
|max\_id|[int](../types/int.md) | Yes|
|limit|[int](../types/int.md) | Yes|


### Return type: [messages\_Chats](../types/messages_Chats.md)

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

$messages_Chats = $MadelineProto->messages->getCommonChats(['user_id' => InputUser, 'max_id' => int, 'limit' => int, ]);
```

Or, if you're into Lua:

```
messages_Chats = messages.getCommonChats({user_id=InputUser, max_id=int, limit=int, })
```

