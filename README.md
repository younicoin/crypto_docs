# Crypto Docs

Documents related to crypto.

### lbtcftcl-v220.pdf

From here https://github.com/BlockchainCommons/Learning-Bitcoin-from-the-Command-Line \
MD files converted to pdf and merged like this:

<pre>
sudo apt install wkhtmltopdf
pip install grip
git clone https://github.com/BlockchainCommons/Learning-Bitcoin-from-the-Command-Line.git
cd Learning-Bitcoin-from-the-Command-Line
mkdir /tmp/learnbitcoin; while read l; do for i in `ls ${l}_*`; do grip $i 6699 & sleep 10; wkhtmltopdf http://localhost:6699 /tmp/learnbitcoin/${i}.pdf; sleep 10; fuser 6699/tcp -k; done; done < <(echo `seq -w 20` A1 A2 A3 | tr ' ' '\n')
qpdf --empty --pages `ls -tr /tmp/learnbitcoin/*.pdf` -- ../lbtcftcl-v220.pdf
</pre>
