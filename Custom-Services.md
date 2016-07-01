# Custom Services

Assuming you have already read [Service Basics](), the process of implementing you own service is very straightforward. Simply implement the methods you want to expose.

By default, a service will throw a `405 Method Not Allowed` error if you haven't written any logic to handle a given method. This means you only need to write handlers for operations you plan to actually have carried out.

Do make sure to invoke the `super` constructor in any of your constructors, as that's where services set up their routes. Without it, your service will not be accessible to the Internet, as it will not have any front-facing routes set up at all.

```dart
class MyService extends Service {
  MyService():super() {
    // Feel free to add your own constructor, just don't
    // neglect the `super`...
  }
}
```