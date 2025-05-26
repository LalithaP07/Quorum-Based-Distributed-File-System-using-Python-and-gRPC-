# Quorum-Based-Distributed-File-System-using-Python-and-gRPC-

A distributed file system built with Python and gRPC, implementing the Quorum Protocol to ensure data consistency, fault tolerance, and high performance. The system enables efficient file storage and retrieval across multiple distributed nodes while balancing the CAP theorem constraints.

🔧 Features
📁 Distributed file storage and retrieval
🔒 Quorum-based read and write operations
⚙️ Fault tolerance and high availability
🚀 Scalable architecture using gRPC for fast node-to-node communication
🔄 Ensures data integrity in a partitioned environment
📡 Asynchronous request handling for efficient performance

🧠 How It Works
The system follows the Quorum Protocol:
Read Quorum (R) and Write Quorum (W) satisfy the condition:
R + W > N (where N is the total number of nodes)
A write is successful only if it reaches W nodes
A read is successful if it fetches data from R nodes
Ensures eventual consistency even under node failure

🛠️ Tech Stack
Python – Core implementation
gRPC – Remote communication between distributed nodes
Protocol Buffers (protobuf) – Define service contracts
Multithreading / Async I/O – To handle concurrent requests

📦 Installation & Usage
1. Clone the Repository
bash
git clone https://github.com/yourusername/Quorum-Based-Distributed-File-System-using-Python-and-gRPC.git
cd Quorum-Based-Distributed-File-System-using-Python-and-gRPC
2. Install Dependencies
bash
pip install -r requirements.txt
3. Compile Protobufs
bash
python -m grpc_tools.protoc -I. --python_out=. --grpc_python_out=. file_service.proto
4. Run Nodes
Start multiple server instances to simulate distributed nodes:
bash
python server.py --port=5001
python server.py --port=5002
python server.py --port=5003
5. Run Client
bash
python client.py
Use the client to perform read/write operations.

📁 Project Structure
pgsql
├── client.py
├── server.py
├── quorum.py
├── file_service.proto
├── file_service_pb2.py
├── file_service_pb2_grpc.py
├── README.md
└── requirements.txt
🧪 Testing Scenarios
Simulate node failures and observe quorum logic
Test various quorum combinations (e.g., W=2, R=2 for N=3)
Perform concurrent reads/writes and verify consistency
