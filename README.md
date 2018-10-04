# ABRD based on the [NCBI antibiotic gene ressitant database](https://www.ncbi.nlm.nih.gov/bioproject/PRJNA313047)

 **Download protein database from NCBI: ```esearch -db bioproject -query "PRJNA313047" | elink -target protein|efetch -format fasta > ncbi_antibiotic_database.faa```**
*Keep in mind that the protein target can also be changed to nucleotide target if that is what you prefer.

Sequences were aligned using [DIAMOND](https://github.com/bbuchfink/diamond)

Once DIAMOND is downloaded create your database
```diamond makedb --in ncbi_antibiotic_database.faa -d NCBIATB```

The following is an example of how I typically run my command.
```diamond blastx -d ~/db/CARD/CARD.dmnd --outfmt 6 stitle  -q {infasta} -o {out.txt} --max-target-seqs 1 -e 0.00000000000000001 --id 100 --query-cover 99```

Quick look at all uniqe hits for bacteria
```cat  {out.txt} | cut -d'[' -f2 | sort | uniq```

## DIAMOND with docker
### Build docker
```bash
sudo docker build -t dmd NCBI_DB/

docker run -v `pwd`:`pwd` -w `pwd` dmd diamond blastx -d NCBI_DB/NCBIATB.dmnd -q NCBI_DB/practice_insert.fa -o matches.m8
```
Antibiotic Gene Reference Database:

[CARD](https://card.mcmaster.ca/)

[NCBI AMR DBS](https://www.ncbi.nlm.nih.gov/bioproject/PRJNA313047)



