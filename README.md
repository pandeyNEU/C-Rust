# C-Rust

Why Rust over other low- level languages( C & C ++)?

@ Memory Safety 
Rust wants you to avoid unexpected updates by intoducing ownership and borrowing.
Ownership - Every value owned by single variable at a time.
Borrowing - Reassigning value to other variable going to moved the value. Old variable can't be used to access the value anymore.
for example:

    let s1 = String::from("hello");
    let s2 = s1;
    println!("{s1}, world!");

Here rust will ensure memory safty by making s1 invalid. We can no longer access s1 after line let s2 = s1. Therfore Rust does not care about freeing memory of s1.

@Concurrency

Concurrent programming(where different parts of program run independetly) and Parallel programming(where different parts of program run at the same time) challenges are being solved by using memory safety and type systems at compile time itself.

For example:


    use std::thread;

    use std::time::Duration;

    fn main() {
  
    let handle = thread::spawn(|| {
        for i in 1..10 {
            println!("hi number {i} from             the spawned thread!");
    thread::sleep(Duration::from_millis(1));
        }
    });

    handle.join().unwrap();

    for i in 1..5 {
        println!("hi number {i} from the            main thread!");
    thread::sleep(Duration::from_millis(1));
    }
    }

Here calling join method on handle blocks the thread currently running and waits for the thread represented by handle terminates.

Here main thread will wait for the spawned thread to complete its for loop , then main thread run its own for loop.Output would look like this -

hi number 1 from the spawned thread!
hi number 2 from the spawned thread!
hi number 3 from the spawned thread!
hi number 4 from the spawned thread!
hi number 5 from the spawned thread!
hi number 6 from the spawned thread!
hi number 7 from the spawned thread!
hi number 8 from the spawned thread!
hi number 9 from the spawned thread!
hi number 1 from the main thread!
hi number 2 from the main thread!
hi number 3 from the main thread!
hi number 4 from the main thread!




@Runtime Performance and Compilation Speed

Comparable to C++,Slightly overhead due to Safety checks and have more complex compilation checks.

@Community-Support

Rust is a language of fast growing community. Developers help each other to solve problem and make community richer day by day.
Visit the forum - 
https://users.rust-lang.org/





