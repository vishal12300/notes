## REMnux: A Linux Toolkit for Malware Analysis
REMnux® is a Linux toolkit for reverse-engineering and analyzing malicious software. REMnux provides a curated collection of free tools created by the community. Analysts can use it to investigate malware without having to find, install, and configure the tools

#### PDF's are capable of containing many more types of code that can be executed without the user's knowledge. This includes:
* Javascript
* Python
* Executables
* Powershell Shellcode

#### Using peepdfto begin a precursory analysis of a PDF file to determine the presence of Javascript. If there is, we will extract this Javascript code (without executing it) for our inspection.
Command
```
peepdf demo_notsuspicious.pdf
```

### Analysing Malicious Microsoft Office Macros
Malware infection via malicious macros (or scripts within Microsoft Office products such as Word and Excel) are some of the most successful attacks to date.
We can simply use REMnux's ` vmonkey ` which is a parser engine that is capable of analysing visual basic macros without executing (opening the document).
Command
```
vmonkey DefinitelyALegitInvoice.doc
```
## Entropy
The measure of randomness of data in a file is known as entropy. Entropy is very useful in identifying compressed and packed malware. Packed or compressed files usually have a high entropy.
At it's very simplest, file entropy is a rating that scores how random the data within a PE file is. With a scale of 0 to 8. 0 meaning the less "randomness" of the data in the file, where a scoring towards 8 indicates this data is more "random".
For example, files that are encrypted will have a very high entropy score. Where files that have large chunks of the same data such as "1's" will have a low entropy score.



