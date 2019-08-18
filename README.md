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

Jade4J.render(template, model, writer);

JadeConfiguration config = new JadeConfiguration();
JadeTemplate template = config.getTemplate("index");
Map<String, Object> model = new HashMap<String, Object>();
model.put("company", "neuland");
config.renderTemplate(template, model);


JadeTemplate t1 = config.getTemplate("index.jade");
JadeTemplate t2 = config.getTemplate("index.jade");
t1.equals(t2)

config.clearCache();

config.setCaching(false);

config.setPrettyPrint(true);

config.setMode(Jade4J.Mode.HTML);
config.setMode(Jade4J.Mode.XHTML);
config.setMOde(Jade4J.Mode.XML);

config.setFilter("coffeescript", new CoffeeScriptFilter());

public class MathHelper {
  public long round(double number) {
    return Math.round(number);
  }
}

model.put("math", new MathHelper());

p= math.round(1.44);

Map<String, Object> defaults = new hashMap<String, Object>();
defaults.put("city", "Bremen");
defaults.put("country", "Germany");
defaults.put("url", new MyUrlHelper());
config.setSharedVariables(defaults);

TemplateLoader loader = new FileTemplateLoader("/templates/", "UTF-8");
config.setTemplateLoader(loader);
```

```sh
mvn install

```

```coffee
script
  :coffeescript
   sayHello
   
sayHello(function() {
  return alert("hello world");
});

- var book = {"price": 4.99, "title": "The Book"}
if book.price < 5.50 && !book.soldOut
  p.sale special offer: #{book.title}
  
each author in ["artur", "stefan", "micheal"]
  h2= author
  
- var book = {size: 540}
book.size
book["size"]
```


