# Abstract Class Example

This is an example of implementing Animal, Dog, and Cat using an abstract class for Piazza question @75.

### Animal Abstract Class

```java
// Animal abstract class
public abstract class Animal {

    String name;
    int age;

    public Animal(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() { return this.name; }

    public int getAge() { return this.age; }

   abstract void makeNoise();
}
```

### Dog Class

```java
// Dog class
public class Dog extends Animal {

    public Dog(String name, int age) {
        super(name, age);
    }
    // getName() and getAge() are inherited
    public void makeNoise() {
        System.out.println("Woof!");
    }
}
```

### Cat Class

```java
// Cat class
public class Cat extends Animal {

    public Cat(String name, int age) {
        super(name, age);
    }
    // getName() and getAge() are inherited
    public void makeNoise() {
        System.out.println("Meow!");
    }
}
```
