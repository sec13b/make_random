# Make random


Use `/dev/urandom` as the seed because pseudo-random numbers are sufficient.

* Character type is controlled by tr
* The number of characters is the fold command
* number of lines in head

```
$ cat /dev/urandom | tr -dc 'a-zA-Z0-9' | fold -w 16 | head -n 8
Qz5D4Ddy0CUTk7mU
FLbxZE5pls5tLCaJ
nAy4ApBXZGGEX0qQ
q9HRZk9panIlwS4V
C0YUOnYaA7CSwCil
BZ8KdSfs8sCKcYrr
ZDQTPabwm2c4m06D
dhHKEwCcL3JbyaKJ
```

If you want only uppercase letters, adjust like `tr -dc 'A-Z0-9'`.

```
$ cat /dev/urandom | tr -dc 'A-Z0-9' | fold -w 16 | head -n 8
04ES0JNSY6YFWWPR
EXT2R89QY5PZRISD
LA455ECHNW0ZH4H4
VVJ20UIXN7H8Y0W6
1M1JSGJOHB8IP0SN
F6ZHYDBX70THR1R9
67LJQHUXK31H0OKF
SIGHPVOQVORPAKDO
```
echo "ā, ä, ǟ, ḑ, ē, ī, ļ, ņ, ō, ȯ, ȱ, õ, ȭ, ŗ, š, ț, ū, ž." | sed -r 's/[^a-zA-Z0-9]+/-/g' | sed -r 's/^-+\|-+$//g' | tr A-Z a-z                  130 ↵
ā-ä-ǟ-ḑ-ē-ī-ļ-ņ-ō-ȯ-ȱ-õ-ȭ-ŗ-š-ț-ū-
