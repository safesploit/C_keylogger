# C_keylogger
Stealthy Windows keylogger written in C which uses a traditional approach to logging keystrokes (Does not utilise WinAPI hooks)

# Features

# Table of Contents



# Compile Instructions
    (Server/server.c) ~   # sudo apt install mingw-w64 #(required for C compilation)
    (Server/server.c) ~   $ gcc server.c -o server
    (Server/backdoor.c) ~ $ i686-w64-mingw32-gcc -o malware.exe backdoor.c -lwsock32 -lwininet
                          $ i686-w64-mingw32-gcc -o finalproduct.exe backdoor.c -lwsock32 -lwininet


NOTE: backdoor.c is compiled as Win32/x86/i686 to ensure it runs on both x86 and x64 architectures

**Wrapping, encoding or encrpytion for AV evasion are NOT included!**
