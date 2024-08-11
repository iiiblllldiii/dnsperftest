# DNS Performance Test

اسکریپت شل برای تست و آزمایش عملکرد محبوب‌ترین DNS های خارجی و داخلی روی سرور شما

Includes by default:
 * Shecan
 * Begzar
 * Electro
 * CloudFlare
 * Level3
 * Google
 * Quad9
 * SafeDNS
 * Freenom
 * OpenDNS
 * Norton
 * CleanBrowsing
 * Yandex
 * AdGuard
 * Neustar
 * Comodo
 * NextDNS

# Required 

You need to install bc and dig. 

For Ubuntu:

```
  sudo apt-get install bc dnsutils
```

For macOS using homebrew:

```
  brew install bc bind
```

# Utilization

``` 
 git clone --depth=1 https://github.com/iiiblllldiii/dnsperftest/
 cd dnsperftest
 bash ./dnstest.sh
```

examples:
```
$ bash ./dnstest.sh
                     test1   test2   test3   test4   test5   test6   test7   test8   test9   test10  Average 
shecan               88 ms   1000 ms 84 ms   80 ms   84 ms   1000 ms 88 ms   1000 ms 88 ms   80 ms     359.20
begzar               88 ms   176 ms  84 ms   84 ms   80 ms   172 ms  80 ms   168 ms  84 ms   84 ms     110.00
electro              84 ms   84 ms   80 ms   76 ms   80 ms   84 ms   76 ms   168 ms  80 ms   92 ms     90.40
cloudflare           4 ms    8 ms    4 ms    4 ms    8 ms    8 ms    8 ms    8 ms    4 ms    4 ms      6.00
level3               16 ms   16 ms   16 ms   12 ms   16 ms   12 ms   16 ms   20 ms   12 ms   16 ms     15.20
google               8 ms    4 ms    8 ms    8 ms    4 ms    24 ms   8 ms    8 ms    4 ms    8 ms      8.40
quad9                4 ms    4 ms    16 ms   4 ms    12 ms   4 ms    4 ms    8 ms    1 ms    12 ms     6.90
safedns              8 ms    4 ms    8 ms    8 ms    8 ms    4 ms    8 ms    8 ms    8 ms    4 ms      6.80
freenom              128 ms  132 ms  128 ms  132 ms  132 ms  132 ms  144 ms  132 ms  132 ms  128 ms    132.00
opendns              28 ms   8 ms    8 ms    8 ms    4 ms    92 ms   4 ms    12 ms   8 ms    4 ms      17.60
norton               4 ms    8 ms    4 ms    8 ms    8 ms    4 ms    4 ms    4 ms    8 ms    8 ms      6.00
cleanbrowsing        8 ms    8 ms    8 ms    4 ms    4 ms    4 ms    4 ms    8 ms    8 ms    4 ms      6.00
yandex               52 ms   48 ms   52 ms   52 ms   136 ms  56 ms   56 ms   60 ms   52 ms   48 ms     61.20
adguard              1000 ms 1000 ms 1000 ms 1000 ms 1000 ms 1000 ms 1000 ms 1000 ms 1000 ms 1000 ms   1000.00
neustar              12 ms   12 ms   12 ms   12 ms   12 ms   12 ms   12 ms   12 ms   12 ms   12 ms     12.00
comodo               8 ms    4 ms    12 ms   4 ms    8 ms    8 ms    8 ms    8 ms    8 ms    8 ms      7.60
nextdns              60 ms   60 ms   4 ms    4 ms    8 ms    4 ms    4 ms    8 ms    8 ms    4 ms      16.40
```

To sort with the fastest first, add `sort -k 22 -n` at the end of the command:

```
  $ bash ./dnstest.sh |sort -k 22 -n
               test1   test2   test3   test4   test5   test6   test7   test8   test9   test10  Average 
cloudflare     1 ms    1 ms    1 ms    4 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms      1.30
norton         2 ms    2 ms    2 ms    2 ms    2 ms    2 ms    2 ms    2 ms    2 ms    2 ms      2.00
neustar        2 ms    2 ms    2 ms    2 ms    1 ms    2 ms    2 ms    2 ms    2 ms    22 ms     3.90
cleanbrowsing  11 ms   23 ms   11 ms   11 ms   11 ms   11 ms   11 ms   13 ms   12 ms   11 ms     12.50
google         4 ms    4 ms    3 ms    21 ms   21 ms   61 ms   3 ms    21 ms   21 ms   22 ms     18.10
opendns        2 ms    2 ms    2 ms    39 ms   2 ms    75 ms   2 ms    21 ms   39 ms   13 ms     19.70
comodo         22 ms   23 ms   22 ms   22 ms   22 ms   22 ms   22 ms   22 ms   22 ms   23 ms     22.20
quad9          10 ms   37 ms   10 ms   10 ms   10 ms   145 ms  10 ms   10 ms   10 ms   20 ms     27.20
yandex         177 ms  216 ms  178 ms  182 ms  186 ms  177 ms  183 ms  174 ms  186 ms  222 ms    188.10
adguard        199 ms  210 ms  200 ms  201 ms  202 ms  202 ms  199 ms  200 ms  198 ms  201 ms    201.20
```

To test using the IPv6 addresses, add the IPv6 option:

```
  $ bash ./dnstest.sh ipv6| sort -k 22 -n
                     test1   test2   test3   test4   test5   test6   test7   test8   test9   test10  Average 
cleanbrowsing-v6     1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms      1.00
cloudflare-v6        1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    5 ms    1 ms    1 ms    1 ms      1.40
quad9-v6             1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    21 ms     3.00
8.8.8.8              7 ms    1 ms    16 ms   1 ms    1 ms    24 ms   1 ms    8 ms    1 ms    7 ms      6.70
neustar-v6           1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    60 ms     6.90
opendns-v6           1 ms    1 ms    1 ms    1 ms    1 ms    62 ms   1 ms    1 ms    29 ms   1 ms      9.90
google-v6            8 ms    8 ms    7 ms    8 ms    14 ms   67 ms   1 ms    7 ms    8 ms    61 ms     18.90
adguard-v6           52 ms   55 ms   52 ms   53 ms   52 ms   56 ms   52 ms   55 ms   52 ms   57 ms     53.60
yandex-v6            177 ms  178 ms  178 ms  179 ms  179 ms  178 ms  179 ms  178 ms  178 ms  223 ms    182.70
```

To test both IPv6 and IPv4, add the "all" option:
```
  $ bash ./dnstest.sh all| sort -k 22 -n
                     test1   test2   test3   test4   test5   test6   test7   test8   test9   test10  Average 
cleanbrowsing        1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms      1.00
cleanbrowsing-v6     1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms      1.00
cloudflare-v6        1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms      1.00
neustar              1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms      1.00
nextdns              1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms      1.00
quad9-v6             1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms      1.00
cloudflare           1 ms    1 ms    1 ms    1 ms    1 ms    2 ms    1 ms    1 ms    1 ms    1 ms      1.10
quad9                1 ms    1 ms    1 ms    2 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms      1.10
google               1 ms    1 ms    6 ms    1 ms    1 ms    6 ms    1 ms    7 ms    9 ms    7 ms      4.00
8.8.8.8              6 ms    1 ms    25 ms   1 ms    1 ms    6 ms    1 ms    7 ms    1 ms    7 ms      5.60
neustar-v6           1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    1 ms    64 ms     7.30
opendns-v6           7 ms    1 ms    21 ms   8 ms    1 ms    1 ms    1 ms    6 ms    1 ms    29 ms     7.60
opendns              1 ms    1 ms    27 ms   27 ms   1 ms    67 ms   1 ms    6 ms    1 ms    27 ms     15.90
comodo               1 ms    1 ms    1 ms    1 ms    4 ms    1 ms    1 ms    1 ms    1 ms    150 ms    16.20
google-v6            7 ms    6 ms    33 ms   7 ms    7 ms    87 ms   7 ms    8 ms    8 ms    25 ms     19.50
level3               27 ms   26 ms   25 ms   27 ms   27 ms   25 ms   27 ms   27 ms   25 ms   28 ms     26.40
norton               28 ms   26 ms   28 ms   26 ms   26 ms   28 ms   27 ms   27 ms   27 ms   27 ms     27.00
adguard-v6           52 ms   54 ms   55 ms   56 ms   52 ms   52 ms   52 ms   53 ms   53 ms   54 ms     53.30
adguard              58 ms   58 ms   58 ms   58 ms   60 ms   58 ms   60 ms   60 ms   58 ms   60 ms     58.80
freenom              140 ms  140 ms  140 ms  145 ms  135 ms  140 ms  140 ms  140 ms  140 ms  134 ms    139.40
yandex-v6            178 ms  179 ms  178 ms  179 ms  178 ms  178 ms  178 ms  179 ms  179 ms  205 ms    181.10
yandex               178 ms  178 ms  177 ms  179 ms  178 ms  174 ms  180 ms  178 ms  179 ms  222 ms    182.30

```



# For Windows users using the Linux subsystem

If you receive an error `$'\r': command not found`, convert the file to a Linux-compatible line endings using:

    tr -d '\15\32' < dnstest.sh > dnstest-2.sh
    
Then run `bash ./dnstest-2.sh`

Tanks For https://github.com/cleanbrowsing
