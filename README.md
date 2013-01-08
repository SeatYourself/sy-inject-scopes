# sy-inject-scopes
__________________

Special singleton scopes for Guice:

-   __LazySingletonScope__: Lazy creation of singletons even in PRODUCTION stage
    
-   __ConcurrentSingletonScope__: Eager asynchronous creation of singletons

To use, annotate classes with @LazySingleton or @ConcurrentSingleton and install an instance of SingletonScopesModule when creating your injector.

```java
@LazySingleton
public class HeavyOptionalService {
    ...
}

@ConcurrentSingleton
public class CreateMeInBackground {
    ...
}

Injector injector = Guice.createInjector(
    new SingletonScopesModule(),
    ... other modules
);
```
    
See this posting for a link to my original blog entry about ConcurrentSingleton, with some caveats on its use:

https://groups.google.com/d/msg/guava-discuss/NazZoQs80oE/hnIqSAt3Iy8J

___________________

Copyright &copy; 2012-2013 Seat Yourself