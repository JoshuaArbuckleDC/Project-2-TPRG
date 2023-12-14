# Project-2-TPRG

This code consists of two Python scripts, one for a client and one for a server, which communicate with each other over a network connection. Here's a brief overview of what each script does:

Client Script (client.py):

The client script gathers system information like core temperature, voltage, ARM clock frequency, disk usage, and GPU temperature using various shell commands.
It creates a GUI window using the tkinter library to display the connection status.
It creates a socket and attempts to connect to a server at a specified IP address (host) and port.
If the server is running and accepts the connection, it updates the GUI to indicate a successful connection.
The client then enters a loop where it collects system information, creates a data packet containing this information, and sends it to the server in JSON format.
This process is repeated 50 times with a 2-second delay between each data transmission.
After completing the data transmission, the client closes the socket and destroys the GUI window.
Server Script (server.py):

The server script also uses tkinter to create a GUI window that displays the connection status, a simulated LED indicator, and information received from the client.
It creates a socket, binds it to a specific IP address (host) and port, and starts listening for incoming connections.
The GUI initially displays a message indicating that it is waiting for a connection.
When a client connects, the server updates the GUI to show the connection is established.
It starts a separate thread to continuously receive data from the client, parse the received JSON data, and update the GUI with the system information.
The server periodically toggles the color of a simulated LED in the GUI to indicate data reception.
If any error occurs during data reception or if the client disconnects, the GUI updates to show a disconnection message.
