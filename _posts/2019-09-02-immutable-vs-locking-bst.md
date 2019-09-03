---
layout: post
title: Immutable vs Locking BST
subtitle: Excerpt from Soulshaping by Jeff Brown
tags: [concurrency, functional programming, data structures]
---

* Core tenets of immutable data structures
    * Simple idea - single thread scope data structure
        * Structural sharing - Every modification is a new tree
        * But not exactly a new tree - only the path leading to modification is new

    * How to make it shareable across threads?
        * Use mutation :troll_face:
        * But not exactly - we use refs, atoms, stm etc and use the pointer to the root of the tree
        * Every thread has lock-free access to the DS. The only contention happens when they want to modify the global state
        * This contention happens at the root node where the pointer is stored.
        * So technically speaking, immutable, lock-free data structure is has mutation and locking! :more_troll_face:

* Core tenets of thread-safe locking data structures

* Core tenets of core.async

* Experiment setup, benchmarking mechanism and data used

* Results (include graphs)
    * Memory profile
    * Garbage collection stats
    * Average thread wait time
    * Collision ratio

* Conclusions

* Future work
    * Include lock free data structures in the comparison (link to the paper)
