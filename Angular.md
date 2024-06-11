## What is Angular ?

>> To install angular CLI Globally
* npm install -global @angular/cli@latest

>> To create a new angular project
* ng new sample-web-app

>> To run the project
* ng serve

**main.ts is the entry point of any Angular Application**

## Angular Component :

```js
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
```js
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

```js
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
```js
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

```js
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
```js
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
```js
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

```js
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

```js
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

