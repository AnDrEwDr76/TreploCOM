# TreploCOM
This is an amateur training progrect. Even worse.
The program requires jssc serial port library.
https://github.com/scream3r/java-simple-serial-connector

The program connects to the COM port and shows bytes coming to it (as text).
You can send a line of text to this port or one byte in the range -128 - +127, composed by switching eight checkboxes.
The program was tested using two programs:
1. COM port emulator: Virtual Serial Port Driver 9.0 (Eltima Sofware) - trial version with full functionality for 14 days;
2. Traffic generator and logger: COM Port Data Emulator & Traffic generator (AGG Software) is a free program. He, he.
The jssc 2.8.0 library is used to work with the COM port. For window display uses awt.

The main method gives the command to create an instance of the ComPortLogger06 class and a command to display it.
ComPortLogger06 registers a bunch of static variables and runs its constructor.
Constructor describes data models for dropdowns and calls the visualizationGUI method.
This method arranges buttons and hangs listener ActionWorker on them.
ActionWorker reacts on events: changes the connection settings, connects to the specified port,
disconnects, sends to the port, sends messages in the status bar at the bottom.
The listener class PortListener works separately (jssc.SerialPortEventListener). This is a static class.
He directs information from the port to the working window (portSay).

In future versions: log file .csv, byte receive, cascade opening of several windows, the ability to change the range bytes
(either -128 + 127, or 0-255), config file, accounting for encodings or display in different encodings, display in binary, ...

IDE Eclipse Version: 2020-03 (4.15.0)
