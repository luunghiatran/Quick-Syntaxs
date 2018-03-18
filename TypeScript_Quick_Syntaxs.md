# TypeScript Cú pháp nhanh

<!-- TOC -->

- [TypeScript Cú pháp nhanh](#typescript-cú-pháp-nhanh)
    - [Variable - Biến](#variable---biến)
        - [Type - Kiểu biến](#type---kiểu-biến)
        - [Declaration - Khai báo](#declaration---khai-báo)
    - [Function - Hàm chức năng](#function---hàm-chức-năng)
    - [Interfaces](#interfaces)
    - [Class](#class)
    - [Extend - Kế thừa](#extend---kế-thừa)
    - [Generics - kiểu chung T](#generics---kiểu-chung-t)
    - [Modules - Gọi hàm ngoài](#modules---gọi-hàm-ngoài)
    - [Lambda - Biểu thức nhanh](#lambda---biểu-thức-nhanh)

<!-- /TOC -->

## Variable - Biến

### Type - Kiểu biến

Number(float+int)
String
Boolean
Arrays Có 2 kiểu cú pháp: 

```ts
my_arr: number[];
my_arr: Array<number> = [2, 3, 5, 7];
```

Enum

```ts
enum Role {Employee, Manager, Administrator};
var role: Role = Role.Employee; //Using
```

Any (kiểu tự do)
Void - Hàm không trả về


### Declaration - Khai báo

```ts
var burger: string = 'hamburger',     // String 
    calories: number = 300,           // Numeric
    tasty: boolean = true;            // Boolean

// Alternatively, you can omit the type declaration:
var burger = 'hamburger';

// String expression
var str = `${title} costs ${price}`;
// nhiều dòng
var html = `<html>
              <body>
              </body>
            </html>`;
```

## Function - Hàm chức năng

```ts
function speak(food: string, energy: number): void {
  console.log("Our " + food + " has " + energy + " calories.");
}

//Using
speak(burger, calories);
```

## Interfaces

```ts
// Here we define our Food interface, its properties, and their types.
interface Food {
    name: string;
    calories: number;
    eating(): boolean;
}

// We tell our function to expect an object that fulfills the Food interface. 
// This way we know that the properties we need will always be available.
function speak(food: Food): void{
  console.log("Our " + food.name + " has " + food.calories + " calories.");
}

// We define an object that has all of the properties the Food interface expects.
// Notice that types will be inferred automatically.
var ice_cream = {
  name: "ice cream", 
  calories: 200
}

// Using
speak(ice_cream);

// Implements
class ChickenFood implements Food {
    eating() {
        return true;
    }
}
```

## Class

```ts
class Menu {
  // Our properties:
  // By default they are public, but can also be private or protected.
  items: Array<string>;  // The items in the menu, an array of strings.
  pages: number;         // How many pages will the menu be, a number.

  // A straightforward constructor. 
  constructor(item_list: Array<string>, total_pages: number) {
    // The this keyword is mandatory.
    this.items = item_list;    
    this.pages = total_pages;
  }

  // Methods
  list(): void {
    console.log("Our menu for today:");
    for(var i=0; i<this.items.length; i++) {
      console.log(this.items[i]);
    }
  }

} 

// Create a new instance of the Menu class.
var sundayMenu = new Menu(["pancakes","waffles","orange juice"], 1);

// Call the list method.
sundayMenu.list();
```

## Extend - Kế thừa

```ts
class HappyMeal extends Menu {
  // Properties are inherited

  // A new constructor has to be defined.
  constructor(item_list: Array<string>, total_pages: number) {
    // In this case we want the exact same constructor as the parent class (Menu), 
    // To automatically copy it we can call super() - a reference to the parent's constructor.
    super(item_list, total_pages);
  }

  // Just like the properties, methods are inherited from the parent.
  // However, we want to override the list() function so we redefine it.
  list(): void{
    console.log("Our special menu for children:");
    for(var i=0; i<this.items.length; i++) {
      console.log(this.items[i]);
    }

  }
}

// Create a new instance of the HappyMeal class.
var menu_for_children = new HappyMeal(["candy","drink","toy"], 1);

// This time the log message will begin with the special introduction.
menu_for_children.list();
```

## Generics - kiểu chung T

```ts
// The <T> after the function name symbolizes that it's a generic function.
// When we call the function, every instance of T will be replaced with the actual provided type.

// Receives one argument of type T,
// Returns an array of type T.

function genericFunc<T>(argument: T): T[] {    
  var arrayOfT: T[] = [];    // Create empty array of type T.
  arrayOfT.push(argument);   // Push, now arrayOfT = [argument].
  return arrayOfT;
}

// Using
var arrayFromString = genericFunc<string>("beep");
console.log(arrayFromString[0]);         // "beep"
console.log(typeof arrayFromString[0])   // String

var arrayFromNumber = genericFunc(42);
console.log(arrayFromNumber[0]);         // 42
console.log(typeof arrayFromNumber[0])   // number
```

## Modules - Gọi hàm ngoài

```ts
// Import other ts
import { ZipCodeValidator } from "./ZipCodeValidator";

// Using
let myValidator = new ZipCodeValidator();
```

## Lambda - Biểu thức nhanh

```ts
var product = ["Apple", "Lemon", "Banana"];
//javasript
product.forEach(function(p) {
    console.log(p);
});

//typescript
product.forEach( (p) => console.log(p) );
```

---
**Tham khảo:**
https://techmaster.vn/posts/34286/hoc-typescript-trong-30-phut