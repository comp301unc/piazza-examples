# Interface Example

This is an example of implementing `Animal`, `Dog`, and `Cat` using an interface for Piazza question @75.

### Animal Interface
```java
// Animal interface
public interface Animal {

   String getName();
   int getAge();
   void makeNoise();
}
```

### Dog Class
```java
// Dog class
public class Dog implements Animal {

    String name;
    int age;

    public Dog(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() { return this.name; }

    public int getAge() { return this.age; }

    public void makeNoise() {
        System.out.println("Woof!");
    }
}
```

### Cat Class
```java
// Cat class
public class Cat implements Animal {

    String name;
    int age;

    public Cat(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() { return this.name; }

    public int getAge() { return this.age; }

    public void makeNoise() {
        System.out.println("Meow!");
    }
}
```
