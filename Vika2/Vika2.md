# Chapter 2: Operating System Structures

This chapter delves into system components, including user interfaces, command-line interfaces (CLIs), peripherals, and more.

## 2.2 User Interfaces of Operating Systems

Everything within a computer that a user can interact with, including processes, CLIs, search bars, and desktops, is considered a user interface. A user interface is a system that allows the user to execute commands within the operating system.

### Types of User Interfaces
1. **Graphical User Interface (GUI):**
   - User-friendly graphical interface based on a desktop metaphor.
   - Utilizes icons, windows, and menus, often navigated with a mouse or touch gestures.
   - Examples: Microsoft Windows, macOS Aqua GUI, Linux with Gnome or KDE.

2. **Batch Interface:**
   - Executes pre-defined scripts or commands line by line.
   - No user interaction after processing starts.

3. **Command-Line Interface (CLI):**
   - Allows direct command entry via the keyboard.
   - Outputs simple text responses on a terminal.
   - Commands may be built into the shell or external programs executed in new processes.

All these interfaces execute system calls to communicate with the operating system’s middleware. These services include program execution, I/O operations, file systems, resource allocation, error detection, and more.

## 2.3 System Calls

System calls provide a programmatic interface for services provided by the OS, typically implemented as software interrupts (traps) callable via assembly-language instructions. 

### Common APIs
- **Windows API:** Libraries available for major Microsoft programming languages.
- **POSIX API:** For UNIX-like systems, including Mac OS X and Linux. 
- **Standard C Library:** Provides OS-independent APIs for common services.
- **Java API:** Offers an OS-independent interface for the Java Virtual Machine.

### How System Calls Work
1. **Number Association:**
   - Each system call is associated with a unique number, identifying its routine in the OS kernel.

2. **API Invocation:**
   - APIs invoke system calls in the OS kernel, passing the number and parameters using a trap instruction.

3. **Parameter Passing Methods:**
   - **CPU Registers:** Parameters passed in registers (limited by their number).
   - **Block/Table:** Parameters stored in memory and a pointer is passed.
   - **Stack:** Parameters pushed onto the stack, with no limit on number or length.

### API vs. ABI
- **API (Application Programming Interface):** Used by high-level programming languages.
- **ABI (Application Binary Interface):** Defines the interface at the machine code level.

## 2.4 Types of System Calls

Six major categories:
1. **Process Control:** Manage processes (e.g., create, terminate, wait, signal).
2. **File Management:** Handle files (e.g., read, write, open, close).
3. **Device Management:** Access and manage devices.
4. **Information Maintenance:** Retrieve and modify system data.
5. **Communications:** Enable inter-process communication.
6. **Protection:** Ensure secure access to system resources.

## 2.5 System Programs/System Services

System programs provide a convenient environment for development and execution, often serving as user interfaces to system calls.

### Categories:
- **File Management:** Create, delete, copy, and manipulate files.
- **Status Information:** Retrieve system info (e.g., memory usage, date/time).
- **File Modification:** Text editors, search tools, and text transformation utilities.
- **Programming Support:** Compilers, assemblers, and debuggers.
- **Program Execution:** Loaders and shells.
- **Communications:** Tools for messaging and remote file access.
- **Application Programs:** Specific tools like word processors or games.
- **Background Programs (Daemons):** E.g., print spoolers, logging, and cron jobs.

## 2.6 Operating System Design and Implementation

Operating systems are implemented based on specific goals and mechanisms:

### Design Goals
- **User Goals:** Convenience, reliability, safety, and speed.
- **System Goals:** Simplicity, flexibility, reliability, and efficiency.

### Policy vs. Mechanism
- Policies dictate what will be done, while mechanisms implement how it is done.
- Example: CPU scheduling policy (e.g., multitasking) vs. the scheduler mechanism.

### Implementation Languages
- **Higher-Level Languages:** E.g., C for portability.
- **Assembly:** For critical tasks like context switching.

### Structures
- **Monolithic Systems:** Simple, with no strict separation between layers.
- **Layered Systems:** Hierarchical but slower due to inter-layer communication.
- **Microkernel Systems:** Minimal kernel, with additional functionality in user space.
- **Module-Based Systems:** Kernel with dynamically loadable modules.
