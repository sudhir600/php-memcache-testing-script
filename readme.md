Sample code- 

````
<?php
  $memcache = memcache_connect('localhost', 11211);
  if ($memcache) {
    $memcache->set("str_key", "Hello memcached");
    $memcache->set("num_key", 123);
    $object = new StdClass;
    $object->attribute = 'test';
    $memcache->set("obj_key", $object);
    $array = Array('assoc'=>123, 456, 789);
    $memcache->set("arr_key", $array);
    var_dump($memcache->get('str_key'));
    var_dump($memcache->get('num_key'));
    var_dump($memcache->get('obj_key'));
  }
  else {
    echo "Memcached Connection failed";
  }
?>
````
