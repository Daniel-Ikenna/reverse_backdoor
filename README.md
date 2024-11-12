## Reverse Backdoor

A reverse backdoor setup using Python, consisting of two scripts: a listener (`Listener.py`) that waits for incoming connections and a backdoor client (`reverse_backdoor.py`) that initiates a connection to the listener. This setup allows remote command execution on the compromised system.

### Script 1: Listener.py

#### Overview
`Listener.py` is designed to wait for incoming connections and execute commands remotely on the compromised system.

#### Key Features
- **Reliable Command Execution**: Remotely send and execute commands, such as file upload/download, directory changes, and shell commands.
- **Download/Upload File Handling**: Provides an option to upload files to or download files from the remote system.

#### Usage
1. **Configure the Listener IP and Port**: Update the IP address and port in the script where `my_listener = Listener("192.168.**.**", 4444)`.
2. **Run the Listener**:
   ```bash
   python Listener.py
   ```

### Script 2: reverse_backdoor.py

#### Overview
`reverse_backdoor.py` establishes a connection to `Listener.py` and allows for remote command execution.

#### Key Features
- **Persistence**: Automatically adds itself to the system startup on Windows for persistence.
- **Remote Command Execution**: Execute system commands, upload/download files, and change directories on the target machine.

#### Usage
1. **Configure the Listener IP and Port**: Update the IP address and port in the script where `my_backdoor = Backdoor("192.168.**.**", 4444)`.
2. **Run the Backdoor**:
   ```bash
   python reverse_backdoor.py
   ```

### Requirements
- **Python 3.x**
- **Permissions**: Run with administrator privileges for persistence and file access.

---

### Important Note

This project is for **educational purposes only**. Unauthorized use on any system without explicit consent is prohibited.

### Authors
- [Zaid Sabih](https://ie.linkedin.com/in/zaid-sabih-al-quraishi-5444a6127)
- [Uzoeshi Daniel](https://www.linkedin.com/in/daniel-ikenna-33b709235)
