
# 1:4 DEMUX using 1:2 DEMUXes

## Introduction

Welcome to the project on building a **1:4 Demultiplexer (DEMUX) from 1:2 Demultiplexers**! 
This project illustrates a fundamental principle in digital logic design: how to construct a larger, more complex circuit by combining smaller, simpler building blocks. 
Building a 1:4 DEMUX using 1:2 DEMUXes is not only a great academic exercise but also demonstrates the modularity and efficiency in integrated circuit design.

## What is a Demultiplexer (DEMUX)?

A Demultiplexer (DEMUX) is a combinational logic circuit that takes a single data input and routes it to one of many outputs, depending on the select bits. 
Essentially, it acts like a "data distributor," allowing you to direct information from one source to a specific destination among several available.

* **1:2 DEMUX:** Has one data input, one select bit, and two outputs. The input data is routed to one of the two outputs based on the state of the select bit.
* **1:4 DEMUX:** Has one data input, two select bits, and four outputs. The input data is routed to one of the four outputs based on the combination of the two select bits.

## Why Build a 1:4 DEMUX from 1:2 DEMUXes?

Constructing a 1:4 DEMUX from 1:2 DEMUXes showcases a vital concept in digital engineering: **hierarchical design**. It allows us to:

* **Simplify Complexity:** Instead of designing a large 1:4 circuit from scratch, we can break down the problem into smaller, more manageable parts.
* **Module Reusability:** 1:2 DEMUXes can be treated as reusable modules, making the design process faster and less prone to errors.
* **Deeper Understanding:** This provides insight into how more complex circuits are built from basic components, which is essential for understanding larger digital systems.

This project will demonstrate how individual 1:2 DEMUX components are logically interconnected to achieve the functionality of a full 1:4 DEMUX, providing a practical example of creating efficient and scalable circuits.
