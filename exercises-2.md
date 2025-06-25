# Small exercises to get used to Rust syntax, work with functional programming, async and `tokio` crate

## Exercise 1: Sum of Squares (Easy)

### Objective: Calculate the sum of the squares of a list of integers

1. Procedural Style: Write a function `sum_of_squares_procedural` that takes a vector of integers and returns the sum of their squares using a loop procedurally.

   ```rust
   fn sum_of_squares_procedural(numbers: Vec<i32>) -> i32 {
       // ...
       for xyz in numbers {
           // ...
       }
       // ...
   }
   ```

2. Functional Style: Write a function `sum_of_squares_functional` that achieves the same result using iterators and functional programming concepts.

   Hints:

   - This should be possible in one line without using a single `;`
   - relevant methods: `map` and `sum`

   ```rust
   fn sum_of_squares_functional(numbers: Vec<i32>) -> i32 {
       numbers.SOME_ITERATOR_METHOD().SOME_OTHER_ITERATOR_METHOD() // ...
   }
   ```

## Exercise 2: Filtering Even Numbers (Medium)

### Objective: Filter out even numbers from a list and return a new list

1. Procedural Style: Write a function `filter_even_numbers_procedural` that takes a vector of integers and returns a new vector containing only the odd numbers using a loop.

2. Functional Style: Write a function `filter_even_numbers_functional` that uses iterators to filter out even numbers.

   Hint:

   - This is again possible in one line
   - relevant methods: `filter`

   ```rust
   fn filter_even_numbers_xyz(numbers: Vec<i32>) -> Vec<i32> {
       // ...
   }
   ```

## Exercise 3: Grouping and Counting (Difficult)

### Objective: Group a list of strings by their lengths and count how many strings fall into each length category

1. Procedural Style: Write a function `group_by_length_procedural` that takes a vector of strings and returns a HashMap where the keys are the lengths of the strings and the values are the counts of strings of that length.

2. Functional Style: Write a function `group_by_length_functional` that achieves the same result using iterators and functional programming techniques. Hint:

   Hint:

   - This is once again possible in one line
   - relevant methods: `map` and `fold`

   ```rust
   fn group_by_length_xyz(strings: Vec<String>) -> HashMap<usize, usize> {
       // ...
   }
   ```

## Exercise 4: Asynchronous HTTP Client & Serde Usage

### Objective: Create an asynchronous HTTP client that fetches data from a public API and processes the response

Tasks:

- Use the `reqwest` crate (which works well with `tokio`) to make asynchronous HTTP requests.
- Fetch data from a public API, such as the [JSONPlaceholder API](https://jsonplaceholder.typicode.com/posts).
- Parse the JSON response and print the titles of the posts.
- Here are relevant dependencies

  ```toml
  [dependencies]
  tokio = { version = "*", features = ["full"] }
  reqwest = { version = "*", features = ["json"] }
  serde = { version = "*", features = ["derive"] }
  serde_json = "*"
  ```

## Exercise5: Asynchronous Chat Server

### Objective: Build a simple asynchronous chat server using Tokio that allows multiple clients to connect, send messages, and receive messages in real-time

Task:

- Create a TCP server that listens for incoming connections.
- Allow multiple clients to connect and communicate with each other.
- Implement a basic protocol for sending and receiving messages.
- Use `tokio`'s asynchronous features to handle multiple clients concurrently.

Steps:

1. Set Up the Project: Create a new Rust project and add the necessary dependencies in Cargo.toml. `tokio` should be enough but feel free to include whatever you want.
2. Create the Chat Server: Write the main server logic:

   - The server will listen for incoming TCP connections
   - once a client connects, spawn a new task for that client
   - exchange the chat messages to all existing clients (hint: use `Arc<Mutex<_>>` to track all the clients and share the data between tasks)
   - disconnect clients properly when they leave

3. Run the Chat Server: Compile and run the server. Make it listen for incoming connections on 127.0.0.1:8080.
4. Create a Simple Client: You can create a simple client using `telnet` CLI or write a separate Rust client that connects to the server.
