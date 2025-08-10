🌐 Java Networking Servers (SingleThread / MultiThread / ThreadPool)

A compact and educational Java project demonstrating three classic server designs — SingleThread, MultiThread, and ThreadPool — to showcase how concurrency models affect performance, scalability, and resource usage in network programming.

⸻

✨ Key Features
	•	SingleThread Server – Handles one client at a time
	•	MultiThread Server – Spawns a new thread per connection
	•	ThreadPool Server – Uses a fixed ExecutorService for controlled concurrency
	•	TCP-based communication with Java Sockets
	•	Client programs for quick load testing
	•	Easily configurable port, pool size, and concurrency level

⸻

🛠 Tech Stack

Language: Java 8+
Networking: Java Sockets (java.net)
Concurrency: Threads, ExecutorService
Build Tool: javac (command-line)
Platform: CLI

⸻

🧱 Project Structure

.
├── SingleThread/
│   ├── Server.java     – Single-threaded server
│   └── Client.java     – Single connection test client
├── MultiThread/
│   ├── Server.java     – Thread-per-connection server
│   └── Client.java     – Spawns 100 concurrent client threads
└── ThreadPool/
└── Server.java     – Fixed thread pool server

⸻

⚙️ How It Works

SingleThread Server:
	•	Listens on a port and processes one client request at a time.
	•	Other clients must wait until the current request finishes.

MultiThread Server:
	•	Creates a new thread for every accepted connection.
	•	Handles multiple clients in parallel.
	•	Risk of resource exhaustion at high concurrency.

ThreadPool Server:
	•	Uses a fixed-size thread pool (ExecutorService) to limit concurrent threads.
	•	Incoming requests beyond the pool size are queued until a thread becomes available.

⸻

🚀 Getting Started

Step 1: Compile the Project
javac SingleThread/.java MultiThread/.java ThreadPool/*.java

Step 2: Run the Server (Choose One)
SingleThread: java -cp . SingleThread.Server
MultiThread: java -cp . MultiThread.Server
ThreadPool: java -cp . ThreadPool.Server

Step 3: Run the Client
For SingleThread server: java -cp . SingleThread.Client
For MultiThread or ThreadPool servers (load testing): java -cp . MultiThread.Client

⸻

📊 Comparison Overview

SingleThread:
	•	Model: Serial (one at a time)
	•	Pros: Simple, minimal overhead
	•	Cons: Very low throughput

MultiThread:
	•	Model: Thread per connection
	•	Pros: High concurrency, simple logic
	•	Cons: Thread explosion risk

ThreadPool:
	•	Model: Fixed-size thread pool
	•	Pros: Stable resource usage, scalable
	•	Cons: Queuing delays under heavy load

⸻

🔬 Load Testing Example

Linux/macOS:
for i in $(seq 1 50); do java -cp . MultiThread.Client & done; wait

Windows PowerShell:
1..50 | ForEach-Object { Start-Process -NoNewWindow -FilePath “java” -ArgumentList “-cp . MultiThread.Client” }

⸻

🛠 Troubleshooting

BindException: Address already in use – Change port or stop the running server.
Connection refused – Start the server before running the client.
ClassNotFoundException – Run from the project root and include -cp .

⸻

📄 License

MIT (or your preferred license)

⸻

👤 Author

Akshaya Pratap Singh
Email: akshayasingh61@gmail.com
LinkedIn: https://www.linkedin.com/in/akshaya-singh-b65864229
GitHub: https://github.com/akshaya-cp
