# Assignment

Our system needs a way for searching in product feeds given to us, for example this [feed file](feed.xml) using diferent filters. So your team leader give you a task to create a simple feed search class to integrate this functionality. 

He wants the usage of our feed search to looks something like this:

```php
$fs = new FeedSearch($feed);
$item = $fs->brand('SONY')
           ->used()
           ->cheapest();
echo $item->id;           
```

Implement methods described in the following interface

```php
interface FeedSearchInterface {
    public function brand(string $category): self;
    public function used(): self;
    public function new(): self;
    public function cheapest(): Item;
    public function mostExpensive(): Item;
}
```

### Test data

Search: Find cheapest new Sony TV  
Expected producr ID: 14

Search: Find most expensive product in the feed  
Expected producr ID: 20

Search: Find cheapest used product in the feed  
Expected producr ID: 12

>  *Note:* 
>You can use a simple class, a framework or a structured files as you see fit, you also can use external libraries.
>Since this is a exercise, speed is not a concern.