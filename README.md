# cmd-parser

**cmd-parser** is a C library that provides a Linux-like command-line interface (CLI) for custom C applications. It allows developers to easily integrate an interactive CLI into their applications, enabling users to execute commands and interact with the backend logic.

## Features

- **Custom Command Registration:** Developers can register their own commands and associated callbacks.
- **Command Validation:** The library authenticates command formats and values before triggering callbacks.
- **Built-in Commands:** Supports common commands such as `show`, `debug`, `clear`, and `config`.
- **Command Negation:** Supports negation for `config` commands.
- **Contextual Help:** Pressing `?` displays a list of valid next sub-options and help strings.
- **Single Process Support:** The CLI currently supports one process at a time, communicating with the backend via callbacks.
- **Extensible:** Future versions will support IPC between the CLI and backend processes.

## Getting Started

### Prerequisites

- GCC or any standard C compiler
- Make

### Building the Library

1. Run `make` to compile the library and example application.

### Running the Example Application

1. Execute the test application:
   ```sh
   ./exe
   ```

2. Interact with the CLI using the registered commands.

## Usage
- Include the following headers in your application:

```bash
#include "libcli.h"
#include "cmdtlv.h"
```
- Link your application with the libcli.a library:

```bash
gcc your_app.c -lcli -o your_app
```

See the provided Makefile for more details.)

Refer to `testapp.c` for a usage example.

## Notes
- The CLI library is designed to emulate the interactive shell found on routing devices.
- Only one CLI process is supported at a time in the current version.


## TODO
- Add validation checks for supported data types.
- Extend support for inter-process communication (IPC) between the CLI and backend.

<!-- For more detailed documentation, see the LinuxLikeCommandLineInterface.docx file included with the source code. -->


## Compilation

Copy the main*.c files up one directory level.

```bash
# Compile main*.c files
gcc -g -c main1.c -o main1.o

# Linking with libcli to create executable
gcc -g main1.o -o main1.exe -L ./cmd-parser/ -lcli
```

The first command compiles the `main1.c`to create object file `main1.o`. `–I` option tells compiler where to find header files included in `main1.c`.  
The second command links our project with libcli library and create final executable – `main1.exe`. You can run this executable and play around the same default commands implemented. Also, use show help to get yourself familiar with the CLI. Try out `“?”, “.”, “/”` features. 

See the figure below.
<!-- ![main1](static/image.png) -->