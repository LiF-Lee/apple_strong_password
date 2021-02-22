# apple_strong_password
Apple Strong Password for PHP  | Ex: (int)-(int)-(int) |

* Source Code
```PHP
<?php

function appleStrongPw($pw = '') {
    $str = '0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ';
    if(strlen($pw) === 18) {
        preg_match_all('/\w{6}/', $pw, $strongPw);
        return implode('-', $strongPw[0]);
    } else return appleStrongPw($pw.$str[rand(0, 61)]); 
}

echo appleStrongPw();

?>
```

* Result
```PHP
'fYvTzJ-vYthSp-Ropt5v'
```
