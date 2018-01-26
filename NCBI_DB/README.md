docker build -t diamondatb .


docker run -v `pwd`:`pwd` -w `pwd` diamondatb diamond blastx -d NCBIATB.dmnd -q practice_insert.fa -o matches.m8
