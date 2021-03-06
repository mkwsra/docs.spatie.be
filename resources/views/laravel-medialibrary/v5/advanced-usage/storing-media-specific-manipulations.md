---
title: Storing media specific manipulations
---

A media object has a property `manipulations`, which can be set to an array of manipulation values, with their conversion name as key.

When saving the media object, the package will regenerate all files and use the saved manipulation as the first manipulation when creating a derived image.

```php
// Add a width filter to the 'thumb' manipulations
$mediaItems = $newsItem->getMedia('images');
$mediaItems[0]->manipulations = ['thumb' => [ 'width' => '10']];

// This will cause the thumb conversion to be regenerated
$mediaItems[0]->save();
```

Calling `save` in this example will regenerate the `thumb` image.
