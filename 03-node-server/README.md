## Notlar

- `.dockerignore` dosyası sayesibde aynı `.gitignore`'da olduğu gibi dosyaların kopyalanmasını engeller. Yani;
  dockerignore dosyası içerisinde `node_modules/` satırı olduğu için bu dosya `Dockerfile` içerisinde bulunan `COPY . .` komutu çalışırken kopyalanmayacaktır. Zaten `node_modules/` dosyasının oluşturulması için sonraki satılarda `RUN npm i` komutu kullanılmıştır.

- `docker build -t simple-node-server` komutuyla beraber image build edilir.

- `docker run -p 3001:3000 simple-node-server` komutuyla birlikte ise `localhost:3001` üzerinde proje ayağa kalkmış olacaktır.
