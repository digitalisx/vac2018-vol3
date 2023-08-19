<p align='center'><img src=https://static.wikia.nocookie.net/eldenring/images/f/f6/ER_Icon_Scroll_Royal_House.png height="256"></p>
<h1 align="center">VAC2018-VOL3</a></h1>
<p align="center">
  <em>VAC 2018 Practice on Volatility3 Framework</em>
</p>

> The authors of this [report](https://volatility-labs.blogspot.com/2018/11/results-from-annual-2018-volatility-contests.html) put together a realistic lab scenario modeled after Korean APT investigations they have performed. We were not only impressed by the number of Volatility plugins represented in the analysis efforts, but also that the infected systems spanned multiple operating systems (Windows and Linux). Memory analysis was leveraged to shed light on the toolkits and methodologies used by the attackers, including Eternal Blue, Dark Comet, Spear Phishing, HWP exploits, DLL injections, MongoDB vulnerabilities, and more. Evidence from Outlook PSTs were reconstructed from RAM and shellcode was explored and identified in memory using Yarascan, Volshell, and various other capabilities provided by Volatility.

## Introduction

This is a project to migrate key plugins and profiles to ensure a smooth hands-on experience with VAC 2018 in a Volatility3 environment.

## How to use?

```shell
> git clone https://github.com/digitalisx/vac2018-vol3.git
```

## Plugins

Most of your work will likely be merged into an official plugin rather than included here.

### VADTree (Draft)

```shell
> python3 vol.py -h
windows.vadtree.VadTree "Walk the VAD tree and display in tree format."
```

```shell
> python3 vol.py -f case.vmem -r pretty windows.vadtree --pid=508 
Volatility 3 Framework 2.3.0
Formatting...0.00               PDB scanning finished                        
         | PID |   Process |         Offset | Type |          Start |            End |  Tag
*        | 508 | csrss.exe | 0x97065bf58dd0 |  N/A |  0x1842f7a0000 |  0x1842f7a0fff | VadS
**       | 508 | csrss.exe | 0x97065bf575c0 |  N/A |  0x1842da00000 |  0x1842dbfffff | VadS
***      | 508 | csrss.exe | 0x97065bf58b00 |  N/A |   0x6086fc0000 |   0x6086ffffff | VadS
****     | 508 | csrss.exe | 0x97065bf57520 |  N/A |   0x6086e80000 |   0x6086ebffff | VadS
*****    | 508 | csrss.exe | 0x97065b6771f0 |  N/A |     0x7ffe2000 |     0x7ffe2fff | VadS
******   | 508 | csrss.exe | 0x97065b6777e0 |  N/A |     0x7ffe0000 |     0x7ffe0fff | VadS
```

https://github.com/volatilityfoundation/volatility3/pull/753

## Profiles

Note, this profile only supports `linux.psscan`.

```shell
> cp ubuntu1404.json ~/volatility3/volatility3/symbols/linux/ubuntu1404.json
```

## Organizer
- Dongbin Oh ([@sinsin9090](https://github.com/sinsin9090))
- Donghyun Kim ([@digitalisx](https://github.com/digitalisx))
- Seonho Lee ([@horensic](https://github.com/horensic))
- Suhyeon Jin ([@suhyeonjin](https://github.com/suhyeonjin))
