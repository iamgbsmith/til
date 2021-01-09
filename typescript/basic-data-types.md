# Basic Data Types

__Category: TypeScript__

TypeScript basic data types are are used in interfaces and type definitions.

| Data Type            | Example Value/Description   |
| -------------------- |-----------------| 
| `array` | `let list: Array<string> = ["cat", "dog", "parrot"];` |
| `boolean` | `let isCompleted: boolean = false;` |
| `enum` | `enum Color {Red, Green, Blue}` <br> `let c: Color = Color.Green;` |
| `number` |  `let size: number = 6;` <br> `let hex: number = 0xb33f;` |
| `object` | `object` is a type that represents a non-primitive type, i.e. anything that is not number, string, boolean, etc. |
| `string` | `let color: string = "blue";` |
| `tuple` | `let details: [string, number, number];` <br> `details = ["morning", 10, 42];` |
| `void` | `void` is considered the opposite of any and can be used as the return type of functions that do not return a value <br> `function doNothing(): void { console.log("This is a log statement"); }` |
| `any` | `let thing: any = 4;` <br> `thing = "hello world";` <br> `thing = 42;` |

__Note:__ Using the `any` type is a way to opt-out of type checking and let the values pass through compile-time checks. 

Use of `any` should be avoided where possible however it may be required if describing variables types that are unknown at the time of developing an application.

See [Basic Types](https://www.typescriptlang.org/docs/handbook/basic-types.html) for more details.