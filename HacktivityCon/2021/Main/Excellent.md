### Excellent

With Volatility 3 

Search for openfiles.

```
#:> vol.py -f image.bin windows.filescan.FileScan
0xaa873a6567c0    \Users\congon4tor\Desktop\flag.ods    216
0xaa873ab2e740    \Users\congon4tor\Desktop\flag.ods    216
0xaa873df14610    \Users\congon4tor\Desktop\.~lock.flag.ods#    216
0xaa873df19750    \Users\congon4tor\AppData\Roaming\Microsoft\Windows\Recent\flag.lnk    216
```
Dump the memory space of 0xaa873ab2e740

```
#:> vol.py -f image.bin windows.dumpfiles.DumpFiles --virtaddr 0xaa873ab2e740
file.0xaa873ab2e740.0xaa873cf02050.SharedCacheMap.flag.ods.vacb
```
Then we open the file in MS Word/LibreWriter
