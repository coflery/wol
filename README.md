# wol.sh
wol.sh is a simple Wake-on-LAN shell script.

- [wol.sh](#wolsh)
  - [Download](#download)
  - [Compatibility](#compatibility)
  - [Before Use](#before-use)
  - [Syntax](#syntax)
  - [Examples](#examples)
  - [Why wol.sh](#why-wolsh)
  - [What is Wake-on-LAN or Wake-on-WLAN?](#what-is-wake-on-lan-or-wake-on-wlan)
  - [Licence](#licence)

## Download
- [Download the latest version of wol.sh (0.1)](https://github.com/leestevetk/wol.sh/releases/download/v0.1/WoL.sh) or [browse older versions](https://github.com/leestevetk/wol.sh/releases).
- __DISCLAIMER:__ wol.sh is currently at pre-release stage - users should exercise caution.

## Compatibility
wol.sh should *(but is not guaranteed to)* work on most __Mac__ or __Linux__ systems.  The author is using this utility on a macOS 10.15.3 system to wake up a Windows 10 PC, both on Wi-Fi.

## Before Use
Like any shell script, you must first make wol.sh executable.  This can be done by running in terminal (assuming wol.sh is located at `~/Desktop/wol.sh`):
```
chmod u+x ~/Desktop/wol.sh
```

## Syntax
```
wol.sh [MAC] [IP] [Port]
```
- `MAC`: __mandatory__, MAC address of the target machine
- `IP`: recommeded, the magic packet will be sent to this IP, default: 255.255.255.255 (broadcast to all IPs)
- `Port`: *optional*, the magic packet will be sent to this port, default: 9

## Examples

### Example 1 (Recommended)
```
~/Desktop/wol.sh 0F:1E:2D:3C:4B:5A 192.168.1.100
```
In this example:
- wol.sh is located at `~/Desktop/wol.sh`.
- The target computer's MAC address is `0F:1E:2D:3C:4B:5A`.
- This command will send a magic packet to `192.168.1.100` at port `9` (usual port for magic packets).  

### Example 2
```
~/Desktop/wol.sh 0F:1E:2D:3C:4B:5A 192.168.1.100 9000
```
In this example:
- wol.sh is located at `~/Desktop/wol.sh`.
- The target computer's MAC address is `0F:1E:2D:3C:4B:5A`.
- This command will send a magic packet to `192.168.1.100` at port `9000`.  It is usually unnecessary to specify the port unless port 9 of the target is blocked (e.g. by a firewall).

## Example 3
```
~/Desktop/wol.sh 0F:1E:2D:3C:4B:5A
```
In this example:
- wol.sh is located at `~/Desktop/wol.sh`.
- The target computer's MAC address is `0F:1E:2D:3C:4B:5A`.
- This command will broadcast a magic packet to all systems at port `9`.
- __This command has not been tested.__

## Why wol.sh
__wol.sh does not require installation.__  Most authors on the web recommend dedicated programs to perform Wake-on-LAN. A common example is "wakeonlan" for Macs.  These programs are well-tested and probably contain more features than wol.sh.  But there are many scenarios where installing a program is inappropriate or not allowed (e.g. on a company machine) or there may be  concerns over installing new software.

## What is Wake-on-LAN or Wake-on-WLAN?
A computer can be configured to wake from sleep when it receieves a special network message known as a "Magic Packet".  This technique is known as "Wake-on-LAN" (for a computer using a wired connection) or "Wake-on-WLAN" (for a computer using a wireless connection).  Read more on https://en.wikipedia.org/wiki/Wake-on-LAN

## Licence
wol.sh is distributed under the MIT License.
```
MIT License

Copyright (c) 2020 Steve's Toolkit

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
