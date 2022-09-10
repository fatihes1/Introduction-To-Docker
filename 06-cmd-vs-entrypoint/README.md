# Notelar

- `docker build -t ubuntu-sleeper .` komutu ile dizinde bulunan Dockerfile kullanılarak `ubuntu-sleeper` adlı bir image oluşturulur.

- `docker run ubuntu-sleeper 5` komutu ile 5 saniye durması ve sonra kapanması sağlanır. Eğer parametre olarak verilen 5 gibi bir değer girilmez ise varsayılan (defaul) değer olarak bir sonraki satırda bulunan `10` değeri kullanılır.

- Yani; `docker run ubuntu-sleeper` komutu ile `docker run ubuntu-sleeper 10` komutu aynı işi yapmış olur.

- `ENTRYPOINT` ile `CMD` farklı en basitinde böyledir.
