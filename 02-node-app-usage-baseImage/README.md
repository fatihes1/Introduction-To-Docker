## NEDEN?

`01-node-app-ubuntu` dizinde bulunan proje için base image olarak `ubuntu:18.04` base image'ini kullandık. Ancak zaten halihazırda `node.js` için tanımlı bir base image varken neden bu işlemleri uygulayalım?

- `FROM node:14-slim` komutu ile base image olarak kullanarak sonrasında sadece proje çalıştırma işlemlerini uygulayabiliriz.
