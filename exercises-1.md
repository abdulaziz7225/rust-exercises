# Design and Implement a Small Plugin System

## Thread-Based Plugins

### Overview

In this exercise, we will design and implement a thread-based plugin system. The architecture will consist of two main components: a plugin manager and the plugins themselves. Here’s how it will work:

- **Plugin Manager**: 
  - A dedicated thread will run the plugin manager, which starts with zero registered plugins.
  - The plugin manager will continuously poll each registered plugin for updates.
  - If a plugin has work to do, it will execute that work in a blocking manner on the plugin manager's thread. This means that no two plugins can perform their tasks in parallel at this stage, which is acceptable for our initial implementation.

- **User Interaction**:
  - On a separate thread, the user will have the ability to register and unregister plugins dynamically.

The definitions of a `Plugin` and the `PluginManager` will be provided through Rust traits. It will be our responsibility to implement example structs that fulfill the required functionality for these traits.

### Exercises

The following exercises should help us to get some experience with the
necessary tools to implement the thread based plugin system.

## Exercise 1: Getting Comfortable with Threads in Rust

### Objective
Develop a multi-threaded program that demonstrates the use of threads in Rust.

### Instructions

1. **Spawn Multiple Threads**
   - Write a program that spawns a specified number of threads (e.g., 5).
   - Each thread should print its own unique identifier (e.g., thread number).

2. **Join Threads**
   - Ensure that the main thread waits for all spawned threads to complete before exiting.

3. **Experiment**
   - Modify the number of threads and observe the output.
   - Change the task performed by each thread to something simple, like counting or performing a calculation.

---

## Exercise 2: Getting Comfortable with Arc<Mutex<T>> in Rust

### Objective
Create a multi-threaded program that safely shares state between threads using `Arc<Mutex<T>>`.

### Instructions

1. **Set Up Shared State**
   - Define a shared counter that will be accessed by multiple threads.
   - Use `Arc<Mutex<T>>` to wrap the counter to ensure safe concurrent access.

2. **Spawn Threads**
   - Write a program that spawns multiple threads (e.g., 10).
   - Each thread should increment the shared counter a specified number of times (e.g., 1000).

3. **Join Threads**
   - Ensure that the main thread waits for all spawned threads to complete before printing the final value of the counter.

4. **Experiment**
   - Change the number of threads or the number of increments per thread and observe the final counter value.
   - Introduce a delay in the thread execution to see how it affects the output.


For the small project we're going to need a few tools

## Exercise 3: Getting Comfortable with Box<dyn Trait> in Rust

### Objective
Create a program that demonstrates the use of `Box<dyn Trait>` for dynamic dispatch in Rust.

### Instructions

1. **Define a Trait**
   - Create a trait named `Shape` with methods for calculating the area and perimeter of a shape.

2. **Implement the Trait**
   - Define at least two structs (e.g., `Circle` and `Rectangle`) that implement the `Shape` trait.
   - Ensure each struct has the necessary fields to calculate area and perimeter.

3. **Use Box<dyn Shape>**
   - Create a vector that holds `Box<dyn Shape>` to store different shapes.
   - Add instances of your `Circle` and `Rectangle` structs to this vector.

4. **Iterate and Display**
   - Write a loop that iterates over the vector of shapes and calls the methods to calculate and print the area and perimeter for each shape.

5. **Experiment**
   - Add another shape (e.g., `Triangle`) that also implements the `Shape` trait.
   - Modify the program to handle the new shape and display its area and perimeter.

## Exercise 4: Using UUID v4 as Hashes in Rust

### Objective
Create a program that generates UUID v4 values and demonstrates their use as unique identifiers or hashes.

### Instructions

1. **Add the UUID Dependency**
   - Open `Cargo.toml` and add the `uuid` crate as a dependency.

2. **Generate UUID v4**
   - Write a program that generates a specified number of UUID v4 values (e.g., 5).
   - Print each generated UUID v4 to the console.

3. **Use UUIDs as Hashes**
   - Create a simple data structure (e.g., a struct representing a user or an item) that includes a UUID v4 field as a unique identifier.
   - Implement a function that creates an instance of this data structure and assigns a newly generated UUID v4 as its identifier.

4. **Store and Retrieve Data**
   - Use a `HashMap` to store multiple instances of your data structure, using the UUID v4 as the key.
   - Write a function to retrieve an instance from the `HashMap` using its UUID v4.

5. **Experiment**
   - Modify the program to generate UUIDs for different types of data (e.g., products, sessions) and demonstrate how they can be used to uniquely identify and retrieve these items.
   - Consider the implications of using UUIDs as hashes in terms of collision resistance and uniqueness.
