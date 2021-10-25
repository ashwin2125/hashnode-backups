## Generics in Java - Explained !

Generic programming allows users to write flexible, reusable functions that can handle any valid data type by defining a simple change in approach to our existing code while still ensuring type safety. When defining classes, interfaces, and methods, generics allow types (classes and interfaces) to be parameters. Type parameters, like the more common formal parameters used in method declarations, make it possible for you to reuse the same code with different types of inputs. The only difference is that formal parameters' inputs are values, whereas type parameters' inputs are types.

### **Scope of the article:**

- This article describes Generics in Java and addresses the questions "Why" and "How" generic programming works, allowing you to gain a comprehensive understanding of Generics.

- The sole motivation of this article is to help the readers comprehend the fundamental principles of Generics, so it does not delve into depth into the underlying functioning mechanism of Generics.

### **Contents: **

- Definition

- Java Generics : Why?

- Java Generics : How?

- Bounded Type Parameters

- Generics : Wildcards

- Summary

### **Definition:**

Generics let users to write generic code that works with objects of different types such as Integers, Strings, and so on, allowing for code reuse and compile-time type safety (which identifies invalid types when the code is being compiled).

Generics was introduced in Java 5 with the Collection Framework in 2004. Generics let us to define classes, interfaces, and functions that accept 'types' as 'parameters', thereby allowing our code to be more reliable. . We use angle brackets (<>) to specify the type parameters. These type parameters usually contain single, uppercase letters as Generic variables to make it easily distinguishable from other variables that we define.

**Example:**

With Java Generics, you can write a generic method to explicitly define a datatype to sort a list of arrays and then invoke the generic method with Integer or String array to sort the elements, thereby eliminating the need to typecast and enabling code reusability.


```
private List<E> array = new ArrayList<>(size);
``` 

### **Why use Java Generics:**

You could write and compile the following code without raising an error or warning before the introduction of generics in Java 5:

```
List arrList = new ArrayList();
arrList.add("Hi, Scaler !");
arrList.add(new Object());
``` 

You could add values of any type to a list or another Java Collection without having to declare what type of data it stores. However, when retrieving the values from the list, you must explicitly convert it to a certain type.

If we iterate the above list, the compiler will produce a **CastClassException** when i=1:

```
for (int i=0; i< arrList.size(); i++) {
    String value = (String) arrList.get(i);//CastClassException when i=1
}
```

Allowing the creation of a list without first declaring the stored data type, as we did, may lead to programmers committing errors like the one above, resulting in **ClassCastException** being thrown at **runtime**.

Here's where **Generics** comes into the scene. Generics was introduced to prevent programmers from making such mistakes.

With Generics, you can explicitly declare the data type that is going to be stored when creating a Java Collection, as shown below.

```List<E> arrayList = new ArrayList<>();```

- **E **-- Generic Data Type parameter.

Now, you can make the **arrayList** store **Integer**, **String, etc.,** explicitly. Now, you cannot mistakenly store an Integer in a String type list, without throwing a compile-time error, thereby ensuring **type safety** at the compile-time itself.

### **How to use Java Generics:**

Generics in Java is used with methods and classes in common.

**1. Generic Method:**

A generic method is similar to a regular function, except it contains type parameters that are cited by the actual type. This makes it possible to utilize the generic approach in a broader context.

The compiler handles type safety, making it easier for programmers to code because they don't have to execute tedious, individual type casts.

```public static <T> T element(T obj){ return returnValue; }```

**2. Generic Class:**

A generic class is created in the same way as a non-generic class. The main difference is that it has a section for **"type parameters"**.

A comma can be used to separate many types of parameters. Parameterized classes or parameterized types are classes that take one or more parameters.

```
class Test<T> {
private T item; 
public T getItem() {  return item; }
public void setItem(T item) {this.item = item; }   
}```

### **Bounded Type Parameters:**

So far, any data type other than primitive types may be parameterized in the generic classes and methods we've created. But what if we wanted to restrict the data types that generics may accept?

This is where the concept of **bounded type parameters** comes into play.

You can restrict the data types that a generic class or function accepts by declaring it to be a subclass of another data type.

**For example:**

```
//accepts only subclasses of List
public class UpperBoundedClass<T extends List>{
public <T extends List> void UpperBoundedMethod(T[] arr) {
}
}```

Only subclasses of the List data type can be used to parameterize the **UpperBoundedClass** and **UpperBoundedMethod**.

The type parameter's upper bound is set by the list data type. It will produce a compile-time error if you try to use a data type that isn't a subtype of List.

The bounds aren't only restricted to classes. You can also pass interfaces. In this situation, extending the interface means implementing it.

### **Java Generics Wildcards:**

Wildcards are used to pass on parameters of generic types to methods. Unlike a generic method, the generic argument is passed to the method's accepted parameters, which is not the same as the data type parameter we mentioned before. The `?` symbol is used to signify a wildcard.


```
public void printItems(List<?> list) {
for (int i=0; i< list.size(); i++) {
    System.out.println(list.get(i));
}
}```

### **Summary:**

- Generics in Java resemble templates in C++. It is a significant aspect to the Java programming language as it makes development easier and less error prone.

- Generics offer type safety at compile time and, more crucially, let us to implement generic algorithms without adding overhead to our projects.

- Ada, C#, Delphi, Eiffel, F#, Java, Python, Rust, Swift, TypeScript and Visual Basic are some of the programming languages that supports Generics as of now.


Did you note how it generalizes classes and methods so that you don't have to repeat code for multiple data types? 

Having good knowledge of Generics is important for you moving forward as a programmer/developer. So, try applying what you learned in this article in code.

That's it for now. Meet you in the next article ! 💌

வாழ்க தமிழ் ! வளர்க தமிழினம் ! 🟥🟨