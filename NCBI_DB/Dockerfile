FROM ubuntu#need to add verison

MAINTAINER Pedro J. Torres

# Installing wget to be able to download the DIAMOND sequence aligner
RUN apt update && \
	apt-get install -y build-essential wget unzip  git  bats awscli curl

# Installing diamond software, then extracting it finally adding that diamond
# binary file into our /usr/bin so we can execute it.
RUN wget http://github.com/bbuchfink/diamond/releases/download/v0.9.15/diamond-linux64.tar.gz \
&& tar xzf diamond-linux64.tar.gz \
&& mv diamond /usr/bin



RUN chmod +x /usr/bin/diamond
