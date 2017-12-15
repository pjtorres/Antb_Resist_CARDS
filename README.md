# ABRD based on the [CARD database](https://card.mcmaster.ca/download)

db_CARDS includes homolog and variant model for protein.

Sequences were aligned using [DIAMOND](https://github.com/bbuchfink/diamond)

```diamond blastx -d ~/db/CARD/CARD.dmnd --outfmt 6 stitle  -q {infasta} -o {out.txt} --max-target-seqs 1 -e 0.00000000000000001 --id 100 --query-cover 99```
