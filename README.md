# shellcode_formatter

A tool to make the process of crafting custom shellcode payloads easier. Simply write your shellcode in assembly language, save it and run shellcode_formatter with the output format and your file as argument.


## Usage

If you shellcode is in *~/shellcodes/shellcode.s* and your target is a standard x64 machine run:
```
./shellcode_formatter elf64 ~/shellcodes/shellcode.s
```
The output will be something like:
```
Object saved in /tmp/9jI8TV6UTefeky8yzVnEC
Objcopy saved in /tmp/DbeBbPpcw9po8mWvgiKTe
Shellcode saved in /tmp/Pduo9bEjux9fFfDC6gV22

You can use the following payload in your script:
\x48\x31\xff\x48\x89\xf8\x48\xbf\xbc\x88\xa5\xb9\xbd\xcc\xa1\x01\x48\xc1\xef\x02\x57\x48\x89\xe7\x50\x50\x57\x48\x89\xe6\xba\x76\x00\x00\x00\x48\x92\x48\xd1\xe8\x0f\x05
```
You can simply copy-paste the payload in your python script. If you need to fine-tune details the different files generated are located in the `/tmp` directory as per the output.

At the moment this script only works with nasm as a compiler, to see the output formats available see `man nasm`

## Requirements

This script requires:
- nasm (`sudo apt install nasm`)
- objcopy (should already be installed on Linux distributions as part of the package binutils)
