## Link Two Container

- Dockerfile içerisinde gerekli ayarlamalar yapıldıktan sonra MongoDB için container ayağa kaldırılmalıdır.

- `docker images` komutu ile images listelendiğinde `mongo` yok ise; `docker pull mongo` ile image yerele çekilir.

- `docker run --name mongo-server -p 27017:27017 -d mongo` komutu ile mongo image'i container olarak `up` olur. İsim olarak `mongo-server` değerini alırken port olarak iç ve dışta 27017 PORT'u üzerinden ulaşılabilir. `-d` parametresi `detach` modda çalışır.

- `05-node-mongo-todo` dizinindeyken `docker build -t todo-app .` komutu ile dizinde bulunan `Dockerfile` kullanılarak image build edilir.

- Mongo için container çalışır durumda iken `docker run --link mongo-server:mongo-alias -p 4000:4000 todo-app` komutuyla birlikte ayakta olan mongo container'ına `link` keyword'ü ile bağlantı sağlanır. `mongo-server:mongo-alias` kısmında ise `mongo-server` adını kullanarak ayakta olan container'a code base'de `mongo-alias` ile bağlanılacağı belirtilmiştir.

- `app.js` dosyası içeriside `app.listen` yapılan alanda bu değer kullanılmıştır:

```
app.listen(PORT, async () => {
  console.log(`Sunucu çalışıyor... ${PORT} | MongoDB'ye bağlanılacak..`);
  // mongo-alias keyword'ü ile mongoDB'ye bağlanıyoruz. Mongo image'ı ayağa kaldırılırken bu alias ile kaldırılmalıdır !
  await Mongoose.connect("mongodb://mongo-alias:27017/todos", {
    . . .

```

- Bu işlemlerden sonra `localhost:4000` adresine atılacak `GET` isteği ile todo listesine erişilir.

- `localhost:4000/todo` adresine atılacak ve body içerisinde JSON formatında aşağıdaki gibi bir data ile `POST` isteği atıldığında liste todo oluşturulur. :

```
{
  "title": "Docker Deneme 1",
  "description": "Docker üzerinden POST request",
  "completed": false
}
```
