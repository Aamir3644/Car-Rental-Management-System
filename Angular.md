## What is Angular ?

>> To install angular CLI Globally
* npm install -global @angular/cli@latest

>> To create a new angular project
* ng new web-app 
 (This Command will create a project without module.ts file)
* ng new web-app --no-standalone
 (This Command will create a project with module.ts file)

>> To run the project
* ng serve

**main.ts is the entry point of any Angular Application**

## Angular Component :

```ts
        import {Component} from @angular/core;

        // "@" is called a decorator, it is a typescript feature
        @Component({
            selector : 'app-my-component',
            templateUrl : './app.component.html',
            styleUrls : ['./app.component.css']
        })

        export class MyComponent {

        }
```

## DataBinding :
>> It is the way of binding the data defined in your TypeScript Code to your HTML template and vice versa.

- There are different types of Data Bindings :

(1) String Interpolation : 

- It is used to bind data from component class to the view (HTML file). It uses {{}} double curly braces. 
```ts
        //app.component.ts

        export class AppComponent{
            address : string = "Pune";
            user = {
                name = "Aamir";
                age = 25;
            };
        }
```
```html
        <!-- app.component.html -->

        <h1>User Name - {{user.name}}</h1>
        <p>Address - {{address}}</p>
```

(2) Property Binding : 

- It is used to bind the data in the component to an element property in the DOM.
- It is used to bind the data in the component to an attribute of an HTML Tag.
- It is done using square brackets []

```ts
        //app.component.ts

        export class AppComponent {
            imageUrl = 'https://angular.io/assets/images/logos/angular/angular.png';
            isDisabled = true;
        }
```
```html
        <!-- app.component.html -->

        <img [src]="imageUrl" alt="Angular Logo">
        <button [disabled]="isDisabled">Click Me</button>
```

(3) Event Binding : 

- Event binding is used to listen to events such as keystrokes and clicks. It is done using parentheses ().
```ts
        // app.component.ts
        // In below code, `event.target` property is of generic type EventTarget, which does not have a value property. By casting it to `HTMLInputElement`, you can access the value property.

        export class AppComponent {
                serverName = 'Testserver';
  
                onUpdateServerName(event) {
                    this.serverName = (<HTMLInputElement>event.target).value;
                };
        }
```
```html
        <!-- app.component.html -->
        <input
        type="text"
        class="form-control"
        (input)="onUpdateServerName($event)">

        <p>Server Name : {{ serverName }}</p>
```

(4) Two-way Binding : 
- Two-way data binding combines property binding and event binding, typically used with forms. It uses the [(ngModel)] syntax.
- For two-way data binding to work, you need to import FormsModule in your module.
- It uses the ngModel directive to enable this synchronization.

```ts
        export class AppComponent {
        
            serverName = 'Test Server';
        }
```
```html
        <input 
            type="text"
            class="form-control"
            [(ngModel)]="serverName">

        <p>Server Name : {{ serverName }}</p>
```

## Directives :
>> Directives are classes that can change the appearance or behavior of elements in your Angular application. 

- There are three main types of directives:

(1) Component Directives : These are the most common type, extending the @Component decorator. Components are essentially directives with a template.

(2) Structural Directives : These directives change the structure of the DOM, adding or removing elements. 
Structural Directives are commonly used with * but they can be used without * if they are getting used in `ng-template`.
Examples include *ngIf, *ngFor, and *ngSwitch.

(3) Attribute Directives : These directives change the appearance or behavior of an element, component, or another directive. Examples include ngClass, ngStyle, and custom attribute directives.


### ngIf 
>> It is basically used in Conditional Rendering Tasks.
>> ngIf can be used with with * (Asterisk) or without * (Asterisk). Both of the examples are below.

- With *
```html
        <div>
                <div *ngIf="isSignedIn; else elseBlock">
                        <h1>Welcome to the application</h1>
                        <h2>Products</h2>
                        <ul>
                        <li *ngFor="let product of products">{{product}}</li>
                        </ul>
                </div>
                <ng-template #elseBlock><h1>You are not signed in</h1></ng-template>
        </div>
```

- Without * : Using `ng-template`
```html
        <ng-template [ngIf]="condition">
                <div>Content to display if condition is true.</div>
        </ng-template>

```

### ngFor
>> The *ngFor directive repeats a template for each item in a list.
>> It is similar to the use of the map() function in React when we try to mount elements in the UI from an array.
>> ngFor can be used with with * (Asterisk) or without * (Asterisk). Both of the examples are below.

- With *
```html
        <table>
        <thead>
            <th>Name</th>
        </thead>
        <tbody>
            <tr *ngFor="let hero of heroes">
                <td>{{hero.name}}</td>
            </tr>
        </tbody>
        </table>
```
```html
        <ul>
                <li *ngFor="let hero of heroes">{{hero.name}}</li>
        </ul>
```

- Without * : Using `ng-template`
```html
        <ng-template ngFor let-item [ngForOf]="items">
                <li>{{ item }}</li>
        </ng-template>

```

### ngSwitch
>> Used to switch between different content based on a condition.

-With *
```html
        <div [ngSwitch]="expression">
                <div *ngSwitchCase="'case1'">Case 1 content</div>
                <div *ngSwitchCase="'case2'">Case 2 content</div>
                <div *ngSwitchDefault>Default content</div>
        </div>
```

- Without * : Using `ng-template`
```html 
        <ng-template [ngSwitch]="expression">
                <ng-template [ngSwitchCase]="'case1'">
                <div>Case 1 content</div>
                </ng-template>
                <ng-template [ngSwitchCase]="'case2'">
                <div>Case 2 content</div>
                </ng-template>
                <ng-template ngSwitchDefault>
                <div>Default content</div>
                </ng-template>
        </ng-template>
```

### ngStyle
>> The ngStyle directive allows you to set inline styles dynamically.
```html
        <div [ngStyle]="{ 'color': textColor, 'font-size': fontSize + 'px' }">
                 This div's style depends on textColor and fontSize.
        </div>
```

### ngClass
>> The ngClass directive adds and removes a set of CSS classes.

**We can not use Two Structural Directives on a single html element**

## Custom Property Binding :
>> Custom property binding allows communication between parent component and child component.
>> We can send data from Parent Component to Child Component and vice versa.
>> @Input is used to send data from parent component to child component.
>> @Output is used to send data form child component to parent component.

- Sending Data from Parent Component to Child Component
```ts
        //child.component.ts
        export class ChildComponent {
           @Input() title : string;
           @Input() description : string;
        }
```
```html
        <!-- child.component.html -->
        <h1>Title : {{title}}</h1>
        <h2>Description : {{description}}</h2>
```
```ts
        //parent.component.ts
        export class ParentComponent {
           parentTitle = "Weoto Technologies";
           parentDescription = "Canada Corner, Nashik";
        }
```
```html
        <!-- parent.component.html -->
        <app-child [title]="parentTitle" [description]="parentDescription"></app-child>
```

- Sending Data from Child Component to Parent Component

> The child component defines an EventEmitter using the @Output() decorator.

```ts
        //child.component.ts
        export class ChildComponent {
           @Output() customEvent : EventEmitter<string> = new EventEmitter<string>();

           sendDataToParent() {
              this.customEvent.emit('Data from Child');
           }
        }
```

> When the method sendDataToParent() is called, it emits an event with the data 'Data from Child'.

```html
        <!-- child.component.html -->
        <button (click)="sendDataToParent()">Send Data to Parent</button>
```

> In the parent component's template, you bind to the `customEvent` using the event binding syntax. The handler method handleCustomEvent in the parent component will be called when the event is emitted.

```ts
        //parent.component.ts
        export class TestComponent {
           show = '';

           handleCustomEvent(data: string) {
              console.log(data); // Output: 'Data from Child'
              this.show = data;
           }
        }
```

> The parent component defines the method handleCustomEvent which receives the emitted data as its parameter.

```html
        <!-- parent.component.html -->
        <app-child (customEvent)="handleCustomEvent($event)"></app-child>
        <h1>{{show}}</h1>
```
## Non-Null Assertion Operator :
>> The `!` is called the "non-null assertion operator" in TypeScript.
>> It is used to tell the TypeScript compiler that you are certain that a variable or property will not be null or undefined at runtime
>> In the context of Angular's @Input(), properties are often initialized by the parent component after the child component has been instantiated. TypeScript's strict null checks might complain that these properties are potentially undefined because they are not initialized in the constructor. By using the !, you assert to TypeScript that these properties will indeed be initialized before they are used.
```ts
        @Input() count!: number; // Non-null assertion
```

## Template Reference Variable :
>> Template reference variables in Angular are a powerful feature that allow you to reference a DOM element or an Angular component within a template.
>> You can create a template reference variable by adding a `#` followed by the variable name to any element.

```html
        <input #myInput type="text">
        <button (click)="logValue(myInput.value)">Log Input Value</button>
```
```ts
        export class AppComponent {
           logValue(value: string) {
           console.log(value);
           }
        }
```

## @ViewChild 
- The `@ViewChild` decorator in Angular is used to access a child component, directive, or DOM element from a parent component. It allows you to interact with the child component's properties and methods directly in the parent component.

```ts
        @ViewChild('dobInput') dob : ElementRef;
        @ViewChild('ageInput') age : ElementRef;

        calculateAge(){
                let birthYear = new Date(this.dateOfBirth.nativeElement.value).getFullYear();
                let CurrentYear = new Date().getFullYear();
                let age = currentYear - birthYear;
                this.age.nativeElement.value = age;
        }
```
```html
        <input type="date" #dobInput (blur)="calculateAge()">
        <input type="text" #ageInput>
```

## ng-content :
- Content projection is a way to pass the HTML content from the parent component to the child component. The child component will display the template in a designated spot.
- The `ng-content` tag acts as a placeholder for inserting external or dynamic content. The Parent component passes the external content to the child component. When Angular parses the template, it inserts the external content where ng-content appears in the child component’s template.
```html
        <!-- child.component.html -->
        <h2>Child Component</h2>
        <ng-content></ng-content>
```
```html
        <!-- parent.component.html -->
        <h2>This is Parent Component</h2>
        <app-child>
                <p #paragraph>This is a paragraph</p>
        </app-child>
```

## @ContentChild
- The `@ContentChild` decorator is used to access an element or a component that is projected into another component.
- This means that the element being sent from the parent component can be accessed using `@ContentChild`
```html
        <!-- parent.component.html -->
        <h2>This is Parent Component</h2>
        <app-child>
                <p #paragraph>This is a paragraph</p>
        </app-child>
```
```html
        <!-- child.component.html -->
        <ng-content></ng-content>
```
```ts
        //child.component.ts
        export class ChildComponent implements OnInit, AfterContentInit {

           ngOnInit() : void{
                console.log(this.paragraphEl); 
                //This will print undefined cause properties decorated with @ContentChild gets initialized just before ngAfterContentInit()
           }

           ngAfterContentInit(){
                console.log(this.paragraphEl.nativeElement.textContent);
                // Above line can now access the element cause it is initialized.
           }

           @ContentChild('paragraph') paragraphEl : ElementRef
        }
```

## Angular Life Cycle :

- **Change Detection Cycle**
*Change detection is the mechanism by which angular keeps the template in sync with the component*
- Angular runs a change detection cycle on every event that may result in a change. It runs on every input change, DOM event, and timer event like setTimeout(), setInterval(), HTTP requests, etc. 
- During the change detection cycle, angular checks every bound property in the template with that of the component class. If it detects any changes, it updates the DOM. 

- **Angular Life Cycle Hooks are as follows :**

(1) `ngOnChanges`
- `ngOnChanges` is the first lifecycle hook called in Angular.
- Input data-bound properties gets initialized first and then this hook gets called.
- It is triggered whenever there are changes to the input properties of a component.
- This hook provides a way to react to changes in input properties before the component is initialized with `ngOnInit`
- If the component has no input properties or there are no changes, `ngOnChanges` is not called.

(2) `ngOnInit`
- `ngOnInit` hook is fired right after `ngOnChanges`.
- This hook is fired only once and immediately after its creation (during the first change detection).
- This is a perfect place where you want to add any initialization logic for your component.  Here you have access to every input property of the component. You can use them in HTTP get requests to get the data from the back-end server.
- But note that none of the child components or projected content are available at this point. Hence any properties we decorate with @ViewChild, @ViewChildren, @ContentChild & @ContentChildren will not be available to use.

(3) `ngDoCheck`
- Whenever a event happens, angular runs a change detection cycle. For every change detection cycle, ngDoCheck gets called.
- You can use this lifecycle hook to manually check for state changes outside of Angular's normal change detection, manually updating the component's state.
- This method runs very frequently and can significantly impact your page's performance. Avoid defining this hook whenever possible, only using it when you have no alternative.
- During initialization, the first `ngDoCheck` runs after `ngOnInit`

(4) `ngAfterContentInit`
- This hook gets called when projected content gets initialized completely.
- This hook gets called only once during first change detection cycle, after that it does not gets called.

(5) `ngAfterContentChecked`
- This hook gets called when projected content changes.
- This hook gets called for every change detection cycle.

(6) `ngAfterViewInit`
- This hook gets called when component's view and all its child views gets initialized.
- This hook also gets called only once, during the first change detection cycle.

(7) `ngAfterViewChecked`
- This hook gets called whenever any change happens to the view.
- This hook gets called for every change detection cycle.

(8) `ngOnDestroy`
- This hook is called just before the Component/Directive instance is destroyed by Angular.

## Service
- A service is a class that contains reusable business logic, data fetching, and other operations that can be shared across different components. 
- It is possible for two components to communicate with each other which does not have a relationship, using services.

## Dependency Injection
- Dependency Injection is a design pattern in which dependency to the components are provided externally instead of creating them locally.
- This promotes loose coupling and modular development.

## Hierarchical Injection System
- Root Injector: Singleton service instance throughout the application.
```ts
        @Injectable({
           providedIn: 'root'
        })
        export class RootService { }

```
- Module Injector: Singleton within the module.
```ts
        @NgModule({
           providers: [ModuleService]
        })
        export class FeatureModule { }

```
- Component Injector: New instance per component.
```ts
        @Component({
           selector: 'app-parent',
           template: `<app-child></app-child>`,
           providers: [ComponentService]
        })
        export class ParentComponent { }

```
- Inheritance: Child components inherit services from parent components unless overridden.

- **Note**
> When a service is provided at the component level, each component gets its own instance of that service. Consequently, if data in a component-level service instance is updated, this change will not be reflected in other components that have their own instances of the same service.

## Observables
- We use observables to perform asynchronous operations and handle asynchronous data.
- Observables can be created using many ways as follows :
```ts
        myobservable = new Observable((observer)=>{
           observer.next('hello');
           observer.complete();
        })
```
```ts
        myobservable = of(5,10,5);
```
```ts
        myobservable = from([5,90,8]);
        //from() function takes array as an input emit element present in an array one by one.
```
- We can subscribe to an observable to receive data.
- After complete(), we do not receive data.
```ts
        this.myobservable.subscribe({
           next : value => console.log(value),
           error : err => console.log(err),
           complete : () => console.log("observable completed...")
        }) 
```

### Operators
- There are different operators like map(), filter() that we can use to operate on the data that we are receiving from an observable.

```ts
        transformedObs = this.myobservable.pipe(map((val)=>{
                return val*2;
        }));
```

## Routing
- Routing is a feature that enable us to navigate between different views of our application.

## Route Guards
- Route guards are used to control access to certain routes based on certain conditions.
- They help in protecting routes from unauthorized access, ensuring that only authorized users can navigate to certain parts of an application.

- **There are Five types of Route Guards**
> (1) CanActivate: Checks if a route can be activated.
> (2) CanActivateChild: Checks if child routes can be activated.
> (3) CanDeactivate: Checks if a route can be deactivated.
> (4) Resolve: Pre-fetches data before activating a route.
> (5) CanLoad: Checks if a module can be loaded.