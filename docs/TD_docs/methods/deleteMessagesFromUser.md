---
title: deleteMessagesFromUser
description: Deletes all messages in the chat sent by the specified user. Works only in supergroup channel chats, needs appropriate privileges
---
## Method: deleteMessagesFromUser  
[Back to methods index](index.md)


Deletes all messages in the chat sent by the specified user. Works only in supergroup channel chats, needs appropriate privileges

### Params:

| Name     |    Type       | Required | Description |
|----------|:-------------:|:--------:|------------:|
|chat\_id|[long](../types/long.md) | Yes|Chat identifier|
|user\_id|[int](../types/int.md) | Yes|User identifier|


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

$Ok = $MadelineProto->deleteMessagesFromUser(['chat_id' => long, 'user_id' => int, ]);
```

Or, if you're into Lua:

```
Ok = deleteMessagesFromUser({chat_id=long, user_id=int, })
```

