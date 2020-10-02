# phpbyte
Dealing  with socket  binary transformation with orher language . wrap byte by PHP's object ...  easy to use like java .

# usage 

#### write  

 ```
$bytes = Bytes::initBytes();
$bytes->writeDouble(-5.123)->writeInt(5.3)->writeFloat(-12.123);
var_dump($bytes->readDouble());
var_dump($bytes->readInt());
var_dump($bytes->readFloat());  
```

#### read

```
$host = 'xx.xx.xx.xx';
$port = xxxx;

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP) or die("Could not create socket.\n");
$connection = socket_connect($socket, $host, $port) or die("Could not connect server.\n");

$ret = socket_recv($socket, $msg, 130, MSG_PEEK  );


$bytes = Bytes::initBytes($msg);
$short = $bytes->readShort();
$int = $bytes->readInt();
$float = $bytes->readFloat();
$double = $bytes->readDouble();
$string = $bytes->readString(100);
```

just like this, very simple.
