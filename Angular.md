# Angular topics

Source:
- https://angular.io/docs
- https://www.udemy.com/course/the-complete-guide-to-angular-2/


## Basics

### Getting started with Angular

- What is Angular?
```a
Angular is a development platform, built on TypeScript. As a platform, Angular includes:

- A component-based framework for building scalable web applications
- A collection of well-integrated libraries that cover a wide variety of features, including routing, forms management, client-server communication, and more
- A suite of developer tools to help you develop, build, test, and update your code

With Angular, you're taking advantage of a platform that can scale from single-developer projects to enterprise-level applications. Angular is designed to make updating as straightforward as possible, so take advantage of the latest developments with a minimum of effort. Best of all, the Angular ecosystem consists of a diverse group of over 1.7 million developers, library authors, and content creators.
```
- What elements are there in Angular (Angular Vocabulary)?
```a
Component:
- A class with the @Component() decorator that associates it with a companion template. Together, the component class and template define a view. A component is a special type of directive. The @Component() decorator extends the @Directive() decorator with template-oriented features.
- An Angular component class is responsible for exposing data and handling most of the view's display and user-interaction logic through data binding.

Directive:
- A class that can modify the structure of the DOM or modify attributes in the DOM and component data model. A directive class definition is immediately preceded by a @Directive() decorator that supplies metadata.
- A directive class is usually associated with an HTML element or attribute, and that element or attribute is often referred to as the directive itself. When Angular finds a directive in an HTML template, it creates the matching directive class instance and gives the instance control over that portion of the browser DOM.
- There are three categories of directive:
	- Components use @Component() (an extension of @Directive()) to associate a template with a class.
	- Attribute directives modify behavior and appearance of page elements.
	- Structural directives modify the structure of the DOM.
- Angular supplies a number of built-in directives that begin with the ng prefix. You can also create new directives to implement your own functionality. You associate a selector (an HTML tag such as <my-directive>) with a custom directive; this extends the template syntax that you can use in your applications.
- UpperCamelCase, such as NgIf, refers to a directive class. You can use UpperCamelCase when describing properties and directive behavior.
- lowerCamelCase, such as ngIf refers to a directive's attribute name. You can use lowerCamelCase when describing how to apply the directive to an element in the HTML template.

Injectable:
- An Angular class or other definition that provides a dependency using the dependency injection mechanism. An injectable service class must be marked by the @Injectable() decorator. Other items, such as constant values, can also be injectable.

Injector:
- An object in the Angular dependency-injection system that can find a named dependency in its cache or create a dependency using a configured provider. Injectors are created for NgModules automatically as part of the bootstrap process and are inherited through the component hierarchy.
	- An injector provides a singleton instance of a dependency, and can inject this same instance in multiple components.
	- A hierarchy of injectors at the NgModule and component level can provide different instances of a dependency to their own components and child components.
	- You can configure injectors with different providers that can provide different implementations of the same dependency.

NgModule:
- A class definition preceded by the @NgModule() decorator, which declares and serves as a manifest for a block of code dedicated to an application domain, a workflow, or a closely related set of capabilities.
- Like a JavaScript module, an NgModule can export functionality for use by other NgModules and import public functionality from other NgModules. The metadata for an NgModule class collects components, directives, and pipes that the application uses along with the list of imports and exports. See also declarable.
- NgModules are typically named after the file in which the exported thing is defined. For example, the Angular DatePipe class belongs to a feature module named date_pipe in the file date_pipe.ts. You import them from an Angular scoped package such as @angular/core.
- Every Angular application has a root module. By convention, the class is called AppModule and resides in a file named app.module.ts.

Observable:
- A producer of multiple values, which it pushes to subscribers. Used for asynchronous event handling throughout Angular. You execute an observable by subscribing to it with its subscribe() method, passing callbacks for notifications of new values, errors, or completion.
- Observables can deliver single or multiple values of any type to subscribers, either synchronously (as a function delivers a value to its caller) or on a schedule. A subscriber receives notification of new values as they are produced and notification of either normal completion or error completion.
- Angular uses a third-party library called Reactive Extensions (RxJS).

Observer:
- An object passed to the subscribe() method for an observable. The object defines the callbacks for the subscriber.

Pipe:
- A class which is preceded by the @Pipe{} decorator and which defines a function that transforms input values to output values for display in a view. Angular defines various pipes, and you can define new pipes.

Service:
- In Angular, a class with the @Injectable() decorator that encapsulates non-UI logic and code that can be reused across an application. Angular distinguishes components from services to increase modularity and reusability.
- The @Injectable() metadata allows the service class to be used with the dependency injection mechanism. The injectable class is instantiated by a provider. Injectors maintain lists of providers and use them to provide service instances when they are required by components or other services.

Structural directives:
- A category of directive that is responsible for shaping HTML layout by modifying the DOM—that is, adding, removing, or manipulating elements and their children.

Template:
- Code that defines how to render a component's view.
- A template combines straight HTML with Angular data-binding syntax, directives, and template expressions (logical constructs). The Angular elements insert or calculate values that modify the HTML elements before the page is displayed. Learn more about Angular template language in the Template Syntax guide.
- A template is associated with a component class through the @Component() decorator. The template code can be provided inline, as the value of the template property, or in a separate HTML file linked through the templateUrl property.
- Additional templates, represented by TemplateRef objects, can define alternative or embedded views, which can be referenced from multiple components.
```

- How is it different from other frameworks?
```a
1. Automatic synchronization with two-way data binding
Unlike some of the other frameworks that offer one-way data binding, the Angular framework provides two-way data binding. It seamlessly synchronizes the data between Model as well as View. Hence, when data is modified or changed, these two components get updated automatically in real-time. Otherwise, developers would have to manually make those changes which require additional efforts and consumes more time.

2. Bug fixes
With the latest Angular version, there have been a number of bug fixes and issues in compiler, route, core, service workers, modules and others have been resolved. Another bug fix ensures proper identification of modules affected by commands in TestBed.

3. Code consistency and reusability
Code consistency is the foundation for a strong development environment to be successful. Thanks to the Angular CLI (command line interface) and documentation style guide, they both drive consistency at the pioneer level. Angular CLI tool enables the Angular developers to create initial projects, perform tests and integrate diverse features in the same project while keeping the entire team on the same page.

Moreover, with Angular, the investment of time and effort is relatively less as it enables the reuse of codes and simplifies the development process. Also, it allows developers to include more functionalities with shorter codes, making it productive for the development team working on similar projects back to back.

4. Default Ivy renderer
The new Angular engine is comprised of features such as highly optimized bundle sizes and faster component loading. With Ivy renderer, enterprises can get incomparable code debugging and a user-friendly app experience. Moreover, it makes the framework more accessible and sets an instance by reducing the file sizes making this framework a feature-rich platform for app development.

5. Declarative UI
The Angular framework leverages HTML that when compared to JavaScript is a less complex language. HTML is also popular as a declarative and intuitive language that eliminates the need to invest a lot of time in program flows and planning what loads first. Angular developers just need to map out what is needed and the framework will do the rest.

6. Supported by Google:
Google is one of the biggest firms in technology and the talented pool of Google developers are offering Long-Term Support (LTS) for Angular to scale up enterprise Angular applications development. Also, a lot of big brands such as Netflix, Gmail, YouTube TV, Upwork and others use the Angular framework.
```

- Angular-command line interface

The Angular CLI is a command-line interface tool that you use to initialize, develop, scaffold, and maintain Angular applications directly from a command shell.

```a
- ng add
- ng build
- ng config
- ng deploy
- ng generate
- ng new
- ng run
- ng serve
- ng test
- ng update
- ng version
```

### Components

- Component decorators
```a
Component decorator allows you to mark a class as an Angular component and provide additional metadata that determines how the component should be processed, instantiated and used at runtime.

Example:
@Component({selector: 'greet', template: 'Hello {{name}}!'})
class Greet {
  name: string = 'World';
}

Metadata Properties:
- animations - list of animations of this component
- changeDetection - change detection strategy used by this component
- encapsulation - style encapsulation strategy used by this component
- entryComponents - list of components that are dynamically inserted into the view of this component
- exportAs - name under which the component instance is exported in a template
- host - map of class property to host element bindings for events, properties and attributes
- inputs - list of class property names to data-bind as component inputs
- interpolation - custom interpolation markers used in this component's template
- moduleId - ES/CommonJS module id of the file in which this component is defined
- outputs - list of class property names that expose output events that others can subscribe to
- providers - list of providers available to this component and its children
- queries - configure queries that can be injected into the component
- selector - css selector that identifies this component in a template
- styleUrls - list of urls to stylesheets to be applied to this component's view
- styles - inline-defined styles to be applied to this component's view
- template - inline-defined template for the view
- templateUrl - url to an external file containing a template for the view
- viewProviders - list of providers available to this component and its view children
```

- Parent - Child interaction using `@Input`
```a
This is probably the most common and straightforward method of sharing data. It works by using the @Input() decorator to allow data to be passed via the template.
```

- Child - Parent interaction using `@Output` and `EventEmitter`
```a
Another way to share data is to emit data from the child, which can be listed to by the parent. This approach is ideal when you want to share data changes that occur on things like button clicks, form entires, and other user events.

In the parent, we create a function to receive the message and set it equal to the message variable.

In the child, we declare a messageEvent variable with the Output decorator and set it equal to a new event emitter. Then we create a function named sendMessage that calls emit on this event with the message we want to send. Lastly, we create a button to trigger this function.

The parent can now subscribe to this messageEvent that’s outputted by the child component, then run the receive message function whenever this event occurs.
```

- Child - Parent interaction using `ViewChild`
```a
ViewChild allows a one component to be injected into another, giving the parent access to its attributes and functions. One caveat, however, is that child won’t be available until after the view has been initialized. This means we need to implement the AfterViewInit lifecycle hook to receive the data from the child.
```

- Unrelated Components: Sharing Data with a Service
```a
When passing data between components that lack a direct connection, such as siblings, grandchildren, etc, you should use a shared service. When you have data that should always be in sync, I find the RxJS BehaviorSubject very useful in this situation.

You can also use a regular RxJS Subject for sharing data via the service, but here’s why I prefer a BehaviorSubject.
- It will always return the current value on subscription — there is no need to call onnext
- It has a getValue() function to extract the last value as raw data.
- It ensures that the component always receives the most recent data.

In the service, we create a private BehaviorSubject that will hold the current value of the message. We define a currentMessage variable handle this data stream as an observable that will be used by the components. Lastly, we create function that calls next on the BehaviorSubject to change its value.

The parent, child, and sibling components all receive the same treatment. We inject the DataService in the constructor, then subscribe to the currentMessage observable and set its value equal to the message variable.

Now if we create a function in any one of these components that changes the value of the message. when this function is executed the new data it’s automatically broadcast to all other components.
```

- What is the difference between Component and Directive?
```a
1. A component is always elements (‘E’) where directive can be an attribute, element name, comment or CSS class (‘E’, ‘A’, ‘C’, ‘M’). Templates are the mandatory property and always required in Component, but Directive doesn’t always require them.

2. Component is used to break up the application into smaller components. But Directive is used to design re-usable components, which is more behavior-oriented. That is why components are widely used in later versions of Angular to make things easy and build a total component-based model.

3. As Component has views, viewEncapsulation can be defined. Whereas Directive doesn’t have views. So you can’t use viewEncapsulation in directive.

4. Although Components make it easier to write simple, effective code, it has a simpler configuration than plain directives, it is optimized for component-based architecture. But when not to use a component? The answer is – a component does not support “compile” and “pre-link” functions. So for manipulating DOM objects, we should use the directives.

- Components should never modify any data or DOM that is out of their own scope. Directives have isolated scopes, by default the child inherits the scope from its parent.
- Only one component can be present per DOM element. There can be more than one directive in a DOM element
- To register component we use @Component meta-data annotation. For directive, we use @Directive meta-data annotation. Two simple examples are shown in the point ‘Example’ above.
```
- `ng-content`
```a
They are used to create configurable components. This means the components can be configured depending on the needs of its user. This is well known as Content Projection. Components that are used in published libraries make use of <ng-content> to make themselves configurable.
```

### Modules

- What is module?
```a
Angular applications are modular and Angular has its own modularity system called NgModules. NgModules are containers for a cohesive block of code dedicated to an application domain, a workflow, or a closely related set of capabilities. They can contain components, service providers, and other code files whose scope is defined by the containing NgModule. They can import functionality that is exported from other NgModules, and export selected functionality for use by other NgModules.

Every Angular application has at least one NgModule class, the root module, which is conventionally named AppModule and resides in a file named app.module.ts. You launch your application by bootstrapping the root NgModule.
```

- Explain module properties
```a
An NgModule is defined by a class decorated with @NgModule(). The @NgModule() decorator is a function that takes a single metadata object, whose properties describe the module. The most important properties are as follows.
- declarations: The components, directives, and pipes that belong to this NgModule.
- exports: The subset of declarations that should be visible and usable in the component templates of other NgModules.
- imports: Other modules whose exported classes are needed by component templates declared in this NgModule.
- providers: Creators of services that this NgModule contributes to the global collection of services; they become accessible in all parts of the application. (You can also specify providers at the component level.)
- bootstrap: The main application view, called the root component, which hosts all other application views. Only the root NgModule should set the bootstrap property.
```

- Module scopes
```a
When the service is registered in providers array in one @NgModule, we say its service in the module.

There are two different scenarios to cover when one service is provided in Angular Module:
- Service is provided in the root module or in an eagerly loaded module – The Angular DI mechanism will use a Root Module Injector and will create one service instance which will be shared between the root module and eagerly loaded modules (all providers from all imported modules are merged into the root injector)
- Service is provided in a lazy-loaded module – The Angular DI mechanism will use Lazy Module (child injector) and will create one instance for every different lazy-loaded module where it is provided
```

- What is the difference between importing Service and Component from different modules?
```a
Creating shared modules allows you to organize and streamline your code. You can put commonly used directives, pipes, and components into one module and then import just that module wherever you need it in other parts of your application.

Importing Component:
- Export Component 1 from Module 1
- Import Module 1 inside Module 2
- You can use Component 1 inside Component 2

Importing Service:
- Import the service from file
- Insert it in @NgModule decorator in provicers array
```

- Circular Dependency
```a
Circular dependency occurs when service A injects service B, but service B in turn injects service A, usually indirectly. For example, B depends on service C which depends on A – A -> B -> C -> A forms a circle.
```

### Pipes

- What are pipes?
```a
Use pipes to transform strings, currency amounts, dates, and other data for display. Pipes are simple functions to use in template expressions to accept an input value and return a transformed value. Pipes are useful because you can use them throughout your application, while only declaring each pipe once.

Angular provides built-in pipes for typical data transformations, including transformations for internationalization (i18n), which use locale information to format data. The following are commonly used built-in pipes for data formatting:
- DatePipe: Formats a date value according to locale rules.
- UpperCasePipe: Transforms text to all upper case.
- LowerCasePipe: Transforms text to all lower case.
- CurrencyPipe: Transforms a number to a currency string, formatted according to locale rules.
- DecimalPipe: Transforms a number into a string with a decimal point, formatted according to locale rules.
- PercentPipe: Transforms a number to a percentage string, formatted according to locale rules.
```

- What are parameterized pipes?
```a
In Angular, we can pass any number of parameters to the pipe using a colon (:) and when we do so, it is called Angular Parameterized Pipes.
```

- How do you chain pipe?
```a
The chaining Pipe is used to perform the multiple operations within the single expression. This chaining operation will be chained using the pipe (|).
```

- What is custom pipe?
```a
Create custom pipes to encapsulate transformations that are not provided with the built-in pipes. Then, use your custom pipe in template expressions, the same way you use built-in pipes—to transform input values to output values for display.
```

### Directives

- What are directives?
```a
Directives are classes that add additional behavior to elements in your Angular applications. Use Angular's built-in directives to manage forms, lists, styles, and what users see.

Directives are the functions which will execute whenever Angular compiler finds it. Angular Directives enhance the capability of HTML elements by attaching custom behaviors to the DOM.

From the core concept, Angular directives are categorized into three categories:
- Attribute Directives
- Structural Directives
- Components
```

- What are they used for (examples)?
```a
Adding and removing classes with NgClass

On the element you'd like to style, add [ngClass] and set it equal to an expression. In this case, isSpecial is a boolean set to true in app.component.ts. Because isSpecial is true, ngClass applies the class of special to the <div>:
```
```
<div [ngClass]="isSpecial ? 'special' : ''">This div is special</div>
```

- Build-in Directives
```a
Attribute directives listen to and modify the behavior of other HTML elements, attributes, properties, and components.

Many NgModules such as the RouterModule and the FormsModule define their own attribute directives. The most common attribute directives are as follows:
- NgClass — adds and removes a set of CSS classes.
- NgStyle — adds and removes a set of HTML styles.
- NgModel — adds two-way data binding to an HTML form element.
```

- Structural directives `ngIf` and `ngFor`
```a
ngIf:
- A structural directive that conditionally includes a template based on the value of an expression coerced to Boolean. When the expression evaluates to true, Angular renders the template provided in a then clause, and when false or null, Angular renders the template provided in an optional else clause. The default template for the else clause is blank.

ngFor:
- The core directive ngFor allows us to build data presentation lists and tables in our HTML templates.
- With ngFor we can print this data to the screen under the form of a data table, by generating HTML
```

- Custom Directives
```a
Attribute directive also called custom directives are used when no additional template is needed. The directive can execute logic and apply visual changes to the element it is applied to. This is useful if you want to alter the behavior or style of existing HTML-elements, without wrapping them into a new component.

Creating a custom directive is easy. Just create a new class and decorate it with the @Directive decorator.

We need to make sure that the directive is declared in the corresponding (app-) module before we can use it. If you are using the angular-cli this should be done automatically.
```

### Templates

- What is template?
```a
You define a component's view with its companion template. A template is a form of HTML that tells Angular how to render the component.

Views are typically arranged hierarchically, allowing you to modify or show and hide entire UI sections or pages as a unit. The template immediately associated with a component defines that component's host view. The component can also define a view hierarchy, which contains embedded views, hosted by other components.

A view hierarchy can include views from components in the same NgModule, but it also can (and often does) include views from components that are defined in different NgModules.
```

- Ways of showing data inside templates?
```a
We can display data in Angular by putting in a JavaScript expression in the template. To reference variables, we can declare them as fields in our component and the reference them our template. We can display items conditionally with *ngIf directive and render arrays and other iterable objects with *ngFor directive.

Ways of doing that:
- template file - in the separate template file with double curly bracets around the variable
- inline - in the template property under the @Component decorator directly in the .ts file
```

- Template expressions and template statements
```a
Template statements:
- Template statements are methods or properties that you can use in your HTML to respond to user events. With template statements, your application can engage users through actions such as displaying dynamic content or submitting forms.
- Use template statements with elements, components, or directives in response to events:
<button (click)="deleteHero()">Delete hero</button>

Template expressions:
- A template expression produces a value and appears within the double curly braces, {{ }}. Angular executes the expression and assigns it to a property of a binding target; the target could be an HTML element, a component, or a directive.
- The interpolation braces in {{1 + 1}} surround the template expression 1 + 1. In the property binding, a template expression appears in quotes to the right of the = symbol as in [property]="expression".
- In terms of syntax, template expressions are similar to JavaScript. Many JavaScript expressions are legal template expressions, with a few exceptions.
```

- Data bindings
```a
Data binding is a technique, where the data stays in sync between the component and the view. Whenever the user updates the data in the view, Angular updates the component. When the component gets new data, the Angular updates the view.

There are many uses of data binding. You can show models to the user, dynamically Change element style, respond to user events, etc...
```

```a
- One way binding - in one way binding data flows from one direction. Either from view to component or from component to view:
	- From Component to View:
		- Interpolation - {{ templateExpression }}
		- Property binding - [binding-target]=”binding-source”
		- Attribute binding - <button [attr.aria-label]="closeLabel" (onclick)="closeMe()">X</button>
	- From View to Component:
		- Event Binding - <button (click)="onSave()">Save</button>

- Two Way binding - two-way binding means that changes made to our model in the component are propagated to the view and that any changes made in the view are immediately updated in the underlying component. The two-way binding uses the special syntax known as a banana in a box [()] ->
```
```
<someElement [(someProperty)]="value"></someElement>
```
```a
	- ngModel -The Angular uses the ngModel directive to achieve the two-way binding on HTML Form elements. It binds to a form element like input, select, selectarea. etc.
```
```
<input type="text" name="value" [(ngModel)]="value">
```

- `ng-container`
```a
The <ng-container> can be used to hold directives without creating an HTML element.

The ng-container directive provides us with an element that we can attach a structural directive to a section of the page, without having to create an extra element just for that.
```

- `ng-template`
```a
Like the name indicates, the ng-template directive represents an Angular template: this means that the content of this tag will contain part of a template, that can be then be composed together with other templates in order to form the final component template.

Angular is already using ng-template under the hood in many of the structural directives that we use all the time: ngIf, ngFor and ngSwitch.
```

- Template Variables
```a
Template variables help you use data from one part of a template in another part of the template. Use template variables to perform tasks such as respond to user input or finely tune your application's forms.

A template variable can refer to the following:
- a DOM element within a template
- a directive
- an element
- TemplateRef
- a web component
```
```
<input #phone placeholder="phone number" />
```

### Services and Dependency Injection

- What is service?
```a
Service is a broad category encompassing any value, function, or feature that an application needs. A service is typically a class with a narrow, well-defined purpose. It should do something specific and do it well.

Angular distinguishes components from services to increase modularity and reusability. By separating a component's view-related functionality from other kinds of processing, you can make your component classes lean and efficient.

A component can delegate certain tasks to services, such as fetching data from the server, validating user input, or logging directly to the console. By defining such processing tasks in an injectable service class, you make those tasks available to any component. You can also make your application more adaptable by injecting different providers of the same kind of service, as appropriate in different circumstances.

Angular doesn't enforce these principles. Angular does help you follow these principles by making it easy to factor your application logic into services and make those services available to components through dependency injection.
```

- What is service use for?
```a
The separation of concerns is the main reason why Angular services came into existence. An Angular service is a stateless object and provides some very useful functions. These functions can be invoked from any component of Angular, like Controllers, Directives, etc. This helps in dividing the web application into small, different logical units which can be reused.

An example of when to use services would be to transfer data from one controller to another custom service.
```

- What is Dependency Injection?
```a
DI is wired into the Angular framework and used everywhere to provide new components with the services or other things they need. Components consume services; that is, you can inject a service into a component, giving the component access to that service class.

To define a class as a service in Angular, use the @Injectable() decorator to provide the metadata that allows Angular to inject it into a component as a dependency. Similarly, use the @Injectable() decorator to indicate that a component or other class (such as another service, a pipe, or an NgModule) has a dependency.

The injector is the main mechanism. Angular creates an application-wide injector for you during the bootstrap process, and additional injectors as needed. You don't have to create injectors.

An injector creates dependencies, and maintains a container of dependency instances that it reuses if possible.

A provider is an object that tells an injector how to obtain or create a dependency.

For any dependency that you need in your app, you must register a provider with the application's injector, so that the injector can use the provider to create new instances. For a service, the provider is typically the service class itself.
```

### Lifecycle Hooks

- `ngOnChanges`
```a
When the value of a data bound property changes, then this method is called.
```

- `ngOnInit`
```a
This is called whenever the initialization of the directive/component after Angular first displays the data-bound properties happens.
```

- `ngDoCheck`
```a
This is for the detection and to act on changes that Angular can't or won't detect on its own.
```

- `ngAfterContentInit`
```a
This is called in response after Angular projects external content into the component's view.
```

- `ngAfterContentChecked`
```a
This is called in response after Angular checks the content projected into the component.
```

- `ngAfterViewInit`
```a
This is called in response after Angular initializes the component's views and child views.
```

- `ngAfterViewChecked`
```a
This is called in response after Angular checks the component's views and child views.
```

- `ngOnDestroy`
```a
This is the cleanup phase just before Angular destroys the directive/component.
```

- What is the difference between `ngOnInit` and constructor?
```a
- We mostly use ngOnInit in every startup/announcement and avoid things to work in builders. The constructor should only be used to start class members but should not do the actual “work”.
- So you should use the constructor() to set Dependency Injection and not much. ngOnInit() is a better “starting point” – this is where / when component combinations are solved.
- We use constructor() for all the initialization/declaration.
- It’s better to avoid writing actual work in the constructor.
- The constructor() should only be used to initialize class members but shouldn’t do actual “work”.
- So we should use constructor() to set up Dependency Injection, Initialization of class fields, etc.
- ngOnInit() is a better place to write “actual work code” that we need to execute as soon as the class is instantiated.
- Like loading data from Database — to show the user in your HTML template view. Such code should be written in ngOnInit().
```

### Http Interaction

- What is http client and its benefits? (Observable API)
```a
Most front-end applications need to communicate with a server over the HTTP protocol, to download or upload data and access other back-end services. Angular provides a client HTTP API for Angular applications, the HttpClient service class in @angular/common/http.

The HTTP client service offers the following major features.
- The ability to request typed response objects.
- Streamlined error handling.
- Testability features.
- Request and response interception.
```

- Http Interceptors
```a
Angular provides many built-in tools to help scale out large JavaScript applications. Interceptors are one of the built-in tools for specifically handling HTTP requests at a global application level.

Often we want to enforce or apply behavior when receiving or sending HTTP requests within our application. Interceptors are a unique type of Angular Service that we can implement. Interceptors allow us to intercept incoming or outgoing HTTP requests using the HttpClient. By intercepting the HTTP request, we can modify or change the value of the request.
```

- Request options for httpClient
```
- first: string | HttpRequest<any>
- url?: string
- options: { body?: any; headers?: HttpHeaders | { [header: string]: string | string[]; }
- context?: HttpContext
- observe?: "body" | "events" | "response"
- params?: HttpParams | { ...; }
- reportProgress?: boolean
- responseType?: "arraybuffer" | ... 2 more ... | "json";
- withCredentials?: boolean
```

### Angular Forms

- Reactive Forms
```a
Reactive forms provide a model-driven approach to handling form inputs whose values change over time.

Reactive forms use an explicit and immutable approach to managing the state of a form at a given point in time. Each change to the form state returns a new state, which maintains the integrity of the model between changes. Reactive forms are built around observable streams, where form inputs and values are provided as streams of input values, which can be accessed synchronously.

Reactive forms also provide a straightforward path to testing because you are assured that your data is consistent and predictable when requested. Any consumers of the streams have access to manipulate that data safely.
```
```
export class NameEditorComponent {
  name = new FormControl('');
}

<label for="name">Name: </label>
<input id="name" type="text" [formControl]="name">
```

- Template Driven Forms
```a
Template-driven forms use two-way data binding to update the data model in the component as changes are made in the template and vice versa.

Angular supports two design approaches for interactive forms. You can build forms by writing templates using Angular template syntax and directives with the form-specific directives and techniques described in this tutorial, or you can use a reactive (or model-driven) approach to build forms.

Template-driven forms are suitable for small or simple forms, while reactive forms are more scalable and suitable for complex forms.

Template-driven forms rely on directives defined in the FormsModule.
- The NgModel directive reconciles value changes in the attached form element with changes in the data model, allowing you to respond to user input with input validation and error handling.
- The NgForm directive creates a top-level FormGroup instance and binds it to a <form> element to track aggregated form value and validation status. As soon as you import FormsModule, this directive becomes active by default on all <form> tags. You don't need to add a special selector.
- The NgModelGroup directive creates and binds a FormGroup instance to a DOM element.

Steps example:
1. Build the basic form.
	- Define a sample data model.
	- Include required infrastructure such as the FormsModule.
2. Bind form controls to data properties using the ngModel directive and two-way data-binding syntax.
	- Examine how ngModel reports control states using CSS classes.
	- Name controls to make them accessible to ngModel.
3. Track input validity and control status using ngModel.
	- Add custom CSS to provide visual feedback on the status.
	- Show and hide validation-error messages.
4. Respond to a native HTML button-click event by adding to the model data.
5. Handle form submission using the ngSubmit output property of the form.
	- Disable the Submit button until the form is valid.
	- After submit, swap out the finished form for different content on the page.
```

- Validator
```a
You can improve overall data quality by validating user input for accuracy and completeness.

Validating input in template-driven forms:
- To add validation to a template-driven form, you add the same validation attributes as you would with native HTML form validation. Angular uses directives to match these attributes with validator functions in the framework.
- Every time the value of a form control changes, Angular runs validation and generates either a list of validation errors that results in an INVALID status, or null, which results in a VALID status.
- You can then inspect the control's state by exporting ngModel to a local template variable.
```

```
<input type="text" id="name" name="name" class="form-control"
      required minlength="4" appForbiddenName="bob"
      [(ngModel)]="hero.name" #name="ngModel">
<div *ngIf="name.invalid && (name.dirty || name.touched)"
    class="alert">
  <div *ngIf="name.errors?.['required']">
    Name is required.
  </div>
  <div *ngIf="name.errors?.['minlength']">
    Name must be at least 4 characters long.
  </div>
  <div *ngIf="name.errors?.['forbiddenName']">
    Name cannot be Bob.
  </div>
</div>
```
```a
Validating input in reactive forms:
- In a reactive form, the source of truth is the component class. Instead of adding validators through attributes in the template, you add validator functions directly to the form control model in the component class. Angular then calls these functions whenever the value of the control changes.
- Validator functions can be either synchronous or asynchronous.
	- Sync validators: Synchronous functions that take a control instance and immediately return either a set of validation errors or null. Pass these in as the second argument when you instantiate a FormControl.
	- Async validators: Asynchronous functions that take a control instance and return a Promise or Observable that later emits a set of validation errors or null. Pass these in as the third argument when you instantiate a FormControl.
- For performance reasons, Angular only runs async validators if all sync validators pass. Each must complete before errors are set.
```
```
ngOnInit(): void {
  this.heroForm = new FormGroup({
    name: new FormControl(this.hero.name, [
      Validators.required,
      Validators.minLength(4),
      forbiddenNameValidator(/bob/i) // <-- Here's how you pass in the custom validator.
    ]),
    alterEgo: new FormControl(this.hero.alterEgo),
    power: new FormControl(this.hero.power, Validators.required)
  });
}
```

- Custom validator
```a
Defining custom validators
The built-in validators don't always match the exact use case of your application, so you sometimes need to create a custom validator.
```
```
/** A hero's name can't match the given regular expression */
export function forbiddenNameValidator(nameRe: RegExp): ValidatorFn {
  return (control: AbstractControl): ValidationErrors | null => {
    const forbidden = nameRe.test(control.value);
    return forbidden ? {forbiddenName: {value: control.value}} : null;
  };
}
```
```a
The function is a factory that takes a regular expression to detect a specific forbidden name and returns a validator function.
```
```a
Adding custom validators to reactive forms:
- In reactive forms, add a custom validator by passing the function directly to the FormControl.
```
```
this.heroForm = new FormGroup({
  name: new FormControl(this.hero.name, [
    Validators.required,
    Validators.minLength(4),
    forbiddenNameValidator(/bob/i) // <-- Here's how you pass in the custom validator.
  ]),
  alterEgo: new FormControl(this.hero.alterEgo),
  power: new FormControl(this.hero.power, Validators.required)
});
```
```a
Adding custom validators to template-driven forms:
- In template-driven forms, add a directive to the template, where the directive wraps the validator function.
- Angular recognizes the directive's role in the validation process because the directive registers itself with the NG_VALIDATORS provider. NG_VALIDATORS is a predefined provider with an extensible collection of validators.
```
```
providers: [{provide: NG_VALIDATORS, useExisting: ForbiddenValidatorDirective, multi: true}]
```
```a
The directive class then implements the Validator interface, so that it can easily integrate with Angular forms. Here is the rest of the directive to help you get an idea of how it all comes together.
```
```
@Directive({
  selector: '[appForbiddenName]',
  providers: [{provide: NG_VALIDATORS, useExisting: ForbiddenValidatorDirective, multi: true}]
})
export class ForbiddenValidatorDirective implements Validator {
  @Input('appForbiddenName') forbiddenName = '';

  validate(control: AbstractControl): ValidationErrors | null {
    return this.forbiddenName ? forbiddenNameValidator(new RegExp(this.forbiddenName, 'i'))(control)
                              : null;
  }
}
```
```a
Once the ForbiddenValidatorDirective is ready, you can add its selector, appForbiddenName, to any input element to activate it. For example:
```
```
<input type="text" id="name" name="name" class="form-control"
      required minlength="4" appForbiddenName="bob"
      [(ngModel)]="hero.name" #name="ngModel">
```

- Form array
```a
A FormArray, just like a FormGroup, is also a form control container, that aggregates the values and validity state of its child components.

But unlike a FormGroup, a FormArray container does not require us to know all the controls up front, as well as their names.

Actually, a FormArray can have an undetermined number of form controls, starting at zero! The controls can then be dynamically added and removed depending on how the user interacts with the UI.

Each control will then have a numeric position in the form controls array, instead of a unique name.

Form controls can be added or removed from the form model anytime at runtime using the FormArray API.

These are the most commonly used methods available in the FormArray API:
- controls: This is an array containing all the controls that are part of the array
- length: This is the total length of the array
- at(index): Returns the form control at a given array position
- push(control): Adds a new control to the end of the array
- removeAt(index): Removes a control at a given position of the array
- getRawValue(): Gets the values of all form controls, via the control.value property of each control

The FormArray class is used to create a dynamic form. But before that, let us explore other essential classes that constitute a reactive form. They are:
- FormControl
- FormGroup
- Validators
```

- Submitting form
```
<form [formGroup]="checkoutForm" (ngSubmit)="onSubmit()">
  <button class="button" type="submit">Purchase</button>
</form>
```

### Routing

- Angular Router
```a
In a single-page app, you change what the user sees by showing or hiding portions of the display that correspond to particular components, rather than going out to the server to get a new page. As users perform application tasks, they need to move between the different views that you have defined.

To handle the navigation from one view to the next, you use the Angular Router. The Router enables navigation by interpreting a browser URL as an instruction to change the view.
```

- What is router outlet?
```a
The router-outlet is a directive that's available from the @angular/router package and is used by the router to mark where in a template, a matched component should be inserted.

Thanks to the router outlet, your app will have multiple views/pages and the app template acts like a shell of your application. Any element, you add to the shell will be rendered in each view, only the part marked by the router outlet will be changed between views.

Each outlet can have a unique name, determined by the optional name attribute. The name cannot be set or changed dynamically. If not set, default value is "primary".
```
```
<router-outlet></router-outlet>
<router-outlet name='left'></router-outlet>
<router-outlet name='right'></router-outlet>
```
```a
Named outlets can be the targets of secondary routes. The Route object for a secondary route has an outlet property to identify the target outlet:
```
```
const routes: Routes = [
  {
    path: "first",
    component: FirstComponent,
    outlet: "first_outlet_name"
  },
  {
    path: "second",
    component: SecondComponent,
    outlet: "second_outlet_name"
  }
];
```
```a
Using named outlets and secondary routes, you can target multiple outlets in the same RouterLink directive.
```

- How to use router parameters and query parameters?
```a
Using router parameters:
- Say we are creating an application that displays a product list. When the user clicks on a product in the list, we want to display a page showing the detailed information about that product. To do this you must:
	- add a route parameter ID
	- link the route to the parameter
	- add the service that reads the parameter.

1. Declaring Route Parameters:
- The route for the component that displays the details for a specific product would need a route parameter for the ID of that product. We could implement this using the following Routes:
```
```
export const routes: Routes = [
  { path: '', redirectTo: 'product-list', pathMatch: 'full' },
  { path: 'product-list', component: ProductList },
  { path: 'product-details/:id', component: ProductDetails }
];
```
```a
2. Linking to Routes with Parameters
- In the ProductList component you could display a list of products. Each product would have a link to the product-details route, passing the ID of the product:
```
```
<a *ngFor="let product of products"
  [routerLink]="['/product-details', product.id]">
  {{ product.name }}
</a>
```
```a
Note that the routerLink directive passes an array which specifies the path and the route parameter. Alternatively we could navigate to the route programmatically:
```
```
goToProductDetails(id) {
  this.router.navigate(['/product-details', id]);
}
```
```a
3. Reading Route Parameters
- The ProductDetails component must read the parameter, then load the product based on the ID given in the parameter.
- The ActivatedRoute service provides a params Observable which we can subscribe to to get the route parameters (see Observables).
```
```
import { Component, OnInit, OnDestroy } from '@angular/core';
import { ActivatedRoute } from '@angular/router';

@Component({
  selector: 'product-details',
  template: `
    <div>
      Showing product details for product: {{id}}
    </div>
  `,
})
export class LoanDetailsPage implements OnInit, OnDestroy {
  id: number;
  private sub: any;

  constructor(private route: ActivatedRoute) {}

  ngOnInit() {
    this.sub = this.route.params.subscribe(params => {
       this.id = +params['id']; // (+) converts string 'id' to a number

       // In a real app: dispatch action to load the details here.
    });
  }

  ngOnDestroy() {
    this.sub.unsubscribe();
  }
}
```
```a
Using query parameters:
1. Using Query Parameters with Router.navigate:
- Query parameters in Angular allow for passing optional parameters across any route in the application. Query parameters are different from regular route parameters, which are only available on one route and are not optional (e.g., /product/:id).
- If you are navigating to the route imperatively using Router.navigate, you will pass in query parameters with queryParams.
```
```
goProducts() {
  this.router.navigate(
    ['/products'],
    { queryParams: { order: 'popular' } }
  );
}
```
```a
This will result in a URL that resembles:
http://localhost:4200/products?order=popular

2. Using Query Parameters with RouterLink:
```
```
<a
  [routerLink]="['/products']"
  [queryParams]="{ order: 'popular'}"
>
  Products
</a>
```
```a
Accessing Query Parameter Values:
- Now that we know how to pass in optional query parameters to a route, let’s see how to access these values on the resulting routes. The ActivatedRoute class has a queryParams property that returns an observable of the query parameters that are available in the current URL.

Given the following route URL:
http://localhost:4200/products?order=popular

We can access the order query parameter like this:
```
```
import { ActivatedRoute } from '@angular/router';
import 'rxjs/add/operator/filter';

@Component({ ... })
export class ProductComponent implements OnInit {
  order: string;
  constructor(private route: ActivatedRoute) { }

  ngOnInit() {
    this.route.queryParams
      .filter(params => params.order)
      .subscribe(params => {
        console.log(params); // { order: "popular" }

        this.order = params.order;

        console.log(this.order); // popular
      }
    );
  }
}
```

- Router Resolver
```a
One way for handling retrieving and displaying data from an API is to route a user to a component, and then in that component’s ngOnInit hook call a method in a service to get the necessary data. While getting the data, perhaps the component can show a loading indicator.

There is another way to use what is known as a route resolver, which allows you to get data before navigating to the new route.

Steps to build an example resolver:
1. Building a Resolver
Let’s start by implementing a resolver that returns a string after a delay of 2 seconds. This small proof of concept can help with exploring the fundamentals of wiring routes that can be applied to larger projects.
- First, create a separate class for the resolver in a file of its own:
```
```
./node_modules/@angular/cli/bin/ng generate resolver news
```
```
import { Injectable } from '@angular/core';
import { Resolve } from '@angular/router';

import { Observable, of } from 'rxjs';
import { delay } from 'rxjs/operators';

@Injectable({
  providedIn: 'root'
})
export class NewsResolver implements Resolve<Observable<string>> {
  resolve(): Observable<string> {
    return of('Route!').pipe(delay(2000));
  }
}
```
```a
Implementing the Angular router’s Resolve interface requires the class to have a resolve method. Whatever is returned from that method will be the resolved data.

This code will return an observable that wraps a string after a delay of 2 seconds.

2. Accessing the Resolved Data in some other Component
In some other component, you can access the resolved data using the data property of ActivatedRoute’s snapshot object:
```
```
import { Component, OnInit } from '@angular/core';

import { ActivatedRoute } from '@angular/router';

@Component({ ... })
export class TopComponent implements OnInit {
  data: any;

  constructor(private route: ActivatedRoute) {}

  ngOnInit(): void {
    this.data = this.route.snapshot.data;
  }
}
```
```a
3. Accessing Route Parameters
You can get access to the current route parameters in your resolver using the ActivatedRouteSnapshot object.
```
```
import { Injectable } from '@angular/core';
import { Resolve, ActivatedRouteSnapshot } from '@angular/router';
import { Observable } from 'rxjs';

import { NewsService } from './news.service';

@Injectable({
  providedIn: 'root'
})
export class PostResolver implements Resolve<any> {
  constructor(private newsService: NewsService) {}

  resolve(route: ActivatedRouteSnapshot): Observable<any> {
    return this.newsService.getPost(route.paramMap.get('id'));
  }
}
```

- Route Guard
```a
Angular route guards are interfaces provided by angular which when implemented allow us to control the accessibility of a route based on condition provided in class implementation of that interface.
Five types of route guards are provided by Angular:
- CanActivate - preventing access to the specific route
- CanActivateChild - prevent access to child routes of a given route
- CanLoad - control the navigation as well as prevent downloading of that module
- CanDeactivate - keep the user from navigating away from a specific route
- Resolve - resolving data based on implemented code and pass that data to the component
```
```
// AuthGuard Service example with CanActivate guard
import {CanActivate, ActivatedRouteSnapshot, RouterStateSnapshot, Router} from '@angular/router';
import { Observable } from 'rxjs/Observable';

export class AuthGuard implements CanActivate {
  constructor(private authService: AuthService, private router: Router) {}

  canActivate(
    route: ActivatedRouteSnapshot,
    state:RouterStateSnapshot
  ): Observable<boolean> | Promise<boolean> | boolean {
  // return true if you want to navigate, otherwise return false
  }
}
```

### Angular RXJS Subjects and Observables with API requests

- What is observable?
```a
Observable is a function that converts the ordinary stream of data into an observable stream of data. You can think of Observable as a wrapper around the ordinary stream of data.

Observable stream or simple Observable emits the value from the stream asynchronously. It emits the complete signals when the stream completes or an error signal if the stream errors out.

Observables are declarative. You define an observable function just like any other variable. The observable starts to emit values only when someone subscribes to it.
```

- What is observer?
```a
The Observable on its own is useless unless someone consumes the value emitted by the observable. We call them observers or subscribers.

The observers communicate with the Observable using callbacks

The observer must subscribe with the observable to receive the value from the observable. While subscribing it optionally passes the three callbacks. next(), error() & complete()

The observable starts emitting the value as soon as the observer or consumer subscribes to it.

The observable invokes the next() callback whenever the value arrives in the stream. It passes the value as the argument to the next callback. If the error occurs, then the error() callback is invoked. It invokes the complete() callback when the stream completes.
```
```
// Example with observable and observer
import { Component, OnInit } from '@angular/core';
import { Observable } from 'rxjs';
 
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent implements OnInit {
  title = 'Angular Observable using RxJs - Getting Started';
 
  obs = new Observable((observer) => {
    console.log("Observable starts")
      observer.next("1")
      observer.next("2")
      observer.next("3")
      observer.next("4")
      observer.next("5")
  })
 
  data=[];
 
  ngOnInit() {
    this.obs.subscribe(
      val=> { console.log(val) },
      error => { console.log("error") },
      () => {console.log("Completed") }
    )
  }
}
```

- What is subject?
```a
What are Subjects ?
A Subject is a special type of Observable that allows values to be multicasted to many Observers. The subjects are also observers because they can subscribe to another observable and get value from it, which it will multicast to all of its subscribers.

Basically, a subject can act as both observable & an observer.

Subjects implement both subscribe method and next, error & complete methods. It also maintains a collection of observers[]

An Observer can subscribe to the Subject and receive value from it. Subject adds them to its collection observers. Whenever there is a value in the stream it notifies all of its Observers.

The Subject also implements the next, error & complete methods. Hence it can subscribe to another observable and receive values from it.
```
```
import { Component, VERSION } from "@angular/core";
import { Subject } from "rxjs";
 
@Component({
  selector: "my-app",
  templateUrl: "./app.component.html",
  styleUrls: ["./app.component.css"]
})
export class AppComponent {
 
  subject$ = new Subject();
 
  ngOnInit() {
    
    this.subject$.subscribe(val => {
      console.log(val);
    });
 
    this.subject$.next("1");
    this.subject$.next("2");
    this.subject$.complete();
  }
}
```

- What is RxJs?
```a
RxJS is a library for composing asynchronous and event-based programs by using observable sequences. It provides one core type, the Observable, satellite types (Observer, Schedulers, Subjects) and operators inspired by Array#extras (map, filter, reduce, every, etc) to allow handling asynchronous events as collections.

RxJS provides an implementation of the Observable type, which is needed until the type becomes part of the language and until browsers support it. The library also provides utility functions for creating and working with observables. These utility functions can be used for:
- Converting existing code for async operations into observables
- Iterating through the values in a stream
- Mapping values to different types
- Filtering streams
- Composing multiple streams

Think of RxJS as Lodash for events.

Normally you register event listeners.
```
```
document.addEventListener('click', () => console.log('Clicked!'));
```
```a
Using RxJS you create an observable instead.
```
```
import { fromEvent } from 'rxjs';

fromEvent(document, 'click').subscribe(() => console.log('Clicked!'));
```

- Difference between Promise and Observable?

| Observable | Promise |
| ----------- | ----------- |
| Emit multiple values over a period of time. | Emit a single value at a time. |
| Are lazy: they’re not executed until we subscribe to them using the subscribe() method. | Are not lazy: execute immediately after creation. |
| Have subscriptions that are cancellable using the unsubscribe() method, which stops the listener from receiving further values. | Are not cancellable. |
| Provide the map for forEach, filter, reduce, retry, and retryWhen operators. | Don’t provide any operations. |
| Deliver errors to the subscribers. | Push errors to the child promises. |

- Unsubscribing
```a
The subscription starts to emit values when the child component is rendered by Angular. But when we destroy the component, the observable still keeps emitting new values. We can see this in console window.

If we render the child component again, it starts a new subscription. Now we have two subscriptions running. As and when we create a new instance of the child component, it will create a new subscription, and those subscriptions never cleaned up.

Unsubscribing from an observable as easy as calling Unsubscribe() method on the subscription. It will clean up all listeners and frees up the memory
```
```
ngOnDestroy() {
    this.obs.unsubscribe();
}
```

- Difference between Subject and BehaviorSubject

| Subject | BehaviorSubject |
| ----------- | ----------- |
| If you subscribe to an subject, you won’t get the current value or initial value. | When you subscribe to an Behavior Subject, you will be able to get the current value or the initial value. |
| You don’t have to define a default value whenever you declare the subject. | You have to define a default value whenever you declare Behavior Subject based upon the data type. |
| In Subject, each next subscribers receive only the upcoming values. | In Behavior Subject, each next subscribers receive one previous value and upcoming values. |
| Subject has state, it keeps a list of observers. On the other hand, an observable is just a function that sets up observation. | Observable is a Generic, and Behavior Subject is technically a sub–type of Observable because BehaviorSubject is an observable with specific qualities. |
```a
Both Subject and BehaviorSubject cannot be reused once you unsubscribe the respective Subject.
```

### Styles in Angular

Angular applications are styled with standard CSS. That means you can apply everything you know about CSS stylesheets, selectors, rules, and media queries directly to Angular applications.

Additionally, Angular can bundle component styles with components, enabling a more modular design than regular stylesheets.

- ViewEncapsulation
```a
In Angular, a component's styles can be encapsulated within the component's host element so that they don't affect the rest of the application.

The Component's decorator provides the encapsulation option which can be used to control how the encapsulation is applied on a per component basis.

Choose from the following modes:
- ViewEncapsulation.ShadowDom, Angular uses the browser's built-in Shadow DOM API to enclose the component's view inside a ShadowRoot (used as the component's host element) and apply the provided styles in an isolated manner.
- ViewEncapsulation.Emulated, Angular modifies the component's CSS selectors so that they are only applied to the component's view and do not affect other elements in the application (emulating Shadow DOM behavior). For more details, see Inspecting generated CSS.
- ViewEncapsulation.None, Angular does not apply any sort of view encapsulation meaning that any styles specified for the component are actually globally applied and can affect any HTML element present within the application. This mode is essentially the same as including the styles into the HTML itself.
```


## Advanced:

- `NgRx`
```a
NgRx is a framework for building reactive applications in Angular. NgRx provides libraries for:
- Managing global and local state.
- Isolation of side effects to promote a cleaner component architecture.
- Entity collection management.
- Integration with the Angular Router.
- Developer tooling that enhances developer experience when building many different types of applications.

State:
- Store - RxJS powered global state management for Angular apps, inspired by Redux.
- Effects - Side effect model for @ngrx/store.
- Router Store - Bindings to connect the Angular Router to @ngrx/store.
- Entity - Entity State adapter for managing record collections.
- ComponentStore - Standalone library for managing local/component state.

Data:
- Data - Extension for simplified entity data management.

View:
- Component - Extension for fully reactive Angular applications.

Developer Tooling:
- Store Devtools - Instrumentation for @ngrx/store that enables visual tracking of state and time-travel debugging.
- Schematics - Scaffolding library for Angular applications using NgRx libraries.
```
```a
1.1. Store
A good guideline that might help answer the question, "Do I need NgRx Store?" is the SHARI principle:
- Shared: state that is accessed by many components and services.
- Hydrated: state that is persisted and rehydrated from external storage.
- Available: state that needs to be available when re-entering routes.
- Retrieved: state that must be retrieved with a side-effect.
- Impacted: state that is impacted by actions from other sources.

Actions:
```
```
import { createAction } from '@ngrx/store';

export const increment = createAction('[Counter Component] Increment');
export const decrement = createAction('[Counter Component] Decrement');
export const reset = createAction('[Counter Component] Reset');
```
```a
Reducer:
```
```
import { createReducer, on } from '@ngrx/store';
import { increment, decrement, reset } from './counter.actions';

export const initialState = 0;

const _counterReducer = createReducer(
  initialState,
  on(increment, (state) => state + 1),
  on(decrement, (state) => state - 1),
  on(reset, (state) => 0)
);

export function counterReducer(state, action) {
  return _counterReducer(state, action);
}
```
```a
In app.module.ts:
```
```
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';

import { AppComponent } from './app.component';

import { StoreModule } from '@ngrx/store';
import { counterReducer } from './counter.reducer';

@NgModule({
  declarations: [AppComponent],
  imports: [BrowserModule, StoreModule.forRoot({ count: counterReducer })],
  providers: [],
  bootstrap: [AppComponent],
})
export class AppModule {}
```
```a
Use the store:
```
```
import { Component } from '@angular/core';
import { Store } from '@ngrx/store';
import { Observable } from 'rxjs';
import { increment, decrement, reset } from '../counter.actions';

@Component({
  selector: 'app-my-counter',
  templateUrl: './my-counter.component.html',
})
export class MyCounterComponent {
  count$: Observable<number>;

  constructor(private store: Store<{ count: number }>) {
    this.count$ = store.select('count');
  }

  increment() {
    this.store.dispatch(increment());
  }

  decrement() {
    this.store.dispatch(decrement());
  }

  reset() {
    this.store.dispatch(reset());
  }
}
```
```a
1.2. Effects:
In a service-based Angular application, components are responsible for interacting with external resources directly through services. Instead, effects provide a way to interact with those services and isolate them from the components. Effects are where you handle tasks such as fetching data, long-running tasks that produce multiple events, and other external interactions where your components don't need explicit knowledge of these interactions.

Key Concepts:
- Effects isolate side effects from components, allowing for more pure components that select state and dispatch actions.
- Effects are long-running services that listen to an observable of every action dispatched from the Store.
- Effects filter those actions based on the type of action they are interested in. This is done by using an operator.
- Effects perform tasks, which are synchronous or asynchronous and return a new action.

Writing Effects:
To isolate side-effects from your component, you must create an Effects class to listen for events and perform tasks.

Effects are injectable service classes with distinct parts:
- An injectable Actions service that provides an observable stream of all actions dispatched after the latest state has been reduced.
- Metadata is attached to the observable streams using the createEffect function. The metadata is used to register the streams that are subscribed to the store. Any action returned from the effect stream is then dispatched back to the Store.
- Actions are filtered using a pipeable ofType operator. The ofType operator takes one or more action types as arguments to filter on which actions to act upon.
- Effects are subscribed to the Store observable.
- Services are injected into effects to interact with external APIs and handle streams.
- To show how you handle loading movies from the example above, let's look at MovieEffects.

Write an Effects class:
```
```
import { Injectable } from '@angular/core';
import { Actions, createEffect, ofType } from '@ngrx/effects';
import { EMPTY } from 'rxjs';
import { map, mergeMap, catchError } from 'rxjs/operators';
import { MoviesService } from './movies.service';

@Injectable()
export class MovieEffects {

  loadMovies$ = createEffect(() => this.actions$.pipe(
    ofType('[Movies Page] Load Movies'),
    mergeMap(() => this.moviesService.getAll()
      .pipe(
        map(movies => ({ type: '[Movies API] Movies Loaded Success', payload: movies })),
        catchError(() => EMPTY)
      ))
    )
  );

  constructor(
    private actions$: Actions,
    private moviesService: MoviesService
  ) {}
}
```
```a
Registering root effects:
```
```
import { EffectsModule } from '@ngrx/effects';
import { MovieEffects } from './effects/movie.effects';

@NgModule({
  imports: [
    EffectsModule.forRoot([MovieEffects])
  ],
})
export class AppModule {}
```
```a
Registering feature effects:
```
```
import { EffectsModule } from '@ngrx/effects';
import { MovieEffects } from './effects/movie.effects';

@NgModule({
  imports: [
    EffectsModule.forFeature([MovieEffects])
  ],
})
export class MovieModule {}
```
```a
1.3. Router store
Bindings to connect the Angular Router with Store. During each router navigation cycle, multiple actions are dispatched that allow you to listen for changes in the router's state. You can then select data from the state of the router to provide additional information to your application.
```
```
import { StoreRouterConnectingModule, routerReducer } from '@ngrx/router-store';
import { AppComponent } from './app.component';

@NgModule({
  imports: [
    BrowserModule,
    StoreModule.forRoot({
      router: routerReducer,
    }),
    RouterModule.forRoot([
      // routes
    ]),
    // Connects RouterModule with StoreModule, uses MinimalRouterStateSerializer by default
    StoreRouterConnectingModule.forRoot(),
  ],
  bootstrap: [AppComponent],
})
export class AppModule {}
```
```a
1.4. Entity:
Entity State adapter for managing record collections.

Entity provides an API to manipulate and query entity collections.
- Reduces boilerplate for creating reducers that manage a collection of models.
- Provides performant CRUD operations for managing entity collections.
- Extensible type-safe adapters for selecting entity information.

Entity and class instances:
Entity promotes the use of plain JavaScript objects when managing collections. ES6 class instances will be transformed into plain JavaScript objects when entities are managed in a collection. This provides you with some assurances when managing these entities:
- Guarantee that the data structures contained in state don't themselves contain logic, reducing the chance that they'll mutate themselves.
- State will always be serializable allowing you to store and rehydrate from browser storage mechanisms like local storage.
- State can be inspected via the Redux Devtools.

This is one of the core principles of NgRx. The Redux docs also offers some more insight into this constraint.
```
```a
1.5. ComponentStore:
ComponentStore is a stand-alone library that helps to manage local/component state. It's an alternative to reactive push-based "Service with a Subject" approach.

Key Concepts:
- Local state has to be initialized, but it can be done lazily.
- Local state is typically tied to the life-cycle of a particular component and is cleaned up when that component is destroyed.
- Users of ComponentStore can update the state through setState or updater, either imperatively or by providing an Observable.
- Users of ComponentStore can read the state through select or a top-level state$. Selectors are very performant.
- Users of ComponentStore may start side-effects with effect, both sync and async, and feed the data both imperatively or reactively.

The details about initialization, writing and reading from state, and side-effects management can be found in the corresponding sections of the Architecture.

@ngrx/store or @ngrx/component-store?
The Global Store and Component Store are designed to solve different problems and can be used independently from each other. The detailed comparison can be found at Store vs ComponentStore section.
```
```a
2.1. Data:
NgRx Data is an extension that offers a gentle introduction to NgRx by simplifying management of entity data while reducing the amount of explicitness.

Key Concepts:
- automates the creation of actions, reducers, effects, dispatchers, and selectors for each entity type.
- provides default HTTP GET, PUT, POST, and DELETE methods for each entity type.
- holds entity data as collections within a cache which is a slice of NgRx store state.
- supports optimistic and pessimistic save strategies
- enables transactional save of multiple entities of multiple types in the same request.
- makes reasonable default implementation choices
- offers numerous extension points for changing or augmenting those default behaviors.

Entity:
An entity is an object with long-lived data values that you read from and write to a database. An entity refers to some "thing" in the application domain. Examples include a Customer, Order, LineItem, Product, Person and User.

Defining the entities:
```
```
import { EntityMetadataMap } from '@ngrx/data';

const entityMetadata: EntityMetadataMap = {
  Hero: {},
  Villain: {}
};

// because the plural of "hero" is not "heros"
const pluralNames = { Hero: 'Heroes' };

export const entityConfig = {
  entityMetadata,
  pluralNames
};
```
```a
Registering the entity store:
```
```
import { NgModule } from '@angular/core';
import { HttpClientModule } from '@angular/common/http';
import { EffectsModule } from '@ngrx/effects';
import { StoreModule } from '@ngrx/store';
import { DefaultDataServiceConfig, EntityDataModule } from '@ngrx/data';
import { entityConfig } from './entity-metadata';

@NgModule({
  imports: [
    HttpClientModule,
    StoreModule.forRoot({}),
    EffectsModule.forRoot([]),
    EntityDataModule.forRoot(entityConfig)
  ]
})
export class AppModule {}
```
```a
Creating entity data services
```
```
import { Injectable } from '@angular/core';
import {
  EntityCollectionServiceBase,
  EntityCollectionServiceElementsFactory
} from '@ngrx/data';
import { Hero } from '../core';

@Injectable({ providedIn: 'root' })
export class HeroService extends EntityCollectionServiceBase<Hero> {
  constructor(serviceElementsFactory: EntityCollectionServiceElementsFactory) {
    super('Hero', serviceElementsFactory);
  }
}
```
```a
Using NgRx Data in components:
```
```
import { Component, OnInit } from '@angular/core';
import { Observable } from 'rxjs';
import { Hero } from '../../core';
import { HeroService } from '../hero.service';

@Component({
  selector: 'app-heroes',
  templateUrl: './heroes.component.html',
  styleUrls: ['./heroes.component.scss']
})
export class HeroesComponent implements OnInit {
  loading$: Observable<boolean>;
  heroes$: Observable<Hero[]>;

  constructor(private heroService: HeroService) {
    this.heroes$ = heroService.entities$;
    this.loading$ = heroService.loading$;
  }

  ngOnInit() {
    this.getHeroes();
  }

  add(hero: Hero) {
    this.heroService.add(hero);
  }

  delete(hero: Hero) {
    this.heroService.delete(hero.id);
  }

  getHeroes() {
    this.heroService.getAll();
  }

  update(hero: Hero) {
    this.heroService.update(hero);
  }
}
```
```a
3.1. Component:
Component is a set of primitive reactive helpers to enable fully reactive, Zoneless applications. They give more control over rendering, and provide further reactivity for Angular applications.

Key Concepts
Rendering happens in the template only:
- The ngrxPush pipe provides a drop-in replacement for the async pipe.
- The ngrxLet directive provides a structural directive with better support for handling observables.

Usage:
Both the *ngrxLet directive, and ngrxPush pipe are provided through the ReactiveComponentModule. To use them, add the ReactiveComponentModule to the imports of your NgModule.
```
```
import { NgModule } from '@angular/core';
import { ReactiveComponentModule } from '@ngrx/component';

@NgModule({
  imports: [
    // other imports
    ReactiveComponentModule
  ]
})
export class MyFeatureModule {}
```
```a
4.1. Store Devtools
Store Devtools provides developer tools and instrumentation for Store.
```
```
import { StoreDevtoolsModule } from '@ngrx/store-devtools';
import { environment } from '../environments/environment'; // Angular CLI environment

@NgModule({
  imports: [
    StoreModule.forRoot(reducers),
    // Instrumentation must be imported after importing StoreModule (config is optional)
    StoreDevtoolsModule.instrument({
      maxAge: 25, // Retains last 25 states
      logOnly: environment.production, // Restrict extension to log-only mode
      autoPause: true, // Pauses recording actions and state changes when the extension window is not open
    }),
  ],
})
export class AppModule {}
```
```a
4.2. Schematics
Scaffolding library for Angular applications using NgRx libraries.

Schematics provides Angular CLI commands for generating files when building new NgRx feature areas and expanding existing ones. Built on top of Schematics, this tool integrates with the Angular CLI.
```

- `RxJS` operators and how to use them
```a
RxJS is mostly useful for its operators, even though the Observable is the foundation. Operators are the essential pieces that allow complex asynchronous code to be easily composed in a declarative manner.

Operators are functions. There are two kinds of operators:
1. Pipeable Operators:
- The kind that can be piped to Observables using the syntax observableInstance.pipe(operator()). These include, filter(...), and mergeMap(...). When called, they do not change the existing Observable instance. Instead, they return a new Observable, whose subscription logic is based on the first Observable.
- A Pipeable Operator is a function that takes an Observable as its input and returns another Observable. It is a pure operation: the previous Observable stays unmodified.
- A Pipeable Operator is essentially a pure function which takes one Observable as input and generates another Observable as output. Subscribing to the output Observable will also subscribe to the input Observable.

2. Creation Operators:
- The other kind of operator, which can be called as standalone functions to create a new Observable. For example: of(1, 2, 3) creates an observable that will emit 1, 2, and 3, one right after another. Creation operators will be discussed in more detail in a later section.
```
```a
Categories of operators:
- Creation Operators - ajax, bindCallback, bindNodeCallback, defer, empty, from, fromEvent, fromEventPattern, generate, interval, of, range, throwError, timer, iif
- Join Creation Operators - combineLatest, concat, forkJoin, merge, partition, race, zip
- Transformation Operators - buffer, bufferCount, bufferTime, bufferToggle, bufferWhen, concatMap, concatMapTo, exhaust, exhaustMap, expand, groupBy, map, mapTo, mergeMap, mergeMapTo, mergeScan, pairwise, partition, pluck, scan, switchScan, switchMap, switchMapTo, window, windowCount, windowTime, windowToggle, windowWhen
- Filtering Operators - audit, auditTime, debounce, debounceTime, distinct, distinctUntilChanged, distinctUntilKeyChanged, elementAt, filter, first, ignoreElements, last, sample, sampleTime, single, skip, skipLast, skipUntil, skipWhile, take, takeLast, takeUntil, takeWhile, throttle, throttleTime
- Join Operators - combineLatestAll, concatAll, exhaustAll, mergeAll, switchAll, startWith, withLatestFrom
- Multicasting Operators - multicast, publish, publishBehavior, publishLast, publishReplay, share
- Error Handling Operators - catchError, retry, retryWhen
- Utility Operators - tap, delay, delayWhen, dematerialize, materialize, observeOn, subscribeOn, timeInterval, timestamp, timeout, timeoutWith, toArray
- Conditional and Boolean Operators - defaultIfEmpty, every, find, findIndex, isEmpty
- Mathematical and Aggregate Operators - count, max, min, reduce
```

- Lazy loading a module
```a
By default, NgModules are eagerly loaded, which means that as soon as the application loads, so do all the NgModules, whether or not they are immediately necessary. For large applications with lots of routes, consider lazy loading—a design pattern that loads NgModules as needed. Lazy loading helps keep initial bundle sizes smaller, which in turn helps decrease load times.

To lazy load Angular modules, use loadChildren (instead of component) in your AppRoutingModule routes configuration as follows.
```
```
const routes: Routes = [
  {
    path: 'items',
    loadChildren: () => import('./items/items.module').then(m => m.ItemsModule)
  }
];
```
```a
In the lazy-loaded module's routing module, add a route for the component.
```
```
const routes: Routes = [
  {
    path: '',
    component: ItemsComponent
  }
];
```
```a
Also be sure to remove the ItemsModule from the AppModule. 
```

- AOT and JIT compilation in Angular

An angular application mainly consists of HTML templates, their components which include various TypeScript files. There are some unit testing and configuration file. Whenever we run over an application, the browser cannot understand the code directly hence we have to compile our code.
```a
1. Ahead of Time (AOT) compiler:
All technologies Ahead of Time is a process of compiling higher-level language or intermediate language into a native machine code, which is system dependent.

In simple words, when you serve/build your angular application, the Ahead of Time compiler converts your code during the build time before your browser downloads and runs that code. From Angular 9, by default compiling option is set to true for ahead of time compiler.  

Why should you use the Ahead of Time compiler?
- When you are using Ahead of Time Compiler, compilation only happens once, while you build your project.
- We don’t have to ship the HTML templates and the Angular compiler whenever we enter a new component.
- It can minimize the size of your application.
- The browser does not need to compile the code in run time, it can directly render the application immediately, without waiting to compile the app first so, it provides quicker component rendering.
- The Ahead of time compiler detects template error earlier. It detects and reports template binding errors during the build steps before users can see them.
- AOT provides better security. It compiles HTML components and templates into JavaScript files long before they are served into the client display. So, there are no templates to read and no risky client-side HTML or JavaScript evaluation. This will reduce the chances of injections attacks.

How Ahead of Time works?
- We use Typescript, HTML, style-sheets to develop our Angular project and ng build –prod or ng build to build our source code into bundles which include JS files, index.html, style-sheets, and assets files.
- Now Angular uses the angular compiler (whichever you have selected) to build source code, and they do it in three phases, which are code analysis, code generation and template type checking. At the end of this process, bundle size will be much smaller than the JIT compiler’s bundle size.
- After that AOT builds this into a war file to deploy directly by using Heroku or by JBoss or by any other hosting that supports Node. And then we map this host to the domain by using a CNAME.
- Now the clients can access your web application via the domain. The browser will download all necessary files like HTML, style-sheets, and JavaScript which is needed for the default view.  At last, your application will get bootstrap and get rendered.  

How to compile your app in ahead of time compiler?
- For compiling your app in Ahead of time, you don’t have to do much, because from angular 9 default compiling option is set to Ahead of time. Just add –AoT at the end ng serve –aot.
```
```a
2. Just in Time (JIT) compiler:
Just in time compiler provides compilation during the execution of the program at a run time before execution. In simple words, code get compiles when it’s needed, not at the build time.

Why and When Should you use Just In Time Compiler?
- Just in time compiler compiles each file separately and it’s mostly compiled in the browser. You don’t have to build your project again after changing your code.
- Most compiling is done on the browser side, so it will take less compiling time.
- If you have a big project or a situation where some of your components don’t come in use most of the time then you should use the Just in time compiler.
- Just in Time compiler is best when your application is in local development.

How Just in Time compiler Works?
- Initially, compiler was responsible for converting a high-level language into machine language, which would then be converted into executable code.
- Just in time compiler, compiles code at runtime which means instead of interpreting byte code at build time, it will compile byte code when that component is called.

A few important points:
- In case of Just in time, not all code is compiled at the initial time. Only necessary component which are going to be needed at the starting of your application will be compiled. Then if the functionality is need in your project and it’s not in compiled code, that function or component will be compiled.
- This process will help to reduce the burden on the CPU and make your app render fast.
- One more interesting thing is, you can see and link to your source code in inspect mode because Just in Time, compiles your code with JIT mode and a map file.
```
```a
Comparison between Ahead of Time (AOT) and Just in Time (JIT):
```
| AOT | JIT |
| ----------- | ----------- |
| AOT has already complied with the code while building your application, so it doesn’t have to compile at runtime. | JIT downloads the compiler and compiles code exactly before Displaying in the browser. |
| Loading in AOT is much quicker than the JIT because it already has compiled your code at build time. | Loading in JIT is slower than the AOT because it needs to compile your application at runtime. |
| AOT is much suitable in the case of Production mode. | JIT is more suitable for development mode. |
| Bundle size optimized in AOT, in results AOT bundle size is half the size of JIT bundles. | Bundle size is higher compare to AOT. |
| To run your app in AOT you have to provide –aot at the end like: <br /> `ng build --aot OR ng serve --aot`| You can run your app in JIT with this command: <br /> `ng build OR ng serve` |
| You can catch the template error at building your application. | You can catch template binding error at display time. |

```a
Conclusion: You can compile your angular application in two ways: JIT and AOT. Both are suitable for a different scenario like you can use JIT for development mode and AOT is better in production mode.  Implementing features and debugging is easy in JIT mode since you have to map files while AOT does not have it. However, that AOT provides a big benefit to angular developers for production mode by reducing bundle size and making your app render faster.
```

- Zone.js

As an Angular developer, you may know NgZone, which is a service for executing work inside, or outside of the angular Zone. You may also know that this NgZone service is based on a library called zone.js, but most developers may not directly use the APIs of zone.js, or know what zone.js is.
```a
Zone.js is a library that provides a concept called Zone, which is an execution context that persists across async tasks.

Zone.js provides a mechanism, called zones, for encapsulating and intercepting asynchronous activities in the browser (e.g. setTimeout, , promises).

These zones are execution contexts that allow Angular to track the start and completion of asynchronous activities and perform tasks as required (e.g. change detection). Zone.js provides a global zone that can be forked and extended to further encapsulate/isolate asynchronous behaviour, which Angular does so in its NgZone service, by creating a fork and extending it with its own behaviours.

A Zone can:
- Provide execution context that persist across async tasks.
- Intercept async task, and provide life cycle hooks.
- Provide centralized error handler for async tasks.
```

- Optimizing rendering using ChangeDetectionStrategy
```a
By default, Angular 2+ performs change detection on all components (from top to bottom) every time something changes in your app. A change can occur from a user event or data received from a network request.

Change detection is very performant, but as an app gets more complex and the amount of components grows, change detection will have to perform more and more work.

One solution is to use the OnPush change detection strategy for specific components. This will instruct Angular to run change detection on these components and their sub-tree only when new references are passed to them versus when data is mutated.
```
```
import { Component, Input, ChangeDetectionStrategy } from '@angular/core';

@Component({
  selector: 'app-child',
  templateUrl: './child.component.html',
  changeDetection: ChangeDetectionStrategy.OnPush
})
export class ChildComponent {
  @Input() data: string[];
}
```
```a
After recompiling and visiting the application in a browser, you should observe an unsorted list containing shark, dolphin, and octopus.

However, adding a new aquatic creature does not seem to append it to the unordered list. The new data still gets pushed into the aquaticCreatures array in the parent component, but Angular does not recognize a new reference for the data input and therefore it does not run change detection on the component.

To pass a new reference to the data input, you can replace Array.push with the spread syntax (...) in addAquaticCreature:
```
```
// ...
addAquaticCreature(newAquaticCreature) {
  this.aquaticCreatures = [...this.aquaticCreatures, newAquaticCreature];
}
// ...
```
```a
With this variation, you are no longer mutating the aquaticCreatures array. You are returning a completely new array.

After recompiling, you should observe that the application behaves as before. Angular detected a new reference to data, so it ran its change detection on the child component.

This concludes modifying a sample parent and child component to use the OnPush change detection strategy.
```