+++
title = "CS 50 Week 0 - Scratch"
date = "2021-07-08T20:52:53-07:00"
author = "Lux"
cover = "/images/cs50_week0_cover.jpg"
tags = ["cs50", "scratch", "binary", "algorithms", "ascii"]
keywords = ["", ""]
description = "Notes to recap Week 0 of CS50"
showFullContent = false
+++

# ✌️ binary

- Binary is a base-2 system, unlike the decimal, base-10 system standard in much of the world.
    - Where a base-10 number such as 146 has a 6 in the 1s place (or $10^0$ place), a 4 in the 10s place (or $10^1$ place), and a 1 in the 100s place (or $10^2$ place), a base-2 number such as 001 has a 1 in the 1s place (or $2^0$ place), a 0 in the 2s place (or $2^1$ place) and a 0 in the 4s place (or $2^2$ place).
    - Put more visually:

        ![Visual representation of binary](/images/cs50_week0_binary.png)

- Effectively, binary is the "language of computers."

    > Because computers are machines, they cannot literally think in terms of 0s and 1s. Instead, this is a convention we use to describe the on & off states of the transistors that make up the computer's circuitry.

- Because the world is made of more than 0s and 1s, humans have agreed on conventions like [ascii](#-vocabulary) and [unicode](#-vocabulary) to represent other letters and characters.
    - Similarly, we have created systems that map binary numbers to colors, sounds, and more, to allow for the wide spectrum of information we can view on a computer.

    > Computers are context-sensitive! The file extension lets the computer know it should use a certain set of decoding instructions to correctly represent the information in any particular file.

## 🤔 test yourself

- Using the following [ascii chart](https://asciichart.com), see if you can decode the binary number to reveal a message.

    ![https://asciichart.com](/images/ascii.png)

- **message in binary**
    - 01000100 01100101 01110110 01010011 01110001 01110101 01100001 01100100
- Look for the [answer](#binary-message-answer) at the bottom of the page!

# 🧮 algorithms

- At its most basic, an **algorithm** is a set of instructions meant to accomplish a task.
    - In the world of computers, algorithms have to be exact and explicit; computers do not infer or read between the lines. What you say is what you get!
- The success of an algorithm is not solely dependent on its correctness; equally important is its efficiency!
- Consider the phonebook example:

    ![Graph of phonebook solutions](/images/cs50_week0_graph.png)

    - When trying to flip through the a phonebook to find a specific name, flipping one page at a time could be represented by the $n$ line. The size of the problem directly corresponds to the time it takes to solve the problem.
    - When flipping through two pages at a time, the solution is represented by the $n/2$ line. Now, the time it takes to solve the problem is divided in half.
    - When flipping through half the phonebook at a time, the solution is represented by the $log_{2}5$ line. While the time to solve the problem still goes up with the size of the problem, as the problem gets larger and larger, the time goes up less and less. This is the most efficient method.

# 🎨 abstraction

- **Abstraction** is the process of deliberately simplifying systems by "abstracting away" the more complex aspects of the system to deal with.
- An example of abstraction is defining a function that performs a series of commonly used steps in a program. By defining this function in one place with a descriptive name, you can simply call the function into use in any part of your code without having to worry again about the minute implementation details.
- Abstraction is key to creating more complex projects; you must start **small** and iterate.

# 🗝 vocabulary

- **bits**
    - derived from "binary digits"
    - each digit in a binary number is one bit
- **bytes**
    - 8 bits = 1 byte
- **ascii**
    - an agreement between humans to represent specific letters and characters with specific binary numbers
    - each character is comprised of 1 byte, or 8 bits
        - thus ascii is limited to 256 possibilities as there are only 256 unique ways to arrange 8 bits
- **unicode**
    - newer system of mapping binary numbers to characters that aims to represent all of humanity's written languages and symbols
    - uses up to 32 bits per character to allow for a much wider range of possibilities

# binary message answer
- **message in decimal**
    - 68 101 118 83 113 117 97 100
- **message in english** (only look once you are done decoding!)
    - DevSquad