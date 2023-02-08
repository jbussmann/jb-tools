# Black Magic Debug Probe

When connected via USB, the Black Magic probe will enumerate as a CDC-ACM device which the OS should present as a serial port. The first interface provides the GDB server, and the second provides a USB to UART adapter.

### Minimal flash programming session

Command | Function
--- | ---
`arm-none-eabi-gdb <filename>` | start gdb with optional binary file
`target extended-remote \\.\COMxx` | connect to debug interface using second COM port (LED brightens)
`monitor version` | show firmware version info
`monitor swdp_scan` | detach connected targets and show targets available on the SWD interface
`attach <n>` | attach to target and pause ecexution
`load <filename>` | upload optionally specified file
`compare-sections` | compare memory sections to binary file to verify flash programming
`detach` | detach from target
`quit` | exit gdb

One liner for Windows: `arm-none-eabi-gdb -batch -nx -ex "target extended-remote \\.\COMxx" -ex "monitor swdp_scan" -ex "attach <n>" -ex "load" -ex "compare-section" <filename>`

### Programm execution

Command | Function
--- | ---
`set confirm off` | disable confirmation requests
`run` | restart execution and run uninterrupted
`start` | restart execution and break at main
`continue` | continue execution until CTRL + C interrupt or breakpoint


### Breakpoints

Command | Function
--- | ---
`break <function>` | set funktion breakpoint
`tbreak <function>` | set single use funktion breakpoint
`hbreak <function>` | set hardware funktion breakpoint
`watch <var>` | set variable breakpoint
`info break` | print table of break- and watchpoints
`disable <n>` | disable specific breakpoint
`enable <n>` | enable specific breakpoint
`delete <n>` | delete specific or all breakpoint(s) 

Commands can be abbreviated to as few letters as are unambiguous. 
