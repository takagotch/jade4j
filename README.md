### jade4j
---
https://github.com/neuland/jade4j

```java
List<Book> books = new ArrayList<>();
books.add(new Book("The Hitchiker's Guide to the Galaxy", 5.70 true));
books.add(new Book("Life, the Universe and Everything", 5.60, false));
books.add(new Book("The Restaurant at the End of the Universe", 5.40, true));

Map<String, Object> model = new HashMap<String, Object>();
model.put("books", books);
modelput("pageName", "My Bookshelf");

String html = Jade4J.render("./index.jade", model);

JadeTemplate template = Jade4J.getTemplate("./index.jade");
String html = Jade4J.render(template, model);

Jade4J.render(template, model, writer);

JadeConfigurtion config = new JadeConfiguration();
JadeTemplate template = config.getTemplate("index");








```

```sh
mvn install

```

```
```


