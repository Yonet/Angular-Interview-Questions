#### What is the use case of services?

The main use case of Services is to move duplicated code into a single location, acting like a Singleton. It encourages DRY (Don't Repeat Yourself), which is a principle in Software Engineering, aimed at reducing repitition of information or code in a multi-layered architecture.

Services can serve as a method of interaction between an application and a data store. It also can provide communication channels between directives, as well as any other business logic access.

#### How are the services injected to your application?

There are two ways to inject a service into your application:

- Per Application: Provides the service at an application level
- Per Component: Provides the service at a component level (and all child components)

Providing a service at an application level or a higher level creates a single instance of that service and shares it with all sub directives. This is useful in the case of sharing properties or state between service holders.

Providing a service for every different component would create an instance for each of the components with separate resources.

Injecting a service can be done by importing the service and specifying it in the `NgModule`'s metadata array preperty `providers`, and inject it into the directive using it via the constructor. To inject a service into another service, annotate the target service class with `@Injectable`.

```ts
//annotation used for services injecting other services
@Injectable()
export class MessageService {
	//injected service
	constructor(private errorService: ErrorService){}
}
```

#### How do you unit test a service with a dependency?
[insert answer]

#### Why is it a bad idea to create a new service in a component like the one below?

```ts
let service = new DataService();
```

That's a bad idea for several reasons including:

Our component has to know how to create a DataService. If we ever change the DataService constructor, we'll have to find every place we create the service and fix it. Running around patching code is error prone and adds to the test burden.

We create a new service each time we use new. What if the service should cache data and share that cache with others? We couldn't do that.

We're locking the component into a specific implementation of the DataService. It will be hard to switch implementations for different scenarios. Can we operate offline? Will we need different mocked versions under test? Not easy.
