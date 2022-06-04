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



### References for more deep knowledge

##### Zeltser Security Corp., 2020. REMnux (image) Retrieved from: https://remnux.org/
##### Sikorski, M. and Honig, A., 2012. Practical Malware Analysis. San Francisco: No Starch Press, pp.386-387.
##### Docs.microsoft.com. 2018. Processes And Threads - Win32 Apps. Retrieved from: https://docs.microsoft.com/en-us/windows/win32/procthread/processes-and-threads

### Additional Reading

* A Look At Entropy Analysis [https://fsec404.github.io/blog/Shanon-entropy/](https://fsec404.github.io/blog/Shanon-entropy/)
* BlackHat 2019 Investigating Malware Using Memory Forensics (Video)[https://www.youtube.com/watch?v=BMFCdAGxVN4](https://www.youtube.com/watch?v=BMFCdAGxVN4)
* Malware Threat Report - Q2 2020 (Avira) [https://www.avira.com/en/blog/malware-threat-report-q2-2020-statistics-and-trends](https://www.avira.com/en/blog/malware-threat-report-q2-2020-statistics-and-trends)
* Malware Detection in PDF and Office Documents: A survey [https://api.semanticscholar.org/CorpusID:212680542%20(P.%20Singh,%20S.%20Tapaswi,%20S.Gupta)](https://api.semanticscholar.org/CorpusID:212680542%20(P.%20Singh,%20S.%20Tapaswi,%20S.Gupta))

### Cheatsheets
* REMnux 7.0 Documentation [https://docs.remnux.org/](https://docs.remnux.org/)
* Volatility 2.4. Windows & Linux Profile Cheatsheets [https://downloads.volatilityfoundation.org/releases/2.4/CheatSheet_v2.4.pdf](https://downloads.volatilityfoundation.org/releases/2.4/CheatSheet_v2.4.pdf)

