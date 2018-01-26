FROM ubuntu

MAINTAINER Pedro J. Torres

# Installing wget to be able to download the DIAMOND sequence aligner
RUN  apt-get update \
  && apt-get install -y wget \
  && rm -rf /var/lib/apt/lists/*

# Installing diamond software, then extracting it finally adding that diamond
# binary file into our /usr/bin so we can execute it.
RUN wget http://github.com/bbuchfink/diamond/releases/download/v0.9.15/diamond-linux64.tar.gz \
&& tar xzf diamond-linux64.tar.gz \
&& mv ./diamond /usr/bin

# Helpful tips and commands
CMD echo 'Your current folder should contain at least 2 files. 1) Docker file and 2) Your Antimicrobial Resistant Gene database already built in diamond (NCBIATB.dmnd).The following script will help you analyze your data: diamond blastx -d NCBIATB.dmnd --outfmt 6 stitle -q query.fasta -o output.txt --max-target-seqs 1 -e 0.00000000000000000001 --id 80 --query-cover 90'
