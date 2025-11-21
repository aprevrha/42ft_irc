# ft_irc

A small, standards-oriented IRC server written in C++98. Created for learning and as part of the 42 Vienna curriculum.

## Features

- User registration (PASS / NICK / USER)
- Basic channel support: JOIN, PART, TOPIC, MODE
- Private and channel messaging: PRIVMSG
- Invite and kick: INVITE, KICK
- Ping/pong handling
- Graceful QUIT handling

## Requirements

- GNU Make
- A C++98-compatible compiler (tested with g++ / clang++)

## Build

Build the server using the included Makefile:

```sh
make
```

This produces the `ircserv` binary in the repository root.

Clean build artifacts with:

```sh
make clean
make fclean  # removes the binary too
```

## Run

Start the server with a port and password. Example:

```sh
# run on port 6667 (default IRC port)
./ircserv 6667 my_server_password
```

## Connect with a client

Connect with a full IRC client (e.g. irssi) or use netcat for quick testing:

```sh
# using netcat
nc -C localhost 6667

# using irssi
irssi -c localhost -p 6667 -w my_server_password
```

Example registration sequence (manual via netcat):

```
PASS my_server_password
NICK mynick
USER myusername 0 * myrealname
```
