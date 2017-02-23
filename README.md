# php-eval
This is a simple PHP extension for hooking eval().

## Requirements
* PHP 7 (recommend)
* PHP 5.6.x (untested)

## Building and installing on Windows
* Download source code file `php_eval.c`
* Download PHP source code and prepare your PHP building environment (https://wiki.php.net/internals/windows/stepbystepbuild)
* Compile `php_eval.c` and build a DLL file with your Visual C++
* Copy the DLL file into PHP extension dir and install it by modifying php.ini
* Restart your server

## Usage
Example:

    <?php
    
    /* write your code in __eval() */
    function __eval($code, $file) {
      echo "eval() @ {$file}:\n{$code}\n\n";
      // you can return FALSE to prevent this eval()
      return false;
      // or you can return a string to replace $code for executing
      return 'echo 2;';
      // or you can return nothing to executing $code next
    }
    
    eval('echo 1;');

## License

MIT
