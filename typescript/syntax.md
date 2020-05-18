# 🔥Typescript Syntax

```ts
//boolean
let isCool: boolean = true;

//numberr
let age: number = 26;

//string
let personName: string = 'John Doe';
let quote: string = `I'm not old, I am only ${age}`;

//Array
let pets: string[] = ['cat', 'dog', 'rabbit'];
let pets2: Array<string> = ['cat', 'dog', 'rabbit'];

//Object
let studentDetails: object = {
    name: 'john',
    age: 22
}

//null and undefined
let progress: undefined = undefined;
let report: null = null;

//Tuple
let basket: [string, number];
basket = ['basketball', 5];

//Enum
enum size { Small = 1, Medium = 2, Large = 3 };
let sizeName: string = size[2];

//Any 
let whatever: any = 'ahfffffffffffff noooooooooooo!!';
whatever = 5;

//void - doesn't return anything
let sing = (): void => {
    console.log('lalalllllalalal');
}
sing();

//never - Cannot have a reachable endpoint and does not return anything
let error = (): never => {
    throw Error('oops!!');
}

//interface
interface RobotArmy {
    count: number,
    type: string,
    magic?: string //optional
}
let fightRobotArmy = (robots: RobotArmy) => {
    console.log('Fight');
}
// Above code is equivalent to following code
let fightRobotArmy2 = (robots: { count: number, type: string, magic: string }) => {
    console.log('Fight');
}

//Type assertion
interface CatArmy {
    count: number,
    type: string,
    magic: string
}

let dog = {} as CatArmy;
dog.count;

//functions
let fightRobotArmy3 = (robots: RobotArmy): void => {
    console.log('Fight');
}

//Classes
class Animal {
    private sing: string = 'lalalalalalala';
    constructor(sound: string) {
        this.sing = sound;
    }
    greet() {
        return `Hello ${this.sing}`;
    }
}

let cat = new Animal('meowwwww');
cat.greet();

//Union
let confused: string | number;
confused = 'skeptical';
confused = 0;

let x = 4;
//x = 'five';//five is not a number
x = 5;

```