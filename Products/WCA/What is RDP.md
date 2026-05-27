RDP stands for remote desktop protocol. It lets you see and control another computer's desktop over a network connection.

When you launch an app, your local machine connects via RDP to a terminal server- a windows server with cargowise installed on it and RDS enabled. It allows multiple users to connect to it simultaneously and run their own session (when a user connects to a terminal server, it uses their login details that they provided to accessor client).

> On naming: Your PC is the dumb terminal, the server accepts terminal connections. It is the server that terminal clients connect to. Like how a web server serves web pages to browsers, a terminal server serves desktop sessions to terminal clients. The thing doing the serving gets the name.

The user gets to see a live stream of the screen and sends your key and mouse inputs over to the machine.