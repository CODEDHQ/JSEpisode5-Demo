# JSEpisodeFive-Demo

[Slides](https://docs.google.com/presentation/d/1N31I6dP7xlx30G8BT7g66g2Gk0AhDXRjuBIEn0XYHyQ)

---

### Code Blocks (Methods)

BLOCK 01 (OBJECT METHODS)

```javascript
let obj = {
  incrementCounter: counter => counter++
};

obj.incrementCounter(5); // returns 6
```

---

### Code Blocks (`this`)

BLOCK 01 (THIS - WRONG)

```javascript
let instructor = {
  name: "Asis",
  sayHello: () => console.log(`Hi, I'm ${name}`)
};
```

BLOCK 02 (THIS - RIGHT)

```javascript
let instructor = {
  name: "Asis",
  sayHello: () => console.log(`Hi, I'm ${this.name}`)
};
```

---

### Code Blocks (Classes)

BLOCK 00 (INTUITION)

Why is it bad to create the same kind of object manually?
Time-consuming, error-prone

```javascript
const instructorHamsa = {
  name: "Hamsa Makia",
  ...
}

const instructorFawas = {
  name: "Fawas Almutairi",
}
```

BLOCK 01 (CLASS - EMPTY)

```javascript
class Instructor {}
```

You can create a new class by using the `new` keyword:

```javascript
let instructor = new Instructor();
```

BLOCK 02 (CLASS - PROPERTIES)

```javascript
class Instructor {
  name = "Lailz";
  courses = ["JavaScript", "React", "React Native"];
  awesomePoints = 1000000;
}
```

```javascript
let instructor = new Instructor();
console.log(instructor); // Instructor { name: 'Lailz', ... }
```

BLOCK 03 (CLASS - METHODS)

```javascript
class Instructor {
  name = "Lailz";
  courses = ["JavaScript", "React", "React Native"];
  awesomePoints = 1000000;

  sayHello = () => console.log(`Hi, I'm ${this.name}`);

  addCourse = newCourse => this.courses.push(newCourse);

  teach = () => {
    this.awesomePoints++;
    console.log(this.courses.map(course => `I teach ${course}`).join("\n"));
  };
}
```

```javascript
let instructor = new Instructor();
instructor.sayHello();
...
```

BLOCK 04 (CLASS - CONSTRUCTOR)

We still haven't solved the problem!
What if there are more instructors than just Lailz?!
How do we create many _different_ instructors from the same blueprint (class)?

```javascript
class Instructor {
  constructor(firstName, lastName, courses) {
    this.name = `${firstName} ${lastName}`;
    this.courses = courses;
  }

  awesomePoints = 0;

  ...
}
```

```javascript
let instructorAsis = new Instructor("Asis", "Alsaffar", [
  "JavaScript",
  "Node",
  "React"
]);
let instructorHamsa = new Instructor("Hamsa", "Darth", ["Python", "Django"]);
let instructorFawas = new Instructor("Fawas", "Almutairi", [
  "React Native",
  "Hacking"
]);

instructorAsis.sayHello(); // logs "Hi I'm Asis Alsaffar"
instructorHamsa.sayHello(); // logs "Hi I'm Hamsa Makia"
instructorFawas.sayHello(); // logs "Hi I'm Fawas Almutairi"
...
```

---

### Code Blocks (Inheritance)

BLOCK 01 (INHERITANCE - PARENT CLASS)

```javascript
class Person {
  constructor(firstName, lastName, age = 0) {
    this.name = `${firstName} ${lastName}`;
    this.age = age;
  }

  grow = () => (this.age = this.age + 1);

  sayHello = () => console.log(`Hi! I'm ${this.name}`);
}
```

BLOCK 02 (INHERITANCE - CHILD CLASS)

```javascript
class Instructor extends Person {
  constructor(firstName, lastName, subjects, age) {
    super(firstName, lastName, age);
    this.subjects = subjects;
  }

  awesomePoints = 0;

  // Methods
  ...
}
```

BLOCK 03 - (INHERITANCE - METHOD OVERRIDE)

```javascript
class Instructor extends Person {
  constructor(firstName, lastName, subjects, greeting="Hi", age) {
    super(firstName, lastName, age);
    this.subjects = subjects;
    this.greeting = greeting;
  }

  awesomePoints = 0;

  sayHello = () => console.log(`${this.greeting}! I'm ${this.name}`);

  ...
}
```
