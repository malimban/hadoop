# dataset

wget https://www.cs.cmu.edu/~./enron/enron_mail_20150507.tar.gz

tar xvzf enron...tar.gz

- how to make everything one file
- also UTF-8 encoding?

## combine to one file

find ./maildir/ -type f -exec  cat {} + >> output
