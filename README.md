# Python-Socket-Chat-Application
A Client-Server Chat Application built using Python Socket Programming, Multithreading, and Tkinter GUI. The project demonstrates how a client and server communicate over a TCP connection. The client provides a graphical chat interface, while the server handles incoming client connections and sends received messages back to the connected client. 

📌 Project Overview

This project consists of two Python programs:

server.py – Starts a TCP server and listens for client connections.
client.py – Provides a Tkinter-based graphical chat interface and connects to the server.

The application uses:

TCP Sockets for communication
Multithreading to handle communication without freezing the GUI
Tkinter for the client-side graphical interface
How it works
              TCP Connection
       ┌─────────────────────────┐
       │                         │
       ▼                         │
┌──────────────┐          ┌──────────────┐
│   Client     │          │    Server    │
│  client.py   │◄────────►│  server.py   │
│              │   TCP    │              │
│ Tkinter GUI  │          │ Socket       │
└──────────────┘          │ Multithread  │
                          └──────────────┘

When the client sends a message:

Client → Server → Client

The server receives the message and sends it back to the client.

✨ Features
TCP socket-based communication
Client-server architecture
Graphical user interface using Tkinter
Send and receive messages
Multithreaded client message receiving
Server handles client connections using threads
Simple and beginner-friendly implementation
Runs completely on localhost
No external database required
🛠️ Technologies Used
Technology	Purpose
Python	Main programming language
Socket	Network communication
TCP/IP	Communication protocol
Threading	Handling communication concurrently
Tkinter	Graphical user interface
Git/GitHub	Version control and project hosting
📂 Project Structure
Python-Socket-Chat/
│
├── server.py
├── client.py
├── README.md
└── screenshots/
    └── chat-interface.png
⚙️ Requirements

Make sure Python is installed on your system.

Check Python installation
python --version

or:

python3 --version

Tkinter is normally included with Python.

Windows

For most Python installations, Tkinter is already available.

You can test it using:

python -m tkinter

If a Tkinter window appears, it is installed correctly.

🚀 Installation
1. Clone the repository
git clone https://github.com/YOUR-USERNAME/Python-Socket-Chat.git
2. Open the project directory
cd Python-Socket-Chat
3. Run the server

Open a terminal and execute:

python server.py

You should see:

Server started on localhost:5001
🖥️ Running the Client

Keep the server running.

Open another terminal in the same project directory and run:

python client.py

A GUI window called Chat Client will open.

You can type a message and click Send.

Example:

You: Hello Server!
Server: Hello Server!
🔄 Execution Flow
Step 1 — Start Server
python server.py

The server:

Creates a TCP socket.
Binds to localhost:5001.
Starts listening for connections.
Accepts incoming clients.
Creates a separate thread for each connected client.
Step 2 — Start Client
python client.py

The client:

Creates a TCP socket.
Connects to the server.
Opens the Tkinter GUI.
Starts a background thread for receiving messages.
Step 3 — Send Message

When the user enters:

Hello

the client sends:

Hello

to the server.

The server receives it and sends it back to the client.

The client displays:

You: Hello
Server: Hello
🧵 Multithreading

Multithreading is used so that the application can perform multiple tasks without blocking the main program.

Server

Each connected client gets its own thread:

thread = threading.Thread(
    target=handle_client,
    args=(client_socket, address),
    daemon=True
)

thread.start()

This allows the server to handle multiple connections.

Client

The client also uses a separate thread to receive messages:

threading.Thread(
    target=listen_for_messages,
    daemon=True
).start()

This prevents the Tkinter interface from freezing while waiting for messages.

🌐 Network Configuration

The application currently uses:

HOST = "localhost"
PORT = 5001
Host

localhost means the server and client are running on the same computer.

Port

The application communicates through:

5001

If port 5001 is already being used, you can change it in both files.

For example:

PORT = 6000

Make sure the port number is the same in server.py and client.py.

📸 Application Interface

Add screenshots of your application inside the screenshots folder.

Example:

screenshots/
└── chat-interface.png

Then add the screenshot to this README:

## 📸 Screenshot

![Chat Application](screenshots/chat-interface.png)
📚 Concepts Demonstrated

This project demonstrates several important Python and Computer Networks concepts:

Python
Functions
Exception handling
Modules
Threads
GUI programming
Object interaction
Computer Networks
Client-server architecture
TCP communication
IP addresses
Port numbers
Socket programming
Connection handling
Operating Systems
Multithreading
Concurrent execution
Background processes
🔐 Limitations

This project is designed for learning purposes and has some limitations:

Communication currently uses localhost.
Messages are echoed back by the server.
No user authentication is implemented.
Messages are not encrypted.
No message history/database is maintained.
The current server does not broadcast messages between different clients.
No file/image sharing functionality is included.
🔮 Future Improvements

The project can be extended with:

👥 Multi-client group chat
🔐 User authentication
🔒 End-to-end encryption
💾 Chat history
🗄️ Database integration
📎 File sharing
🖼️ Image sharing
😀 Emoji support
🟢 Online/offline status
🔔 Message notifications
👤 Usernames
🗑️ Delete messages
🌐 LAN-based communication
☁️ Cloud deployment
🎯 Learning Objectives

The main objectives of this project are:

Understand TCP socket programming.
Learn the client-server communication model.
Implement network communication using Python.
Understand the use of IP addresses and ports.
Implement multithreading.
Build a basic desktop GUI using Tkinter.
Understand asynchronous message receiving.
Practice Git and GitHub project management.
🧪 Example
Server Terminal
Server started on localhost:5001
Client connected: ('127.0.0.1', 52341)
('127.0.0.1', 52341): Hello Server
Client GUI
You: Hello Server
Server: Hello Server
👨‍💻 Author

Nitin Chauhan

B.Tech CSE Student

📄 License

This project is created for educational and academic purposes.

You are free to modify and improve the project for learning purposes.
