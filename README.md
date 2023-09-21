# Minitalk - 42 Project

![Minitalk](https://img.shields.io/badge/Minitalk-42-success)

The **Minitalk** project is part of the curriculum at [42 Adelaide](https://www.42adel.org.au/). It involves creating a simple client-server communication system using signals in C.

## Project Objectives

The Minitalk project aims to introduce students to interprocess communication (IPC) and signal handling in a Unix-based environment. It provides an opportunity to practice the following skills:

- Working with signals in C
- Implementing a basic client-server architecture
- Handling message transmission between processes

## How to use

To use the **Minitalk** program, follow these steps:

1. Clone the repository to your local machine:

   ```bash
   git clone https://github.com/fionashane/minitalk.git
   ```

2. Compile the server and client programs using the provided Makefile:

   ```bash
   make
   ```

3. Start the server by running:

   ```bash
   ./server
   ```

   The server will display its process ID (PID).

4. Start the client, specifying the server's PID as an argument:

   ```bash
   ./client SERVER_PID "Your message to send"
   ```

   Replace `SERVER_PID` with the actual server's process ID and `"Your message to send"` with the message you want to transmit.

5. The server will receive the message and display it. You can continue sending messages using the client as needed.

## Program Details

- **Server**: The server program initializes a signal handler to receive messages from clients. When a message is received, it reconstructs and displays the original message.

- **Client**: The client program sends messages to the server by sending individual bits via signals. It converts characters into binary and sends each bit as a signal to the server.

## Example

Here's a simple example of how to use the Minitalk program:

1. Start the server:

   ```bash
   ./server
   ```

   Note the server's process ID (e.g., 12345).

2. Send a message from the client:

   ```bash
   ./client 12345 "Hello, Minitalk!"
   ```

   The server will receive the message and display it:

   ```
   Received message: Hello, Minitalk!
   ```

3. You can send additional messages by repeating step 2.
