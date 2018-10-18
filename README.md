# JSEpisodeFive-Demo

[Slides]()

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

### Code Blocks (this)

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

BLOCK 01 (CLASS - EMPTY)

```javascript
class Instructor {
    ...
}
```

BLOCK 02 (CLASS - W/CONSTRUCTOR)

```javascript
class Instructor {
  constructor(firstName, lastName, courses) {
    this.name = `${firstName} ${lastName}`;
    this.courses = courses;
    this.awesomePoints = 0;
  }
}
```

BLOCK 03 (CREATING OBJECT FROM CLASS)

```javascript
let instructor = new Instructor("Asis", "Alsaffar", [
  "JavaScript",
  "Node",
  "React"
]);
```

BLOCK 04 (WHOLE SHEBANG)

```javascript
class Instructor {
  constructor(firstName, lastName, courses) {
    this.name = `${firstName} ${lastName}`;
    this.courses = courses;
    this.awesomePoints = 0;
  }

  sayHello() {
    console.log(`Hi, I'm ${this.name}`);
  }

  addCourse(newCourse) {
    this.courses.push(newCourse);
  }

  teach() {
    this.awesomePoints++;
    return this.courses.map(course => `I teach ${course}`).join("\n");
  }
}

let instructorHamsa = new Instructor("Hamsa", "Makia", ["Python", "Django"]);
let instructorFawas = new Instructor("Fawas", "Almutairi", [
  "React Native",
  "Hacking"
]);

instructorHamsa.sayHello(); // logs "Hi I'm Hamsa Makia"
instructorFawas.sayHello(); // logs "Hi I'm Fawas Almutairi"
```

---

### Code Blocks (Inheritance)

BLOCK 01 (GENERIC STRUCTURE)

```javascript
class Child extends Parent {
  constructor(initialValues) {
    super(initialValues);
  }
}
```

BLOCK 02 (EXAMPLE - PARENT CLASS)

```javascript
class Person {
  constructor(firstName, lastName, age) {
    this.name = `${firstName} ${lastName}`;
    this.age = age;
  }

  greetings() {
    console.log(`Hi! I'm ${this.name}`);
  }
}
```

BLOCK 03 (EXAMPLE - CHILD CLASS)

```javascript
class Instructor extends Person {
  constructor(firstName, lastName, age, subjects) {
    super(firstName, lastName, age);
    this.subjects = subjects;
    this.awesomePoints = 0;
  }
}
```

BLOCK 04 (EXAMPLE - USING CHILD CLASS)

```javascript
let instructor = new Instructor("Asis", "Alsaffar", 32, [
  "JavaScript",
  "React",
  "Node"
]);

console.log(instructor); // logs {name: "Asis Alsaffar", age: 32, subjects: ["JavaScript", "React", "Node"], awesomePoints: 0}

instructor.greetings(); // logs "Hi! I'm Asis Alsaffar"
```
