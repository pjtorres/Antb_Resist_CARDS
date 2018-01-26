Your current folder should contain at least 2 files. 1) Docker file and 2) Your Antimicrobial Resistant Gene database already built in diamond (NCBIATB.dmnd). The third file is practice_insert.fa which is a test file. The following commands shoud result in one hit.


```docker build -t diamondatb .```


```docker run -v `pwd`:`pwd` -w `pwd` diamondatb diamond blastx -d NCBIATB.dmnd -q practice_insert.fa -o matches.m8```



