# ABRD based on the [CARD database](https://card.mcmaster.ca/download)

db_CARDS includes homolog and variant model for protein.

Sequences were aligned using [DIAMOND](https://github.com/bbuchfink/diamond)

```diamond blastx -d ~/db/CARD/CARD.dmnd --outfmt 6 stitle  -q {infasta} -o {out.txt} --max-target-seqs 1 -e 0.00000000000000001 --id 100 --query-cover 99```

Quick look at all uniq hits for bacteria
```cat  {out.txt} | cut -d'[' -f2 | sort | uniq```

Antibiotic Gene Reference Database:
[CARD](https://card.mcmaster.ca/)
[NCBI AMR DBS](https://www.ncbi.nlm.nih.gov/bioproject/PRJNA313047)
 **Download protein database from NCBI: ```esearch -db bioproject -query "PRJNA313047" | elink -target protein|efetch -format fasta > ncbi_antibiotic_database.faa```***
