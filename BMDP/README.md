# Black Magic Debug Probe

When connected via USB, the Black Magic probe will enumerate as a CDC-ACM device which the OS should present as a serial port. The first interface provides the GDB server, and the second provides a USB to UART adapter.

### Minimal Flash programming Session

Command | Function
--- | --- | ---
`arm-none-eabi-gdb <filename>` | start gdb with optional binary file
`target extended-remote \\.\COM15` | connect to debug interface using second COM port (LED brightens)
`monitor version` | show firmware version info
`monitor swdp_scan` | detach connected targets and show targets available on the SWD interface
`attach <n>` | attach to target and pause ecexution
`load <filename>` | upload optionally specified file
`compare-sections` | compare memory sections to binary file to verify flash programming
`continue` | continue execution until CTRL + C interrupt
`detach` | detach from target
`kill` | detach from target and reset
`quit` | exit gdb


### Minimal Debug Session

Command | Function
--- | --- | ---
`arm-none-eabi-gdb <filename>` | start gdb with optional binary file
`target extended-remote \\.\COM15` | connect to debug interface using second COM port (LED brightens)
`monitor version` | show firmware version info
`monitor swdp_scan` | detach connected targets and show targets available on the SWD interface
`attach <n>` | attach to target and pause ecexution
`load <filename>` | upload optionally specified file
`compare-sections` | compare memory sections to binary file to verify flash programming
`continue` | continue execution until CTRL + C interrupt
`detach` | detach from target
`kill` | detach from target and reset
`quit` | exit gdb


Commands can be abbreviated to as few letters as are unambiguous. 
