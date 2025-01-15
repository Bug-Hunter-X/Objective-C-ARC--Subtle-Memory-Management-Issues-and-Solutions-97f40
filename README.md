# Objective-C ARC: Subtle Memory Management Issues

This repository demonstrates a common, yet often subtle, bug in Objective-C related to Automatic Reference Counting (ARC) and strong property references.  The code illustrates how improper use of strong properties can lead to memory leaks through retain cycles or unexpected object releases.

## Bug Description:
The `bug.m` file contains an example of a `MyClass` with a strong reference to an `NSString`. This showcases how strong properties can lead to:

1. **Retain Cycles:** If the referenced object has a strong reference back to `MyClass`, a cycle is created preventing deallocation.
2. **Dangling Pointers:** If the referenced object is released elsewhere, `MyClass` will hold a dangling pointer.

The solution in `bugSolution.m` addresses these issues using weak references where appropriate, demonstrating best practices for memory management in Objective-C with ARC.

## How to run:
Clone the repository.  You'll need Xcode to compile and run the code. This code is self-contained, no other dependencies are necessary.