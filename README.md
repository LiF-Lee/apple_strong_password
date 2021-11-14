## apple_strong_password
Apple Strong Password Generator for PHP

### Source Code

```PHP
<?php

function appleStrongPw($version = 'v1', $pw = '') {
    $str = '0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ';
    if(strlen($pw) === (($version === 'v1') ? 18 : 12)) {
        $regEx = ($version === 'v1') ? '/\w{6}/' : '/\w{3}/';
        preg_match_all($regEx, $pw, $strongPw);
        return implode('-', $strongPw[0]);
    } else return appleStrongPw($version, $pw.$str[rand(0, 61)]);
}

echo 'v1: '.appleStrongPw('v1');
echo '<br>';
echo 'v2: '.appleStrongPw('v2');

?>
```

### Result

```
v1: dZIpfu-3Hpyk1-CXmBpT
v2: PFQ-pO2-vvi-qAU
```
