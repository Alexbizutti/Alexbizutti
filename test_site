#!/bin/bash

#Test captura de site

if [ $1 == " " ]
then
        echo "Test scan"
        echo "$0 www.exemplo.com.br"

else
wget $1
fi
#Criar lista das urls
grep href index.html | cut -d "/" -f 3 |grep "\.com" |grep -v "<di" | grep -v "<l" | grep -v "<a" | grep -v "a>" | sort |uniq | cut -d "'" -f 1 |cut -d '"' -f 1 > lista.txt

#Remove o arquivo index.html
rm -f index.html

#Descoberta de IP
for url in $(cat lista.txt);
do host $url | grep "has address" >>resolvido.txt;
done
nl resolvido.txt
rm -f resolvido.txt
