# Python RMI Lab using Pyro5

## Project Description

This project translates the core architecture of Java Remote Method Invocation (RMI) into a Python-based distributed system using Pyro5.

The system provides remote access to four product objects: Laptop, Mobile, Power Charger, and MotorBike.

## Project Structure

```text
PYTHON_RMI_LAB/
├── product.py
├── server.py
├── client.py
└── README.md
```

## Requirements

- Python 3
- Pyro5

## Installation

Install Pyro5 using:

```bash
python -m pip install Pyro5
```

## How to Run

Open three separate terminals in the project directory.

**Terminal 1: Start the Pyro5 Name Server**

```bash
python -m Pyro5.nameserver -n 127.0.0.1 -p 9090
```

**Terminal 2: Start the Product Server**

```bash
python server.py
```

**Terminal 3: Run the Client**

```bash
python client.py
```

## Expected Output

```text
The product name is: Laptop , The price is: 1740.0
The product name is: Mobile , The price is: 241.0
The product name is: Power Charger , The price is: 841.0
The product name is: MotorBike , The price is: 44.0
```

## Java RMI to Pyro5 Mapping

| Java RMI | Python Pyro5 |
|---|---|
| Remote interface | Product class |
| Product implementation | Product class methods |
| RMI Registry | Pyro5 Name Server |
| UnicastRemoteObject.exportObject() | daemon.register() |
| registry.rebind() | ns.register() |
| registry.lookup() | ns.lookup() |
| Remote method call | Proxy method call |

## Author
John Paul M. Toyco