## NEDEN?

`01-node-app-ubuntu` dizinde bulunan proje için base image olarak `ubuntu:18.04` base image'ini kullandık. Ancak zaten halihazırda `node.js` için tanımlı bir base image varken neden bu işlemleri uygulayalım?

- `FROM node:14-slim` komutu ile base image olarak kullanarak sonrasında sadece proje çalıştırma işlemlerini uygulayabiliriz.

- `docker build . -t simple-node-app-2` komutu ile image buil edilebilir.

- `docker run simple-node-app-2` komutu ile proje container olarak ayağa kaldırılır ve ekrana gerekli log ifadelerini yazar ve sonrasında sonlanır.
