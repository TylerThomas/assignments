# Homework 2.1 - Ever wonder what all these signs say?

For Homework 1.1, you found a nice project on Github, forked it into your own account, and cloned it into your Cloud 9 IDE account. For this assignment, pick one or more Javascript files from your project (you DID pick a Javascript project, didn't you?) and identify some of the following items of Javascript grammar and vocabulary that we talked about in class, including but not limited to:

* Variables: `$name`
* Constants: `E_USER_WARNING`, `MY_AWESOME_CONSTANT`
* Arithmetic operators: addition (+), subtraction (-)
* Functions: `array_slice()`, `do_something_amazing()`

When you find one, identify the file and line number in this file, below the instrcutions per the example below. Try to make the indentation match the original file (yes, copy and paste), even if that means there's NO indentation. Crazy Javascript-ers.

You don't have to identify EVERYTHING in a given line or even in a single file, but you may get extra points if you're thorough or make a survey of more than one file... And you might get docked if you make too much work for me. I at least want to see about 50 lines of code.

When you're done editing this file, save it, commit it, and push it to your "assignments" repo, called "origin". You remember how to push, right?

## Your work should look like this...

`path/to/file.js:3`
```javascript
    if ( true )
    // Boolean: true
```

`path/to/file.js:42`
```javascript
    var name = do_something_amazing() + 1;
    // Variable: name
    // Function: do_something_amazing()
    // Integer: 1
```

## Now get to it!


var utils = require('utility');

// md5 hash
utils.md5('@Python发烧友'); // '1369e7668bc600f0d90c06f5e395d7a9'
utils.md5(new Buffer('')); // 'd41d8cd98f00b204e9800998ecf8427e'
// md5 hase output base64
utils.md5('苏千', 'base64'); // 'X3M8R8WKB31hJXECstREgQ=='

// Object md5 hash
utils.md5({foo: 'bar', bar: 'foo'}).should.equal(utils.md5({bar: 'foo', foo: 'bar'}));

// sha1 hash
utils.sha1('@Python发烧友'); // 'ed6a2381ad20f2cf7875fc04d52257380015b574'
utils.sha1(new Buffer('')); // 'da39a3ee5e6b4b0d3255bfef95601890afd80709'
// sha1 hase output base64
utils.sha1('苏千', 'base64'); // 'Ckr/a6tjS5wvmbcfJel2kh/N5aU='

// sha256 hash
utils.sha256('@Python发烧友'); // '80ddd84d1453c994af764bf558c4b96adaced9dd8d7d2194705fe58e1b3162df'

// Object sha1 hash
utils.sha1({foo: 'bar', bar: 'foo'}).should.equal(utils.sha1({bar: 'foo', foo: 'bar'}));

// hmac
// hmac-sha1 with base64 output encoding
utils.hmac('sha1', 'I am a key', 'hello world'); // 'pO6J0LKDxRRkvSECSEdxwKx84L0='

// base64 encode
utils.base64encode('你好￥'); // '5L2g5aW977+l'
utils.base64decode('5L2g5aW977+l') // '你好￥'

// urlsafe base64 encode
utils.base64encode('你好￥', true); // '5L2g5aW977-l'
utils.base64decode('5L2g5aW977-l', true); // '你好￥'

// empty function
process.nextTick(utils.noop);
function foo(callback) {
  callback = callback || utils.noop;
}

// html escape
utils.escape('<script/>"& &amp;'); // '&lt;script/&gt;&quot;&amp; &amp;'

// Safe encodeURIComponent and decodeURIComponent
utils.decodeURIComponent(utils.encodeURIComponent('你好, nodejs')).should.equal('你好, nodejs');

// get first ip
[WARNNING] getIP() remove, PLEASE use `https://github.com/node-modules/address` module instead

// get a function parameter's names
utils.getParamNames(function (key1, key2) {}); // ['key1', 'key2']

// get a random string, default length is 16
utils.randomString(32, '1234567890'); //18774480824014856763726145106142

// check if object has this property
utils.has({hello: 'world'}, 'hello'); //true