### Sıfırdan bir Node.js projesi için aşamalar nelerdir?

- `docker pull ubuntu:18.04` komutu ile ubuntu image olarak yerel makineye çekilir.

- `docker run -it ubuntu:18.04` komutu ile (-it : interactive terminal) ubuntu container'ına girilir.

- `apt-get update` ile sistem güncellenir.

- `apt-get install curl -y` komutu ile gelen tüm sorulara `yes` cevabı verilecek şekilde `cURL` kurulumu yapılır.

- `curl -sL https://deb.nodesource.com/setup_10.x | bash ` komutu ile `curl` kullanılarak `node.js` indirilir.

- `apt-het install nodejs -y` komutu ile gelen tüm sorulara `yes` cevabı verilecek şekilde `node.js` kurulumu yapılır.

- `cd opt`, `mkdir node-app`, `cd node-app` komutları sayesinde `opt/node-app` dizini oluşturulur ve bu dizinin içine gidilir.

- `echo 'console.log("Nodejs App from Ubuntu")' > index.js` komutu ile `console.log` ifadesisi `index.js` dosyasına yazılır.

- `node index.js` komutu ile proje çalıştırılır.

### Dockerfile Oluştururken bu süreç nasıl işler?

- `FROM ubuntu:18.04` komutu ile base image belirlenir.

- `RUN apt-get update` ile güncellemelere ubuntu'nun up olduğu container üzerinde yapılır.

- `RUN apt-get install curl -y` ile curl ubuntu'nun up olduğu container üzerinde çalıştırılır.

- `RUN curl -sL https://deb.nodesource.com/setup_10.x | bash` ile gerekli kurulum yapılır.

- `RUN apt-get install nodejs -y` komutu ile ubuntu'nun up olduğu container üzerinde `node.js` kurulumu yapılır.

- `WORKDIR /opt/node-app` komutu ile çalışma dizini belirlenir.

- `COPY . .` komutu ile `Dockerfile`'ın bulunduğu dizindeki tüm dosyalar, `/opt/node-app` dizinine aktarılır.

- `CMD ["node", "index.js"]` komutu ile container ayağa kalktıktan sonra uygulamanın çalışması için gerekli komut verilmiş olur.

### Her şey tamam, nasıl çalışacak?

- `docker build . -t first-image` ile Dockerfile üzerinden **image** elde edilir.

- `docker images` komutu ile oluşturulan image, listede görünecektir.

- `docker run first-image` komutu ile images çalıştırılır ve container olarak `up` olur. `docker container ls --all` komutu ile tüm container'lar listelenir. Bu container'da orada kendine yer bulacaktır.
