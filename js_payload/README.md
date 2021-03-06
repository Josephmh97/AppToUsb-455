# PS4 4.55 Kernel Exploit
---
## Summary
In this project you will find a full implementation of the "bpf" kernel exploit for the PlayStation 4 on 4.55. It will allow you to run arbitrary code as kernel, to allow jailbreaking and kernel-level modifications to the system. This release however, *does not* contain any code related to defeating anti-piracy mechanisms or running homebrew. This exploit does include a loader that listens for payloads on port `9020` and will execute them upon receival.

This bug was discovered by qwertyoruiopz, and can be found hosted on his website [here](http://crack.bargains/455/).

## Patches Included
The following patches are made by default in the kernel ROP chain:
1) Disable kernel write protection
2) Allow RWX (read-write-execute) memory mapping
3) Syscall instruction allowed anywhere
4) Custom system call #11 (`kexec()`) to execute arbitrary code in kernel mode
5) Allow unprivileged users to call `setuid(0)` successfully. Works as a status check, doubles as a privilege escalation.

## Notes
- Early stages, so no payloads yet, I may provide a debug menu payload later on in the day.

## Contributors
Massive credits to the following:

- [qwertyoruiopz](https://twitter.com/qwertyoruiopz)
- [Flatz](https://twitter.com/flat_z)
- Anonymous
