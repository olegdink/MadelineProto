---
title: photos.getUserPhotos
description: photos.getUserPhotos parameters, return type and example
---
## Method: photos.getUserPhotos  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|:-------------:|---------:|
|user\_id|[InputUser](../types/InputUser.md) | Yes|
|offset|[int](../types/int.md) | Yes|
|max\_id|[int](../types/int.md) | Yes|
|limit|[int](../types/int.md) | Yes|


### Return type: [photos\_Photos](../types/photos_Photos.md)

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

$photos_Photos = $MadelineProto->photos->getUserPhotos(['user_id' => InputUser, 'offset' => int, 'max_id' => int, 'limit' => int, ]);
```

Or, if you're into Lua:

```
photos_Photos = photos.getUserPhotos({user_id=InputUser, offset=int, max_id=int, limit=int, })
```

