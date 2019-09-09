# Assignment1
  cd ~
  /bin/bash
  perl -MNet::FTP -e \
    '$ftp = new Net::FTP("ftp.ncbi.nlm.nih.gov", Passive => 1);
     $ftp->login; $ftp->binary;
     $ftp->get("/entrez/entrezdirect/edirect.tar.gz");'
  gunzip -c edirect.tar.gz | tar xf -
  rm edirect.tar.gz
  builtin exit
  export PATH=${PATH}:$HOME/edirect >& /dev/null || setenv PATH "${PATH}:$HOME/edirect"
  ./edirect/setup.sh
esearch -db pubmed -query "lycopene cyclase" | efetch -format abstract
esearch -db pubmed -query "lycopene cyclase" | efetch -format abstract > pubmed.090419.v1.txt
pip install Wordcloud
pip install Wordcloud --user
vim pubmed.090419.v1.txt
:%s/\n/ /g
:wq
wordcloud_cli --text pubmed.090419.v1.txt --imagefile wordcloud.png
rsync -avz maiacorpuz@trgn.usc.edu:~/wordcloud.png ~/Desktop (local .bash_profile)
esearch -db pubmed -query "rna crosslinking" | efetch -format abstract > pubmed.090419.v1.txt
wordcloud_cli --text pubmed.090419.v1.txt --image wordcloud.png
